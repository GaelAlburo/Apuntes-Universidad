Links: [[Compiladores]]
___

# Predictivo (ASDP)
El Autómata Push-Down o de Pila que constituye un ASDP, tiene las siguientes características:
- El conjunto de estados $Q$ esta conformado por q0
	- $Q = \{q_0\}$
- La estructura de la tabla de dicho estado, a la cual nombraremos tabla de Parser, esta conformada por los siguientes elementos:
	- Las columnas están etiquetadas por el alfabeto de la gramática  y el indicador de fin de cadena
		- $\Sigma_P = \Sigma_G U \{-|\}$
	- Los renglones estarán etiquetados por los elementos que entraran en la pila, los cuales son: $\nabla$
		- $\Gamma = N U \{\nabla\} U \{a \in \Sigma_a \}$ 
		- $N$: Conjunto de no-terminales
		- $\nabla$: Indicador de la pila vacía
		- Tal que: $a$ no este **exclusivamente al inicio del lado derecho de las producciones**
	- Operaciones en la pila pueden ser:
		- *pop*: Reemplaza por una cadena o nada sobre la pila
	- Operaciones en la cadena de entrada:
		- Avanza un carácter
		- Retiene el carácter actual

___
#### Ejercicio:
**Construir la tabla de Parser de la siguiente gramática**
1. E $\rightarrow$ TE'      C.S.(1) = {a}
2. E' $\rightarrow$ TE'     C.S.(2) = {+}
3. E' $\rightarrow$ $\epsilon$        C.S. (3) = { +) }
4. T $\rightarrow$ FT'      C.S. (4) = { (a }
5. T' $\rightarrow$ \*FT'    C.S. (5) = {\*}
6. T' $\rightarrow$ $\epsilon$        C.S. (6) = {+)+}
7. F $\rightarrow$ (E)      C.S. (7) = { ( }
8. F $\rightarrow$ a         C.S. (8) = {a}

**Tabla de Parser**

|          | (                     | )           | +                      | *              | a              | -\|         |
| -------- | --------------------- | ----------- | ---------------------- | -------------- | -------------- | ----------- |
| E        | reemp(TE'$)^r$        |             |                        |                | reemp(TE'$)^r$ |             |
| E'       |                       | pop, reten  | reemp$(TE')^r$, avanza |                |                | pop, reten  |
| T        |                       |             |                        |                |                |             |
| T'       |                       | pop, reten  | pop, reten             | reemp$(ET')^r$ |                | pop, reten  |
| F        | reemp$(E))^r$, avanza |             |                        |                |                | pop, avanza |
| )        |                       | pop, avanza |                        |                |                |             |
| $\nabla$ |                       |             |                        |                |                | Acepta      | 


**Operaciones sobre la tabla de Parser de acuerdo a las producciones**

| Caso1 | Tipo produccion                   | Celda TP                      | Operaciones               |
| ----- | --------------------------------- | ----------------------------- | ------------------------- |
| 1     | A $\rightarrow$ b                 | TP [A,b]                      | pop avanza                |
| 2     | A $\rightarrow$ b$\alpha$         | TP[A,b]                       | reemp$(\alpha)^r$, avanza  |
| 3     | A $\rightarrow$ $\epsilon$        | TP[A, x] para toda x$\in$C.S. | pop, reten                |
| 4     | A $\rightarrow$ B$\alpha$         | TP[A,x] para toda x$\in$C.S.  | reemp(B$\alpha)^r$, reten |
| 5     | Para toda $b$ que entra a la pila | TP[b,b]                       | pop, avanza                          |
