                                                                                                                                                                # Secuenciador Básico

![[Pasted image 20240919115846.png|center|400]]

**Microinstrucciones:**
![[Pasted image 20240919120007.png|center|400]]
![[Pasted image 20240919120103.png|center|400]]

**Logica Interna con XNOR:**
![[Pasted image 20240919120350.png|center]]

**Logica Interna con XOR:**
![[Pasted image 20240919120425.png|center]]

## Ejemplo
![[Pasted image 20240919114845.png|center|300]]

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

![[Pasted image 20240919114917.png|center|400]]

___
# Secuenciador Básico de Microinstrucciones Alternativa

![[Pasted image 20240919115055.png|center]]

![[Pasted image 20240919115156.png|center|300]]

![[Pasted image 20240919115226.png|center|300]]

___
# Secuenciador Básico de 8 Microinstrucciones

![[Pasted image 20240919120657.png|center]]

- **Microinstrucciones:**

0 0 0 - Salto Contiguo
0 0 1 - Salto Condicional con cero
0 1 0 - Salto Condicional con uno
0 1 1 - Salto de Transformación (Registro de Transformación)
1 0 0 - Salto de Interrupción con cero (INT - Registro de Interrupcion)
1 0 1 - Salto de Interrupción con uno (INT - Registro de Interrupcion)
1 1 0 - Salto forzado (Liga)9
1 1 1 - Wait (Liga)

Dividimos en 2 el salto condicional y salto de interrupcion ya que no tenemos el XOR.

- **Logica Interna:**
![[Pasted image 20240919120828.png|center]]

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