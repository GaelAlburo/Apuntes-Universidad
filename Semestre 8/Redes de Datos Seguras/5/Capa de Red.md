Links:
____

- Mueve paquetes desde la entrada del router hasta una salida apropiada del mismo, a esto se le conoce como **retransmision** o ***forwarding***.

- Determina la ruta tomada por los paquetes desde el origen al destino. Esto se le conoce como **encaminamiento**, **ruteo** o ***routing***

___
# Funciones de la Capa de Red

1. Transporta segmentos desde un emisor a un host receptor
2. El emisor encapsula los segmentos dentro de datagramas
3. El receptor entrega los segmentos a la capa de transporte
4. El protocolo de capa de red interviene en cada host y router
5. El router analiza la cabecera IP de todos los datagramas que pasan a traves de el

Hay una caracteristica principal de los medios que la capa de red considera: el tamano maximo de la PDU que cada medio puede transportar. Esta caracteristica se conoce como la unidad de transmision maxima (MTU)

___
# Router
Tambien llamado enrutador o encaminador, es un conmutador de paquetes que permite enterconectar tanto redes LAN como WAN.
- Los routers proporcionan un control del trafico y funciones de filtrado a nivel de red.
- Son capaces de almacenar datos en unas tablas llamadas **Tablas de ruteo de encaminamiento o enrutamiento**

En un router se tienen 4 componentes:
- Puertos de entrada: Es por donde entra la información hacia el router
- Entrada de conmutación
- Puertos de salida
- Procesador de encaminamiento: Almacena la información sobre el encaminamiento

___
# Enrutamiento
Se lleva a cabo paquete por paquete y salto por salto

