Se sustituyen los Circuitos Combinacionales por un Circuito Secuencial porque no se podían tomar decisiones

Ahora sustituimos el Circuito Secuencial por Memoria ROM, ya que la lógica alambrada de los C.S. no es escalable
- En la memoria ROM almacenamos cada estado
- La arquitectura con memoria ROM sera la parte del CONTROL

# Direccionamiento por Trayectoria

![[Pasted image 20240822073500.png|center|400]]

- Se guarda el Edo.Sig. y las salidas de cada estado de la carta ASM en una localidad de memoria
- La parte de memoria que indica el Edo.Sig. es la "Liga"
- La parte llamada "Salidas" es la que indica las salidas de los estados

>[!info] En Memoria Externa (clases sobre operaciones) guarda Cod. de Operación, Datos, Apuntadores, lo que conforman a un Programa Principal. En la memoria ROM, usada en los direccionamientos, se guardan Maquinas de Estados (cartas ASM), microoperaciones, lo que conforman a un Microprograma

El registro del diagrama se conforma de la siguiente manera:
`img telefono registro latch`

El tamano de la memoria ROM se determina de la sig. manera:

n = # Bits de Entradas + # Bits del Edo. Siguiente
m = # Bits del Edo. Siguiente + # Bits Salidas
	Bits del Edo. Siguiente = Bits del Edo. Presente

## Ejemplos:

- Estados = 9
- Entradas = 3
- Salidas = 4

n = 3 + 4 = 7
m = 4 + 4 = 8

Tamaño de la memoria:   $2^7 * 8 = 128 * 8 = 1024 [bits]$
___

- Estados = 32
- Entradas = 6
- Salidas = 8

n = 6 + 5 = 11
m = 5 +8 = 13

Tamaño de la memoria:   $2^{11} * 13 = 26,624 [bits]$
___

## Ejemplo Carta ASM

![[WhatsApp Image 2024-08-22 at 8.08.52 AM.jpeg|center|400]]

1. **Asignacion Binaria a los Estados**
Hay que nombrar a cada uno de los estados en binario

2. **Calcular el tamano de la memoria**
- Estados: 6
- Entradas: 5
- Salidas: 4

n = 5 + 3 = 8 (Del lado de Direccion)
m = 3 + 4 = 7 (Del lado de Contenido)
$\text{Tamaño} = 2^8 * 7 = 1,792[bits]$

3. Obtener el contenido de la memoria (Microprogramacion)

4. Grabar la memoria

## Caracteristicas

- Soporta todas las cartas ASM
- Soporta todas las salidas condicionales
- Soporta mas de una condicion por estado
- Desperdicia mucha memoria
- Hardware:
	- Memoria RAM
	- Registros

___
# Direccionamiento Entrada-Estado

![[Pasted image 20240827072901.png|center]]

>[!info] Solo soporta cartas ASM con una sola entrada por estado.

La memoria se divide en distintos bloques:
- PRUEBA: Contiene una representación binaria de la entrada a probar en cada estado
- LIGAS: Se escoge uno de los 2 estados siguientes (Falsa/Verdadera) de acuerdo a la entrada seleccionada por PRUEBA

Si el valor de la entrada por el SELECTOR DE ENTRADAS es 0 se elige la LIGA FALSA en el SELECTOR DE LIGA
Si el valor es 1 se elige la LIGA VERDADERA en el SELECTOR DE LIGA

![[Pasted image 20240827073400.png|center]]

**Calculo de Memoria:**
- n = Bits de los estados
- m = Bits de prueba + Bits Liga Falsa + Bits Liga Verdadera + Bits de salida
## Ejemplos
we
- Estados = 9
- Entradas = 3
- Salidas = 4
n = 4
m = 2 (bits de entrada) + 4 (bits de estados) + 4 (bits de estados) + 4 = 14\

Memoria = $2^4 * 14 = 224 [bits]$

>[!done] Se ahorra mucha memoria con este direccionamiento a comparación del de por trayectoria

- Estados = 32
- Entradas = 6
- Salidas = 8
n = 5
m = 3 + 5 + 5 + 8 = 21

Memoria = $2^5 * 21 = 672 [bits]$

## Ejemplo Carta ASM

1. Asignacion Binaria los estados y entradas
PRUEBA
C - 00
B - 01
A - 10

2. Calcular el tamano de la memoria
n = 3
m = 2 + 3 + 3 + 4 = 12

Memoria = $2^3 * 12$

3. Obtener el contenido de memoria (microprogramacion)

## Caracteristicas

- No soporta todas las cartas ASM
	- No se puede tener mas de una condicion por estado
	- No soporta salidas condicionales
- Ahorra mucha memoria
- Hardware:
	- Memoria ROM
	- 2 MUX (multiplexor)
	- Registro

# Direccionamiento Entrada-Estado 2.0

![[Pasted image 20240829071239.png|center|400]]

Esta arquitectura nos permite tener salidas condicionales

____
# Direccionamiento Implícito

![[Pasted image 20240905071904.png|center]]
![[Pasted image 20240905072028.png|center]]

Utiliza solo un campo de liga
Una variable de entrada y VF son las que deciden si se utiliza la direccion de liga 

El campo VF (Verdadero-Falso) sirve para indicarle a la lógica cuánto debe valer la variable de entrada, para así cargar en el contador el valor de la liga y hacer el salto.
![[Pasted image 20240905072228.png|center]]

![[Pasted image 20240905072321.png|center|400]]

## Tamaño memoria

n = Bits de estado
m = Bits de Prueba + VF + Bits de Liga + Salidas

- Estados 8,   Entradas =6,    Salidas = 7
<mark class="hltr-pink">Se debe suma 1 a Entradas por Qaux</mark>

n = 3
m = 3 + 1 + 3 + 7 = 14

- Estados = 9,   Entradas = 8,   Salidas = 5
n = 4
m = 4 + 1 + 4 + 5 = 14

## Ejemplo Carta ASM

1. Asignacion binaria a estados
Todos los estados deben cumplir la regla n, n+1, p

- Asignacion binaria a las entradas
PRUEBA
x: 000
y: 001
z: 010
T: 011
Qaux: 100

2. Tamano de la memoria
Estados = 8,   Entradas = 4 + 1,   Salidas: 4

n = 3
m = 3 + 1 + 3 + 4 = 11
Memoria = $2^3 * 11$ bits

3. Obtener contenido de la memoria (microprogramacion)
Encerrar los valores de entradas que generan un salto para facilitar la microprogramacion

## Caracteristicas:

- No soporta todas las cartas ASM
	- No soporta salidas condicionales
	- No soporta mas de una condicion por estado
- Ahorra mucha memoria
- Todos los estados deben cumplir con la regla n, n+1, p
- Elementos de HW:
	- Memoria ROM
	- Compuertas XOR y/o NOT
	- Multiplexor
	- Contador (Registros e Incrementador)

___
# 