Temas: 1.1, 1.2

Lo mas valioso, actualmente es la información, permite tomar mejores y rápidas decisiones

# Que es?
Análisis y Exploración automatizadas para <mark class="hltr-pink">descubrir nuevo conocimiento</mark>, patrones o reglas de comportamiento

Conceptualmente se ha realizado por mucho tiempo:
- Identificar el patron para generar fuego
- Descubrir que el planeta es redondo
- Gestion de millones de datos para descubrir patrones

>  Docu "Nada es privado"

La digitalizacion, big data, cloud data han aumentado en gran manera la cantidad de datos

La minería es aplicable a cualquier tipo de area

La ética es una cuestión delicada en la minería de datos

___
- Mesa redonda:
Tema: "Gobierno: Como puede beneficiar a la poblacion explotando la Ciencia de Datos y demas disciplinas alrededor"
- 15 min 
___

# Dominio del Negocio

Es lo primero que se debe identificar, en el descubrir conocimiento de la informacion (KDD)

Se trata de la informacion que usa cada area de negocio y de cual posee una gran cantidad de informacion, y sobre la cual deben obtener el mayor conocimiento posible para solucionar sus necesidades:
- De ventas
- De competencia
- De inventarios
- De clientes
- De costos
- Etc.

___
**Concepto:**
- Aquello que queremos aprender y la salida/resultado de un proceso de aprendizaje
- Puede ser cualquier columna de una vista minable
	- Pero dependiendo del area de negocio estos son distintas

**Atributo:**
- Cada instancia que al entrar al proceso de aprendizaje es caracterizado por sus valores
- Pueden ser:
	- Numericos
	- Nominales
	- Intervalos
	- Booleanos
	- etc.

**Instancia:**
- Conjunto de cosas que seran clasificadas, asociadas o agrupadas

**Vista Minable:**
- Tabla que contiene toda la información que se analizara

___
# Integración de Información

Al hacer el analisis con mineria de datos, es necesario recuperar o integrar toda la informacion para realizar grupos

# Limpieza de Datos

Datos Escasos / Faltantes / Missing

Es terminos de almacenamiento, es optimo registrar los datos faltantas de una forma que no implique espacio de almacenamiento

Es usual que NO siempre se tenga toda la informacion, dependiendo del contexto

Es posible inferir estos valores faltantes a partir de la informacion ya reacabada

### Valores Inexactos

Se debe analizar los datos para identificar atributos defectuosos
Esto ya que la informacion almacenada no se guarda con el objetivo de ser analizada, por lo que no hay mucho rigor

- Errores Tipograficos: Valores que distorsionan el analisis

### Datos Duplicadas / Redundantes

La gente al cambiar un poco sus datos, pueden generar variaciones. Con el proposito de cuidar su informacion o algo parecido

# Conocer la Informacion

Desde generar histogramas, graficas, son de gran ayuda para conocer la informacion general

## Limpieza automatica

Las mismas tecnicas de Mineria de Datos nos permiten realizar la limpieza de los datos, esto mediante una revision meticulosa

### Regresion

Los investigadores usualmente eliminan manualmente los valores "ruido" aislados para realizar una regresion lineal

# Transformacion de Datos

Un proceso exitoso de mineria de datos implica un adecuado algoritmo de aprendizaje y aplicarlo sobre informacion

Cada metodo require distintas transformaciones de los datos para funcionar eficientemente

## Intercambio de Dimensiones

- Creacion de atributos
- Derivados de otros atributos
- Util para predecir comportamientos y encontrar patrones de informacion 

## Discretizacion

- Esencial si la tarea involucra atributos numericos que solo se manejan como categoricos
- Se da una categoria a un grupo de numeros
	- Discretizar rangos de edad:
		- Menor: 0-17
		- Adulto joven: 18-32
		- Adulto: 33-50
Dsitribuciones normales

**Discretizacion Supervisada**
- Establece las clases en que se generara la discretizacion

**Discretizacion No supervisada**
- Establece que las clases las haga la herramienta
- Si se esta deacuerdo se deja, de lo contrario se interfiere

## Numerizacion

- Conversion de una instancia discreta a numerica
	- Se dan valores numericos a valores categoricos
	- Manzana - 5
	- Platano - 6
	- Naranja - 3
- Principalmente para algoritmos de aprendizaje que usan regresion (que naturalmente necesitan valores numericos)

## Normalizacion

- Se puede realizar mediante la media estadistica y la desviacion estandar de los valores
- A cada atributo de la instancia se le sustrae el valor de la media y se divide por la desviacion estandar

- Esto se le llama Estandarizacion de una variable

- Se paga mensualmente 5,000 de un pago minimo mensual de 8,000 de una deuda de 30,000
	- 5,000/8,000 : Se obtiene un indice (una razon), el cual podemos traducir como nivel de compromiso de pago
	- 9,000/8,000 : El compromiso es mayor

## Series de Tiempo

- Cuando se analiza informacion a traves del tiempo
- Util para determinar valores incrementales o deltas en los atributos posteriores al valor inicial
- Para ciertos procesos la delta o valor incremental es mas util que un valor mismo en una instancia

<mark class="hltr-pink">Siguientes Miercoles 21 no hay clases</mark>

___
# Tareas de Mineria de Datos

- Base de Informacion
	- Seleccion: Datos relevantes
		- Preproceso: Datos preprocesados
			- Transformacion: Datos Transformados (se genera una vista minable)
				- Mineria de Datos: Patrones 
					- Interpretacion/Evaluacion: Nuevo conocimiento

Generalmente los primeros pasos son los mas tardados debido a la limpieza, transformacion, y la gran cantidad de informacion

- Evaluacion: De los resultados del modelo, comparalo con las predicciones hechas y lo sucedido en la realidad
	- 