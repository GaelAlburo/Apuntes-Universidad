Links: [[Temario Redes]]
___

# Red de Datos
Una **red de datos** es un conjunto de dispositivos que están interconectados por uno o mas medios de transmisión para compartir recursos, información o datos.
El objetivo es que estas actividades se realicen lo mas eficiente, confiable y segura posible. (IDEAL)

# Concepto de Seguridad
Conjunto de protecciones que permite resguardar un bien (material o no).
Un bien es algo importante o valioso para alguien o un conjunto de personas.
Estas protecciones aseguran la integridad, confidencialidad y disponibilidad de los bienes

CIA: Confidentiality, Integrity, Availability - Triada de seguridad

# Medio de Transmisión
Canal que permite la comunicación entre un emisor o un receptor.
Se clasifican de la siguiente manera:
- Terrestres: Guiados o Alámbricos
- Aéreos: No guiados o Inalámbricos

# Tipos de Dispositivos para usar una Red
Elementos preparados para realizar una funcion determinada:
- Dispositivos Pasivos: Se usan para interconectar los enlaces de una red de datos
	- No es necesario conectarlos a la red electrica
- Dispositivos Activos: Se encargan de distribuir en forma logica y activa la informacion a traves de la red (Switch, NIC [tarjeta de red])
	- Requieren estar conectados a la red electrica (telefono por la pila)
	- Hay dispositivos POE (*Power Over Ethernet*) que obtienen su carga electrica mediante el cable de red

# Switch
Es un dispositivo para la interconexion de redes de datos que opera en la capa 2 (nivel de enlace de datos) del modelo OSI
Interconecta dos o mas segmentos de red, pasando datos de un segmento a otro segun la dirección MAC de destino
Tambien es llamado conmutador.
**Funciona como dispositivo central**. Si no hay switch, no hay red. De este dispositivo se distribuye la red o redes.

Dirección MAC: Dirección de un dispositivo **unica**, para saber a que dispositivo se envía algo.

# Router
Conocido también como ruteador, encaminador, enrutador
Dispositivo para la interconexión de red de datos que opera en la capa 3 (nivel de red).
Permite asegurar el enrutamiento de paquetes entre redes o determinar la mejor ruta que debe tomar el paquete de datos
Físicamente es muy parecido a un switch, pero su función es totalmente distinto. Son mas caros.
Los routers pueden trabajar con distintos medios de transmisión.

> [!done] NOTA: Existen switches de capa 3. Fungen como switches y como routers.

> [!done] En los dispositivos existen niveles de confianza: Alto, Medio y Bajo. El nivel de confianza depende del uso o sobreuso del dispositivo

Que un dispositivo sea nuevo no significa que sea de alto nivel de confianza

# Punto de Acceso
AP: *Access Point*
Dispositivo de red que interconecta equipos inalámbricos de comunicación para formar una red inalámbrica que interconecta dispositivos móviles o tarjetas de red inalámbricas.
Hay puntos de acceso que también funcionan como routers.

>[!done] Las conexiones de red oscilan entre un 90%-95% de conexiones alambricas.

La mayoría de las redes son alámbricas, conexiones Inter atlánticas, conexiones eléctricas, etc.

# Topología
Forma geometrica en que estan distribuidos los equipos de una red.
Su objetivo es buscar la forma mas económica y eficaz de conectar los equipos para facilitar la funcionalidad del sistema, evitar tiempos de espera, mejorar el control de la red y hacerla mas confiable.
Es el mapa físico o lógico de una red para intercambiar datos.

Puede que la topología no sea realmente física, sino como se manejan los datos es la forma de la topología.

Ejemplos de topologías:
- Anillo
- Malla
- Bus
- Estrella (mas utilizada por estandarización)
- Etc.

### Topología Estrella
- Los dispositivos están conectados a un dispositivo central
- El dispositivo central es el que controla (se usan switch)
- La cantidad de dispositivos que se pueden conectar depende de la cantidad de puertos del switch (dispositivo central)
- Si el dispositivo central no funciona, la red deja de funcionar
- Si un solo nodo no funciona, sigue habiendo red para el resto de nodos
- Forma de transferencia /Forma de transmisión **(F.T.)** (Como se enviara la información): Conmutacion (se busca por una direccion hacia donde debe ir la informacion)
- Control de transmisión/Control de transferencia **(C.T.)** (se depende de un dispositivo para enviar la información): Es centralizado
- **Es la empleada en el cableado estructurado**

