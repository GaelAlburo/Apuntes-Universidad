Links: 
___

TCP/IP: *Transmission Control Protocol / Internet Protocol*
IP: Nomenclatura para representar un dispositivo en la web
- IPV6: Dirección IP de 128 bits

El modelo TCP/IP combina varias capas del modelo OSI. En lugar de tener 7 capas, tiene 4 capas.
Cada una de estas se encarga de determinados aspectos de la comunicación y a su vez brinda un servicio especifico a la capa superior.
![[Pasted image 20240214112013.png|center|350]]

___
## Capa de acceso a red (Capa de host / host a red)
En esta capa se manejan todas las características que un paquete IP requiere para el enlace físico, es decir, que medio de transmisión se usara.

Da detalles de las tecnologías WAN y LAN, así como la manera en la que se enlazan los datos con el medio de transmisión

## Capa de internet / interred
Tiene como finalidad seleccionar la mejor ruta para transmitir los paquetes por la red, de tal forma que pase por la menor cantidad de routers en el menor tiempo posible.

El protocolo principal que opera en esta capa es el protocolo de internet (IP)

## Capa de transporte
Se establece una conexión lógica entre el host transmisor y el host receptor.

Los protocolos de transporte dividen los datos en el host origen para que las capas inferiores realicen el envío y una vez que llegan a su destino, son ensamblados para obtener el mensaje original, teniendo un **transporte de extremo a extremo**

Los protocolos son: TCP y UDP (*User Datagrama Protocol*; Protocolo de Datagramas de Usuario)
- TCP: Internet Relay Control (IRC)
- UDP: Streaming, DNS
## Capa de aplicación
Maneja protocolos de alto nivel que permiten la representación de los datos, codificación y control de dialogo (aplicación, transporte y sesión en OSI).

Algunos de los protocolos que operan en esta capa son:
- FTP (*File Transfer Protocol*)
- TFTP (*Trivial Transfer Protocol*)
- NFS (*Network File System*)
- SMTP (*Symbol Mail Transfer Protocol*)
- TELNET - Envío y recepción de información. INSEGURO
- SNMP (*Simple Network Management Protocol*)
- DNS (*Domain Name System*) 