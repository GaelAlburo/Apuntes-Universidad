Links: [[Temario Redes]]
___

Dependiendo de la forma de conducir la señal a traves del medio o soporte físico, se pueden clasificar en dos:
- Medios de transmisión guiados, terrestres o **alámbricos**
- Medios de transmisión no guiados, aéreos o **inalámbricos**

>[!done] Los dispositivos que se emplean de manera inalambrica se conectan de manera alambrica por ser dispositivoc activos (requieren de energia  externa)

>[!info] Porcentaje Alambricos: 85%-95%

>[!info] Medio de transmisión alámbrico mas utilizado es el UTP

# Medios de Transmisión Guiados
- Cable par trenzado
	- Usan cobre, pero es muy delicado por la protección
- Cable coaxial
	- Diferentes diámetros
	- Usan cobre, muy robado
- Fibra óptica

___
### Cable de Par Trenzado
Tiene dos conductores eléctricos aislados y entrelazados para anular las **interferencias** (EMI: Interferencias Electromagnéticas) de fuentes externas y diafonía de los cables adyacentes

>[!info] Se debe evitar trenzar los pares si es que ya se destrenzaron

**Tipos:**
- UTP (*Unshielded Twisted Pair*)
	- Soporta grandes distancias pero esta limitado
	- No es 100% fiable, presenta errores (EMI)
	- Conviene su uso en interiores
	- Mas barato
	- Se pueden utilizar con diferentes dispositivos
	- Sin blindaje
	- El trenzado es a cierta distancia para evitar diafonías
	- Existen categorías que indican ciertas características, como la velocidad de transmisión
- STP (*Shielded Twisted Pair*)
	- Tiene blindaje de aluminio
	- Soporta grandes distancias, pero esta limitado
	- Conviene usarlo en interiores o en exteriores
	- Menos barato que el UTP
	- Se puede emplear con distintos dispositivos y tecnologías
	- Mayor impedancia que la del UTP
	- El trenzado es a cierta distancia para evitar diafonías
- FTP (*Foiled Twisted Pair*):
	- Con blindaje
	- Tiene un alambre para la puesta a tierra
	- Conviene en exteriores para trabajar con dispositivos inalámbricos
	- Mayor impedancia que los anteriores
	- Mas costoso " "

Pares del par trenzado:
1 - BN: Ethernet
2 - N: Ethernet
3 - BV: Ethernet
4 - A
5 - BA
6 - V: Ethernet
7 - BC
8 - C

Se quiere que todos los pines funcionen para que haya un mayor ancho de banda

**Ventajas:**
- Bajo costo
- Alto numero de estaciones de trabajo por segmento
- Facilidad para rendimiento y solución de problemas
- Puede estar previamente cableado en un lugar o cualquier parte
- Nomenclatura: `XBaseT --> 10BaseT`
	- Base: Baseband
	- T: Twisted Pair.
		- Si fuera X: Fibra óptica
	- 10/100/1000 Mbps 
- Longitud maxima: Cuando se utiliza para 10/100/10000 BASE-T es de **100 m**

**Desventajas:**
- Altas tasas de error a altas velocidades
- Ancho de banda limitado
- Baja inmunidad al ruido
- Baja inmunidad a la diafonía
- Alto costo de los equipos
- Distancia limitada (100 metros por segmento)
# Diagrama de una red de datos

- El cable que conecta la computadora al Jack (RJ45 hembra) DEBE SER DIRECTO. ***Patch Cord***
	- Debe ser de máximo 5 metros
	- Puede ser cruzado si la tarjeta de red lo permite, algunas de estas tarjetas lo pueden descruzar
- El cable del Jack que va hasta el patch panel debe ser de máximo 90 metros
- Del patch panel se conecta a un switch, con un cable DIRECTO
	- Debe ser de máximo 5 metros

Se muestra el cableado horizontal para conectar el Area de Trabajo al Cuarto de Telecomunicaciones

___
### Cable Coaxial
Cable usado para transportar señales eléctricas de alta frecuencia que posee dos conductores concéntricos
Es mas resistente a interferencias y atenuación que el cable de par trenzado; por esto fue el mas utilizado.
Tiene dos tipos:
- Cable coaxial delgado: `10Base2`
- Cable coaxial grueso: `10Base5`

