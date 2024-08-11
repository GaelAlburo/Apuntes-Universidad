Links: [[Compiladores]], [[4. Análisis Sintáctico Descendente (ASD)]]
___

- Primer L como se hará el recorrido de una cadena, de izquierda a derecha
- Segunda L se refiere a que se hará una derivación por la izquierda
- (1) se refiere a que basta con que se apunte a un elemento de la cadena de entrada para saber que acción tomar

Una GLC es una gramática LL(1) si y solo si las producciones de un mismo no-terminal tienen Conjuntos de Selección disjuntos.

___
#### Ejercicio 1
**Definir si la siguiente gramática es una LL(1)**
	1. S $\rightarrow$ aAB
	2. A $\rightarrow$ DB
	3. A $\rightarrow$ a
	4. B $\rightarrow$ bD
	5. B $\rightarrow$ $\epsilon$
	6. D $\rightarrow$ cD
	7. D $\rightarrow$ $\epsilon$

**1. Se obtienen producciones anulables**
5, 7 y 2
**Y no-terminales anulables**
B, D y A

2 y A se añadieron porque del lado derecho tienen puros no-terminales anulables

**2. Se calculan los First de las producciones**
First (1) = {a}
First (2) = First (D) U First (B)= {c b}
First (3) = {a}
First (4) = {b}
First (5) = {}
First (6) = {c}
First (7) = {}

**Se calculan los First de los no-terminales**
First (S) = {a}
First (A) = {a} First (D) U First (B) = {a b c}
First (B) = {b}
First(D) = {c}

**3. Se calculan los Follow de los no-terminales anulables**
Follow (B) = Follow (S) U {-|} U Follow (A) = {} U {-|} U {b -|} = {b -|}
Follow (A) = First (B) U {-|} U Follow (S) = {b} U {-|} U {} = {b -|}
Follow (D) = First (B) U Follow (A) U Follow (B) = {b} U {b -|} U {b -|} = {b -|}

**4. Se calculan los Conjuntos de Selección**
Los Conjuntos de Selección se obtendrán de la siguiente forma:
*Sea i: A $\rightarrow \alpha$*
Donde $i$ es el núm.. de producción y $A$ es un no terminal
$$
C.S.(i) = \begin{cases}
   First(i) &\text{para} &\alpha &\text{no anulable}\\  
   First(i) \bigcup Follow(A) &\text{para} &\alpha &\text{anulable}\\
\end{cases}
$$

C.S. (1) = First (1) = {a}
C.S. (2) = First (2) U Follow (A) = {b c -|}
C.S. (3) = First (3) = {a}
C.S. (4) = First (4) = {b}
C.S. (5) = First (5) U Follow (B) = {b -|}
C.S. (6) = First (6) = {c}
C.S. (7) = First (7) U Follow (D) = {b -|}

**5. Se verifica que los C.S. sean disjuntos**
S - 1 $\rightarrow$ Cumple
A - 2 y 3 $\rightarrow$ Cumple
B - 4 y 5 $\rightarrow$ No cumple
D - 6 y 7 $\rightarrow$ Cumple

**Por lo tanto, NO ES GRAMATICA LL(1)**

___
#### Ejercicio 2 
**Determinar si es una gramática LL(1)**
	1. E $\rightarrow$ TE'
	2. E' $\rightarrow$ +TE' 
	3. E' $\rightarrow$ $\epsilon$
	4. T $\rightarrow$ FT'
	5. T' $\rightarrow$ \*FT'
	6. T' $\rightarrow$ $\epsilon$
	7. F $\rightarrow$ (E)
	8. F $\rightarrow$ a

**TAREA PARA ENTREGAR**