Links: [[VLSI]]
___

**(Codificación Binaria de los Estados)**

Que el bloque combinacional se reduzca depende del proceso de minimización del circuito combinacional.
Sin embargo hay efecto en el circuito resultante si se modifica la forma en que se hace la **asignación de estados**

> [!done] El objetivo es encontrar la asignación de estados que haga las funciones de activación de los flip-flops mas simples

___
## Formas de Codificar
- Código binario natural
- Código Gray 
- Código Johnson
- Código "one-hot" (*contador de anillo*)
- Código "one-hot" modificado con estado cero

*Se recomienda seguir la secuencia en que se presentan los estados*

___
# Selección tipo de Flip-Flop
Existen recomendaciones para hacer la selección, dependiendo de la forma que tenga la maquina de estados
La mejor opción es probar con diferentes tipos y ver cual resulta en un circuito mínimo

- En general, para circuitos muy lineales, se usan **tipo T**
- Si es muy complejo, se usan **tipo D**
- Para circuitos intermedios se usan **tipo JK**

