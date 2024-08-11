Links: [[3. Búsquedas Inteligentes y Resolución de Problemas]]
___

- Su objetivo es guiar el proceso de búsqueda
- Elimina cosas innecesarias del espacio de estados
- Usa informacion sobre la cercania de un estado al estado meta
- Primero explora caminos prometedores
- No es seguro encontrar la solucion (en busq. ciegas si)
- Encuentra una buena solucion en tiempo accesible

- Utiliza funciones de evaluacion
- A cada estado $e$ se le da un numero $h(e)$ (heuristica) que indica si es prometedor para alcanzar un estado meta optimo
- $h(e)$ tiene dos interpretaciones:
	- Estiman la calidad del estado $e$ - Buscar nodos con mayor valor 
	- Estiman la proximidad a un estado final - Buscar nodos con menor valor
___
## Máxima Pendiente

1. Toma primer elemento
2. Si es la meta **FIN CON EXITO**
3. Repetir hasta **EXITO** o **FRACASO**
	1. Generar los estados descendientes (aplicando operadores) del estado actual $N$
	2. Agrega los estados descendientes
	3. Calcula el valor heuristico $h(e)$ de los nuevos estados
	4. Toma al mejor hijo
		1. Si es mejor o igual que $N$ se vuelve el nuevo estado actual
		2. Si no, **FRACASO**
	5. Si es la meya indicar **EXITO**
4. Si **EXITO** regresar la ruta de solucion
___
## Primero el mejor

- Se trabaja con todos los estados que no se han revisado
- Se busca no caer en un minimo local como en la busqueda maxima pendiente
- Se busca por el nodo que esta mas cerca de la meta
___
## Algoritmo A*

- Toma en consideracion la longitud de la raiz hasta el estado actual en la funcion de evaluacion $h$
- Considera:
	- Lo bueno que es un estado
	- Como es el camino usado para alcanzarlo
- Funcion de evaluacion A*: $f(n)=g(n)+h(n)$
	- $g(n)$ : costo del mejor camino desde el estado inicial al estado $n$
	- $h(n)$ : estimacion del coste desde $n$ hasta un estado final optimo
	- $f(n)$ : Costo estimado de la mejor solucion que pasa por el estado $n$
- En el proceso de busqueda los costos son aproximados, por lo que se trabaja con: $f'(n)=g'(n)+h'(n)$
	- Pero se considera que $g'(n)>=g(n)$, por lo que los valores son aceptables
### Ejemplo Rumania
![[Pasted image 20230926165808.png | 400]]
$F(A)=g(a)+h(a) = 366$
$F^A (s) = g(s) + h(s) = 140 + 293 = 393$
$F^S (R)= g(R)+h(R)=(140+180) + 193 = 413$
$F^S(F) = (140+99) + 178 = 417$
$F^R(P)=(220+146)+160=526$
$F^R(P)=(220+97)+98=415$
$F^P(B)=(317+101)+0=418$
$F^F(B)=(239+211)+0=450$

Ruta de Solución: $A,S,R,P,B$
___
## Búsqueda MiniMax
- Se utiliza para **búsquedas con competidores**
- Su objetivo es maximizar las *tiradas* considerando que el componente minimizara

- El árbol se divide en niveles
    - El primer jugador (estado raíz) corresponde a Max
    - Min es el oponente y le corresponde el nivel 1
- Los niveles se van alternando entre Min y Max
- Los nodos hoja se evaluan con heuristicas
    - Por lo tanto, los estados necesitan una heuristica
- A Max le convienen los valores mas altos
- A Min los valores mas bajos o negativos
- A ninguno le conviene el 0
- Se retropropagan los valores hasta la raíz

![[Pasted image 20230926170739.png | 400]]
___
- Informadas (inf. para guiar la busqueda que llegue mas rapido a la solucion)
- No es seguro encontrar la solucion (en las ciegas si)
- Busquedas para un participante que quiere llegar a la meta:
	- Maxima pendiente
	- Primero el mejor
	- A* (Busqueda optima)
		- g(n) - lo que lleva
		- g(n) - lo que le falta para la meta
- Busquedas para dos participantes compitiendo:
	- MiniMax