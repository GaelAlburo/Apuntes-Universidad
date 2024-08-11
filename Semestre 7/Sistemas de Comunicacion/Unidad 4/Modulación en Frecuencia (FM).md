Links: [[Sistemas de Comunicaciones]]
___

$\uparrow V_{mensaje}$    $\uparrow f_{portadora}$
$\downarrow V_{mensaje}$    $\downarrow f_{portadora}$

___
# F.M. en el Osciloscopio

___
# Relación F.M. - P.M.

- Es fácil generar señal FM, pero no transmitirla
- Una señal PM es difícil para generarla, pero es muy simple para transmitir

**Proceso para transmitir F.M.**

___
# Índice de Modulación
m estilizada

$$m_{F.M.}=\frac{\Delta f_m}{fp}$$
$\Delta f_m \rightarrow$ Siempre esta expresado en términos de frecuencia, ya que esta normalizado. Originalmente es de [Hz]/[V]. Esta no es la frecuencia del mensaje, es la frecuencia que se requiere para llegar de un voltaje a otro

#### Ejemplo 1:
15 $[kHz] \rightarrow$ 21 $[kHz]$
$\Delta f = 6 [kHz]$
$\Delta f_m = \frac{6 [kHz]}{3 [V]} = 2 [kHz/V] \rightarrow$ Siempre ira normalizado
$$\Delta f_m = 2[kHz]$$
#### Ejemplo 2:
**Datos:**
$f_m=100[Hz]$
$f_p=1.333[kHz]$
$P_{portadora}=100[kW]$
$R_{eq}=130[\ohm]$

10 $[kHz] \rightarrow 12 [kHz]$  Rango de frecuencias
$\Delta f = 2 [kHz]$

2 $\rightarrow$ 3    Voltaje
$\Delta V = 1 [V]$
$$\Delta f_m = \frac{\Delta f} {\Delta V} = \frac {2 [kHz]} {1 [V]} = 2 [kHz / V] = 2 [kHz]$$
$$m_{F.M.} = \frac{2[kHz]}{1.333[kHz]} = 1.5$$
___
# Tablas de Bessel
|            | J_0 | J_1 | ... | Voltaje de las componentes espectrales (NORMALZADAS) |
| ---------- | --- | --- | --- | ---------------------------------------------------- |
| 0.25       |     |     |     |                                                      |
| 0.5        |     |     |     |                                                      |
| ...        |     |     |     |                                                      |
| $m_{F.M.}$ |     |     |     |                                                      |


> [!done] El ancho de banda teórico de F.M. es **infinito**

Las tablas de Bessel nos dan las componentes significativas o características de F.M.
Aun existen un montón de componentes espectrales, pero se desprecian

____
**(Continuación Ejemplo 2)**

Para desnormalizar los valores de la tabla de Bessel:
$P = \frac{V^2}{R} \rightarrow V=\sqrt{PR}$
$V=\sqrt{(100k)(130)} = 3605.55 [V]$

En la tabla, para $m_{F.M.} = 0.5$, el valor de $J_0$ es 0.51
Se desnormaliza: $J_0=0.51(3.6k)=1836[V]$

$J_1=(0.56)(3.6k)=2016$
$J_2=(0.23)(3.6k)=828$
$J_3=(0.06)(3.6k)=216$
$J_4=(0.01)(3.6k)=36$

***(Espectro de F.M.)***