____
### Fibra Optica
- Es una fibra flexible
- Emite pulsos de luz
- Soporta grandes distancias
- Grandes costos
- Dispositivos específicos para la fibra óptica
- No hay interferencias por transmitir luz
- Grandes velocidades

**Tipos:**
- Fibra multimodo: Aquella en la que los haces de luz pueden circular por mas de un modo o camino.
	- No todos los haces llegan al mismo tiempo
	- Dependiendo del tipo de **índice de refracción**, hay dos tipos de fibra multimodo:
		- Indice escalonado o salto de indice
		- Índice gradual o gradiente de índice
	- Nomenclatura: `OM` y tipos `OM1, OM2, OM3, OM4` y `OM5`
		- OM: Modo Óptico (*Optic Mode*) - El numero indica las micras del haz de lux

- Fibra monomodo: Solamente se propaga un modo de luz
	- Se logra reduciendo el diámetro del núcleo de la fibra hasta un tamaño (8,3 a 10 micrones) que solo permite un modo de propagación
	- Nomenclatura: `OS` y tipos `OS1` y `OS2`
		- OS: Modo óptico simple (Optic Simple Mode)

![[Pasted image 20240219123147.png|center|450]]

___

# Medios de Transmision No Guiados
La transmisión y recepción de información se llevan a cabo mediante **antenas**

Al momento de transmitir, la antena irradia energía electromagnética en el medio. Al momento de recibir la antena capta las ondas electromagnéticas del medio que la rodea

## Tipos de Antenas
- Direccionales: Concentra ondas electromagnéticas y las envía en un solo haz. Para que llegue al receptor emplea **LOS** (*Line of Sight* - Linea de Vista)
	- Antena emisora debe estar alineada con la antena receptora

- Omnidireccionales: Las ondas o radiaciones se emiten en todas direcciones (p.j. celulares), las antenas las capturan
	- Se emplea NLOS (*Not Line of Sight* - Sin Linea de Vista)
	- Varias antenas pueden captar las señales/información/ondas

___
## Tipos de Medios No Guiados

- **Radiofrecuencia u ondas de radio**
	- Ondas de radio
	- Ondas de television
	- Telefonía móvil
	- Radionavegación (marina)
	- **Son usados a nivel civil o militar, al igual que los radioaficionados**
- Microondas
	- Terrestres
	- Satelitales
- Luz
	- Infrarroja
	- Laser

### Microondas
- Terrestres
- Satelitales
Permiten transmisiones con antenas terrestres y satelitales.

Dada sus frecuencias, del orden de 1 a 10 GHz, las microondas son **direccionales** y solo se pueden usar donde existe una linea visual entre emisor y receptor.
Estos enlaces permiten grandes velocidades de transmisión, del orden de 10 Mbps.

En cuanto a satélites, estos deben estar colocados a 4 grados entre uno y otro.
Se colocan en la orbita geoestacionaria (35680 km de la superficie terrestre).

>[!info] Se busca que con la menor cantidad de satelites, se cubra la mayor cantidad de territorio.

Usar satélites es costoso y es muy complicado realizar mantenimiento sobre ellos.

___
### Luz Infrarroja
Emplean LEDs, es necesario que los dispositivos estén cerca para que la comunicación sea eficiente. Hay muchos obstáculos que puedan interferir en la linea de vista, además de que la luz se va disipando y es complicado mantener la comunicación a grandes distancias.

- Genera una red PAN, ya que puede comunicar a solo dos dispositivos.
- La distancia para comunicarse es corta
- Puede manipular distintos dispositivos independientemente de la marca
	- Ejemplo: Controles remotos universales
- Se basan en el estándar IDA ( *Infrared Data Association*)

___
### Laser
Funcionan mediante haces de luz.

- Son costosos los dispositivos y el equipo
- Mantenimiento costoso
- Peligroso para el ojo humano
- Idealmente solo se emplean en distancias cortas
- Si hay obstáculos no puede evitarlos
	- Se pueden emplear espejos para evitarlos, pero es muy dificil saber por donde habra obstaculos
- Linea de vista es requerida
- Se necesitan fotodetectores
- Se requiere de mucha precision de un extremo a otro
- Uno de los problemas es la niebla, lluvia, flora densa

>[!done] La fibra óptica es mas viable, económicamente, que las satelitales. Ya que los satelitales tienen muchos obstáculos y eventualidades que pueden sucedes.

>[!info] En teoría, una buena red de datos, debería durar mínimo 10 anos. Esto no es muy cierto en la realidad
