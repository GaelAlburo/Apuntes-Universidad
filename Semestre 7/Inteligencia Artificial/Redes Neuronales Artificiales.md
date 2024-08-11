Links: [[Inteligencia Artificial]]
___
Las RNA emulan las Redes Neuronales biológicas

Se utilizan para aprender estrategias de solucion basadas en ejemplos de comportamiento tipico

> [!done] No requiere que la tarea a ejecutar se programe, generalizan y aprenden de la experiencia

- El conocimiento es adquirido desde el ambiente externo por el proceso de aprendizaje
- Las conexiones interneuronales incluyen pesos sinápticos, los cuales son usados para almacenar el conocimiento adquirido

Cada neurona artificial es un procesador con operaciones primitivas, como suma de entradas

Los <mark class="hltr-pink">pesos</mark> y <mark class="hltr-pink">funciones</mark> de cada neurona definen el comportamiento global de la red

___
# Modelo Interconexionista

- Tenemos $10^{11}$ neuronas y $10^{13}$ interconexiones
- Las neuronas reciben senales (impulsos) de otras
- Las dendtritas son el receptor de la neurona
- El axion es el transmisor de la nuerona
- La union entre las neuronas es la sinapsis
	- El axon de una con las dendritas de otra
- La efectividad de las sinapsis dependen de las senales que pasen por ellas, <mark class="hltr-pink">aprendizaje</mark>
- La salida de una neurona son impulsos electricos

![[Pasted image 20231123160106.png]]

___
# Modelo Computacional de Neuronas

McCulloch y Pitts en 1943, propusieron el modelo.

| Cerebro                      | Computadora                          |
| ---------------------------- | ------------------------------------ |
| Conexión de axon y dendritas | Alambres y modelo de interconexiones |
| Sinapsis                     | Peso de las conexiones               |
| Actividad del soma           | Funcion de activacion                | 

___
# Fases de una RNA

- Fase de aprendizaje
Aprenden por la actualización de los pesos sinápticos que caracterizan a las conexiones
Se usa un conjunto de datos o patrones

- Fase de prueba
Teniendo los pesos de la red calculados, se comparan la(s) salida(s) de la red con la salida deseada

___
# Neurona Artificial Básica

![[Pasted image 20231123160415.png]]

$w \rightarrow$ Peso sináptico

___
# Componentes de la Neurona

- **Vector de Entradas**
$$x=\{x_1,x_2,x_3,...,x_n\}$$
- **Pesos sinápticos**
$w_{ij} \rightarrow$ Percibe la intensidad de interaccion entre la neurona presinaptica $j$ y la postsinaptica $i$
Es decir, intensidad entre la conexión una neurona y otra

- **Funcion de propagacion**
Calcula el valor de la entrada total a la neurona. Simple **suma ponderada** de las entradas

- **Funcion de activacion**
Calcula el nivel o estado de activacion de la neurona en funcion de la entrada total (funcion de propagacion)

- **Funcion de salida**
Calcula la salida de la neurona en funcion de la activacion.
Usualmente solo se toma a la funcion identidad como salida del valor de activacion
Sera un vector del mismo tamaño que las entradas

- **Funcion de propagacion**
Las redes se representan matematicamente por la funcion base $u(w,x)$:
$$u_i(w,x)=\sum^n_{j=1}w_{ij}\space x_j$$
___
# Funciones de Activacion

- Funcion identidad -  $f(x) = x$
No implica ningun tipo de procesamiento

- Funcion escalon
Se asocia a neuronas, compara contra valor (umbral).
La activacion es 1; si es menor, la activacion es 0 o -1

![[Pasted image 20231123162055.png]]

- Sigmoidal
$$f(u_i)=\frac 1 {1+e^{-u_i/\delta}}$$
- Gaussiana
$$f(u_i)=c*e^{{u_i^2\space/\space\delta^2}}$$
___
# Arquitecturas de RNA

Determina la forma de conexion entre los nodos de una RNA
La organizacion entre sus conjuntos de neuronas dan origen a la arquitectura (estructura)

## Propagación hacia adelante y hacia atrás
![[Pasted image 20231123163712.png]]

## RNA de una sola capa

Todas las neuronas se encuentran en una capa


___
# Ejercicio
**FOTOS**