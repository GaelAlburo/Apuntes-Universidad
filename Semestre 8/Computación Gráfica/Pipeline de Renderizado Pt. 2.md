Links:
___

![[Pasted image 20240310235618.png]]

- Vector $V$ es equivalente al vector $Up$
- Vector $N$ es el contrario al vector $View$
- Vector 
![[Pasted image 20240310235702.png|300]]
## Rotación de cámara según su sistema de coordenadas
![[Pasted image 20240228133231.png|center]]
## Traslación de la cámara según su sistema de coordenadas
![[Pasted image 20240228133323.png|center]]
# Matriz de Vista de Cámara
![[Pasted image 20240228133402.png|center]]
![[Pasted image 20240228133453.png|center]]

____
## Ejercicio
Teniendo los siguientes vectores:
- $P_0 (0, 1, 0)$
- $View (0, 1, -1)$
- $Up(0, 1, 0)$

Para obtener la matriz de vista, se deben calculas los valores de $n, u$ y de $v$
![[Pasted image 20240228134025.png|center]]

- $n=\frac {(0, 1, -1)} {\sqrt 2} \space \space = (0, -\frac {1}{\sqrt 2}, \frac {1}{\sqrt 2})$
- $v = \frac{(0, 1, 0)}{1} = (0, 1, 0)$
- $u=(0, 1, 0) x  (0, -\frac {1}{\sqrt 2}, \frac {1}{\sqrt 2}) = (1, 0, 0)$

Con estos valores se puede obtener la matriz de vista. Adicionalmente se obtienen los productos puntos de cada uno de los vectores obtenidos con $P_0$

1         0        0    0
0         1        0    -1
0     $-\frac{1}{\sqrt 2}$    $\frac{1}{\sqrt 2}$    $\frac{1}{\sqrt 2}$
0         0        0     1

Dentro de OpenGL, la matriz de vista se obtiene con la siguiente instrucción. `glm::lookAt(P0, View, Up)`


MOVF PORTA, W
ANDLW 7
ADDWF PCL, F
GOTO CONF1
GOTO CONF2
GOTO CONF3
...
GOTO CONF8
