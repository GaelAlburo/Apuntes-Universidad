Links: [[Inteligencia Artificial]]
___

Razonamiento probabilístico $\rightarrow$ Razonamiento Bayesiano
El teorema de Bayes permite calcular las probabilidades a posteriori

___
# Teorema de Bayes
Obtiene una creencia o hipótesis basada en una nueva evidencia
- Revisa la probabilidad cuando

## Población
Sean A y B dos eventos y P(B) $=!$ 0
Entonces:
$$P(A/B) = \frac{P(A \cap B)}{P(B)}$$
Donde la P(A^B) se denota como la probabilidad de que A suceda una vez sucedido B

### Ejemplo 1:
A $\rightarrow$ cara en el primer lanzamiento
B cara en el segundo lanzamiento
$$P(A\cap B) = P(A) P (B)$$
$$P(A\cap B) = (\frac1 2)(\frac 1 2) = 0.25$$

### Ejemplo 2:
Si la probabilidad de que un sistema de comunicación tendrá alta fidelidad es de 0.81, así como la probabilidad de que tendrá alta fidelidad y alta selectividad es 0.18. Cual es la probabilidad de que un sistema con alta fidelidad también tendrá selectividad?
$P(F) = 0.81$
$P(S) = 0.18$
$P(F \cap S) = 0.81(0.18)=0.146$

___
# Eventos Mutuamente Excluyentes
Si $B_1,B_2,...,B_n$ son eventos mutuamente excluyentes, de los cuales uno debe ocurrir, entonces:
$$P(A) = \sum^n_{i=1} P(B_i)P(A/B_i)$$

### Ejemplo 3:
*foto*
$P(BE)=\sum P(Empresa)*P(BE/Empresa)$
$P(BE/Empresa)$: Posibilidad de buen estado dado que es de la empresa X
$P(Empresa)$: Posibilidad de que sea de X empresa

$P(BE) = (.97)(.5)+(.98)(.40)+(.99)(.1) = .976*100 = 97.6\%$
Posibilidad de 97.6% de que un producto de cualquier empresa (A, B o C) sea de buen estado

____
# Teorema de Bayes
Si $B_1,B_2,...,B_n$ son eventos mutuamente excluyentes, de los cuales uno debe ocurrir, entonces:
$$P(B_R/A)=\frac{P(B_r)P(A/B_r)}{\sum^n_{i=1}P(B_i)P(A/B_i)}$$
### Ejempo:
$$P(Emp/Edo)=\frac{P(Emp)*P(Edo/Emp)}{P(Edo)}$$
$P(C/ME)$: Probabilidad de que sea de la empresa C un producto en mal estado:
$$P(C/ME)=\frac{0.10 * 0.01}{0.024} = 0.416$$
0.024: Probabilidad de que un producto sea en mal estado

Probabilidad de que un producto en mal estado sea de la empresa A:
$$P(A/ME)=\frac{0.50 * 0.03}{0.024} = 0.625$$
___