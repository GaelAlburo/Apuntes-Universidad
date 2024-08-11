Links: [[Temario Microprocesadores]]
___
- Conjunto de Instrucciones
- Repertorio de instrucciones

# Set de Instrucciones
Especificación detallada de las acciones que un microprocesador puede entender y ejecutar
Incluye los comandos implementados por un diseño particular de un microprocesador

Incluye los tipos de datos nativos, los mnemónicos, los registros, la arquitectura de memoria (mapa de memoria), el bloque de entradas/salidas, interrupciones, y los elementos visibles para el programa

# Conjunto de Instrucciones
- CISC (*Complex Instruction Set Computer*)
- RISC (*Reduced Instruction Set Computer*)
- SISC (*Simple Instruction Set Computer*)
	- Orientados a procesamiento de tareas en paralelo
- ASIC (*Application Specific Integrated Circuit*)

# Características del Set de Instrucciones
- COMPLETO
	- Debe ser posible implementar un programa usando una cantidad limitada de memoria y tiempo
- EFICIENTE
	- Las funciones ,as utilizadas deben realizarse con la minima cantidad de instrucciones
- REGULAR
	- Debe ser simétrico (si hay corrimiento a la derecha, debe haber uno a la izquierda) y ortogonal (se deben poder combinar todas las operaciones con todos los tipos de datos y modos de direccionamiento)
- COMPATIBLE
	- El set de instrucciones debe incluir el set de modelos antiguos como un subconjunto

# Tipos de Instrucciones

Un conjunto de instrucciones muy simplificado origina programas muy complejos e ineficientes

Un conjunto de instrucciones muy complejas necesita de sistemas de control de HW sofisticado y costoso

Se debe hacer un compromiso entre la simplicidad del HW y SW

- Instrucciones de Transferencia de Datos
- Instrucciones Aritmeticas
- Instrucciones Logicas
- Instrucciones de Control del Flujo del Programa (bifurcaciones, bucles, procedimientos, etc.)
- Instrucciones de Entrada y Salida

## Instrucciones de Transferencia de Datos
Aparecen como MOV o LOAD en el conjunto de instrucciones

Su funcion es copiar sin borrar el registro de origen
Requieren que se especifique el origen o fuente, al igual que el destino donde se copia

La especificacion de la instruccion variara segun el lugar del origen y destino:
- Registros del microprocesador
- Memoria
- Parte alta de la pila

Si el acceso es una direccion de memoria, es una **forma explicita**
Si se trata de la parte alta de la pila o acumulador, etc., se usa una **forma implicita**
Existen variantes





38400 - Pic