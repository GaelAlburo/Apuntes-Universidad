
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


