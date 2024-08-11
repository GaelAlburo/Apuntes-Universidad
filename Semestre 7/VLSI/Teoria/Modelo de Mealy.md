Links: [[VLSI]]
___

![[Pasted image 20231104211256.png]]

Las variables de salida son una combinación de las entradas y de sus estados
$$Z=Z(Z E, M)$$
___
# Representación del Comportamiento de una Maquina de Estados

- Hay distintas maneras
    - Tabla de Estados
    - Diagrama de estados
- Las características y su forma de construcción depende del modelo conceptual con que se defina

___
# Tabla de Estados

Dada la relación de las entradas y salidas de un circuito secuencial se obtiene las tablas de estado
- Se muestran las transiciones entre estados en función con las entradas, y su relación con las salidas

|          | Entradas Externas         |
| -------- | ------------------------- |
| Estado   |                           |
| Presente | Estado Siguiente, Salidas |

___
# Diagrama de Estados

- Representación grafica del comportamiento de una maquina de estados
- Muestran la misma información que las tablas de estados
- Su diseño depende si se usa un modelo de Mealy o Moore
- Representa a los **estados con círculos** y a las **transiciones como flechas**

___
# Ejemplo - Sumador serial

### ********************************Tabla de estados********************************

|Edo. Pres. \ Ent. Pres.|00|01|10|11|
|---|---|---|---|---|
|S0|S0, 0|S0, 1|S0, 1|S1, 0|
|S1|S0, 1|S1, 0|S1, 0|S1, 1|

### Diagrama de Estados