Es el proceso de conectar diferentes componentes o modulos de HW en un sistema inegrado, de manera que puedenncomunicarse y trabajar juntos

Una interconexion bien disenada es critica para la confibailidad y el rendimiento de los sitemas embebidos.

Opciones de interconexion de Raspberry Pi:
- Interfaz de camara
- Interfaz de pantalla: HDMI, DSI y VGA
- Conectividad Inalambrica: Wi-Fi y Bluetooth
- Variedad de puertos E/S

# GPIO
Pines de E/S de proposito general para conectar distintos componentes y modulos de HW
No utilizan protocolos especificos de interconexion, son de proposito general

Existen distintas bibliotecas y macros para programar el GPIO

Interconexiones:
- SPI
- IIC o I2C
- UART
- PWM

# SPI (*Serial Periphreal Interface*)
Protocolo de comunicacion serie sincrono que se usa para transferencia de datos entre dispositivos

Se basa en una arquitectura de comunicacion maestro/estado, donde la RaspberryPi es el maestro y el periferico o sensor es el dispositivo esclavo.
Utiliza cuatro lineas de senal para la comunicacion:
- MOSI - Usada para transmision de datos del dispositivo maestro al dispositivo esclavo
- MISO - Se usa para transmision de datos del esclavo al maestro
- SCLK - Usada para sincronizar la transferencia de datos entre dispositivos
- SS - 

- Es de modo full duplex
- Rapido y eficiente ya que no tiene sobrecarga adicional 

Para utilizar el SPI se puede usar la biblioteca de Python `spidev`.
Para usarse es necesario habilitar el servicio SPI en la RaspberryPi