### Topología Anillo
- No hay un dispositivo central
- Cada nodo esta conectado con un antecedente y un consecuente
- Se pueden conectar `n` nodos.
- Mientras mas nodos, mas lenta es la transmisión de datos
- Si un nodo deja de funcionar, la red no funciona para el resto de los nodos que van después del nodo que no funciona
- F.T. (Forma de transferencia): Conmutación. Recibe y ve a quien se lo va a mandar
- C.T. (Control de transmisión): Descentralizada
- Para robustecer y hacer eficiente se crea el anillo bidireccional.
	- Se requiere doble medio de transmisión y doble NIC (*Network Interface Card* - Tarjeta de red) **Mas recursos**

### Topología *Bus* (Canal)
- No hay un dispositivo central
- Cada nodo esta conectado a un mismo canal
- Se pueden conectar los nodos que se requieran
- Entre mas nodos haya, la señal se ira atenuando debido a la longitud del canal
	- Segun estándares, se tienen distancias para los canales
- Si el canal, o bus, deja de funcionar no hay red
- Si uno de los nodos deja de funcionar sigue habiendo red
- F.T.: Difusión (Se manda información al canal y que lo recoja el nodo)
- C.T. Descentralizado (Distribuido)
- Existen colisiones - Se manda información y se recibe al mismo tiempo

### Topología Malla (*Mesh*)
- No tiene dispositivo central
- Puede llegar la información por distintas trayectorias porque todos los nodos están interconectados
- Si un nodo deja de funcionar la red funciona para el resto
- Se requiere una cantidad de recursos excesiva
- Es la topología IDEAL
- F.T. : Difusión. Se manda por varios caminos, no importa por cual llegue
- C.T. : Descentralizado (Distribuido)

### Arbol Jerárquica (Hibrida)
- Cada nodo es una red (switch, etc.), no una computadora
- Si el nodo padre deja de funcionar, NO hay red en sus nodos hijos
- Si un nodo hijo deja de funcionar, no afecta la red siempre y cuando ese nodo no es padre
- F.T. y C.T. dependería de cada topología de red empleada

# Modelo
Es todo aquello que nos pueda servir como pauta para ser imitada, reproducida o copiada.
Un modelo ya esta probado y se sabe que funciona, por esto se replica
Un ejemplo es el modelo OSI:
7. Aplicación
6. Presentación
5. Sesión
4. Transporte
3. Red
2. Enlace de Datos
1. Física

> [!done] Diafonia: Interferencia entre dos cables. Cable de red junto al cable de electricidad, se genera interferencia.

# Cableado Estructurado
Es un sistema completo de cables y dispositivos asociados que proporcionan una infraestructura de comunicación para la transmisión.

> [!info] El area de trabajo es donde el usuario final utilice un dispositivo como una laptop, PC o teléfono. Esto puede ser en el closet o en el baño, etc.

Hay normas para realizar el cableado estructurado.

# Beneficios de diseñar una Red de Datos
- Compartir recursos
- Seguridad
- Envío y recepción de información rápidamente
- Ahorro de recursos (No ir a biblioteca, solamente buscarlo en línea)
	- Tambien se generan gastos (Pagar internet, instalación, etc.)
- Fácil manejo, administración, configuración
	- En otras situaciones no es sencillo administrarlos, en el caso de reemplazar un cable
- Control de información
- Consideración de factores externos (fauna, flora, ambiente)
- Hacer consideraciones que eviten problemas a futuro
	- Hornos de microondas, la lengüeta de los cables esta rota, obstrucciones en el AP

# Objetivo de emplear una Red de Datos
Enlazar dos o mas dispositivos para que exista comunicación entre ellos o para compartir información y recursos

# Servicios que usan Redes de Datos
- Banco
- Comunicaciones
- Escuelas
- Mercantiles
- Empresariales
- Servicios medicos o de emergencia
- Transporte (Uber)
- Entretenimiento (Streaming, videojuegos)
- Servicios escolares
- Sistemas penitenciarios
- Redes sociales
- Radio
- Milicia
- Seguridad
- Servicios domésticos
- Bases de datos gubernamentales

# Problemáticas si no existieran las Redes
- Falta de comunicacion-asilamiento
- Servicios mas lentos
- Problemas de registros de datos personales
- Acceso difícil a información
- Perdida de datos (robo)
- Dificultad de evolución en tecnología
- Falta de entretenimiento (pocas opciones)
- Problemas de seguridad

>[!done] Así como las redes tienen muchos beneficios, también generan muchos problemas, socialización, otros servicios se dejaron de usar, etc.

