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
- scitik-learn
- nltk - good for learning
- spaci - PLN para prod. optimizada

___

SIntactica = Sintagmatica (sinonimos)

# Relacion paradigmatica

Documento: Relacion de palabras de cualquier longitud

Similitud:
- Un perro duerme - (Buscando en google, se tienen 326k resultados)
- Un gato duerme - (367k resultados)
- Una idea duerme (1 resultado)


**Modelo: Bolsa de palabras (BoW - Bag of Words)**
- Toma un documento y cuenta las palabras

Documento 1: Un perro duerme
{
- Un: 1
- Perro: 1
- Duerme: 1
}

Documento 2: Un gato duerme
{
- Un: 1
- Gato: 1
- Duerme: 1
}

El EWOC toma en cuenta cuantas palabras en comun dos documentos, y el conteo de cada palabra.


**Modelo: Expected Overlap of Words in Context (EWOC)**

Cada documento es una secuencia de palabras:
$d = {x_1, x_2, ..., x_n}$
Donde cada $x$ es una palabra en el documento

Adicionalmente se debe normalizar:
$x_i=(count(w_i),d_1)/|d_!|$

___
EL vocabulario es cada palabra unica que aparece en cada documento analizado
`vocabulario = [un, perro, gato, idea, una, duerme]`
`d1 = [1, 1, 0, 0, 0, 1]`
`d2 = [1, 0, 1, 0, 0, 1]`
`d3 = [0, 0, 0, 1, 1, 1]`

Normalizando:

