Links: [[VLSI]]
___

Los dispositivos lógicos programables (PLD - *Programmable Logic Device*) estan formados por un conjunto base de arreglos de compuertas cuyas interconexiones se puedan configurar segun a la aplicacion.

Son un arreglo de inversores y de compuertas AND y OR

___
# Tipos de PLD básicos
Dependiendo de que arreglo programable, se tiene:

1. **PROM** - Memoria Programable de Solo Lectura
2. **PAL** - Logica de Arreglos Programables
3. **PLA** - Arreglo Lógico Programable

___
# PROM
Se considera a las PROM y EPROM como los primeros PLD
Tiene $n$ líneas de entrada (lineas de direccion) y $m$ lineas de salida (tamano de palabra).
El tamano de la memoria se expresa como $p*m$, donde $p=n^n$
La salida de cada compuerta AND corresponde a un mintermino

___
# PAL (Programmable Array Logic)

Permite implantar cualquier función lógica expresada como suma de productos (forma estandar)
Su flexibilidad se incrementa al contar con la posibilidad de tener diferentes configuraciones de salidas, pines bidireccionales, e incluir elementos de memoria (flip-flops)

___
# PLA (Programmable Logic Array)

Es el caso con mayor versatilidad de los PLD, al ser programables tanto el arreglo de compuertas AND como el de compuertas OR
Estos dispositivos no son muy comunes por la dificultad para fabricar, programar y verificar el funcionamiento de dos capas de fusibles programables

___
# Otros PLD

Los mas comunes son:
- **GAL** - Generic Array Logic
Variante de los PAL, son reprogramables y tiene mayor versatilidad de configuraciones y conexiones programables de salida
- **CPLD** - Complex Programmable Logic Device
Formados por grupos de bloques lógicos con interconexiones programables. Cada bloque logico es un PLA, PAL o GAL
- **FPGA** - Field Programmable Gate Array
Conjunto de bloques lógicos programables, interconectables y cuenta con bloques programables de salida

___
# CPLD - Dispositivos Lógicos Programables Complejos

Esta formado por un conjunto de PLD simples, una matriz de conexiones programable y un bloque de control de E/S

- Un CPLD tiene una capacidad equivalente a 50 PLD simples