
## Ejemplo

	Carta ASM

1. Asignacion binaria a los estados
Todos los estados deben cumplir n, n+1, p

Prueba:
x - 00
y - 01
INT - 10
Qaux - 11

Microintrucciones:
PC - 00
SC - 01
ST - 10
SI  - 11

2. Tamano de la memoria
Estados = 15
Entradas = 2 + 2
Salidas = 4
	n = 4 
	m = 2 (Prueba) + 1 (VF) + 2 (Microinstruccion) + 4 (Liga) + 4 (Salidas) = 13
	Tamano = $2^4*13$ bits

3. Contenido de la memoria
En paso contiguo (PC), las ligas se ponen en dont care, la logica interna obtiene el paso

en salto de interrupcion (SI) se ponen dont cares en ligas. Se obtiene el salto desde el registro de interrupciones. En VF si se pone el salto

___
# Secuenciador Basico de Microintrucciones Alternativa

	img arq

___
# Secuenciador Básico de 8 Microinstrucciones

Microinstrucciones:

0 0 0 - Salto Contiguo
0 0 1 - Salto Condicional con cero
0 1 0 - Salto Condicional con uno
0 1 1 - Salto de Transformación (Registro de Transformacion)
1 0 0 - Salto de Interrupción con cero (INT - Registro de Interrupcion)
1 0 1 - Salto de Interrupción con uno (INT - Registro de Interrupcion)
1 1 0 - Salto forzado (Liga)9
1 1 1 - Wait (Liga)

Dividimos en 2 el salto condicional y salto de interrupcion ya que no tenemos el XOR.

## Ejemplo Carta ASM

1. Asignacion binaria a estados (n ,n+1, p)
Asignacion binaria a entradas:

Prueba
x - 00
y - 01
INT - 01

Microinstrucciones:
...

2. Tamaño de la memoria\
Estados: 10
Entradas: 2 + 1
Salidas: 4

n = 4
m = 2+3+4+4 = 13
Tamaño: $2^4 * 13$

3. Contenido de la memoria (Microprogramacion)