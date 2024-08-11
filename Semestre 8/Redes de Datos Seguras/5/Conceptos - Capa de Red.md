Links: [[Temario Redes]]
___
# Que es IP
Es el protocolo de internet (*Internet Protocol*) que se emplea para identificar a los dispositivos y permite el envío y recepción de información entre ellos

### Hay dos versiones de IP:
1. IPv4 - La mas utilizada
	- 32 bits
2. IPv6 - Debería ser usada esta, pero no muchos sistemas la reconocen
	- 128 bits

# Dirección IP
Conjunto de números que representan ciertos bits y se emplean como el identificador del dispositivo en la red

- Para IPv4:
	- X.Y.Z.W - Se compone de 4 octetos, donde cada octeto puede tener valores de entre 0 y 255

>[!info] Todas las direcciones de IPv4 ya fueron repartidas por la IANA, desde el 31 de enero de 2002

### Clases de Direcciones IP

Para obtener los bits mas significativos se toma el *ID Red*. El bit mas significativo es el bit o bits que se mantienen igual

| Clase | Bits mas significativos | Rango                                   | Octetos ID Red       | Octetos ID Host      |
| ----- | ----------------------- | --------------------------------------- | -------------------- | -------------------- |
| A     | 0                       | ***0***.0.0.0 - ***127***.255.255.255   | 1 (Primer octeto)    | 3 (Resto de octetos) |
| B     | 10                      | ***128.0***.0.0 - ***191.255***.255.255 | 2 (Primeros octetos) | 2 (Resto de octetos) |
| C     | 110                     | ***192.0.0***.0 - ***223.255.255***.0   | 3 (Primeros octetos) | 1 (Resto de octetos) |
| D     | 1110                    | 224.0.0.0 - 239.255.255.255             | ---------            | ---------            |
| E     | 1111                    | 240.0.0.0 - 255.255.255.255             | ---------            | ---------            |

Las clases A, B y C se usan para dispositivos comunes
Las D y E se usan únicamente para propósitos específicos (decididos por EE.UU.)
- D: Multidifusión
- E: Usos futuros y experimentales

___
# Ejercicio

**Identificar a que clase pertenece cada dirección IP, cual es su ID de red (Net ID) y cual es su ID de host (Host ID). Escriba la dirección en binario**

| Direccion          | Clase | ID Red     | ID Host      | Direccion en binario                |
| ------------------ | ----- | ---------- | ------------ | ----------------------------------- |
| a  192.168.2.10    | C     | 192.168.2  | .10          | 11000000.10101000.00000010.00001010 |
| b  138.92.1.24     | B     | 138.92     | .1.24        | 10001010.01011100.00000001.00011000 |
| c  11.1.15.192     | A     | 11         | .1.15.192    | 00001011.00000001.00001111.11000000 |
| d  128.54.35.102   | B     | 128.54     | .35.102      | 10000000.00110110.00100011.01100110 |
| e  111.112.113.114 | A     | 111        | .112.113.114 | 01101111.01110000.01110001.01110010 |
| f   200.251.48.63  | C     | 200.251.48 | .63          | 11001000.11111011.00110000.00111111 |

>[!done] La mascara de red se aplica de acuerdo a la clase que pertenezca la direccion

___
# Direcciones Restringidas
Las siguientes direcciones no se pueden establecer como identificadores en los dispositivos:
- 0.0.0.0: Representa el dispositivo de origen
- 127.0.0.0 - 127.255.255.255: Dirección que apunta desde la PC a la misma PC (Loophole)
- 255.255.255.255: Hace referencia al broadcast o multidifusión

# Clasificación de Direcciones IP
Se dividen en 2:
- Publicas
- Privadas

### Dirección Privada
Se llaman también direcciones virtuales o no homologadas.
Se pueden tener las mismas direcciones en distintas redes privadas
Existen rangos de direcciones que pueden ser privadas:

| A   | 10.0.0.0 - 10.255.255.255     |
| --- | ----------------------------- |
| B   | 172.16.0.0 - 172.31.255.255   |
| C   | 192.168.0.0 - 192.168.255.255 |

