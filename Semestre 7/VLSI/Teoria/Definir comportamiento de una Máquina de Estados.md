Links: [[VLSI]]
___

1. Identificar un estado inicial del sistema secuencial
2. Definir un conjunto de entradas
3. De las entradas y el estado presente, definir el conjunto de salidas y el estado siguiente
4. Pasar al estado siguiente; se convertirá en el estado actual (señal de reloj)
5. Regresar al paso 2 hasta completar todos los estados

___
# Construcción de Circuitos Secuenciales

Una vez se define el comportamiento y este representado en alguna representación estándar, construir el circuito secuencial es simple.,

Consta de una tarea de dos pasos, definir el **bloque de memoria** y diseñar el **bloque combinacional**

___
# Especificación del bloque de memoria

- A partir de la cantidad de estados se calcula el numero de latches o flip-flops necesarios, donde con $n$ elementos de memoria, se pueden guardar $2^n$ estados.
    - Un **latch*** es un elemento asíncrono. El _********flip-flop********_ asíncrono. Por esto se usan los *flip-flops*
- Para elegir el tipo de memoria es arbitrario, hay que elegir el que sea mejor en el circuito

___
### Latch /Flip flop SR, tipo D (Set / Reset)
![[Pasted image 20231104212946.png|500]]
### Flip Flop D
![[Pasted image 20231104213038.png|500]]
### Flip Flop JK
![[Pasted image 20231104213110.png|500]]

### Flip Flop T Toggle
![[Pasted image 20231104213127.png|500]]

> [!done] La diferencia entre flip flops es la forma en que se guarda la información

___
# Especificación del Bloque Combinacional

Se emplea una ***tabla de transiciones***

## Tabla de transiciones

Consta de las entradas                           y las salidas del sistema

| Edo. Presente | Entradas Externas |     | Edo. SIguiente | Salidas | Senales de Activacion |
| ------------- | ----------------- | --- | -------------- | ------- | --------------------- |
|               |                   |     |                |         |                       |

