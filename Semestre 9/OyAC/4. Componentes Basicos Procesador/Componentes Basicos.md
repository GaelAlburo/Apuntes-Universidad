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