### Dirección Publica
Tambien se llaman direcciones IP reales u homologadas
Se pueden acceder desde cualquier dispositivo y cualquier parte del mundo

- Ej.: 132.248.59.79 $\rightarrow$ https://redyseguridad.fi-b.unam.mx 
Todas las direcciones que no estén en los rangos de las direcciones privadas, son direcciones publicas.

# ID de Red
Indica la red a la que pertenece el dispositivo. Tambien se llama Net ID

# ID de Host
Indica el dispositivo que esta en la red. No puede haber 2 iguales

# Mascara de Red
Conjunto de 32 bits que permite indicar perfectamente cuantos bits se emplean para identificar a la red a la que pertenece y cuantos bits para identificar al host.

Existen dos tipos de mascara de red:
- Típicas o por defecto: Aparecen por automático ya que están asociadas a la clase

| Clase | Mascara en decimal |
| ----- | ------------------ |
| A     | 255.0.0.0          |
| B     | 255.255.0.0        |
| C     | 255.255.255.0      |

- Modificadas: Se deben asignar manualmente

Lo que permanece inamovible es el ID Red.

# Wildcard
Conjunto de 32 bits que nos permite identificar quien es la red y quien es el host.
Lo que se mantiene fijo es el ID Host.

Es el contrario a una mascara de red.

| Clase | Wildcard decimal |
| ----- | ---------------- |
| A     | 0.255.255.255    |
| B     | 0.0.255.255      |
| C     | 0.0.0.255        |

___
# Ejercicios

1. Dada las siguientes direcciones IP indique si es valido colocarlas a dos dispositivos que se encuentran en la misma red
- 192.168.4.2 y 192.168.5.2     A
	Las direcciones pertenecen a la clase C. Si pertenecen a la misma red, sus 3 primeros octetos deben ser iguales. En este caso no es así, por lo que no es valido ya que hacen referencia a dos redes distintas

- 127.0.0.3 y 127.0.0.5       B
	El rango de 127.0.0.0 - 127.255.255.255 son direcciones restringidas , por lo que no se pueden asignar a los dispositivos. No es valido porque son direcciones *loopback*

- 130.8.0.0 y 130.8.1.2           C
	Son de clase B, sus dos primeros octetos hacen referencia a la misma red.
	Pero las direcciones, en esta clase, X.X.0.0 se reservan para definir a la misma red. No se le da a un host. Por lo que no son direcciones validas

- 192.168.2.30 y 192.168.2.140          D
	Son de clase C, hacen referencia a la misma red. Son direcciones validas

- 100.168.2.30 y 100.140.2.140       E
	Son clase A, y su primer octeto es igual, se refieren a la misma red. Son direcciones validas

- 205.44.50.0 y 205.44.50.255       F
	Son clase C, sus octetos de ID Red son iguales. Pero en su ID Host, en ambas, una es perteneciente a la red y la segunda es de un broadcast. No son direcciones validas ninguna dirección.

- 10.0.0.0 y 10.0.0.5        G
	Son clase A. Pero la dirección 10.0.0.0, se reserva para definir a la misma red, por lo que no se utiliza para definir a un dispositivo. Por lo que no son direcciones validas

- 172.16.25.6 y 172.16.36.255       H
	Son clase B, y sus dos primeros octetos son iguales, por lo que son direcciones validas

- 195.56.200.20 y 195.56.200.25           I
	Son clase C. Ambas direcciones son validas para dos dispositivos en la misma red

- 240.25.0.1 y 240.25.0.2        J
	Son clase E. No son direcciones validas ya que son de uso experimental. Esta restringido su uso publico.

___

# Dirección de IP de Broadcast (Multidifusion)
Es una dirección especial que permite la comunicación con todos los dispositivos de la red

# Subred
Grupo o parte menor de una red mayor. Al dividir una red, se generan varias subredes
Las subredes no se pueden comunicar entre si

Hacer divisiones de una red puede ser util en varias situaciones. Como una empresa, al dividir las areas, como de contaduría del area de sistemas.

Debe contar con un rango de direcciones IP como subconjunto de la red y para ello se emplean direccionamientos lógicos y mascaras modificadas

# Segmento de Red
Segmentación es dividir una red en subredes.
Al dividir la red se obtienen subredes, donde cada subred esta representada por un segmento de red.

