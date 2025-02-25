Classroom: imzvtdo

token
gramatica
	1ro
	2do
	3er
sintaxis
semantica
pragmatica
	praxis


texto: representacion grafica de la lengua
lengua es subsistema del lenguaje.

formas de representar lenguas:
bits
secuencia maximal: forma de generar tokens, se juntan letras que mas se repiten, estas son tokens
n-gramas (1-grama se conforma por caracter por caracter)

my name: ingles por *my*
mi nombre: espanol por *mi*

<mark class="hltr-pink">TAREA:
Crear un clasificador de idioma (ingles, espanol) basado en n-gramas
n: 2, 3, 4 y 5</mark>

El n-grama mas probable de espanol es distinta al n-grama mas probable de ingles

___

Hay dos tipos de relacion entre palabras:
- Horizontal: La palabra anterior y posterior tienen relacion (palabra - tienen - relacion) (SINTACTICA)
- Vertical: La palabra tiene una relacion con las otras que pude haber elegido (PARADIGMATICA)
	- Gato come
	- Perro come
	- Dinosaurio come
	- Perro lapiz X (lapiz-come no tienen una relacion)

Las relaciones paradigmáticas sirven para:
- Encontrar significado entre palabras
- Realizar conjuntos entre palabras
- Encontrar relaciones entre palabras
- Intercambiar palabras y mantener un significado muy similar
- Podemos encontrar clusters
	- Identificar emociones

Campos semanticos:
- palabras relacionadas, mismos significados, parecidos


___

Bibliotecas de Python:
- numpy
- scipy
- pandas
- gensim - mineria 
- scikit-learn
- nltk - good for learning
- spaci - PLN para prod. optimizada

___

SIntactica = Sintagmatica (sinonimos)

