
Sintactica = Sintagmatica

Estas relaciones son ocurrencias correlacionadas

Ejemplo:
"come"
Mi  __ come __ el sabado
El __ come __ carne

Hay solo ciertas cosas que se le aplican ciertos verbos

___
Spam:
- oferta (1) es (2) secreto (3)
- click (4) link (5) secreto (3)
- link (5) secreto (3) deportes (6)

No spam (ham):
- practicar (7) deportes (6) hoy (8)
- fui (9) practicar (7) deportes (6)
- deportes (6) secreto (3) hoy (8)
- deporte (10) es (2) hoy (8)
- deportes (6) cuesta (11) dinero (12)

Mensajes spam: $\dfrac{3}{8}$
Mensajes ham: $\dfrac{5}{8}$

Tenemos un vocabulario de 12 palabras, tenemos nuestra BoW:
```python
vocab = {
	1: (1/9, 0/15), 
	2: (1/9, 1/15), 
	3: (3/9, 1/15),
	4: (1/9, 0/15),
	5: (1/9, 0/15),
	6: (1/9, 4/15),
	7: (0/9, 2/15),
	8: (0/9, 3/15),
	9: (0/9, 1/15),
	10: (0/9, 1/15),
	11: (0/9, 1/15),
	12: (0/9, 1/15)
}
```

$P(\text{'secreto'} \, | \, C=spam) \, = \, \dfrac{3}{9}$.  3 palabras 'secreto' en las 9 palabras totales de spam
$P(\text{'secreto'} \, | \, C=ham) \, = \, \dfrac{1}{15}$

- Cual es la probabilidad de elegir la palabra 'secreto' dentro de las dos bolsas:
$P(\text{'secreto'}) \, = \, \dfrac{4}{24} \, = \, P(\text{'secreto'} \, | \, C=spam) P(C=spam) + P(\text{'secreto'} \, | \, C=ham) P(C=ham)$

Probabilidad de elegir la palabra 'secreto' en la bolsa Ham por la probabilidad de elegir la bolsa Ham, mas la probabilidad de elegir la palabra 'secreto' en la bolsa Spam por la probabilidad de elegir la bolsa Spam.

- Si me llego un correo que solo contiene la palabra 'deportes', se clasifica como Ham o Spam?
$P(C=spam \, | \, \text{'deportes'}) \, = \, \dfrac{ \dfrac{3}{8} * \dfrac{1}{9} }{ \dfrac{3}{8} * \dfrac{1}{9} + \dfrac{5}{8} * \dfrac{4}{15} } \, = \, \dfrac{ \dfrac{3}{72} }{ \dfrac{4}{XX} } \, = \, \dfrac{1}{3}$

$P(C=ham \, | \, 'deportes') \, = \, \dfrac{2}{3}$


- Probabilidad que un mensaje con las palabras 'secreto', 'es' y 'secreto' sean Spam:

$P(C=spam\,|\,M_1=\text{'secreto'}, M_2=\text{'es'}, M_3=\text{'secreto'}) \, =$

$\dfrac{ P(C=spam) * P(M_1 | C=spam) * P(M_2|C=spam) * P(M_3|C=spam) }{ P(C=spam) * P(M_1|C=spam) ... P(M_2|C=spam) + P(C=ham) * P(M_1|C=ham) ... P(M_3|C=ham) } \, =$

$= \, \dfrac{ \dfrac{3}{8} * \dfrac{3}{9} * \dfrac{1}{9} * \dfrac{3}{9}} { \dfrac{3}{8} * \dfrac{3}{9} * \dfrac{1}{9} * \dfrac{3}{9} + \dfrac{5}{8} * \dfrac{1}{15} * \dfrac{1}{15} * \dfrac{1}{15} } \, = \, 0.96 \, = \, 96\%$ 


- Probabilidad de que el mensaje 'hoy es secreto' sea Spam

