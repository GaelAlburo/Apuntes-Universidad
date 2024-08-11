Links: [[Temario Redes]]
___

- Se encarga de proporcionar una comunicacion fiable y eficiente entre dos dispositivos
- Envió de bloques de información
- Control de la transferencia de información
- Detección, corrección y recuperación de errores

___
Contiene dos subcapas:

- Subcapa LLC: *Logical Link Control* - Enlace Lógico delos datos
- Subcapa MAC: *Media Access Control* - Control de acceso al medio

| RED        |
| ---------- |
| LLC - MAC  |
| **FISICO** |

# Subcapa LLC
Para conseguir que la transmisión se convierta en una comunicación, es necesario controlar y gestionar el intercambio de datos entre las estaciones participantes

Existen 6 servicios o requisitos en esta subcapa:

1. Sincronización de la trama
2. Control de flujo
3. Control de errores
4. Direccionamiento
5. Datos + información de control en el mismo enlace
6. Gestion de enlace

___
## Sincronización de Tramas

#### Transmisión Síncrona
- Envía una trama de datos o un conjunto de caracteres, la cual configura un bloque de información empezando por un conjunto de bits de sincronización (SYN)
- Termina con otro conjunto de bits de final con un bloque (ETB)

- Los datos fluyen en modo duplex completo en forma de bloques o tramas
- El emisor sabe donde comienza el nuevo byte (ya que no hay ningún huevo entre los datos)
- Destaca por contar con un alto rendimiento en la transmisión
- Es una transmisión apta para operar a altas velocidades
- El flujo de datos es mucho mas regular.

	**Requisitos:**
- Función en torno a la transmisión y el envio de un grupo de caracteres en un flujo continuo de bits
- Tanto el transmisor como el receptor van a proveer una señal de reloj, la cual se emplea para establecer la velocidad de transmisión de los datos

	**Ejemplos:**
- WhatsApp
- Instagram
- Skype
- Messenger
- Telegram
- Videoconferencias

>[!info] La sincronización depende de dispositivos y de protocolos

>[!done] La sincronización síncrona nos permite la comunicación full duplex


#### Transmisión Asíncrona
- No hay ningún tipo de relación temporal entre la estación que transmite con la que recibe
- Los datos fluyen en modo half duplex
- El ritmo en el que la información se presenta al destino no debe coincidir con el de la fuente
- No es necesario que se garantice un ancho de banda (determinado)
- El receptor no va a conocer con absoluta precision en que momento va a recibir un mensaje
- Los caracteres que se transmiten se delimitan con un bit de información que se conoce como cabecera o arranque

	**Ejemplos**
- Correo electronico
- Foros de discusión
- Blogs
- Publicaciones en redes sociales
- YouTube (se sube un video y no debes estar conectado en ese momento para verlo)
- Grupos de noticias
- Wikis

____
## Control de Flujo
- Necesario para no saturar al receptor de uno a mas emisores
- Utiliza mecanismos de retroalimentación
- Suele ir unido a la correcion de errores
- Detectar errores a la hora de enviar tramas al receptor e intentar solucionarlos
- Se realiza mediante diversos tipos de códigos del que hay que resaltar el CRC (código de redundancia cíclica) y Suma de verificación (*checksum*)

Existen dos protocolos para lograr el control de flujo:
- Unilateral: Parada y Espera (*Stop and Wait*)
- Bilateral: Ventana deslizante

La transmisión en las redes se lleva a cabo de 3 maneras:
- **Simple - *Simplex***
	- El emisor envía y el receptor solo escucha. El emisor no recibe respuestas
- **Half-duplex - Semi duplex** (Unilateral - Parada y espera)
	- Solo un dispositivo a la vez puede enviar y recibir
- **Full-duplex - Duplex** (Bilateral - Ventana deslizante)
	- Ambos dispositivos pueden enviar y recibir información al mismo tiempo. Aumenta velocidad


#### Protocolo Parada y Espera
- Protocolo muy sencillo
	- Su complejidad y recursos necesarios son pocos
- Pertenece a los de tipo ARQ (*Automatic Repeat reQuest*)
- Envía una trama y espera a obtener una respuesta (mensaje de confirmación)

Los mensajes de confirmación pueden ser:
- ACK (*Acknowledgment*): Mensajes positivos que confirman una recepción correcta
- NACK (*Negative Acknowledgment*): Mensajes negativos, indican errores en la información y es necesaria una retransmisión

>[!info] Se usaran en redes que usen 

>[!done] Hay aplicaciones que pueden utilizar dos protocolos. El usuario no conoce cuales implementa



