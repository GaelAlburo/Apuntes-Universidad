Links: [[Lab. Compu Gráfica]]
___

Computo Heterogeneo: Tipo de programacion, donde una parte del codigo se ejecuta en un procesador y otros codigos dentro de otro procesador, en este caso en el GPU.

Tipos de shaders:
- Vertex Shader: Permite aplicar efectos en cada uno de los vertices. Cambios de posicion, escala u orientaciones
- Fragment Shader: Que puntos, o fragmentos o pixeles, seran parte de la geometria descritas por los vertices. Dice principalmente el color de estos pixeles

___
# Código
1. Se tienen los encabezados (glad,glfw,glm)
	- Se tienen tambien clases, objetos, que se mostraran en pantalla, figuras
2. Se tienen las funciones 
	- start()
	- update(): Ciclo de renderizado, donde se dibujan las formas geometricas
	- Callbacks: Generan interrupciones al momento de usar el mouse, scroll o el teclado
		- Adicionalmente se tiene una resize, para ajustar el tamano de la ventana, se ejecuta en cuanto se suelte el mouse al arrastrar
3. Se definen variables globales:
	- `window` y variables para el color de fondo RGBa
	- `shaders` carga los codigos de los shaders a la trajeta grafica
	- `mesh` almacena la informacion de los vertices 


en while(!Update()) nos dice que el renderizado se va a mantener a menos que haya un error en la funcion Update()

Dentro de la clase Triangle se tiene la definicion de sus vertices, al igual que el color de cada uno

A nivel de shaders, estos obtienen la informacion de color vertida en los vertices

____
Para dibujar el rectangulo se modifica la clase Traingle, para que se generen los 4 vertices, tanto para su posicion como su color.
Y se generan 6 indices, 3 para el primer triangulo, 3 para el segundo.

___
Para el circulo, se cambia de GL_TRIANGLES a GL_TRIANGLE_FAN