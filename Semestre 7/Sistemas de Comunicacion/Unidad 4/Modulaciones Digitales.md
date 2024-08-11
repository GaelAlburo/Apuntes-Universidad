Links: [[Sistemas de Comunicaciones]]
___

# Tipos:
- ASK $\rightarrow$ OOK
- FSK
- PSK

De estas están sus variantes **uninivel** y **multinivel**

___
# Uninivel
Quiere decir que lo hacen a nivel de bit. De bit a bit

**OOK (On-Off Keying)**
**ASK (Amplitude Shift Keying)**
**FSK (Frequency Shift Keying)**
**PSK (Phase Shift Keying)**

| 0      | 1      | 1      | 0      | 0      | 1      | 1      | 1      |           |
| ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | --------- |
|        | alto   | alto   |        |        | alto   | alto   | alto   | OOK       |
| bajo   | alto   | alto   | bajo   | bajo   | alto   | alto   | alto   | ASK       |
| baja f | alta f | alta f | baja f | baja f | alta f | alta f | alta f | FSK       |
| 0      | 180    | 180    | 0      | 0      | 180    | 180    | 180    | PSK 0-180 |
| 0      | 45     | 45     | 0      | 0      | 45     | 45     | 45     | PSK 0-45          |


FSK: Por convencion, los ceros se manejan en frecuenias bajas y los unos en frecuencias altas. Se varia la frecuencia
PSK: Frecuencia se mantiene constante. Se cambia el angulo cuando se pasa de 0 a 1, o inversa.
PSK Uninivel no se utiliza

___
# Señalización Digital

> Se encuentran resultados de Big Data. No tomarlos para la clase
> Buscar en ingles: *Digital Signaling*

Representación fasorial de una representación PSK

___
# Multinivel
Representa conjunto de bits
\#Niveles = $2^N$. N: \#Bits por grupo

**Ejemplo con 3 bits:**
\#Niveles = $2^3$ = 8

**Tabla PSK:**

|     | V   | $\theta$ | Símbolo |
| --- | --- | -------- | ------- |
| 000 | 5   | 15       | A       |
| 001 | 5   | 65       | B       |
| 010 | 5   | 105      | E       |
| 011 | 5   | 155      | L       |
| 100 | 5   | 195      | M       |
| 101 | 5   | 245      | N       |
| 110 | 5   | 285      | O       |
| 111 | 5   | 335      | U       | 

Si se quieren mas letras, hay que subir de 3 bits a n bits

___
# QAM (Quadrature Amplitude Notation)

Se diferencian por la amplitud ahora, no el ángulo
>*8-PSK*: PSK de ($2^3=8$) 3 niveles

Si se desacoplan los PSK en la TX y en la Rx, hay que calibrar la antena TX. 
Esto mejora la calidad de la señal, es una forma de encriptar las señales de las telefonías.