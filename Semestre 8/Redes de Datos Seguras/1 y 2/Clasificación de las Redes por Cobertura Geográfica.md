Links: [[Temario Redes]]
___
Originalmente se consideraron los siguientes espacios. Actualmente estos valores son modificados debido a las innovaciones tecnológicas.
Esto también cambia por los cambios geográficos, creacion de paises, consideracion de territorios, etc.

| Distancia entre procesadores | Abarca                | Red                               |
| ---------------------------- | --------------------- | --------------------------------- |
| 1m                           | $m^2$                 | PAN (*Personal Area Network*)     |
| 10 m                         | Habitacion-Habitacion | LAN (*Local Area Network*)        |
| 100 m                        | Edificio              | LAN                               |
| 1 km                         | Campus                | LAN                               |
| 10 km                        | Ciudad                | MAN (*Metropolitan Area Network*) |
| 100 km                       | Pais                  | MAN                               |
| 1000 km                      | Continente            | WAN (*Wide Area Network*)         |
| 10,000 km                             | Planeta                      | GAN (*Global Area Network*)                                  |

Las distancias no deben de ser exactas, pueden ser mas o menos.

LAN conecta varios PAN
MAN conecta varios LAN
WAN conecta varios MAN
GAN conecta varios WAN

El internet conecta a todas. No nos interesa exactamente el lugar, país, solo importa que la conexión se mantenga y se llegue la información.

La nomenclatura mas utilizada es la LAN.

___
# Características
No se incluye la PAN por el tamano, se consideran las que pueden soportar mas dispositivos

|      | LAN y MAN                  | WAN y GAN              |
| ----------- | -------------------------- | ---------------------- |
| ENLACES    | Privados                   | Publicos               |
| VELOCIDADES | Altas                     | Bajas                  |
| ERRORES     | Menos y controlados        | Altas tasas de errores |
| TOPOLOGIAS  | **Estrella**, anillo y bus | Arbol, malla, hibridas |
| PROTOCOLOS            | Token, **ethernet**                           | TCP/IP                       |

**ENLACES:**
- En los enlaces entran los medios de transmisión.
- En LAN y MAN los enlaces son privados, es decir, se pueden tomar decisiones
- En servicios externos, como TELMEX o IZZI, no podemos decidir que medio de transmisión se usaran
- En cambio, en WAN y GAN, no se pueden tomar decisiones propias, se debe generar un consenso

> [!done] Mientras mas se acerque en la red, se pueden tomar decisiones, mas alejado mas complicado, al ser publico.

**VELOCIDADES:**
- Mientras mas cercana la red, LAN y MAN, se puede decidir sobre la velocidad al elegir un cierto medio de transmisión
- En las otras, WAN y GAN, se debe tomar en cuenta que decisiones se tomaron en redes locales.
- En las publicas la velocidad depende de la infraestructura

**PROTOCOLOS**
- En el TCP/IP también se incluye el ethernet, pero incluye otros

