Links: [[Inteligencia Artificial]]
___

Utiliza Representación Subsimbólica

> Machine Learning algorithms <mark class="hltr-pink">discover</mark> the relationships between the variables of a system (input, output and hidden) from direct samples of the system
> - Greg Grudic

> [!done] Es una forma donde una computadora aprende los datos. En lugar de aprenderlo mediante la programacion explicita. La salida se genera con el entrenamiento del algoritmo con los datos.


El objetivo principl es que las computadoras aprendan sin intervencion humana
___
# Aprendizaje Supervisado

- Aprendizaje **con maestro**
- Indica los errores en el aprendizaje (en el entrenamiento)
- Corrige los errores
- Conoce cual es la salida esperada

Usos:
- Clasificacion $\rightarrow$ A que clase pertenece un objeto
- Regresion $\rightarrow$ Encuentra un numero

### Clasificacion
El objetivo principal, en lugar de la clasificacion, es la prediccion sobre nuevos datos. Encontrar una clasificacion, con todo lo aprendido, de nuevos datos

| C (Numero de clases) | Tipo de clasificacion         |
| -------------------- | ----------------------------- |
| C = 2                | Clasificacion Biclase/Binaria |
| C >2                 |                               | 

Dado un objeto (conjunto de caracteristicas medidas) asignarle una(s) etiqueta de un conjunto finito

	Se tiene la dupla: (X, Y)
	X = {x1, x2, x3, ..., xn} : Caracteristicas
	Y = {Respuesta conocida}

$F: X \rightarrow Y$  


### Regresión
El objetivo principal es realizar predicciones con nuevos datos no utilizados en el entrenamiento.
Dado un objeto asignarle un numero real

*Ejemplo:* Predecir la relación euro-dólar de manana. Predecir niveles de stock/ventas a fututo

**Modelos utilizados:**
- Regresión lineal
- Regresión logística
- Redes neuronales (Perceptron simple y multicapa)
- Arboles de decision
- **Random Forest**
- Maquinas de soporte vectorial
- K-Vecinos mas cercanos
- Etc.

___

# K-Nearest-Neighbor

- Aprendizaje supervisado
- K es un numero
- Busca la similitud entre datos
- Sirve para regresión y clasificación
- Se toma un dato y nos dice a que clase pertenece
	- La clase es la que resulte de la de los K-datos mas cercanos

**Algoritmo:**
1. Seleccionar el valor de $K$, con 2 clases conviene poner una $K$ impar
2. Calcular la distancia euclidiana de todos los puntos con el nuevo
3. Tomar los $K$ vecinos con la menor distancia
4. Contar de los $K_{nn}$ cuantos son de cada categoria
5. Asignar el nuevo dato a la categoria con mas $K_{nn}$ encontrados

___
# Distancias Utilizadas para Aprendizaje
**Distancia Euclidiana**
$$raiz \sum^k_{i=1} (x_i-y_i)^2$$
Nos          
**Distancia Manhattan**
$$\sum^k_{i=1} |x_i-y_i|$$
**Diferencia de Euclidiana**
$$(M_4,M_1)=\sqrt{ (0-0.6)^2+(0-0)^2+(1-1)^2+(1-0)^2}$$
___
# K-Fold Cross Validation
Dividir los datos de forma aleatoria en $k$ grupos del mismo tamaño
$k-1$ grupos se emplean para entrenar el modelo y uno de los grupos se emplea como test, este proceso se repite $k$ veces utilizando un grupo distinto como *test* en cada iteración