Se segmenta para una mayor eficiencia y administración en cuanto a la gestion de dispositivos y seguridad.

# En las redes y subredes se deben identificar:
-  Dirección de la Red o Subred: Dirección que representa a la red y ningún dispositivo puede tenerla
- Rango de direcciones IP asignables/utilizables o usables
- Dirección de broadcast
- Mascara de red (típica) o subred (modificada)

# Prefijo de Red
Se refiere a la mascara de red/subred

Ejemplo: 255.0.0.0 (Mascara típica de clase A)
Prefijo: 11111111.00000000.00000000.000000000

Ejemplo: 255.192.0.0 (Mascara modificada de clase A)
Prefijo: 11111111.11000000.00000000.00000000

Los prefijos siempre son puros 1 antes de los 0. No puede haber un 01
Prefijos validos:
128, 192, ..., 254,
# Sufijo de Red
Se refiere a la mascara de red/subred

Ejemplo: DirIP/255.0.0.0
		 DirIP/8

Ejemplo: DirIP/255.192.0.0
		 DirIP/10

En el sufijo se pueden colocar solamente la cantidad de bits en '1' de la mascara. Notacion CIDR:
$$DirIP/\#bitsMascara$$

___
# Ejercicio

**Indique cuales son las direcciones IP que representan:**
	1. Rango de la red
	2. Direccion de red/subred
	3. Direccion de broadcast
	4. Rango asignable/utilizable
	5. Notación CIDR

1. **162.3.4.5.  Mascara: 255.255.128.0.**
	1. Se debe pasar a binario la direccio IP
		10100010.00000011.00000100.00000101 (IP)
		11111111.11111111.10000000.00000000 (Mascara)

		Se van a poner en 0s y 1s todos los bits de la IP que no sean innamovibles. Es decir, todos los bits donde en la mascara sean 0.

		Rango de red: 162.3.0.0 - 162.3.127.255

	2. Segmento de red/subred: 162.3.0.0
	3. 162.3.127.255
	4. Rango asignable: 162.3.0.1 - 162.3.0.254
	5. Se toma la direccion IP del segemento de red
		CIDR: 162.3.0.0/17

2. **10.3.48.56.  Mascara: 255.0.0.0**
	1. Rango de red: 10.0.0.0 - 10.255.255.255
	2. 10.0.0.0
	3. 10.255.255.255
	4. Rango asignable: 10.0.0.1 - 10.255.255.254
	5. 10.0.0.0/8

3. **191.100.100.25.  Mascara: 255.192.0.0**
	1. Rango de red: 191.64.0.0 - 191.127.255.255
	2. Segmento de subred: 191.64.0.0
	3. Direccion de broadcast: 191.127.255.255
	4. Rango asignable: 191.64.0.1 - 191.127.255.254
	5. Notacion CIDR: 191.64.0.0/10

4. **200.56.48.9  Mascara: 255.255.255.0**
	1. Rango de red: 200.56.48.0 - 200.56.48.255
	2. Segmento de red: 200.56.48.0
	3. Direccion de broadcast: 200.56.48.255
	4. Rango asignable: 200.56.48.1 - 200.56.48.254
	5. Notacion CIDR: 200.56.48.0/24

5. **25.89.64.72.  Mascara: 255.240.0.0**
	1. Rango de red:  25.80.0.0 - 25.95.255.255
	2. Segmento de red: 25.80.0.0
	3. Direccion de broadcast: 25.95.255.255
	4. Rango asignable: 25.80.0.1 - 25.95.255.254
	5. Notacion CIDR: 25.80.0.0/12

6. 172.16.92.35.  Mascara: 255.255.0.0
	1. Rango de red: 172.16.0.0 - 172.16.255.255
	2. Segmento de red: 172.16.0.0
	3. Direccion de broadcast: 172.16.255.255
	4. Rango asignable: 172.16.0.1 - 172.16.255.154
	5. Notacion CIDR: 172.16.0.0/16


>[!done] Para los gateways, usualmente se asignan la primera asignable o la ultima asignable. Esto para no romper la continuidad de las direcciones asignadas a los equipos


