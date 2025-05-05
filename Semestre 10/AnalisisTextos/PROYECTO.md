>[!info] Análisis de sentimiento a través del tiempo sobre la guerra Rusia-Ucrania

# 1. Selección de Fuentes

Debido al enfoque temporal del proyecto, buscamos fuentes de datos tanto históricas y actuales.

Haremos énfasis en dos fuentes: medios de comunicación tradicionales y redes sociales. La primera como una base más "formal" y tener una visión internacional y política. La segunda, las redes sociales, nos dará un punto de vista "informal", acercado al público general, no tan basado en la política. 

Tener estas dos fuentes principales de información nos permite tanto la opinión institutional, política e influyente de los medios de comunicación, pero también de los influidos, como es de las personas que escriben sus opiniones en redes sociales.

Por tanto, las fuentes a utilizar en este trabajo son las siguientes:
- Medios de Comunicación:
	- The Kyiv Independent (Ucrania) - https://kyivindependent.com/
	- Meduza (Baneado en Rusia) - https://meduza.io/en
	- Russia Today (Rusia) - https://www.rt.com/
	- Aljazeera (Catar) - https://www.aljazeera.com/
	- People's Daily (China) - http://en.people.cn/
	- The Guardian (Reino Unido) - https://www.theguardian.com/international
	- CNN (EEUU) - https://edition.cnn.com/
- Redes Sociales:
	- Twitter (X)
	- Comentarios/posts de Reddit


Se tomará un periodo de tiempo desde el 2014 hasta 2024, siendo el inicio del conflicto entre ambos países en el año 2014  y un año previo al actual de la realización de este proyecto, siendo que la guerra hoy día sigue en curso.

Adicionalmente, se analizarán principalmente los titulares de las noticias, solamente de algunos eventos claves de la guerra se tomará el texto completo para mostrar profundidad.

Los titulares de las noticias muestran las macro tendencias en las noticias, mientras que el texto revelan ciertos cambios menores en los sentimientos


## Noticias:


# 2. Estructura de la Información

Para los textos crudos de noticias se emplearán archivos CSV para almacenar la información:

```csv
fecha, medio, titular, url, texto
```

Almacenarlos de esta forma es más ligero al no repetir los nombres de campos, siendo constantes en una sola línea de cabecera. De igual forma, los CSV son un formato nativo en distintas librerías a utilizar como `pandas` o `numpy`. Adicionalmente, en cuanto a las noticias, de estas siempre recuperaremos la misma información, no tendremos información anidada, como comentarios o reacciones.

En cuanto a la información obtenida de las redes sociales, usaremos los formatos JSON:
```json
{
	"fecha": STR,
	"texto": STR,
	"user": STR,
	"plataforma": STR (X,Reddit),
	"tags": [STR],
	...
}
```

La razón principal de utilizar este formato es que nos permite almacenar información compleja, jerárquica y cambiante de acuerdo a la plataforma. Además, es el formato estándar para el intercambio de datos en la web, por lo que es en este formato como se obtengan la información de las API's de las plataformas.

En caso de que la información obtenida sea de gran tamaño, es posible utilizar el formato de archivo `Parquet` ya que es más rapida y ligera que CSV y JSON. Esto debido a que el formato almacena los datos en binario y los comprime al ingresar. 

# 3. Infraestructura Necesaria

En el proyecto se utilizarán las siguientes herramientas para adquirir la información:

## API's:

- X API (para adquirir información de la red social X) - https://developer.x.com/en/portal/dashboard
- Reddit API  (para adquirir información de subreddits) - https://www.reddit.com/dev/api (https://www.youtube.com/watch?v=x9boO9x3TDA)
- News API (permite obtener noticias de miles de fuentes periodísticas y filtrarlas) - https://newsapi.org/
- Mediastack API (permite obtener noticias de todo el mundo) - https://mediastack.com/
- GDLET - *talvez*


# 4. Preprocesamiento

asd


___
# Procedimiento:

### 1. News API
1. Registration in News API

>[!info] NewsAPI es de costo, solamente es gratis para noticas recientes (1 semana ~)

# Estado del Arte

 - GDLET
Proyecto masivo que recopila datos de multiples medios alrededor del mundo, analiza eventos, emociones y tendencias en tiempo real.