Cada router hace una accion con el paquete de las 3 posibles:
1. Enviarlo al router del proximo salto que se encuentra en otra red o subred
2. Enviarlo al host de destino que se encuentra dentro de la misma red o subred
3. Descartarlo de la red (Se pasaron el máximo de saltos

___
# Elementos de Tabla de Ruteo

1. Destino de red
2. Mascara de red
3. Puerta de enlace o gateway
4. Interfaz
5. Métrica:

![[Pasted image 20240405124146.png|center|450]]
Se pueden encontrar tres tipos de rutas en las tablas de enrutamiento
1. **Ruta Directa**: En el ejemplo, cada router tiene 2 rutas directas
2. **Ruta Indirecta**: No se encuentran los dispositivos en la misma red. En el ej. cada computadora tiene 1 ruta indirecta
3. **Ruta por defecto**: Rutas precargadas en el router por el fabricante

____

# Routers
Comunmente manejan redes alambricas (Ethernet, ADSL, ISDN), pero tambien existen routers inalambricos que permiten hacer una interfaz entre redes alambricas e inalambricas (WiFi, GPRS, UMTS, WiMAX).

La diferencia entre ambos tipos es la potencia que alcanzan, las frecuencias y los protocolos en que trabajan.

En WiFi las diferencias se denominan en clase a/b/g/n

# Switch
Al igual que el router, es un dispositivo de conmutacion de paquetes de almacenamiento y reenvio.

La diferencia fundamental es que el switch opera en la capa 2, por lo que para enviar un paquete lo hace mediante la dirección MAC.
**Un router emplea la direccion IP para mandar los paquetes.**

Hay switches de la capa 3; siendo un switch y un router al mismo tiempo. Esto permite conmutar paquetes tomando en cuenta tanto las direcciones MAC como la IP

- Direccion MAC $\rightarrow$ Direccion Fisica
- Direccion IP $\rightarrow$ Direccion Logica

___
# Direccionamiento Logics

Es la forma de asignarle direcciones IP a un dispositivo y como se agrupan subredes o superredes de dispositivos.

Hay diferentes métodos:
- Subneteo o *subnetting* (mas utilizado)
- VLSM (mas utilizado)
	- Método solo funcional para dispositivos CISCO o compatibles
- CIDR
	- Basado en VLSM
- Sumarizacion de rutas o superneteo

### Subneteo o  *subnetting*
- Las subredes son del mismo tamano (todas tienen la misma cantidad de hosts)
- Cada subred cuenta con $2^n-2$ direcciones IP asignables (se quitan 2 por la direccion IP sel segmento y la del broadcast)
- De todas las subredes que se generan, ni la primera ni la ultima se pueden emplear, por lo que quedan $2^n-2$ subredes asignables
- Para generar o detectar al ID de la subred se emplean bits "prestados" (bits del ID host)
- Se basan en las clases de direcciones IP para crear las mascaras modificadas
- Todas las subredes que se generan de una red emplean la misma mascara 

**Tabla:**

| Subred en binario | Subred en decimal | Subred en ordinal | Subred asignable en ordinal |
| ----------------- | ----------------- | ----------------- | --------------------------- |
| 00                | 0                 | 1a                | --------                    |
| 01                | 1                 | 2a                | 1a asignable                |
| 10                | 2                 | 3a                | 2a asignable                |
| 11                | 3                 | 4a                | --------                    |

**Ejemplo:**
**Partiendo de la direccion IP 192.168.4.0/28 indique cuantas subredes asignables existen, que rango de direcciones IP tienen cada una, cuantas subredes existen, emplea el metodo del subneteo para realizar el direccionamiento logico**

Numero de subredes: $2^n = 2^4 = 16 \space \text{subredes}$
$n$ son la cantidad de bits prestados

Numero de subredes asignables: $2^n-2 = 16-2 = 14 \space \text{subredes asignables}$

- Primera subred: Subred 0

Se cambian los bits en la IP que esten prestados en la mascara modificada

Rango de IP asignables: 192.168.4.0 - 192.168.4.15

Numero de hosts: $2^n=2^4=16 \space \text{hosts}$
Numero de hosts asignables: $2^n-2=2^4-2=14 \space \text{hosts asignables}$
$n$ es la cantidad de bits que se quedan para el host

- Segunda subred: Subred 1
11000000.10101000.00000100.<mark class="hltr-pink">0001</mark>0000 (IP) = 192.168.4.16
11111111.11111111.11111111.11110000 (Mascara)

11000000.10101000.00000100.0001111 = 192.168.4.31

Segmento: 192.168.4.16
Rango de IP 192.168.4.16 - 192.168.4.31
Rango de IP asignables: 192.168.4.17 - 192.168.4.30
Numero de hosts: $2^n=2^4=16$
Numero de hosts asignables: $2^n-2=16-2=14$
Broadcast: 192.168.4.31

- Tercera subred: Subred 2
11000000.10101000.00000100.0010000 - 192.168.4.32
192.168.4.00101111 - 192.168.4.47

Segmento: 192.168.4.32
Rango IP: 192.168.4.32 - 192.168.4.47
Rango IP asignables: 192.168.4.33 - 192.168.4.46

Numero de hosts: $2^n = 16$
Numero de hosts asignables: $2^n-2 = 14$
Broadcast: 192.168.4.47

- Cuarta subred: Subred 3
192.168.4.00110000 - 192.168.4.48 - Segmento
192.168.4.00111111 - 192.168.4.63 - Broadcast

Rango IP asignables: 192.168.4.49 - 192.168.4.62

Numero de hosts: 16
Hosts asignables: 14

- Quinta subred: Subred 4
192.168.4.01000000 - 192.168.4.64 - Segmento
192.168.4.01001111 - 192.168.4.79 - Broadcast

Rango IP asignables: 192.168.4.65 - 192.168.4.78

Numero de hosts: 16
Hosts asignables: 14

- Sexta subred: Subred 5
192.168.4.80 - Segmento
192.168.4.95 - Broadcast

Rango IP asignables: 192.168.4.81 - 192.168.4.94

- Septima subred: Subred 6
192.168.4.96 - Segmento
192.168.4.111 - Broadcast

Rango IP asignables: 192.168.4.97 - 192.168.4.110

- Octava subred: Subred 7
192.168.4.112 - Segmento
192.168.4.127 - Broadcast

Rango IP asignables: 192.168.4.113 - 192.168.4.126

____
# Ejercicio - Subnetting

`Insertar diagrama cuaderno`

Se selecciona usar una Clase B
172.16.0.0 - 172.31.255.255

<mark class="hltr-pink">ID Subred</mark>
172.16<mark class="hltr-pink">.000</mark><mark class="hltr-blue">00000.00000000</mark>
<mark class="hltr-blue">ID Host</mark>

Subredes: $2^n-2 = 2^3-2 = 8-2 = 6 \space \text{subredes asignables}$
Hosts: $2^13 = 8192$

- S0  - NO SE PUEDE UTILIZAR
S: 172.16.0.0
M.M.: 255.255.224.0
R.A.: 172.16.0.1 - 172.16.31.254
B: 172.16.31.255

- S1
S: 172.16.32.0
R.A.: 172.16.32.1 - 172.16.63.254
B: 172.16.63.255

- S2
S: 172.16.64.0
R.A.: 172.16.64.1 - 172.16.95.254
B: 172.16.95.255

- S3
S: 172.16.96.0
R.A.: 172.16.96.1 - 172.16.127.254
B: 172.16.127.255

- S4
S: 172.16.128.0
R.A.: 172.16.128.1 - 172.16.159.254
B: 172.16.159.255

- S5
S: 172.16.160.0
R.A.: 172.16.60.1 - 172.16.191.254
B: 172.16.191.255


____
# VLSM (*Variable Length Subnet Mask*)

Creado por y para dispositivos CISCO.

- Las subredes NO necesariamente son del mismo tamaño
- Las mascaras modificadas son de longitud variable porque se adaptan a la cantidad de hosts
- Las direcciones asignables están dadas por $2^n - 2$
- La dirección del segmento y del broadcast en cada rango no se pueden asignar
- Todas las subredes generadas se pueden utilizar o asignar

`Insertar diagrama cuaderno`

Se siguen teniendo las 5 subredes
- S0: 150
- S1: 100
- S3: 2
- S4: 2
- S5: 2

- Una desventaja del VLSM es que si se quieren añadir o quitar hosts de una subred, se debe realizar el direccionamiento de nuevo. Pueden cambiar de orden las subredes 

\# Host Asignables
- $2^n - 2 = 2^8 - 2 = 254$
- $2^7 - 2 = 126$
- $2^2 - 2 = 2$
- $2^2 - 2 = 2$
- $2^2 - 2 = 2$

- Se decide utilizar la dirección IP 10.0.0.0

- 255.255.255.0                  /24  (Se toman los 8 primeros bits de la IP para host)
- 255.255.255.128              /25 (Se toman los 7 primeros bits para el host)
- 255.255.255.252              /30 (Se toman los 2 primeros bits para el host)
- 255.255.255.252              /30
- 255.255.255.252              /30

Rangos:
- 10.0.0.0 - 10.0.0.255 (se requieren 254 direcciones mas el de segmento)
- 10.0.1.0 - 10.0.1.127 (se requieren 128 direcciones se suman 127)
- 10.0.1.128 - 10.0.1.131 (se requieren 4 se suman 3)
- 10.0.1.132 - 10.0.1.135
- 10.0.1.136 - 10.0.1.139

____
# Superneteo (Sumarizacion de rutas o *supernetting*)

Método que permite agrupar multiples rutas IP contiguas en una unica ruta, varias subredes se engloban en una super red

**Ventajas:**
- Reduce el volumen de información de enrutamiento publicado
- Reduce la complejidad de las tablas de enrutamiento, reduciendo la cantidad de rutas
- Aumenta la estabilidad de las tablas de ruteo ya que una ruta sumaria permanece activa mientras al menos una de las rutas sumarizadas permanezca activa
- Reduce los requerimientos de memoria RAM en los dispositivos ya que se reduce el tamaño de la tabla de ruteo
- Reduce los requerimientos de procesamiento ya que minimiza los procedimientos de actualización de rutas y se reduce la cantidad de rutas a evaluar
- Para aplicar el método las direcciones IP deben ser contiguas
- Esta técnica es utilizada por los ISP (Proveedores de Servicios de Internet)

**EJEMPLO:** Aplicar sumarizacion de rutas  a las siguientes direcciones IP:
- 172.16.168.0/24 - 10101100.00010000.10101000.00000000
- 172.16.169.0/24 - 10101100.00010000.10101001.00000000
- 172.16.170.0/24 - 10101100.00010000.10101010.00000000
- 172.16.171.0/24 - 10101100.00010000.10101011.00000000
- 172.16.172.0/24 - 10101100.00010000.10101100.00000000

1. Se debe transformar a binario las direcciones IP
2. Se deben verficar, del mas significativo al menos, que los bits sean iguales
	1. En este caso, hasta el sexto bit ($\rightarrow$) del tercer octeto todos los bits son iguales

Segmento de red: 172.16.168.0
Broadcast: 172.16.175.255
Mascara: 255.255.248.0/21

____
# CIDR (*Clasless InterDomain Routing*)

- Usa la técnica VLSM para hacer posible la asignación de prefijos de longitud arbitraria
- Usada en internet para redes publicas
- Mas eficiente el uso de direcciones IP
- El uso de múltiplos prefijos contiguos en super redes
- Reduce el numero de entradas en tablas de rutas globales
- La mascara modificada puede ser menor o mayor a la mascara típica de la dirección IP que se emplea
- Considera sumarizacion de rutas
- Todas las direcciones IP deben ser contiguas


____
# Ejercicios

Utilizando subnetting obtenga lo que se pide: 

- Dada la red de tipo C 194.200.30.X, con mascara 255.255.255.0
	- Dividir la red en 2 segmentos de subred a traves de la mascara
	- Identificar cada uno de los segmentos
	- Identificar cual seria el broadcast
	- Dar el rango de IP's utilizables para cada subred

- .0
- .1 - 126
- .127

- 128
- 129-254
- 255

- Considere que se necesitan 14 subredes utilizables y 14 hosts utilizables, la direccion de red es 192.10.10.0, obtenga:
	- Mascara de subred por defecto
	- Macara modificada
	- Num. total de subredes
	- Num. total de redes utilizables
	- Num. total de direcciones de hosts
	- Num. total de direcciones utilizables
	- Cual es el rango de la subred 3?
	- Cual es el numero utilizable para la subred 7?
	- Cual es la dirección de broadcast para la subred 12?
	- Cuales son las direcciones asignables para la red 8?


- Crear y disenar un esquema de direccionamiento para la red mostrada usando Mascara de Red de Longitud Variable (VLSM)
Network: 192.168.10.0


- Aplicar sumarizacion de rutas a las siguientes direcciones IP:
	- 192.22.40.0/24
	- 192.22.42.0/24
	- 192.22.41.0/24
	- 192.22.43.0/24
	- 192.22.44.0/24