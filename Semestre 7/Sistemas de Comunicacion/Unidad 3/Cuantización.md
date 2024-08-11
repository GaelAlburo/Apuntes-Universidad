Links: [[Sistemas de Comunicaciones]]
___

- Entre mas niveles de cuantización mejor
- Pero en general, el numero de niveles se dará en términos de $log_2(x)$, por el binario                                                                                                                                                                    t
- N bits $\rightarrow$ # Niveles = $2^N$
**Cuantizar considerando al menos 14 niveles**:
	$log_2(14)=3.x ~= 4$

Hay 2 tipos:
- Uniforme
- No uniforme
___
## Cuantización Uniforme
Diagrama de Cuantización
- Determina el promedio de 
___
## Cuantización No Uniforme
Diagrama de Cuantización

Se crearon varias leyes:
- Ley $\mu$ $\rightarrow$ Observancia América
- Ley A $\rightarrow$ Observancia Europea
- Ley J$\rightarrow$ Observancia Japonesa y aledañas

### Ley $\mu$
$$|\mho| =\frac {log(1+M|m|)} {log(1+\mu)}$$
	$\mu \rightarrow$ Valores de la tabla de $\mu$
	$m \rightarrow$   Valor del mensaje
### Ley A
$$
\mho = \begin{cases} 
  \frac {A|m|} {1+logA}  &\text{si } 0 <= m <= \frac 1 A \\  
   \frac {1+log(A |m|)} {1+logA} &\text{si }  \frac 1 A <= m <= 1 
\end{cases}
$$
	$A \rightarrow$ Valores de la tabla de la Ley A
	$m \rightarrow$ Nivel del mensaje
___
## Técnicas de Muestreo
- Redondeo
	- Mejor opción, pero genera un paso extra, para definir el umbral, lo que toma mas recursos
- Truncado
	- Superior
	- Inferior
___
## Ruido de Cuantización
$R.C.=|V_{real}-V_{cuantizado}|$
- Es un error
___
### Estudio de Caso
Sea la señal (foto) con un voltaje máximo de 7[V] realiza la cuantización de la señal con 3 bits
- Se utilizara las técnicas de muestreo
	- RC. con el valor redondeado

$\# Niveles = 2^N = 2^3 = 8 \rightarrow$    Se usa 3 por los 3 bits del problema 
$V_{nivel} = \frac {V_{max}} {\# Nuevo - 1} = \frac 7 {8-1} = 7[V]$

|Valor real| Redondeo|Truncado Inferior|Truncado Superior|RC.|
|---|---|---|---|---|
|2.38 |2 |2|3|0.38|
|1.93|2|1|2|0.07|
|4.76|5|4|5|0.24|
|1.07|1|1|2|0.07|
|5.17|5|5|6|0.17|


___
Códec: Algoritmos   de transformación de analógico a digital
___