 
___

Para la sig. gramática:
a) Obten los conjuntos de selección de cada producción
b) Construye la tabla de Parser
c) Haz el reconocimiento de dos cadenas

**Gramática:**
1. B $\rightarrow$ DLI
2. D $\rightarrow$ TaV;
3. T $\rightarrow$ c
4. T $\rightarrow$ i
5. T $\rightarrow$ f
6. V $\rightarrow$ ,aV
7. V $\rightarrow$ $\epsilon$
8. L $\rightarrow$ DL
9. L $\rightarrow$ $\epsilon$
10. I $\rightarrow$ sP
11. I $\rightarrow$ {P}
12. P $\rightarrow$ sP
13. P $\rightarrow$ {I}
14. P $\rightarrow$ $\epsilon$

**a) Conjuntos de Selección:**

	i) Producciones y no-terminales anulables
	7, 9, 14
	V, L, P

	iii)
	First(1) = {cif}
	First(2) = {cif}
	First(3) = {c}
	First(4) = {i}
	First(5) = {f}
	First(6) = {,}
	First(7) = {}
	First(8) = {cif}
	First(9) = {}
	First(10) = {s}
	First(11) = {{}
	First(12) = {s}
	First(13) = {{}
	First(14) = {}
	First(B) = First(D) = {cif}
	First(D) = First(T) = {cif}
	First(T) = {cif}
	First(V) = {,}
	First(L) = First(D) = {cif}
	First(I) = { s{ }
	First(P) = { s{ }

	iii)
	Follow(V) = {;}
	Follow(L) = First(I) = {s}}
	Follow(P) = Follow(I) U { } } = {-|} }
	Follow(I) = {-|} U Follow(B) U {}} = {-|}}

	iv)
	C.S.(1) = {cif}
	C.S.(2) = {cif}
	C.S.(3) = {c}
	C.S.(4) = {;}
	C.S.(5) = {f}
	C.S.(6) = {,}
	C.S.(7) = {;}
	C.S.(8) = {cif}
	C.S.(9) = {s{}
	C.S.(10) = {s}
	C.S.(11) = {{}
	C.S.(12) = {s}
	C.S.(13) = {{}
	C.S.(14) = {-|}}

**b) Tabla de Parser**
1,        B-i,c,f: reemp(DLI$)^r$, reten
2,        D-i,c,f : reemp(TaV$)^r$, reten
3,4,5,   T-c,i,f : pop avanza
6,        V-, : reemp(aV$)^r$, avanza
7,         V-; : pop, reten
8,         L-c,i,f : reemp(DL$)^r$, reten
9,         L-s,} : pop,reten
10,       I-s : reemp(P$)^r$, avanza
11,       I-} : reemp( P} $)^r$, avanza
12,       P-s : reemp(P$)^r$, avanza
13,       P-{ : reemp( I} $)^r$, avanza
14,       P-},-| : pop, reten
a-a: pop, avanza
;-; : pop,avanza
}-} : pop, avanza
$\nabla$- -| : acepta

**c) Haz el reconocimiento de dos cadenas**
1. ca;fa,a;-|

| ca;fa,a;-\| | B$\nabla$      |
| ----------- | -------------- |
| ca;fa,a;-\| | DLI$\nabla$    |
| ca;fa,a-\|  | TaV;LI$\nabla$ |
| a;fa,a-\|   | aV;LI$\nabla$  |
| ;fa,a-\|    | V;LI$\nabla$   |
| ;fa,a-\|    | ;LI$\nabla$    |
| fa,a-\|     | LI$\nabla$     |
| fa,a-\|     | DLI$\nabla$    |
| fa,a-\|     | TaVLI$\nabla$  |
|             |                |

2. {a,a;ca;-| 

| {a,a;ca;-\| | B$\nabla$ |
| ----------- | --------- |
|             |           |

3. ca;{ss}-|

| ca;{ss}-\| | B$\nabla$      |
| ---------- | -------------- |
| ca;{ss}-\| | DLI$\nabla$    |
| ca;{ss}-\| | TaV;LI$\nabla$ |
| a;{ss}-\|  | aV;LI$\nabla$  |
| ;{ss}-\|   | V;LI$\nabla$   |
| ;{ss}-\|   | ;LI$\nabla$    |
| {ss}-\|    | LI$\nabla$     |
| {ss}-\|    | I$\nabla$      |
| ss}-\|     | P}$\nabla$     |
| s}-\|      | P}$\nabla$     |
| }-\|       | P}$\nabla$     |
| }-\|       | }$\nabla$      |
| -\|        | $\nabla$       |
|            | Acepta         | 



