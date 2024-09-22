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

