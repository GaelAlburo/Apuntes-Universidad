Links:
___
![[Pasted image 20240310235754.png|center]]
# Sistema de Referencias

Todos los objetos están descritas de acuerdo a las coordenadas de mundo. Se miden en unidades de distancia

> [!done] El pipeline de renderizado se encarga de pasar de coordenadas de mundo a coordenadas de pantalla

# Coordenadas de Referencia
- Coordenadas de modelo: Como se da forma a los elementos geométricos
	- Estas están en el origen. Se hace esto porque se modela un objeto, después solo se aplican transformaciones geométricas. El mismo modelo se puede duplicar y colocarlo en distintas partes de la escena
- Coordenadas de mundo
- Coordenadas de camara: Se dividen en dos
	- Coordenadas de Vista
	- Coordenadas de Proyeccion
- Coordenadas Normalizadas
- Coordenadas de Pantalla

Para llevar de coordenadas de modelado a coordenadas de mundo se utilizan transformaciones geométricas (transf., rot., escala)

Una vez se tienen los objetos posicionados se pasan a coordenadas de camara.

Teniendo las coordenadas de camara se pasan a coordenadas normalizadas. Toda la información se pasa a un espacio unitario (2D o 3D). Esto se hace para despues poder escalarlo al tamano del monitor o telefono, etc.

Teniendo el espacio unitario se escala al tamano de la pantalla, obteniendo las coordenadas de pantalla

# Pipeline de Renderizado
En codigo, todo este pipeline se representa como una matriz. Que a su vez se compone de otras matrices

- Transformacion (Matriz) de Modelo: Se conforma de la traslacion, rotacion y escalamiento
- Transformacion (Matriz) de Vista: Contiene la posicion de la camara, la vista y la orientacion de la camara
- Transformacion (Matriz) de Proyeccion: Define de que forma se proyectara toda la informacion en un plano                (*perspectiva, ortogonal*)
- Transformacion Normalizacion y Recorte (*Clipping*): transforma todo al espacio unitario y recorta si es necesario
- Transformacion *Viewport* (Puerto de Vista): Se escala el espacio unitario al monitor de despliegue final

En el examen vendra identificar matrices, que transformacion son 

**Transformacion oblicua:** Se toman todos los puntos y se colocan en un solo eje

# Transformaciones Homogeneas

# Transformaciones en 3D
## Traslacion 3D
Al punto inicial se le aplica la transformada T. De forma que las coordenadas finales estan dadas por:
$x+t_x$ ,  $y+t_y$  y $z+t_z$. Adicionando tambien el termino homogeneo $w=1$

Si se quiere tener una traslacion en los 3 ejes, se aplica la siguiente matriz:
![[Pasted image 20240226131544.png|center]]
Si solamente se quiere tener una traslacion en uno de los 3 ejes, se debe utilizar la matriz respectiva siguiente:
![[Pasted image 20240226131629.png|center]]

## Rotación en 3D
![[Pasted image 20240226132933.png|center|550]]
**Permutación cíclica:** Se cambia al observador con respecto al eje en cuestión. Esto facilita obtener las ecuaciones. En la primera ecuación de rotación (con respecto al eje XY) se sustituyen los valores de X y Y con los nuevos valores de la permutación. Si antes era Y, ahora es Z.  O si antes era Y se cambia por X
![[Pasted image 20240226132543.png|center|580]]

Cuando se rote con respecto al eje A, en la fila de A siempre se tendra solamente un 1

___
#### Ejercicio
- Rx(45) del punto (10, 0, 0)
10   0      0     0
0     0      0   0
0     0      0   0
0     0      0    1

P' (10, 0, 0)

- Rz(90) del punto (0,10,0)
0   -10   0   0
0     0    0    0
0     0    0    0
0     0    0    1

P' (-10, 0, 0)

- Ry(90) del punto (0, 0, 10)
0   0   10   0
0   0    0    0
0   0    0    0
0   0    0    1

P' (10, 0, 0)


- Ty(10), del punto (10, 0, 0)
10   0   0    0
0     0   0   10
0     0   0    0
0    0    0    1

P' (10, 10, 0)

- Txy(5) del punto (1, 1, 0)
1    0   0   5
0    1   0   5
0    0   0   0
0    0   0   1

P' (6, 6, 0)

___
# TRSP
Cada uno de los vertices de la geometrica pasaran por las matrices TRSP, es decir, la matriz M.
Las transformaciones entran al pipeline de renderizado como en un sistema de pila, FILO
![[Pasted image 20240226143718.png|center]]

$$M=R_x(50)\space T(2,4,6) \space Ref_y() \space S_{xy}(5) \space S(3)$$

