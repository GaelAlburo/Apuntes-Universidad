Links: [[Temario Microprocesadores]]
___
Dato Entrada, Instruccion -> microprocesador -> Dato Salida

fetch -> decode -> execute -> save -> fetch -> ... : Ciclo de instruccion

# Partes Básicas Microcomputadora
- Microprocesador
	- ALU
	- U.C.
	- Registros
- Memoria
	- RAM
	- ROM
- Sistemas I/O

## Memoria
Contiene las instrucciones para la ejecucion del programa y los datos con los que trabaja.
Un programa es un grupo de instrucciones que le indican a la microcomputadora que hacer con los datos

## ALU
Hace operaciones aritmeticas y logicas requeridas por las rutinas del programa.
Genera los bits de estado o codigos de condicion (STATUS bits, Condition codes), que le dan la capacidad de tomar decisiones 

## Sistemas I/O
Controlan la comunicación entre la microcomputadora y los dispositivos externos.
La microcomputadora recibe datos de información de *estado* del exterior, por ejemplo de sensores, unidades de almacenamiento, etc.

La microcomputadora produce salidas que depende del programa y los datos.
Estas salidas pueden ser datos, almacenar, o pulsos eléctricos que activan procesos físicos.

## Unidad de Control
Formada por componentes electrónicos como flip-flops, registros, etc. para regular todos los procesos en la ejecución del algoritmo indicado mediante el programa
Genera la secuencia adecuada de eventos que ocuren


## Unidad de memoria
Todas las micro requieren de memoria 
El tipo de memoria depende del tipo de material con el que se construye
La memoria estatica esta hecha con flip-flops
La dinámica con capacitores
Los bits estan organizados en palabras de 4,6,8,16 bits



El PC (*Program Counter*) apunta a la memoria ROM


El *fetch* toma el valor de PC, lo busca en el registro MAR, que esta conectada mediante el bus de direcciones a la memoria ROM.
Una vez se tenga la instrucción en la direccion marcada por el PC, esta entra al Registro de Instrucciones y Decodificador. Iniciando el proceso de *decode*
La instruccion `LOAD` depende de otro valor, que sera el valor siguiente en la memoria. Por lo que en *execute* se aumenta en 1 el PC, apuntando ahora al valor 80 en memoria.
Finalmente se realiza el *save*.

El ciclo fetch-decode-save-execute siempre se ejecutara completo en cada una de las instrucciones. Terminando usualmente al incrementar en 1 el PC.

