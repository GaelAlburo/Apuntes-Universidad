aaqLinks: [[Sistemas de Comunicaciones]]
___

> [!done] El primer enlace telegráfico transatlántico fue de EU a Puerto de Hiro a Londres. Greenpeace nacio en 1907 por estos enlaces, ya que mataban peces, langostas en las costas de Nueva York.

*Imagen cuaderno, sistema mensaje, modulacion*
*Carrier* se presenta en dos contextos como amplitud modulada (portadora), o el *carrier* que es la operadora telefónica. El significado *carrier* en telecomunicaciones depende del contexto.

Si el voltaje del mensaje aumenta, también aumenta el de la portadora.
$Voltaje_{mensaje}\uparrow  \longrightarrow$
Y si disminuye el mismo caso, disminuye en la portadora

En el osciloscopio:

La señal es 
$A_{min}$  es el punto que, con respecto al origen, tiene el punto mínimo
$A_{max}$  es el voltaje pico de la señal modulada
$A_c$  es un valor referencial. Valor referencia con respecto al origen. $A_C = A_{max}-V_{maxPortadora}$

___
# Porcentaje de Modulación
$$\%m_{AM} = \frac{A_{max}-A{min}}{2A_C}$$
- Submodulación $\rightarrow$ $\%m_{AM} < 100\%$
	- $A_{min} < A_C$
	- Mayor porcentaje de modulación, menor porcentaje del canal
- Modulada al 100% $\rightarrow$ $\%m_{AM} = 100\%$
	- $A_{min} = A_C$
	- Forma mas eficiente de transmitir en AM
- Sobremodulación $\rightarrow$ $\%m_{AM} > 100\%$
	- $A_{min} > A_C$
	- No permite transmitir la información por el traslape

Lo mejor es la submodulación, para tener una tolerancia con el voltaje. Con el voltaje es posible tener variaciones. Si se tiene una modulada al 100%, es posible que llegue a la sobremodulación (prohibida).
En cambio si se tiene una submodulación, y hay una variación de voltaje a mayor, no se llega a la sobremodulación. Por lo que no hay penalizaciones.

>[!done] En las estaciones de radio o TV, las frecuencias deben estar siempre activas. Por esto las líneas de colores o música.

