Links: [[Compiladores]], [[4. Análisis Sintáctico Descendente (ASD)]]
___

Una GLC es una gramática *S*, si y solo si:
1. El lado derecho de todas sus producciones comienza con un elemento terminal
2. En las producciones de un mismo no terminal, sus lados derechos deben iniciar con diferente terminal
### Ejemplos
**Identificar que gramáticas son tipo *S***
	*1. A -> i(E)P
	2. E -> aRI
	3. E -> cRI
	4. I -> a
	5. I -> c
	6. R -> <
	7. R -> >
	8. P -> {M
	9. P -> ;
	10. M -> sM
	11. M -> }*
1. Si lo cumple
2. Si lo cumple
Podemos observar que 1) todas las producciones, en su lado derecho, inician con terminal,  2) todos sus  no-terminales inician el lado derecho con distintos terminales

___
	*1. F -> f(E, E, E)P
	2. E -> e
	3. E -> $\epsilon$
	4. P -> {M
	5. P -> ;
	6. M -> sM
	7. M -> }*
1. No lo cumple porque $\epsilon$ no es un elemento terminal
Debido a la producción *3* hace que no se cumpla la condición 1) de una gramática S.

Para transformarla es necesario hacer que E:
	*1. F -> f (E E R P
	2. E -> e
	3. E -> ;
	4. P -> {M
	5. P -> ;
	6. M -> sM
	7. M -> }
	8. R -> e)
	9. R -> )*
- Para lograrlo aumentan numero de no terminales y de reglas de producción

___
**Revisa la siguiente gramática  di si es o no, una gramática S y por qué:**
*1. D $\rightarrow$ VaL:T*
*2. L $\rightarrow$ ,aL*
*3. L $\rightarrow \epsilon$*
*4. T $\rightarrow$ r*
*5. T $\rightarrow$ i*
*6. T $\rightarrow$ b*
No es gramática S porque $\epsilon$ no es un terminal

Para transformarlo se tiene la siguiente solución:
*1. D $\rightarrow$ VaL*
*2. L $\rightarrow$ ,aL*
*3. L $\rightarrow$ :T*
*4. T $\rightarrow$ r*
*5. T $\rightarrow$ i*
*6. T $\rightarrow$ b*

___
##
Las gramáticas definen (no acepta), los autómatas reconocen (aceptan)
Gramáticas equivalentes definen exactamente el mismo lenguaje
Un lenguaje es un conjunto de cadenas o sentencias que son definidas mediante una gramática
