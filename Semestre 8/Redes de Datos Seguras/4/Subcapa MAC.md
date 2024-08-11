Links: [[Temario Redes]]
___
La subcapa MAC (Control de Acceso al Medio) define los protocolos que indican:
- Quien puede usar el enlace
- Como debe usarse el enlace

Existen dos formas de asignar el canal:
- Estática (Empleando las técnicas FDM (Multiplexación por division de frecuencias) y TDM)
- Dinámica

___
Al contar con un **canal de comunicación compartido** entre varios usuarios es necesario contar con un control de acceso:
- Para evitar que varias estaciones empiecen a transmitir a la vez
- Evitar interferencias
- Permitir la comunicación

____
# CSMA

>[!done] CSMA (*Carrier Sense Multiple Access* - Acceso Multiple con Deteccion de Portadora) es un protocolo ideado para solucionar este problema

Este protocolo permite que una estación **sense** el canal para saber si esta libre y puede transmitir información.
- Si esta libre va a transmitir
- Si no esta libre, va a tener que esperar considerando una persistencia

### CSMA Persistente / 1 Persistente
Intenta transmitir tan pronto como el canal queda libre, por lo que **sensa o escucha** continuamente al canal.

- **Ventajas:**
	- El canal se aprovecha mejor
	- Adecuado en una red con pocas estaciones
- **Desventajas:**
	- Aumenta el numero de colisiones con muchas estaciones
	- Invierte mas tiempo en resolver colisiones que en transmitir datos.

### CSMA No Persistente / 0 Persistente
Espera un tiempo aleatorio determinado por una distribución de probabilidad antes de volver a intentar acceder al canal y sensar de nuevo.

- **Ventajas:**
	- Escucha determinado tiempo variable
	- Donde hay muchas estaciones todas usan el canal
- **Desventajas:**
	- Muchos tiempos muertos en el uso del canal

### CSMA $P$ Persistente
Se comporta de forma persistente con una probabilidad $p$, y de forma no persistente con una probabilidad $1-p$.
La escucha se realiza cada tiempo constante

- **Ventajas:**
	- Si hay colisiones se da aviso a las estaciones
	- Las estaciones calculan un tiempo $P$ que indica cuando reanudar el sensado
- **Desventajas:**
	- Al haber una colisión las estaciones cancelan la transmisión de datos

____
## Variaciones del CSMA

Hay dos variaciones principales de **CSMA** que son:
- **CSMA/CD (*Carrier Sense Multiple Access with Collision Detection*)** - Alámbrica
- **CSMA/CA (*Carrier Sense Multiple Access with Collision Avoidance*)** - Inalámbrico

#### CSMA/CD
Acceso Multiple por Detección de Portadora por Detección de Colisiones

- Usado en situaciones en las que se puede escuchar a la vez que transmitir
- Si se detecta una interferencia se interrumpe la transmisión de inmediato
- Una vez despejado el meido de se reanuda la transmision
- Protocolo de enlace utilizado en las redes de la familia Ethernet (802.3) (*1 Persistente*)

#### CSMA/CA
Acceso Multiple por Detección de Portadora y Prevención de Colisiones

- Multiples estaciones utilizan un mismo medio de transmision
- Empleado en redes inalámbricas, ya que estas no transmiten ni reciben simultáneamente
- Si el medio esta libre tras realizar la escucha, se espera un tiempo aleatorio adicional antes de transmitir, lo cual reduce el numero de colisiones
- Cada equipo anuncia opcionalmente su intención de transmitir antes de hacerlo para evitar colisiones entre los paquetes de datos
- Los equipos de la red sabrán cuanto hay colisiones y en lugar de transmitir la trama inmediatamente que el canal este libre, se espera un tiempo aleatorio adicional corto y solamente si, tras ese corto intervalo el medio sigue libre, se procede a la transmisión reduciendo la probabilida de colisiones en el canal
- Se utiliza en 802.11 (IEEE WiFi) basada en redes inalámbricas

Este proceso se puede dividir  en tres fases en las que ele misor:
- Escucha para ver si la red esta libre
- Transmite el dato
- Espera un reconocimiento por parte del receptor