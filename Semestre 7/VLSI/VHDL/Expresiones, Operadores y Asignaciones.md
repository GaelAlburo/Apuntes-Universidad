Links: [[VLSI]]
___

Una **expresión** es una formula que indica como se debe calcular un valor

Se tiene un conjunto de operadores que actuan sobre un conjunto de operandos, y que se evaluan en un orden predeterminado.

La precedencia puede ser modificada por parentesis

- Operación modulo _**mod**_ es el valor absoluto del residuo de la division
- Operación resto **rest** es el valor con signo del residuo de la division
- Corrimiento lógico a la der. → Division. Corrimiento aritmético a la izq. → Multiplicación
- Corrimiento aritmético a la der. → Division, mantiene signo

___
# Operadores

Los operandos dependen del tipo de datos de los operandos, y estos están definidos en las bibliotecas.

Es posible sobrecargar los operadores básicos

## Operadores de asignación

**<=** → Asigna valores a señales

**:=** → Asigna valores a variables, constantes, genéricos y valores iniciales

**=>** → Asigna valores individuales a elementos de vectores y con `others`
