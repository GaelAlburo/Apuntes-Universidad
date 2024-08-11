Links: [[Compiladores]]
___

**Construir un autómata de pila que reconozca el lenguaje definido por:**
- Cadenas de 0s y 1s que contengan el mismo numero de 0s que de 1s
	- 0011
	- 01
	- 1010

___
Se creara una tabla para representarlo
Habrá una tabla por cada estado
# Tabla q0

| q0  | 0                   | 1                   | -\| |
| --- | ------------------- | ------------------- | --- |
| 0   | push(0), avanza, q0 | pop, avanza, q1     |     |
| 1   | pop, avanza, q1     | push(1), avanza, q0 |     |
| $   | push(0), avanza, q0 | push(1), avanza, q0 |     |

**Pila:**

| 0011-\| | $      | q0  |
| ------- | ------ | --- |
| 011-\|  | 0$     | q0  |
| 11-\|   | 00$    | q0  |
| 1-\|    | 0$     | q1  |
| -\|     | $      | q1  |
|         | acepta |     | 
___
**Pila:**

| 1010-\| | $      | q0  |
| ------- | ------ | --- |
| 0101-\| | 1$     | q0  |
| 101-\|  | $      | q1  |
| 01      | 1$     | q1  |
| 1       | $      | q1  |
|         | acepta |     |
___
# Tabla q1
| q0  | 0                   | 1                   | -\|    |
| --- | ------------------- | ------------------- | ------ |
| 0   | push(0), avanza, q1 | pop, avanza, q1     |        |
| 1   | pop, avanza, q1     | push(1), avanza, q1 |        |
| $   | push(0), avanza, q1 | push(1), avanza, q1 | Acepta |
