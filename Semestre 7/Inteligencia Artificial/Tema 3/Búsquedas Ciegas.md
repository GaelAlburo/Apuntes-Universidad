Links: [[3. Búsquedas Inteligentes y Resolución de Problemas]]
___

Hay distintos tipos:
- Búsqueda en Amplitud
- Búsqueda en Profundidad

## Búsqueda en Amplitud
### Algoritmo 1ro en Anchura
1. **Crear** una lista con un solo elemento: *el nodo raíz*
2. **Hasta que** el primer camino de la lista llegue al nodo objetivo o se llegue a la lista vacía **hacer:**
	1. Extraer el primer camino de la lista
	2. Expandir el nodo final de este camino a todos los vecinos del nodo terminal
	3. Eliminar los ciclos de los caminos expandidos
	4. Insertar estos nuevos caminos al **Final** de la lista
3. **FIN Hasta**
4. **Si** se halla el nodo meta, notificar éxito, de lo contrario el fracaso

##### Ejemplos
![[Pasted image 20230926144519.png | 450]]

![[Pasted image 20230926144552.png | 450]]
___
#### Análisis
- Son completas
	- ***b***: factor de ramificación
	- ***d***: profundidad de solución
- Tiempo: $O(b^{d+1})$
- Espacio: $O(b^{d+1})$
	- Mantiene todos los nodos en memoria
___

## Búsqueda en Profundidad
### Algoritmo 1ro en Profundidad

1. **Crear** una lista con un solo elemento: *el nodo raíz*
2. **Hasta que** el primer camino de la lista llegue al nodo objetivo o se llegue a la lista vacía **hacer:**
	1. Extraer el primer camino de la lista
	2. Expandir el nodo final de este camino
	3. Eliminar los ciclos de los caminos expandidos
	4. Insertar estos nuevos caminos al **INICIO** de la lista
3. **FIN Hasta**
4. **Si** la lista esta vacia, **entonces NO** hay solucion; **SI NO** el primer camino de la lista es la solucion 
___
- Expande una rama hasta llegar al final
- Si una rama no es solucion, vuelve al nivel anterior (*backtracking*)
- **Menos exigencia de memoria**, ya que solo almacena los nodos de la ruta donde se expande
___
##### Ejemplos
![[Pasted image 20230926145325.png | 250]]

![[Pasted image 20230926145358.png | 400]]
___
#### Análisis
- Son completas en espacios finitos
- Tiempo: $O(b^{m})$
	- Es terrible si $m$ es mucho mayor a $b$
	- $m$ : máxima profundidad
- Espacio: $O(bm)$
	- Tiene un espacio lineal

### Modificaciones Algoritmo Profundidad

- **Con profundidad limitada**
	- Evita caer en caminos de profundidad muy grandes
	- Al imponer un limite de profundidad maxima
- **Con profundidad iterativa**
	- Aumenta gradualmente la profundidad hasta encontrar una meta
	- Algunos nodos se expanden varias veces
	- En practica es poco trabajo
![[Pasted image 20230926150022.png | 400]]