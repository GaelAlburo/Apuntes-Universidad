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

# Ejemplo Carta ASM

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

