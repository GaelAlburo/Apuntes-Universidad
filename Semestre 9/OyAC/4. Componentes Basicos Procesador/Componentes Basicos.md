> [!info] Usaremos un secuenciador basico normal con XOR

![[Pasted image 20240919072752.png|center]]

 1) **Unidad de Control de la Computadora (UCC)** - Se encarga de enviar las señales de control a los demás elementos de la computadora.
	 - Secuenciador Básico
	 - Memoria ROM
 2) **Unidad de Procesos Aritméticos (UPA)** - En ella se realizan todas las operaciones lógico aritméticas.
	 - ALU
	 - Registros Acumuladores A y B
 3) **Unidad de Control de Programa (UCP)** - Calcula la dirección de la siguiente instrucción a ser ejecutada. Guarda el estado actual del procesador.
	 - Registro Contador PC
	 - Registro Contador AP
 4) **Unidad de Control de Interrupciones (UCI)** - Se encarga del manejo de las interrupciones internas y externas.
	 - Registro de Interrupciones
	 - Flip Flop RS
 5) **Unidad de Registros Internos** - Conjunto de registros capaces de almacenar datos, direcciones de memoria externa y códigos de operación
	 1) Acumuladores: Datos, direcciones
		 - Registros A y B
	2) Contadores: Almacena direcciones, y en ciertos casos datos
		- PC, AP, X, Y, RA
	3) Registro de Banderas: Almacena banderas que genere el procesador
		(*Condition Code Register (CCR)*, Registro de estados)


___
El salto de transformacion es la decodificacion de las instrucciones

Las salidas efectivas ahora son las lineas de control (UP9..UP0 - C2,C1,C0)

___
# Unidad de Procesamientos Aritmeticos

- Operaciones permitidas:
	- A+B
	- B+D
	- A+0
- Operaciones no permitidas:
	- A+A
	- 0+0

![[Pasted image 20240924071456.png|center]]

- Como el bus de datos interno es de 16 bits, nuestra salida del UPA se duplica, teniendo de 8 bits a 16.
	- Por ejemplo, si 7+5 =12 = 0Ch. Se duplica -> 0C0Ch

- El contador de 3 bits es util para ciclos. Su salida `FC` sera 1 solo cuando el contador haya llegado a su valor maximo.

- DUPA: Deshabillita la carga en el registro Yupa
- OEUPA: Habilita la lectura de Yupa

- Banderas generadas por UPA:
	- Acarreo
	- Medio acarreo
	- Signo
	- Overflow
	- Cero

___
# Registros Acumuladores

![[Pasted image 20240926075027.png|center]]

- Transeiver C llega al UPA
- El DECODIFICADOR habilita alguno de los TRANSEIVER, solo puede estar 1 activo
- La linea W habilita la carga de datos
	- 0 - Escribe
	- 1 - Lee

![[Pasted image 20240926075741.png|center]]

Salidas del ACC: Banderas Z y N

___
# Registros Contadores

![[Pasted image 20241010072414.png|center]]

Se tienen 5 registros contadores:
- Y
- X
- RA
- AP
- PC
Estos tienen la misma arquitectura. Tanto X como Y tienen las mismas lineas de control. Solo va a estar activo el registro Y o el X, no los dos a la vez.

No se puede pasar la parte baja de un registro a la parte alta de otra, o viceversa

# Registro de Estados / Banderas / CCR (*Condition Code Register*)

Contiene los valores de ocho variables que indican el estado de los distintos componentes de la arquitectura. Estos valores pueden venir de alguno de los elementos que integran a la arquitectura, o bien, del bus de datos.

- C: Bit de acarreo/borrow. Generada por la UPA en sumas y restas

- V: Bit de sobreflujo (overflow). Se usan numeros con signo

- Z: Bit de cero. Indica si el resultado de la última operación que se realizó en la UPA, o el valor guardado en alguno de los registros (contadores, acumuladores), es igual a cero. 

- N: Bit de negativo. Indica el signo del resultado de la UPA, o del valor guardado en alguno de los registros. 

- I: Bit de interrupción I. Habilita el dispositivo I. Habilita con un cero, y deshabilita con un uno, las interrupciones conectadas a la línea IRQ. 

- H: Bit de medio acarreo. Acarreo de 4 bits menos significativos de la UPA. Se utiliza en operaciones donde se usan números con formato BCD. 

- X: Bit de interrupción X. Habilita el dispositivo X. Habilita con un cero, y deshabilita con un uno, las interrupciones conectadas a la línea XIRQ. 

- S: Bit de stop. Pone al microprocesador en bajo consumo de energía. Pone en stand by al procesador


El bit mas significativo indica el signo:
	1110 -> Representa 14, o si tomamos en cuenta el signo, es un -2
Todos los numeros negativos siempre estan en complemento a 2 (de aqui sale el -2 de 14)

>[!info] Si la suma de 2 numeros positivos muy grandes genera un numero negativo, por lo tanto hay overflow. Y viceversa

Las operaciones las define el programador, no siempre se toma en cuenta el signo para las operaciones.

![[Pasted image 20241015073542.png|center]]

Las líneas d7 a d0 conectan al registro de banderas con el bus de datos. Los circuitos tres estados, en conjunto con la señal HB , aíslan o conectan el registro de banderas al bus de datos interno.

Las líneas CC, CV, CZ, CN, CI, CH, CX y CS controlan los relojes de los flip-flops asociados a las banderas.

Las líneas B9 a B0 controlan la selección de los multiplexores.
Por ejemplo para la bandera de Z, si B5B4B3=000 se selecciona la bandera de Z de la UPA, si B5B4B3=001 la del acumulador A. Para seleccionar el resto de las banderas se procede de manera similar

#### Ejercicios
1- PCbaja <- CCR

![[Pasted image 20241015081735.png|center]]

R  S   Q
0  0    No cambia
0  1    1 - Modo set  (en espera de una interrupcion)
1 0    0 - Modo reset
1 1    No deseada

1. Los flip flops se ponen en modo set
2. Habilita la atencion a interruptores
3. Escuchar las interrupciones de los dispositivos I y X
	1. Cuando exista una interrupcion, los flip flop se ponen en modo reset
4. Cuando se termine de ejecutar la interrupcion los Flip Flop deben regresar a modo set