Links:
___

![[Pasted image 20240311000410.png]]

**Monitor LCD**
Es una pantalla de cristal líquido (*Liquid Crystal Display*).  Consisten en moléculas de cristal líquido contenidas entre dos conjuntos de electrodos transparentes
Cristales líquidos reaccionan de maneras predecibles cuando se cambia la carga eléctrica que circula entre esos electrodos, lo que significa que se tuercen y se mueven de forma que permiten diferentes cantidades (y colores) de luz a través de los cristales.

**Funcionamiento:**
- contienen un **microprocesador** que se encargará de establecer la posición en la que se encuentran cada uno de los píxeles.
- cuenta, generalmente, con 2 placas de vidrio, estando una de ellas iluminada por la parte trasera con una luz intensa procedente de las lámparas **CCFL (Cold-Cathode Fluorescent Lamps / Lámparas fluorescentes de cátodo frío)**. Esto permite el brillo de la pantalla.

El término cristal líquido hace referencia al hecho de
que en estos compuestos las moléculas están
compuestas según una estructura cristalina, a pesar
de que fluyen como en un líquido.

![[Pasted image 20240311000444.png]]

___
# Algoritmo de Dibujado de Líneas

Ecuación de una recta: $y=mx+b$
Pendiente: $m$. Se conoce al saber dos puntos de la recta. $m=\frac {y_1-y_0} {x_1-x_0}$
$b=y_0-mx_0$

Con estas dos expresiones se puede saber que pixeles se pintaran.
- Primero se deben sustituir los valores de el pixel inicial y el final.
$m=3/4$
$b=2-3/4(1)=5/4$
$y_1=3/4(2)+5/4=11/4=2.75$
- Como se trabaja en un espacio discreto, se debe redondear el valor

El algoritmo que realiza estos cálculos se llama **Algoritmo DDA (*Digital Differential Analyzer*)**

- Una desventaja es que trabajo con números decimales

![[Pasted image 20240311000548.png]]
![[Pasted image 20240311000606.png]]
### Algoritmo de Bresenham
![[Pasted image 20240311000623.png]]

![[Pasted image 20240212135620.png|300]]

Para obtener a $P_k$, que es un parámetro para saber que pixel pintar (si es positivo, se pinta el de abajo, si es negativo se pinta al de abajo)

![[Pasted image 20240212140225.png]]

>[!info] En el espacio discreto (pixeles), se toma un valor de la ordenada al origen de $b=0$. Aun se incluye en las ecuaciones para tomarla en cuenta.

Se obtiene el valor de $P_k$:
![[Pasted image 20240212140240.png]]

Al obtener $P_k$ se evita el uso de números decimales, se obtienen todos los resultados como números enteros
![[Pasted image 20240212140255.png]]

Estas ecuaciones son solamente para calcular el pixel siguiente. Si se quiere generalizar el comportamiento, se agrega a $P_{k+1}$
![[Pasted image 20240212141417.png]]

Para eliminar a la constante $c$
![[Pasted image 20240212141449.png]]

Para dejar a todo en términos de $x_k$
![[Pasted image 20240212141641.png]]

![[Pasted image 20240212141914.png]]
- Es 0 cuando $y_{k+1}=y_k$
- Es 1 cuando $y_{k+1}=y_k+1$

Se pinta el pixel de abajo cuando:
![[Pasted image 20240212142229.png]]

Se pinta el pixel de arriba cuando:
![[Pasted image 20240212142251.png]]

Para cuando $x_0, y_0 = 0,0$
![[Pasted image 20240212142354.png]]

**Reflexion en octantes. Simetria en Octantes**

___
# Bresenham para Circunferencias
De igual forma, hace uso de la ecuación de la figura para realizar el algoritmo.

El valor de $P_k$ nos servira para saber si los pixeles estan dentro de la circunferencia o no. Si es positivo se pinta el pixel de abajo, si es negativo se pinta el pixel de arriba
\

___
Graficar la recta de la presentacion 2.1 p.46 usando DDA y Besenham.
- Inicio: $x_0(2,7)$
- Fin: $x_f(20,19)$

Pintar una circunferencia centrada en el origen, con una radio de 25
**Se pueden calcular los puntos, y nadamas graficar los puntos en un SW**
**PARA 28 DE FEBRERO**

pixel, javascript, geogebra: dr irfen
