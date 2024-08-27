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