Se utilizan estados en lugar de tiempo para diferenciar

- Se usaran ahora maquinas de estado

Un circuito secuencial tienen entradas, producen salidas, y usan memoria para definir sus estados 

___
# Ejemplo Metro

Entradas (sensores):
- E
	- 0 - No estacion
	- 1 - Llegamos a estacion
- T
	- 0 - No terminal
	- 1 - Terminal

Salidas (Control):
- M
	- 0 - No se mueve
	- 1 - Avanza
- D 
	- 0 - ABC
	- 1 - CBA

Estados

![[maquina de estados.jpeg|center]]

___
## Tabla de Verdad

![[tabla-de-verdad.jpeg|center]]
## Mapa de Karnaugh

La cantidad de mapas se define por la cantidad de columnas del lado derecho
- Edos Sig y Salidas
- Como hay 4 (Q1+, Q0+, D y M) se hacen 4 mapas de karnaugh
- Los mapas de D y M no se hacen porque su comportamiento es igual a Q1 y Q0 respectivamente (esto se puede ver en la tabla)

![[mapas-karnaugh 1.jpeg|center]]

___
## Logica Alambrada

Se tendran 2 flip flops, porque hay 4 estados
	4 = $2^{cantidad de flip flops} = 2^2$ 

img alambrado

- **Control**: Salidas
- **Memoria**: Flip-flops
- **Proceso**: Aun no se coloca en el diagrama de alambrado

Un circuito secuencial puede no servir porque no cumple la universalidad.
Es decir, si queremos agregar mas instrucciones, se debe realizar otro circuito secuencial, alambrado, etc.

___
# Cartas ASM
ASM: *Algorithmic State Machine*

Es la representación grafica de un sistema de hardware

**Estados**
- Se representan con un rectangulo
- Cada estado tiene su propia asignación binaria
![[Pasted image 20240820073208.png|center]]

**Entradas**
- Se tiene un conjunto de entradas
- Cada entrada es de 1 bit
- Solo aparecen para tomar decisiones
- Las decisiones se representan con un rombo
- Se puede tener decisiones en cascada
![[Pasted image 20240820073137.png|center|400]]

**Salidas**
- Se tiene un conjunto de salidas
- Cada salida es de 1 bit
- Solo se representan las salidas actuales

- Existen 2 tipos de salidas:
1. Salidas no condicionales
	- Se representan dentro de los estados
	- Se les conoce como dependientes de los estados
![[Pasted image 20240820074001.png|center|350]]

2. Salidas condicionales
	- Se representan dentro de un ovalo
	- Los ovalos solo aparecen despues de una decision
	- Como dependientes de las entradas
	- Las salidas condicionales pertenecen al estado inmediato anterior
![[Pasted image 20240820074030.png|center|350]]

![[Pasted image 20240820074100.png|center]]

