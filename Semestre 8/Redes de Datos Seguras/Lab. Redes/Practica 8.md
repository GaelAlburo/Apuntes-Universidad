Links: [[Temario Redes]]
___
rm -rf prac* : remove recursivamente cualquier cosa que empiece por *prac*

Tanto la carpeta como el socket se crea en en usuario, no en superusuario
El socket esta programado en C. Es necesario el compilador *gcc* para que el socket funcione


./sock -e www.fi-b.unam.mx:80
-e: bandera del fin de archivo (*end of file*). Se hara la actividad hasta que se termine la informacion
:80 nos dice que ingrese a la pagina con el puerto 80

GET/ HTTP/1.0: Que obtenga, con el protocolo HTTP,


:22 - puerto SSH

___
Se creara un servidor y un cliente.
Se crearan ambos en la misma maquina

TCP: La informacion no se puede perder y asegura la conexion. Es orientado a la conexion
- C.V. - Canal virtual. 
- Los paquetes estan ordenados, Para que entre un segund paquete el primero debe salir
- Seguridad de que llegue la informacion correcta y completa (No hay perdida de informacion porque hay confirmacion)

Ejemplo: Whatsapp es de tipo TCP

UDP:
- No hay confirmacion de paquetes
- Es expedita pero no hay confirmacion
- Los paquetes no van ordenados. Cuando llegan al destino se ordenan
- No hay canales virtuales (C.V.). Los paquetes pueden llegar por cualquier canal
- No orientado a la conexion

Ejemplo: Streaming es de tipo UDP

____
# Servidor TCP

-l: bandera de *listening*, como escucha. Asi se sabe que este sera el servidor
`./sock -le :1999`

Cliente:
`./sock -e :1999`

Se envian mensajes. Se sabe que es TCP porque se envian y se reciben mensajes, hay comunicacion. En UDP esto no seria posible.

Una vez se corte (Ctrl+C) en el servidor o cliente, en el otro se cortara tambien

____
Servidor
`./sock -l :1998 -d ls`
ls: listar. Dice que todo lo que envie algo, le conteste con los directorios
-l: solo es como escucha, sin el -e. No se pone -e porque no contesta
/
cliente
`./sock -e :1998`

Solo se pone -e porque solo va a mandar

____
Servidor:
`./sock -l :1997 -d date`

Cliente:
`./sock -e : 1997`

___
# Servidor UDP

Servidor:
`./sock -ul :1500`
-ul : La u nos dice que es de UDP

Cliente:
`./sock -u :1500`

Los mensjes escritos en el cliente si se en en el servidor. Pero los mensajes escritos en el servidor no se pueden ver en el cliente


___
# Transferencia de archivos

En TCP no hay errores en la transferenica
En UDP si puede haber errores, y estos no se avisan

### TCP
Servidor
`./sock -l :11000 -d 'cat img1.jpg'`
con `cat` es un comando que concatena

Cliente:
`ssh -l redes 192.168.2.61`
Con este comando se simula que nos estamos conectando a otra maquina (que en este caso es la misma)

Se hace la peticion al servidor desde el cliente:
`./sock -e 192.168.2.61:11000>img2.jpg`

Cuando se ejecuta este el servidor tiene la orden de concatenar la imagen en un nuevo archvio de nombre `img2.jpg`

Cuando se ejecuta el comando `ls -la` se puede ver la imagen nueva con el mismo tamano que la original. TCP transfirio correctamente el archivo sin errores


### UDP
Se sabe que es UDP por la bandera `-u`
Servidor:
`./sock -ul :12000>img2.jpg`

Cliente:
Se vuelve a conectar ahora con UDP
`ssh -l redes 192,168.2.61`

Se solicita al servidor:
`cat img1.jpg | ./sock -u 192,168.2.61:12000`