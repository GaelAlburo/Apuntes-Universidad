Sea $f: \{0,1\}^2 \rightarrow \{0,1\}^ n$  una función es uno a uno; o bien dos a uno. Encontrar que tipo de función es f

De forma clásica se tiene una complejidad exponencial
Ya que se debe verificar el resultado de $\dfrac{2^n}{2}+1$ entradas.

>[!danger] error en n/2+!

Cuando se miden los qubits de salidas hay dos casos:
- Es uno a uno
	- Todos los bits despues de colapsar son distintos

- Dos a uno
	- Alguno sera igual a uno otro.
	- Se tendran dos resultados distintos (para 2 qubits de entrada y salida)