Links: [[Temario Redes]]
___

El documento de OSI que describe el modelo OSI tiene una segunda parte (ISO7498-2), donde se refiere a la arquitectura de seguridad.
Publicada en 1988 y se proporciona una descripción general de los servicios y mecanismos de la seguridad y sus interrelaciones.

>[!done] Un servicio de seguridad es una necesidad que se tiene para resguardar un bien

Para proteger la comunicación de los usuarios, la arquitectura dice que se debe dotar a dichas comunicaciones de **5 posibles servicios**.

# Servicios de Seguridad
**Servicio de Autenticación:** Corrobora la veracidad de la fuente de una unidad de datos
	*Necesito que no cualquiera entre al sistema*

**Servicio de control de acceso:** Se utiliza para evitar el uso no autorizado de los recursos.

**Servicio de confidencialidad de datos:** Brinda protección contra la revelación deliberada o accidental de los datos en una comunicación
	*Necesito que no cualquiera vea la información*

**Servicio de integridad de datos:** Garantiza que los datos recibidos por el receptor en una comunicación coinciden con los enviados por el emisor.

**Servicio de no repudio:** Proporciona la prueba ante una tercera de cada una de las entidades comunicantes que han participado en una comunicación.

>[!done] Una necesidad (servicio de seguridad) debe ser satisfecha por uno o varios mecanismos

>[!done] Un mecanismo de seguridad es *todo aquello* que me permite implementar un servicio de seguridad

# Servicios de Seguridad
*En esta arquitectura, en otras hay distintos mecanismos*

Para proporcionar servicios de seguridad se debe incorpor  ar mecanismos de seguridad en los niveles apropiados de modelo OSI

La arquitectura de seguridad OSI tiene la siguiente clasificación:
- **Mecanismos de Seguridad específicos:** Aquellos que abarcan un area, consideran una cierta cobertura, o una actividad en particular
- **Mecanismos de seguridad generalizados:** Aquellos que abarcan una cobertura más amplia pues se busca que apliquen a una mayor area o a toda la organización. *Depende del punto de vista o escenario*

## Mecanismos de Seguridad Específicos
- **Mecanismo de cifrado:** Se utiliza para proteger la confidencialidad de los datos

- **Mecanismos de firma digital:** Se emplean par proporcionar una analogia electronica a la firma manuscrita en documentos electrónicos

- **Mecanismo de control de acceso:** Se utiliza para autenticar las capacidades de una entidad. *Todos usan llaves, pero no es la misma - Perritos cuando alguien entra a la casa*

- **Mecanismo de integridad de datos:** Se encargan de proteger la integridad de los datos. 

- **Mecanismo de intercambio de autenticación:** Su finalidad es verificar la identidad de las entidades (Autenticación simple y Autenticación fuerte)

- **Mecanismo de relleno de trafico:** Se utiliza para brindar protección contra ataques de análisis de trafico. 
	  *Es para no ver cuando se manda poca informacion o mucha informacion. Si se manda poca informacion, se manda relleno para siempre mandar la misma cantidad.*

- **Mecanismo de control de encaminamiento:** Permite la selección dinámica o preestablecida de rutas especificas para la transmisión de los datos.

- **Mecanismo de certificación:** Su función es asegurarse de ciertas propiedades de los datos

## Mecanismo de Seguridad Generalizados
- **Mecanismo de funcionalidad de confianza**

- **Mecanismo de etiquetas de seguridad**

- **Mecanismo de detección de eventos**

- **Mecanismo de rastreo de auditoria de seguridad**

- **Mecanismo de recuperación de seguridad**

