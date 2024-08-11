Links:
___

# Switch (Conmutador)
Es el dispositivo digital lógico de interconexión de equipos que trabaja en la capa de enlace de datos del modelo OSI

## Tipos
- **Switches de escritorio o *desktop***
	Es el mas basico y se usa, habitualmente, en el ámbito domestico o en pequenas empresas

- **Switches perimetrales no gestionables o no administrables**
	Son switches que se utilizan para constituir redes de pequeño tamaño de prestaciones medias

- **Switches perimetrales gestionables o administrables**
	Es necesario que estos ofrezcan características avanzadas de configuración y gestion

- **Switches troncales de prestaciones medias**
	Están diseñados para formar el núcleo troncal de una red de tamaño medio, proporcionando altas prestaciones y funcionalidades avanzadas

- **Switches troncales de prestaciones altas**
	Se caracterizan por su gran modularidad. Se usan en grandes redes corporativas o de campus, entre otros.


El **switch tiene la capacidad de aprender y almacenar**, por si solo, direcciones de red de dispositivos alcanzables mediante sus puertos.

A diferencia de un hub o concentrador, el switch permite que la **información dirigida a un dispositivo vaya de un puerto origen hacia un puerto destino**.

___
## Modos de Transmisión del Switch

1. **Store and Forward**
Guardan cada trama en un buffer antes del intercambio de información hacia el puerto de salida. Mientras la trama esta en el buffer, el switch calcula el CRC y mide el tamaño de la misma

2. **Cut Though**
Este tipo es mucho mas rápido. En cuanto la trama llega el switch, este lee la cabecera del frame. Obtiene de esta los 8 bytes de preámbulo y la dirección MAC con 6.
En cuanto obtiene esta información reenvía rápidamente por el puerto adecuado

____
## Tipos de conexión de switches (interconexión)

- Cascada
- Apilamiento

___
# Power Over Ethernet (Puerto PoE)
Es una tecnología que permite el envio de alimentación eléctrica junto con los datos en el cableado de una red Ethernet

El estándar IEEE 802.3af en 2003 y en el ano 2009 se publico una revision y ampliación en el estándar IEEE 802.3at

Un dispositivo que soporte PoE obtendrá tanto los datos como la alimentación por el cable de red Ethernet.

___
# NIC (Tarjeta de Red)

Es un componente de hardware importante que se utiliza para proporcionar conexiones de red

La tarjeta de red, tambien conocida como placa de red, adaptador de red, adaptador LAN, Interfaz de red fisica o por sus siglas en ingles, *Network Interface Card* o *Network Interface Controller*

Parametros necesarios para funcionar en red local
a) Direccion IP
b) Mascara de red

Parametros necesarios para salir a internet
a) Direccion IP
b) Mascara de red
c) Gateway
d) DNS

____
## Direcciones MAC
Direcciones físicas guardadas en una memoria ROM contenida en la NIC
- No se pueden modificar
- Deben ser únicas por equipo
- Números asignados por la IANA
- Los 3 primeros bytes son asignados según el fabricante
- Los 3 últimos bytes los asigna el fabricante
- No se puede asignar `00 00 00 00 00 00` ni `FF FF FF FF FF FF`
- Es un identificador de 48 bits (6 bloques de dos caracteres hexadecimales (8 bits))

___
# Bridge-Puente

Puente de red (*bridge*) es el dispositivo de interconexión de redes de datos que opera en la capa 2 del modelo OSI

Interconecta segmentos de red (o divide una red en segmentos) haciendo la transferencia de datos de una red hacia otra con base en la dirección física de destino de cada paquete

El termino *bridge* responde a un dispositivo que se comporta de acuerdo al estándar IEEE 802.1D