#### Protocolo Ventana Deslizante
- Protocolo de tipo ARQ (*Automatic Repeat reQuest*)
- Comunicación Full-duplex
- En este protocolo A puede enviar $n$ tramas sin recibir confirmacion y B puede aceptar y almacenar $n$ tramas
	- Estas tramas están numeradas para identificar las confirmaciones
	- De esta manera B confirma las tramas enviando el numero de tramas que espera recibir

Existen dos tipos de retransmisión cuando se obtiene un NACK
- Retransmisión Selectiva: Debe usar buffers, almacenamiento, donde se detecte cual es la trama incorrecta y solo se reenvie esta, no todas las demas
- Retransmisión No Selectiva: Cuando se recibe un NACK, todas las tramas se vuelven a reenviar

**Requisitos:**
En la ventana deslizante el tamaño mínimo de la ventana debe ser de $2a+1$ para que no se desperdicie el canal

>[!done] Este protocolo se emplea para grandes distancias. Por ejemplo en enlaces satelitales

____
# Ejercicios
Emeplee el protocolo parada y espera para indicar cual es el tiempo total de transmision (ttt) de la trama y se cuenta con la siguiente informacion:
- v = 50 Kb/s
- l = 1000 bits

Emeplee el protocolo parada y espera para indicar cual es el tiempo total de transmision (ttt) de la trama y se cuenta con la siguiente informacion:
- v = 38 Kb/s
- l = 521 bits

Emeplee el protocolo parada y espera para indicar de que tamano es la trama si el tiempo total de transmision es de 0.10 segungos y la velocidad es de 12 Kb/s (kilobits por segundo)

Emeplee el protocolo parada y espera para indicar cual es la utilizacion del canal con los siguientes datos:
- v = 50 Kb/s
- retardo de propagacion = 250 ms (milisegundos)
- trama (l) = 1000 bits


Cual es la utilizacion del canal utilizando el protocolo de parada y espera con la siguiente informacion:
- v = 22 Kb/s
- retardo de propagacion = 100 ms
- l = 250 bits


6- Si la utilizacion del canal es del 5.8 y el tiempo de propagacion es de 200 ms y la velocidad es de 15 Kb/s, de que tamaño es la trama?


Emplee el protocolo de ventana deslizante para indicar cual es el tamano de la ventana para que la utilizacion del canal sea del 100% con los siguientes datos
- v = 50 Kb/s
- l = 1000 bits
- tiempo de propagacion = 100 ms


Emplee el protocolo de ventana deslizante para indicar cual es el tamano de la ventana para que la utilizacion del canal sea del 80% con los siguientes datos
- v = 50 Kb/sw
- l = 1000 bits
- tiempo de propagacion (R) = 100 ms

___
## Control de errores
**CRC: *Cyclic Redundancy Check***

- Se utiliza un algoritmo matematico basado en algebra modular
- Son codigos detectores
- Los bits de una trama se representan como coeficientes de un polinomio
	- Si la trama es 100011, el polinomio es: $x^5+0x^4+0x^3+0x^2+x+x^0$
	- $x^5+x+1$


**Ejemplo:**
Datos: 1 1 0 1 0 1 1 0 1 1
Generador: 1 0 0 1 1 (Este depende de la información que se envía y el CRC)
Emisor: Calcular los bits de protección para los datos


Se suman los mayores grados para obtener el grado del polinomio: 9 + 4 = 13

Datos: $x^{13}+x^{12}+x^{10}+x^8+x^7+x^5+x^4$
Este polinomio se divide entre el de generador: $x^4+x+1$

De residuo se tiene: $x^3+x^2+x+0$
Estos son los bits de proteccion: 1110

El receptor recibe los datos, el generador y los bits de protección
El receptor hace la division de los datos junto a los bits de proteccion entre el polinomio de generador

Si en este resultado da 0, no hay errores, se envia un **ACK**. De lo contrario **NACK**

**Generadores polinomiales estandar:**

| Nombre | Polinomio                                                                         | Aplicacion     |
| ------ | --------------------------------------------------------------------------------- | -------------- |
| CRC-8  | $x^8+x^2+x+1$                                                                     | ATM header<br> |
| CRC-10 | $x^{10}+x^9+x^5+x^4+x^2+1$                                                        | ATM AAL        |
| ITU-16 | $x^{16}+x^{12}+x^5+1$                                                             | HDLC           |
| ITU-32 | $x^{32}+x^{26}+x^{23}+x^{22}+x^{16}+x^{12}+x^{11}+x^{10}+x^8+x^7+x^5+x^4+x^2+x+1$ | LANs           |

Mientras mas bits de proteccion haya mas probable de detectar errores