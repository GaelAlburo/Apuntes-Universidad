ccc c2 vvvc2d f P(A) = p
P(-A) = 1-p
P(A, B) = P(A) P(B)

P(A|B) = n
P(-A|B) = 1-n
P(A|-B) = ?

**Probabilidad total:**
P(Y) = P(X) P(Y|X) + P(-X) P(Y|-X)
P(Y) = $\sum ^N _{i=1} \, P(X_i) \, P(Y|X_i)$

P(X, Y|B) = P(B) P(X|B) P(Y|B)
- P(X|B) y P(Y|B) deben ser independientes

**Teorema de Bayes:**
$P(A|B) \, = \, \dfrac{P(A) \, P(B|A)}{P(B)}$
- $P(A|B)$: Posterior
- $P(A)$: Prior
- $P(B|A)$: Verosimilitud (Algo que **parece** verdad/realidad)
- $P(B$: Verosimilitud Marginal

## Ejemplo Examen Medico
P(C) = 0.01
P(T = + | C) = 0.9
P(T = - | !C) = 0.8

$Acc \, = \, \dfrac{TP+TN}{TP+TN+FP+FN} \, = \, \dfrac{0.9+0.8}{2}$

$Prec \, = \, \dfrac{TP}{TP+FP} \, = \, \dfrac{0.9}{1.1}$

$Prec_N \, = \, \dfrac{TN}{TN+FN} \, = \, \dfrac{0.8}{0.9}$

$Recall \, = \, \dfrac{TP}{TP+FN} \, = \, \dfrac{0.9}{1}$

$Recall_N \, = \, \dfrac{TN}{TN+FP} \, = \, \dfrac{0.8}{1}$


$F_1 = \dfrac{2Prec \, Recall}{Prec+Recall}$

P(-C) = 0.99
P(T = - | C) = 0.1
P(T = + | !C) = 0.2

P(T = -, C) = P(T = -) P (C) = P(T = - | C) P (C) =  (0.1) (0.01) = 0.001

P(T = -, !C) = 0.99 \* 0.8 = 0.798

P(T = +, !C) = 0.2 \* 0.99 = 0.198

P (T=+, C) = 0.9 \* 0.01 = 0.009

Ejemplo Ramiro:

- Primer examen, sale positivo:
$P(C | T_1 = +) \, = \, \dfrac{P(C) \, P(T=+ \,|\, C)}{P(C) P(T=+ \, | \, C) + P(!C)P(T=+ \, | \, !C)} \, = \dfrac{0.009}{0.009+0.198} \,$

- Segundo examen, igual positivo:
$P(C \, | \, T_1=+, T_2=+) \, = \, \dfrac{P(C)P(T_1=+ \,| \, C)P(T_2=+ \, | \, C)} {P(C)P(T_1=+ \,|\, C)P(T_2=+\,|\,C) + P(!C)P(T_1=+\,|\,!C)P(T_2=+\,|\,!C)} \,=\, \dfrac{0.0081}{0.0081+0.0396} \,=\, \dfrac{81}{477}$

