Links:
___

# Protocolo de Control de Transmisión (TCP)

Proporciona un servicio completo y fiable, descrito en la RFC 793.
Cada segmento de TCP posee 20 bytes de carga en el encabezado

**Características**:
- Protocolo orientado a la conexión
- Entrega confiable
- Control de flujo
- Mecanismos de enlace, temporizadores y acuses de recibo y uso dinámico de ventanas
- La confiabilidad implica  cierta sobrecarga en el tamaño de los encabezados y mayor trafico entre el origen y el destino

Ejemplos:
- Navegador web (80)
- Correo electronico (25)
- Pop3 (110)
- Transferencia de archivos - FTP (21)
- IRC (194)

![[Pasted image 20240508121537.png]]
![[Pasted image 20240508121646.png]]
___
# Protocolo de Datagramas de Usuario 

Protocolo que genera procos gastos y se utiliza para las aplicaciones que no requieren un envio de datos confiable
No orientado a la conexión descrito en la RFC 768, solo posee 8 bytes de carga

- No rastrea la recepción de datagramas en el destino, solo envia los datagramas recibidos a la capa de aplicación a medida que legan y no reenvia datagramas perdidos. Por eso es mas rápido y ligero
- Proporciona un servicio de datagrama poco fiable

Ejemplos:
- Sistema de nombres de dominio (DNS)
- Streaming de video (5004)
- Voz sobre IP (5060)
- TFTP (69)

![[Pasted image 20240508121802.png]]

___
# Protocolo de Transmisión para el Control de Flujo (SCTP - *Stream Transmission Control Protocol*)

- Proporciona un servicio completo y fiable
- Ofrece los mismos servicios a las aplicaciones que TCP
- Admite conexiones entre sistemas que tienen mas de una dirección (host multiple)
- La conexión entre el transmisor y receptor se denomina asociación
- Los datos de la asociación se organizan en bloques

Ejemplos:
- Streaming

![[Pasted image 20240508122319.png|center]]
___
