Links: [[Temario Redes]]
___

Provee los servicios utilizados para:
- La organización
- La sincronización

Del dialogo entre usuarios y el manejo e intercambio de datos

___
# Características
- Establece el inicio y termino de la sesión
- Recuperación de la sesión
- Controla el dialogo (se mantiene la sesión para completar la transmisión)
- Referencia a los dispositivos por nombre (depende de la aplicación)

1. Se establece la sesion, mantenimiento y finalizacion en equipos diferentes
2. Se establece, utiliza y termina una conexión (sesión)
3. Se permite la compatibilidad con sesiones a traves de la red (independientemente del HW y el SW (aplicación) )

____
# Control de Dialogo
Controla quien debe transmitir en un momento dado
- Permite la sincronización (usa checkpoints)
- El control puede ser full duplex, half-duplex

____
# Agrupamiento
El flujo de datos se puede marcar y agrupar para definir grupos de datos

___
# Recuperación o sincronización

____
# Notificación de Excepciones
Mecanismo de propósito general para notificar errores inesperados

____
# Diagramas *Handshaking*
	 Diagramas cuaderno

____
# Llamada a procedimiento remoto (RPC - *Remote Procedure Call*)

Es un protocolo que permite a un programa de computadora ejecutar código en otra maquina remota
**Paradigma cliente-servidor**

Se necesitan diez pasos para ejecutar un RPC
![[Pasted image 20240520115420.png|center|400]]

1. Una aplicación cliente ejecuta una llamada a procedimiento a un stub cliente
> [!info] *Stub*: Porción de un programa cliente o servidor que ejecuta el encapsulamiento de datos y rutinas de transporte de red

2. El *stub* cliente llama a las funciones de red del kernel del S.O. para enviar el mensaje

3. El kernel envía el mensaje al sistema remoto

4. El *stub* del servidor desempaqueta los argumentos del mensaje de red convirtiéndolos en la representación de datos propia del servidor

5. El *stub* del servidor llama a la aplicación local del servidor que realiza la ejecución

6. El procedimiento completa regresando los resultados de la ejecución al *stub* servidor

7. El *stub* empaqueta los valores de regreso

8. El mensaje de regreso es enviado

9. El *stub* cliente lee el mensaje utilizando las funciones de red suministradas por el kernel del S.O.

10. El mensaje es desempaquetado y presentado al cliente