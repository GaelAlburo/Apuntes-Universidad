Links: [[VLSI]]
___

# Sistemas Digitales y Analógicos

- **Analógico**
	- Un aparato o un instrumento de medida: Que la representa mediante variables continuas análogas a las magnitudes correspondientes
- **Digital**
	- Referente a los números dígitos y en particular a los instrumentos de medida que la expresan con ellos

- **Señal Analógica**
	- Varia de forma continua en un rango de valores. Entre dos valores cualesquiera existe un numero infinito de ellos
- **Señal Digital**
	- Toma valores fijos discontinuos o discretos, llamados dígitos

> [!done] Las señales digitales toman valores discretos, pero no tienen nada que ver con tiempo sino con la magnitud (amplitud). Hay señales que trabajan en tiempo continuo o discreto Las señales digitales no necesariamente son binarias


- El tipo de sistema depende de la clase de señales con las que trabaje

> [!alert] Sistema digital: Se habla de un sistema electrónico digital, formado por componentes eletrónicos que funcionan con señales digitales

- Una señal digital es de menor calidad que una analógica, ya que se realiza una aproximación al transformar de análoga → digital

____
# Clasificación Sistemas Electrónicos

- Sistemas Electrónicos
    - Sistemas Analógicos
    - Sistemas Digitales
        - Combinacionales
        - Secuenciales (tiene memoria)
            - Asíncronos - no tiene señal de reloj
            - Síncronos - tiene señal de reloj. Único que trabaja en tiempo discreto


|          | Continuo                   | Discreto                                             |
| -------- | -------------------------- | ---------------------------------------------------- |
| Continuo | Sistema Analógico Continuo | Sistema Digital Combinacional o Secuencial Asincrono |
|Discreto|Sistema Analogico Discreto|Sistema Digital Secuencial|

___
# Escalas de Integración de C.I.

- SSI - _Small Scale Integration
    - 10 compuertas simples. Inicios 60’s
- MSI - _Medium “ ”_
    - Funciones completas, 10 a 100 compuertas. Mediados 60’s
- LSI - _Large “ “_
    - Miles de compuertas. Finales de los 60’s
- VLSI - _Very Large Scale Integration_
    - Decenas de miles de compuertas. A partir de los 70’s
- ~~ULSI - _Ultra “ “_~~
- ~~GLSI - _Giga “ “_~~
- ~~XLSI - _Extremely Large Scale Integration_~~

___
# Ley de Moore

- Gordon Moore, en 1965 predijo que el numero de transistores que se pueden integrar en un chip crecería exponencialmente.

>[!done] La densidad de transistores en un circuito integrado se duplicara cada dos años

___
# Circuitos Integrados VLSI

- Mayor eficiencia
    - Tamaño
    - Velocidad
    - Consumo de potencia
- Manufactura de sistemas mas simples (económica)
- Mayor confiabilidad

# Familias Lógicas

- **Bipolar** - Primeros. Alta velocidad. Consumen mucha energía
    - RTL
    - DTL
    - etc.
        - Diferentes subfamilias lógicas
- **MOS** - No tan veloces. Consumen poca energía
    - NMOS
        - Estáticas
    - CMOS
        - Dinámicas
- **Bipolar/MOS**
    - BiCMOS

___

Las características eléctricas dependen de la tecnología:

- **Fan-out**
	- Cantidad de compuertas de un mismo tipo que se pueden colocar a una salida de otra compuerta sin sobrepasar los limites de operación
- ***Margen de ruido***
- ***Retardo de propagación***
	- Tiempo en el que se pone un valor en la entrada y se refleja en la salida. Afecta la velocidad máxima a la que puede operar un circuito
- ***Disipación de potencia***
	- Potencia = Voltaje * Corriente (promedio)
	- Se disipa en calor. Se busca elementos que disipen la menor cantidad de energía posible

___
# VLSI

- Son decenas de miles de compuertas en un espacio reducido
- Se fabrican con tecnología CMOS
    - Por la disipación de energía
    - Un transistor amplifica corriente

___
# Circuitos Integrados VLSI

- C.I. comerciales
    - Para aplicaciones especificas (microprocesador de computadora) de alto volumen de fabricación
- ASIC (_**Aplication-Specific Integrated Circuit**_)
    - No se diseñan desde cero, toman plantillas existentes (bloques) y se genera un circuito complejo
    - No son tan eficientes como los C.I. comerciales, ya que toman bloques prefabricados
- Dispositivos Lógicos Programables (PLD)
    - En un C.I. se tienen muchos bloques prefabricados, los cuales se conectan al gusto. (Similar a los ASIC)
    - Los ASIC se crean a nivel de fabrica. Las conexiones de los PLD son a nivel de usuario, lo que reduce de gran manera los costos de producción

___
# Dispositivos Lógicos Programables (PLD)

- **Básicos** - Formados por un arreglo de compuertas AND seguido de un arreglo de compuertas OR
    1. **PROM** - Memoria Programable de Solo Lectura
        - Se programa como se interconectaran las compuertas OR
        - Las compuertas AND son fijas

    2. ***PAL*** - Lógica de Arreglos Programables
        1. Al revés de las PROM
        2. Se programan las AND. Las OR son fijas

    3. ***PLA*** - Arreglo Lógico Programable
        1. Tanto las AND como las OR son programables

- ***Complejos (CPLD)***
	- Estan formados por un conjunto de PLDs simples. Una matriz de conexiones programable y un bloque de control de E/S. Tiene una capacidad de ~50 PLDs
- ***FPGA (Field Programmable Gate Array)***
	- *Combinación* de un Gate Array con un PLD, donde las conexiones son programables por el usuario final
- ***SoC (System on a Chip)***
	- Tendencia a usar tecnologías de fabricación que integran todos o la mayoría de los elementos que componen a un sistema electrónico en un solo C.I.
	- Existen distintos tipos de SoC: ****
		- **SoC/SoC FPGA/PSoC** - Integran un solo C.I. un microprocesador y un FPGA (tendencia actual)

