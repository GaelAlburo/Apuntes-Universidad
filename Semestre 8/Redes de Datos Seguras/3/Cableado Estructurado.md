Links: [[Temario Redes]]
___

Es una infraestructura de cable destinada a transportar a lo largo y ancho de una red LAN, los datos que necesiten compartir los usuarios.

> [!done] La norma garantiza que las redes que la usen soportaran todas las aplicaciones de telecomunicación presentes y futuras en un rango de 10 años.

# Características
- Brinda Flexibilidad
	- Independencia del fabricante
	- Facilidad del movimiento, cambios, adiciones
	- Conectividad del sistema abierto - Basado en Modelo OSI

- Mejora el retorno de la inversion (ROI - *Return of Investment*)
	- Aumenta la vida del sistema
	- Disminuye el costo del ciclo de vida

___
![[Pasted image 20240301181836.png|center|450]]
1. Entrada al edificio / *Backbone* de campus / Entrada de los servicios
2. Area de equipo / Subsistema de equipos / Cuarto de equipos (*MDF - Main Distribution Frame*)
3. Cableado vertical / Subsistema vertical o modular (*backbone*)
4. Cuarto de telecomunicaciones / Subsistema de administración (*IDF - Intermediate Distribution Frame*)
5. Cableado horizontal
6. Area de trabajo (*Work area*)

___
# Cableado Vertical
Columna vertebral de la red.
Su objetivo principal es intercomunicar a los pisos de un edificio (piso a piso)

Conecta a los cuartos de telecomunicaciones, cuartos de armarios e instalaciones de entrada.

Se consideran las siguientes nomenclaturas:
- MC (*Main connection*): Conexión cruzada principal
- IC (*Intermediate Connection*): Conexión intermedia
- HC (*Horizontal Connection*): Conexión Horizontal
- ER (*Equipment Room*): Cuarto de equipos de telecomunicaciones
- TR (*Telecommunication Room*): Armario de telecomunicaciones

### Medios de Transmisión (*Packet Tracer*)
- UTP -> Ethernet
Z : Conexión serial / Conexión de routers
En estas conexiones, en algún extremo, se requiere un *Clock rate*, ya que se necesitan sincronizar datos. Los routers SIMPRE necesitan sincronizarse
(Del lado donde este el reloj, se debe configurar). 
- El lado donde esta el reloj se llama *DCE*. Donde no esta el reloj se llama *DTE*.
- En Packet Tracer hay dos tipos de conexiones seriales, *DCE* y *DTE*. Marcan donde están los relojes

------- :  Conexión cruzada (*Cross-over*)

Linea recta: Conexión Directa (*Straight Through*)

Conexión cruzada:
- Switch-Switch
- Router-Router
- Equipo-Equipo
- Switch-Hub
- Equipo-Router (El router funciona muy similar a un equipo, por eso se usa cruzada)

Conexión directa:
- Equipo-Switch
- Equipo-Hub
- Switch-Router

**Interfaces en Packet Tracer**
- Se
- Fa0/0
- Fa0/1

___
# Requerimientos de las Canalizaciones
- No deben estar en cubos de elevadores ya que no son fáciles de acceso y generan EMI
- Deben tener contenedores de fuego
- Nunca dejar una via de backbone abierta
- Los backbone UTP **no deben exceder 90m**
- Los backbone CAT5e (ya no se debe usar) y superiores soportan aplicaciones hasta 100MHz
- Los backbones nuevos (CAT6 o +) soportan mayores velocidades y ya no son compatibles con las CAT5e

___
# Armario de Telecomunicaciones
- Transición en vias de acceso de backbone y de distribución horizontal
- Dedicado a la función de telecomunicaciones
- Se recomienda mínimo uno por cada piso
- Considera hasta 1000 $m^2$
- Le da servicio al piso donde se encuentra
- Aloja la conexión cruzada horizontal y el equipo de telecomunicaciones para un piso o area especifica de un edificio
- Maximo 7 metros de conexión de cables de parcheo (Idealmente son 5 metros)

___
# Distribución Horizontal
- Topología estrella
- En este subsistema es conveniente que los cables estén en:
	- Canaletas
	- Tuberías
	- Escalerillas
	- Muebles con espacio apropiado para cableado

Hace referencia a las facilidades dedicadas a la instalación de cable de telecomunicaciones del armario hasta el area de trabajo.

Las canalizaciones horizontales no deben estar localizadas en cubos de elevadores ni cerca o dentro del baño
Estas canalizaciones dentro de edificios deben ser instaladas en lugares secos que protejan a los cables de niveles de humedad.

____
# Area de Trabajo
Es el subsistema donde se encuentran los dispositivos finales y los usuarios que los usan.

Es donde el usuario que usa los dispositivos de telecomunicaciones y los servicios que se proveen

___
# Entrada al Edificio
Entrada para recibir los servicios dados/otorgados/controlados por el ISP (Proveedor de Servicios de Internet).
- Puede ser de tipo aéreo o terrestre

Las entradas dependen del tipo de proveedor

___
# Cuarto de Equipo
En este cuarto se encuentra la llegada de los servicios y se emplean varios dispositivos de telecomunicaciones para poder distribuir, via sistema vertical, dichos servicios.

Se pueden tener distintos servicios, como de base de datos, telefonía, etc.
- Es necesario tener un sistema de ventilación, por la cantidad de dispositivos, la temperatura aumenta mucho.

