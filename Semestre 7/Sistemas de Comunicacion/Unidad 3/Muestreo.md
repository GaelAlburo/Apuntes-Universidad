Links: [[Sistemas de Comunicaciones]]
___

Existen dos tipos de muestreo:
- Muestreo Ideal (Uniforme)
- Muestreo Practico (Natural)
___
## Muestreo Ideal (Uniforme)
Se tomaran muestras de la señal analógica, por un tren de pulsos

Periodo de muestreo -> Tiempo entre muestra y muestra, siempre será igual

$S(t)=\sum ^i_{n=-i} \delta (t-nT)$
	$T: \text{Periodo de Muestreo}$
$S(t)=\frac {2\pi}{T} \sum ^i_{k=-i} \delta(w-kw_s)$
	$w_s: \text{Frecuencia de Muestreo}$
	
$x(t)\leftrightarrow X(f)$
$x_s(t)=X(t)*s(t)$
$X_s(w)=\frac 1 {2 \pi} X(w)*s(w)$
$X_s(w)=\frac 1 T \sum ^i_{n=-i}x_0(w-kw_s)$

- En el dominio de la frecuencia no hay perdida de información, de hecho, se agrega información
- Para recuperar la señal original se utiliza un filtro pasa bandas

- Este caso sigue siendo ideal, porque no existen las deltas de Dirac y  además por el filtro cuadrado
	- En el dominio del tiempo, si se tiene un pulso cuadrado, en el dominio de la frecuencia es como ondas

___
Existen 3 escenarios para
1. **Alliasing**: Se tiene la componente original, y las componentes espectrales (espurias) están sobrepuestas
	- La frecuencia de muestreo debe ser 2 veces menor a la frecuencia de muestreo
		$f_m < 2 f_0$

2. La componente fundamental esta junta a sus espurias, se le aplica una aproximación del filtro ideal
	- Se agrega ruido a la señal original
		$f_m = 2f_0$

3. La componente original esta separada de sus componentes espectrales espurias, y se aplica una aproximacion del filtro
	- Aplica si la frecuencia de muestreo es mayor o igual a 2 veces la frecuencia de oscilación
		$f_m >= 2f_0$

### Teorema de Nyquist-Shannon
	$f_m >= 2f_0$

Se ha descubierto empíricamente la sig. relación para obtener el teorema de Nyquist-Shannon
	$f_m = 8f_0 \rightarrow \text{Frecuencia de muestreo decente}$

___
## Muestreo Practico
Si se multiplica una señal analógica por un tren de pulsos se obtendrá la señal muestreada con una señal de tren pulsos

$A(\frac {\tau} T)$

Implicaciones:
- Teniendo un tren de pulsos con un ciclo de trabajo muy pequeño (ideal), se tendrá una gran cantidad de componentes espectrales                                                                                                                                                                                     
	- Generalmente se emplea un ciclo de trabajo de $\frac 1 {10}$
- Entre mas grande la frecuencia de muestreo, mas grande será el ancho de banda 