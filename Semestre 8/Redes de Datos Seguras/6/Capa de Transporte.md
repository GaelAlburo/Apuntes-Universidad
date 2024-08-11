Links: [[Temario Redes]]
___

Es la encargada de la **transferencia libre de errores** en los datos entre el emisor y el receptor

**Mantiene el flujo de la red** y **proporciona un transporte de datos confiable y económico** del origen al destino
Los procesos de la capa de transporte se llevan a cabo entre la capa de aplicación y la de Internet en el modelo TCP/IP y entre la capa de sesión y la capa de red en el modelo OSI.

___
# Tipos de Servicio

### Servicios orientados a la conexión
- Considera 3 fases: Establecimiento, Mantenimiento (Transferencia) y Liberación
- Se emplean canales virtuales
- La información se envier por los canales virtuales
- Los paquetes viajan ordenados **(FIFO)**
- Detecta errores **ACK/NACK** 
- Existe retransmisión
- No es tan rápida (se mantiene aun en ms) por la confiabilidad

### Servicios no orientados a la conexión 
- No se utilizan canales virtuales
- Los paquetes se manejan de manera individual y viajan por cualquier camino hacia su destino
- Los paquetes pueden llegar en desorden
- Es mas rápido pero no tan confiable
- No hay retransmisión
- Puede haber perdidas de información
- No hay mensajes de confirmación
___
# Primitivas en Transporte
Estas se emplean en un transporte sencillo:
- LISTEN
- CONNECT
- SEND
- RECEIVE
- DISCONNECT

___
# Funciones Principales de la Capa de Transporte

Para manejar los paquetes esta capa cumple con 3 funciones principales:

1. **Fragmentación de paquetes o Segmentación del mensaje**
Acepta un mensaje de la capa de sesión
El mensaje se divide en unidades mas pequeñas (de ser necesario) y estas unidades mas pequeñas las envía hacia la capa de red.
La capa de transporte en la estación de destino permite volver a unir el mensaje.

2. **Secuenciamiento**
-Mensaje de Confirmación: Proporciona la entrega de mensajes confiable de extremo a extremo con las confirmaciones

-Control de trafico de mensajes: Indica a la estación transmisora que repita cuando no hay búferes de mensajes disponibles

-Multiplexion / Multiplexación de sesión: Multiplexa varias secuencias de mensajes o las sesiones en un vinculo lógico y realiza un seguimiento de los mensajes que pertenecen a las sesiones.

3. **Reensamble o Reensamblaje de paquetes o segmentos**
Los protocolos de esta capa describen como se usa la información de encabezado para reensamblar las secciones de datos en paquetes y enviarlos a la capa de aplicación

	Reensamblaje -> Wrap
	Fragmentacion -> Unwrap