$P(C=spam | M_1=\text{'hoy'}, M_2=\text{'es'}, M_3=\text{'secreto'})= \, \dfrac{ \dfrac{3}{8} * \dfrac{0}{9} * \dfrac{1}{9} * \dfrac{3}{9}} { \dfrac{3}{8} * \dfrac{0}{9} * \dfrac{1}{9} * \dfrac{3}{9} + \dfrac{5}{8} * \dfrac{3}{15} * \dfrac{1}{15} * \dfrac{1}{15} } \, = \, 0 \, = \, 0\%$ 


>[!info] Estos son problemas de sobreajuste (overfitting)

Es decir, que para los problemas vistos funciona muy bien. Pero para los problemas no vistos no funciona. Por ejemplo, como no se ve 'hoy' en spam, colapsa a un 0% de probabilidad

- Una solución es aplicar 'spooning'

Crearemos un mensaje virtual con todas las palabras del mundo. Cada vez que llegue una palabra se colocara tanto en Spam como en Ham. Pero no se escribirá explícitamente, sino que aplicaremos conteo de Laplace. Esto hará que la verosimilitud sea menor, pero nos permitirá generar una mejor probabilidad.

$$Laplace \, = \, \dfrac{count+k}{\Big(\sum^N_{i=1} \, count(e_i)\Big) k_N}$$
$k = 1$
En este caso, $N= 2$. Dado que tenemos dos categorías (spam y ham)

$spam \, = \, \dfrac{3+1}{8+1(2)} \, = \, \dfrac{4}{10}$

$ham \, = \, \dfrac{5+1}{8+1(2)} \, = \, \dfrac{6}{10}$

MIentras mayor sea valor de $k$ menor verosimilitud. Mientras menor sea su valor mayor su verosimilitud con el vocabulario real.

$P(W=\text{'hoy'}) \, = \, \dfrac{3+1}{24+1(12)} \, = \, \dfrac{4}{36}$
$N=12$ porque, en nuestro vocabulario, una palabra $W$ puede tomar 12 valores distintos

$P(W=\text{'hoy'}|C=spam) \, = \, \dfrac{0+1}{9+1(12)} \, = \, \dfrac{1}{21}$

$P(W=\text{'hoy'}|C=Ham) \, = \, \dfrac{3+1}{15+1(12)} \, = \, \dfrac{4}{27}$


$P(C=spam | M_1=\text{'hoy'}, M_2=\text{'es'}, M_3=\text{'secreto'})= \, \dfrac{ \dfrac{4}{10} * \dfrac{1}{21} * \dfrac{2}{21} * \dfrac{4}{21}} { \dfrac{4}{10} * \dfrac{1}{21} * \dfrac{2}{21} * \dfrac{4}{21} + \dfrac{6}{10} * \dfrac{4}{27} * \dfrac{2}{27} * \dfrac{2}{27} } \, = \, 0.41 \, = \, 41\%$

Con Laplace, se actualizan las probabilidades de cada palabra en Spam y Ham


- Un problema que surge al programar es de overflow. Debido a la cantidad de operaciones y, usando un vocabulario real, hay muchas palabras con probabilidades ínfimas.

Una solución es tomar en cuenta solo el numerador de las probabilidades. 

$log(P(C))+count(w_i,d) \, \sum^M_{i=1} \,log(P(w_i|e))$

>[!done] Programar este proceso de clasificacion. No usar librerias

___

$X_w \in \{0,1\}$
$X_w = 1:$ w esta presente
$X_w = 0:$ w no esta presente

$P(x_w=1)+P(x_w=0) = 1$


Eje Y: aleatoriedad (impredictibilidad)
Eje X: Probabilidad de que caiga aguila es 0: $P(A=1) = 0$

MIentras mas aleatoria es una variable, es donde alcanza su pico en la gráfica.
Esto es la entropia.

La evolución es un fenómeno biológico de la entropia

Entropia:
$H(X_w) \, = \, \sum_{v\in \{0, 1\}} P(X_w=v) \, log_2 P(X_w=v)$

La entropia se mide en bits (porque es información)

Predictibilidad: predecible verlo como no verlo
Probable: verlo


