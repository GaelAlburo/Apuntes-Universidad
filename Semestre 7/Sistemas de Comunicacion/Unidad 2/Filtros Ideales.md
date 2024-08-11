Links: [[Sistemas de Comunicaciones]]
___

- Pasobajas (*LPF - High Pass Filter*)
- Pasoaltas (*HPF*)
- Pasobanda (*BPF*)
- Supresor de Banda (*SBF*)
- Paso todo (*APF*)
- Paso nada (*NPF*)
---
## LPF (Pasobajas)
![[LPF_grafica | 300]]

BW - [0-F]
$x = \begin{cases}`  
   `a &\text{if } b \\`  
   `c &\text{if } d`  
\end{cases}$

$$  
\begin{align}  
1 == 1 \\  
2 == 2  
\end{align}  
$$
___
## HPF - Pasoaltas
BW - $[f_1 - \infty]$ 
	 - $f_1$
___
## BPF - Pasobanda

BW - $[f_1 - f_2]$
	 - $(f_2 - f_1)$
- Se recomienda especificar ambas rango (1ra) y la diferencia de frecuencias
___
## SPF - Supresor de Banda
.	 \- $[0, f_1]$
	 \- $[f_2, \infty]$
BW - 
	. - $f_2 - f_1$ -> Suprimido
___
## APF - Pasotodo
- Modifica las componentes espectrales, mejorandolos (idealmente)
	- Moduladores de voz, ecualizadores
___
## NPF - Pasonada
- Se inyectan componentes espectrales de muy alta potencia
- Cancelando todas las componentes, cancelando la señal
- No dejando pasar nada
	- Jammers

___
## Definición

> [!check] Un filtro es un dispositivo que modifica las componentes espectrales de un sistema para mejorarlo

