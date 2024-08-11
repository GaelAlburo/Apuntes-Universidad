Links: [[Compiladores]], [[4. Análisis Sintáctico Descendente (ASD)]]
___

## (Con producciones $\epsilon$)
Una GLC es una gramática **q** si y solo si:
1. El lado derecho de todas sus producciones comienza con un elemento terminal o son  producciones $\epsilon$
2. Las producciones de un mismo no-terminal, deben tener **conjuntos de selección disjuntos**
	*Disjuntos: No hay intersección, no hay elementos en común*

## Conjuntos de Selección
Son conjuntos formados por puros elementos terminales, los cuales se calculan para cada producción de la gramática.

Tienen dos funciones:
1. Saber si es una gramática idónea para un análisis sintáctico descendente
2. Son requeridos para la construcción del Analizador Sintáctico Descendente

El proceso del cálculo de los conjuntos de selección para gramáticas con producciones $\epsilon$  y producciones que en su lao derecho inicien con terminal, así como determinar si es gramática **q**, se realiza a través de los s

#### Ejercicio 1
**Calcular los conjuntos de selección para cada producción de la siguiente gramática y determinar si es gramática $q$**
*1. F -> f(E, E, E)P*
*2. E -> e*
*3. E -> $\epsilon$*
*4. P -> {M*
*5. P -> ;*
*6. M -> sM*
*7. M -> }*
**Resolución:**
1. Las producciones que inician en su lado derecho con terminal, su conjunto estará formado por ese terminal:
*1. F -> f(E, E, E)P*
*2. E -> e*
*3. E -> $\epsilon$*
*4. P -> {M*
*5. P -> ;*
*6. M -> sM*
*7. M -> }*

___
#### Ejercicio 2
**Calcular los conjuntos de selección para cada producción de la siguiente gramática y determinar si es gramática $q$**
![[Pasted image 20231005100108.png|400]]

**Resolución Propia:**
1. Conjunto de selección:
	c.s.(1) = {a}
	c.s.(2) = {a}
	c.s.(3) = {b}
	c.s.(4) = {a}
	c.s.(6) = {b}
	c.s.(8) - {c}
2. Hay 3 producciones $\epsilon$, se calculan el conjunto Follow de B, C y D
	First(1) = {a}
	First(2) = {a}
	First(3) = {b}
	First(4) = {a}
	First(5) = {}
	First(6) = {b}
	First(7) = {}
	First(8) = {c}
	First(9) = {}
	First(S) = {a}
	First(A) = {ab}
	First(B) = {a}
	First(C) = {b}
	First(D) = {c}
3. Se calculan los conjuntos Follow
	Follow(B) = First(C) = {b}
	Follow(C) = {}
	Follow(D) = {}
4. Se obtienen los conjuntos de selección faltantes:
	c.s.(5) = {b}
	c.s.(6) = {}
	c.s.(9) = {}

**LOS CONJUNTOS DE SELECCIÓN NO DEBEN SER VACÍOS, DEBEN SER TERMINALES**
**LA SOLUCIÓN CORRECTA ES LA SIGUIENTE:**
1. Se obtienen los no-terminales anulables: **B, C y D**
2. Y las producciones anulables: **5, 7 y 9**
3. Se obtienen los First *(los mismos que los anteriores)*
4. Ahora se obtienen los Follow:
	Follow(C) = *(Como no tiene nada a la derecha, en la proucción 1, se coloca el inficador de fin de cadena)*
	Follow(C) = {&}

	Follow(B) = First(C) = {b}
	*Pero como C es un no-terminal anulable, se debe considerar también el indicador de fin de cadena*
	Follow(B) = First(C) U {&} = {b&-|}

	*Ahora para el Follow(A), lo que tiene a su derecha son no-terminales anulables, por lo que se considera el indicador de fin de cadena:*
	Follow(A)=First(B) U First(C) U {-|}

	*Para el Follow(D), a su derecha no hay nada, pero se encuentra en una producción de A, entonces será el Follow(A)*:
	Follow(D) = Follow(A)

	*Pero siguiendo esta lógica, en Follow(C) a su derecha no hay nada, por lo que se debe considerar que está en una producción de S:*
	Follow(C) = {-|} U Follow(S) = {-|} U {} = {-|}

	*El mismo comportamiento ocurre en Follow(B), ya que como C es anulable, se considera que no hay nada en su derecha, por lo que se considera el Follow(S):*
	Follow(B) = First(C) U {-|} U Follow(S) = {b-|}

	*El mismo comportamiento ocurre en Follow(A)*

#### Ejercicio 3
**Calcula si la siguiente gramática es una gramática q**
	1. S $\rightarrow$ aBbC
	2. B $\rightarrow$ bB
	3. B $\rightarrow$ $\epsilon$
	4. C $\rightarrow$ cDB
	5. C $\rightarrow$ d
	6. D $\rightarrow$ d
	7. D $\rightarrow$ $\epsilon$

**1. Se obtienen las producciones anulables**
3 y 7
**Y los no-terminales anulables**
B y D

**2. Se calcula el First de cada producción**
First (1) = {a}
First (2) = {b}
First (3) = {}
First (4) = {c}
First (5) = {d}
First (6) = {d}
First (7) = {}
**Y el First de cada no-terminal**
First (S) = {a}
First (B) = {b}
First (C) = {cd}
First (D) = {d}

**3. Se calculan los conjuntos Follow de los no-terminales anulables**
- **Follow (B)**
	B esta en la derecha de lsa producciones 1, 2 y 4
	Se debe observar en cada una de ella
Follow (B) = {b}  *Para produccion 1*
	*Para la produccion 2, como B es el ultimo, se debe calcular el Follow (B), pero genera un ciclo, se pasa al siguinte*
	*Para la produccion 4, B es el ultimo igual, pero ahora se calcula el Follow (C)*
Follow (B) = {b} U Follow(C)
Follow (C) = Follow (S) U {-|} = {} U {-|} = {-|}
Follow B = {b} U {-|} = {b -| }

- **Follow (D)**
Follow (D) = First (B) U Follow (C) = {b -|}

**4. Se calculan los Conjuntos de Seleccion**
C.S. (1) = First (1) = {a}
C.S. (2) = First (2) = {b}
C.S. (3) = Follow (B) = {b -|}
C.S. (4) = Follow (4) = {c}
C.S. (5) = First (5) = {d}
C.S. (6) = First (6) = {d}
C.S. (7) = Follow (D) = {b -|}

**5. Se observan si los Conjuntos de Selección del mismo terminal son disjuntos**
S - 1 $\rightarrow$ Se cumple
B - 2 y 3 $\rightarrow$ No se cumple, se comparte b
C - 4 y 5 $\rightarrow$ Se cumple
D - 6 y 7 $\rightarrow$ Se cumple

**NO ES UNA GRAMATICA Q**
Por lo tanto esta gramática no puede ser identificado por una maquina del analizador sintáctico descendente