$P(x_A = 1) = 0.5$ -> En este punto hay mas impredictibilidad
$[(0.5)(-1) + (0.5)(-1)]$

$w_1$: carne -> mayor entropia
$w_2$: la -> menor entropia
$w_3$: unicornio -> menor entropia


$H(X_{carne}) \, = \, -[P(x_{carne=1}) \, \, log_2 P(x_{carne}=1)+P(x_{carne}=0) \, \, log_2P(x_{carne}=0)]$
$H(X_{carne}|X_{come}=1) \, = \, -[P(X_{carne}=1|X_{come}=1) \, \, log_2 P(X_{carne}=1|X_{come}=1)+P(X_{carne}=0|X_{come}=0) \, \, log_2P(X_{carne}=0|X_{come}=0)]$
$H(X_{carne}|X_{come}=0)$ -> Similar a anterior


Entropia de una variable dada otra:
$H(X_{carne} | X_{come}) \, = \, \sum_{U\in\{0,1\}} P(X_{come}=U) \, H(X_{carne}|X_{come}=U)$
$= \, \sum_{U \in \{0,1\}} [P(X_{come}=U) \, \Big( -\sum_{V\in \{0,1\}} P(X_{carne} = V) \Big)]$

```
para cada w1
	para cada w2
		calcular H(x_w1|x_w2)
	ordenar ascendente H(x_w1|x_w2)
tomar el top N
```

- Se puede comparar:
EL mismo elemento en distintos universos. Que tanta informacion aporta el mismo elemento en distintas partes del sistema
$H(X_1 | X_2)$
$H(X_1 | X_3)$

- NO se puede comparar
Disintos elementos en el mismo universo
$H(X_1 | X_2)$
$H(X_3 | X_2)$

___
# Información Mutua

$I(X; Y) \, = \, H(X) - H(X|Y) = H(Y)-H(Y|X)$

Estan relacionadas $X$ y $Y$, porque observar $Y$ reduce la entropia de $X$ y viceversa

$X$: wars tiene una cierta entropia $H$
Pero si se observa $Y$: star, se reduce $H(X)$

>[!info] Reduce la entropia se vuelve mas predecible

>[!info] La información mutua es una medida de interdependencia

- $I(X;Y) >= 0$
- $I(X;Y) = I(Y;X)$
- $I(X;Y) = 0$  iff $X$ y $Y$ son independientes 

Se mide la divergencia:
$$I(X_{w1}; Y_{w2}) \, = \, \sum_{U\in\{0,1\}} \, \sum_{V\in\{0,1\}} \, P\Big( X_{w1}=U, X_{w2}=V \Big) \, log_2 \dfrac{P(X_{w1}=U, X_{w2}=V)}{P(X_{w1}=U) P(X_{w2}=V)}$$
Con el logaritmo restamos de nuestro valor la independencia. Una division de logarimo es equivalente a una resta
SI diverge mucho, ambas variables son muy dependientes. Dando valor positivo
SI no diverge, ambas variables son independientes. Por lo que sera negativo


$$P(X_{w1}=1) + P(X_{w2}=0) = 1$$
$$P(X_{w1}=1) = P(X_{w1}=1, X_{w2}=0) + P(X_{w1}=1, X_{w2} = 1)$$
$$(X_{w2}=1) = P(X_{w1}=0, X_{w2}=1) + P(X_{w1}=1, X_{w2} = 1)$$

Con esto tendríamos el mismo problema de sobreajuste que en el ejemplo de SPAM/HAM. Tendríamos que normalizar para evitar este problema:

$$P(X_{w1}=1) \, = \, \dfrac{count(w_1, d) + 1}{|d| + 2}$$
$$P(X_{w1}=1, X_{w2}=1) \, = \, \dfrac{count((w_1, w_2), d)) + 1}{|d| + 4}$$


- Mayor entropia es un sistema impredecible, es vital
- Menor entropia 

Una lengua con poca entropia, son las lenguas muertas. Porque nadie creara nuevas palabras. En cambio las lenguas vivas y usadas actualmente son las que mayor entropia tienen.

