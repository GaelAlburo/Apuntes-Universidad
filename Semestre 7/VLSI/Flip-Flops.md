Links: [[VLSI]]
___

Estas tablas de verdad muestran las salidas del flip-flop en función de sus entradas. Ten en cuenta que estos son ejemplos genéricos, y las especificaciones exactas pueden variar según el fabricante o la implementación.

1. Flip-Flop RS (Set-Reset):

 | S (Set) | R (Reset) | Q (Salida) | Q' (Negación de salida) |
   | ------- | --------- | ---------- | ----------------------- |
   | 0       | 0         | ?          | ?                       |
   | 0       | 1         | 0          | 1                       |
   | 1       | 0         | 1          | 0                       |
   | 1       | 1         | Indefinido | Indefinido              |
   

3. Flip-Flop D (Data):

| D (Entrada de datos) | CLK (Reloj) | Q (Salida)        |
| -------------------- | ----------- | ----------------- |
| 0                    | ↑           | 0                 |
| 1                    | ↑           | 1                 |
| X (Indefinido)       | X           | Último valor de Q |

5. Flip-Flop JK:

| J (Entrada J) | K (Entrada K) | CLK (Reloj) | Q (Salida) | Q' (Negación de salida) |
| ------------- | ------------- | ----------- | ---------- | ----------------------- |
| 0             | 0             | ↑           | No cambia  | No cambia               |
| 0             | 1             | ↑           | 0          | 1                       |
| 1             | 0             | ↑           | 1          | 0                       |
| 1             | 1             | ↑           | Cambio     | Cambio                  |

7. Flip-Flop T (Toggle):

| T (Entrada Toggle) | CLK (Reloj) | Q (Salida)        |
| ------------------ | ----------- | ----------------- |
| 0                  | ↑           | No cambia         |
| 1                  | ↑           | Inversión de Q    |
| X (Indefinido)     | X           | Último valor de Q |

___

Ten en cuenta que en la tabla de verdad del flip-flop RS, cuando ambos S y R son 1, la salida es indefinida, y eso es una condición que debe evitarse en la práctica. Además, la tabla de verdad de un flip-flop D muestra que la salida toma el valor del dato de entrada cuando el reloj sube (↑). En el caso de un flip-flop JK, las entradas 1-1 se utilizan para cambiar el estado del flip-flop, y las entradas 0-0 y 1-0 se utilizan para mantener o cambiar el estado. Finalmente, el flip-flop T cambia su estado cuando T es 1 y el reloj sube.