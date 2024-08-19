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