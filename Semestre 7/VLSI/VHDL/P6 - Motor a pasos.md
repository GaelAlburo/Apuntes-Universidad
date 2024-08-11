Links: 

### Valores de sm
when sm0 => motor <= "0000";
when sm1 => motor <= "1000";
when sm2 => motor <= "1100";
when sm3 => motor <= "0100";
when sm4 => motor <= "0110";
when sm5 => motor <= "0010";
when sm6 => motor <= "0011";
when sm7 => motor <= "0001";
when sm8 => motor <= "1001";
when sm9 => motor <= "1010";
when sm10 => motor <= "0101";
when others => motor <= "0000";
___
### Fase Simple - FH=00
- Solo utiliza estados *sm1, sm3, sm5 y sm7*
**UD = 0**
- *sm1, sm3, sm5, sm7*
**UD = 1**
- *sm7, sm5, sm3, sm1*

|Pasos|M3|M2|M1|M0|
|---|---|---|---|---|
|Paso 1| 1|0|0|0|0|
|Paso 2|0|1|0|0|
|Paso 3|0|0|1|0|
|Paso 4|0|0|0|1|
___
### Doble Fase - FH=01
**UD = 0**
- *sm8 $\rightarrow$ sm6 $\rightarrow$ sm4 $\rightarrow$ sm2 $\rightarrow$ sm8 $\rightarrow$ ...*
**UD = 1**
- *sm2 $\rightarrow$ sm4 $\rightarrow$ sm6 $\rightarrow$ sm8 $\rightarrow$ sm2 $\rightarrow$ ...*

|Pasos|M3|M2|M1|M0|
|---|---|---|---|---|
|Paso 1| 1|1|0|0|
|Paso 2|0|1|1|0|
|Paso 3|0|0|1|1|
|Paso 4|1|0|0|1|
___
###  Medio Paso - FH=10
**UD = 0**
- *sm8 $\rightarrow$ sm7 $\rightarrow$ sm6 $\rightarrow$ sm5 $\rightarrow$ sm6 $\rightarrow$ sm5 $\rightarrow$ ...*

|Pasos|M3|M2|M1|M0|
|---|---|---|---|---|
|Paso 1|1|0|0|1|
|Paso 2|0|0|0|1|
|Paso 3|0|0|1|1|
|Paso 4|0|0|1|0|
|Paso 5|0|0|1|1|
|Paso 6|0|0|1|0|
|Paso 7|0|0|1|1|

**UD = 1**
- *sm2 $\rightarrow$ sm3 $\rightarrow$ sm4 $\rightarrow$ sm5 $\rightarrow$ sm4 $\rightarrow$ sm5 $\rightarrow$ ...*

|Pasos|M3|M2|M1|M0|
|---|---|---|---|---|
|Paso 1| 1|1|0|0|
|Paso 2|0|1|0|0|
|Paso 3|0|1|1|0|
|Paso 4|0|0|1|0|
|Paso 5|0|1|1|0|
|Paso 6|0|0|1|0|
|Paso 7|0|1|1|0|

___
### Motor Bipolar - FH = 11
**UD = 0**
- *sm4 $\rightarrow$ sm10 $\rightarrow$ sm8 $\rightarrow$ sm9 $\rightarrow$ sm4 $\rightarrow$ sm10 $\rightarrow$ sm8 $\rightarrow$ sm9 $\rightarrow$ sm4 $\rightarrow$ ...*

|Pasos|M3|M2|M1|M0|
|---|---|---|---|---|
|Paso 1|0|1|1|0|
|Paso 2|0|1|0|1|
|Paso 3|1|0|0|1|
|Paso 4|1|0|1|0|
|Paso 5|0|1|1|0|
|Paso 6|0|1|0|1|
|Paso 7|1|0|0|1|
|Paso 8|1|0|1|0|

**UD = 1**
- *sm4 $\rightarrow$ sm9 $\rightarrow$ sm8 $\rightarrow$ sm10 $\rightarrow$ sm4 $\rightarrow$ sm9 $\rightarrow$ sm8 $\rightarrow$ sm10 $\rightarrow$ sm4 $\rightarrow$ sm9 $\rightarrow$ ...

|Pasos|M3|M2|M1|M0|
|---|---|---|---|---|
|Paso 1|0|1|1|0|
|Paso 2|1|0|1|0|
|Paso 3|1|0|0|1|
|Paso 4|0|1|0|1|
|Paso 5|0|1|1|0|
|Paso 6|1|0|1|0|
|Paso 7|1|0|0|1|
|Paso 8|0|1|0|1|

___
![[Pasted image 20231004171216.png | 300]]
![[Pasted image 20231004171651.png | 300]]
![[Pasted image 20231004171846.png|400]]
![[Pasted image 20231004172043.png|400]]
![[Pasted image 20231004172823.png]]
*La ultima es para un motor bipolar, las primeras 3 para un motor unipolar*
Fase simple - Solo se activa una bobina a la vez
Fase doble - Energiza dos bobinas a la vez
Medio paso - Alterna las dos secuencias anteriores