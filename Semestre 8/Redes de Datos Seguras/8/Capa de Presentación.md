Links: 
___
Se encarga de la representación de la información, de manera que aunque distintos equipos puedan tener diferentes representaciones internas de caracteres, números, sonido o imágenes, los datos lleguen de manera reconocible.

____
# Funciones la Capa de Presentación
- Formato de datos
- Cifrado de datos
- Compresión de datos

![[Pasted image 20240522112123.png|center|350]]
____
## Formato de Datos (Formateo)
Opera como traductor entre dos tipos distintos de códigos cuando dos sistemas diferentes emplean distintos códigos.
Es indispensable que se comuniquen y su representación en pantalla sea la misma.

Ejemplos de Códigos:
- ASCII
- EBCDIC
- Unicode

____
## Cifrado de Datos
Protege la información durante la transmisión.
Se utilizan claves de cifrado para cifrar los datos en el lugar de origen y luego descifrarlos en el lugar destino.

Para cifrar los datos se emplea la criptografía. 
Actualmente se encarga del estudio de los algoritmos, protocolos y sistemas que se utilizan para dotar de seguridad a las comunicaciones, a la información y a las entidades que se comunican.

Criptologia:
- Criptografía (+)
- Criptoanálisis (-) : Trata de descifrar de manera ilícita
- Esteganografía: Info oculta dentro de otra

La criptografía se basa en la teoría de la información, conocida también como teoría matemática de la información o comunicación. Es una propuesta teórica presentada por Claude E. Shannon y Warren Weaver en 1948.

La criptografía moderna emplea técnicas modernas de cifrado:
- Confusion $\rightarrow$ Sustituciones
- Difusión $\rightarrow$ Permutaciones

El objetivo es la criptografía  es diseñar, implementar, implantar y hacer uso de sistemas criptográficos para dotar de alguna forma de seguridad.
Las propiedades de las que se ocupa la criptografía son:
- Confidencialidad
- Integridad
- Vinculación
- Autenticación

2 tipos de criptografia:
- Simetrica: Clave privada o clave secreta
	- Se usa una clave: para cifrar y descifrar
	- Se usa para cifrar información. No usa tantos recursos
	- Ejemplo: AES
- Asimétrica: Clave publica
	- Se usan dos claves: Publica y Privada
	- Se usa para cifrar claves
	- Ejemplo: RSA

Un sistema de cifrado i criptograma se representa de la siguiente manera:
- K: Clave / Llave / Key
- Mcla: Mensaje en claro

![[Pasted image 20240522122450.png|center|300]]
___
## Compresión de Datos
Funciona mediante el uso de algoritmos para reducir el tamaño de los archivos

La información que transmiten los datos puede ser de tres tipos:
- **Redundante:** Información repetitiva o predecible
- **Irrelevante:** Información que no se aprecia y cuya eliminación no afecta al contenido del mensaje
- **Básica:** Es relevante y debe ser transmitida para que se pueda reconstruir la señal.

### Tipos de Compresión:
- **Compresión con perdidas (*Lossy*)**
	- Puede eliminar datos para disminuir el tamaño, pero se reduce la calidad
	- Una vez realizada la compresión, no se puede obtener el original, aunque si una aproximación
	- Se usa principalmente en imágenes, videos y sonidos

- **Compresión sin perdidas (*Lossless*)**
	- Los datos antes y después son exactos
	- Se utiliza principalmente en la compresión de texto
	- Se divide en dos:
		- **Sin perdidas realies:** Se transmite toda la entropia del mensaje (toda la informacion basica e irrelevante pero eliminando la redundancia)
		- **Subjetivamente sin perdidas:** Además de eliminar la información redundante se elimina también la irrelevante.

>[!info] Entropía: Incertidumbre.   Entre mas información tenga menos incertidumbre. Entre menos información mas incertidumbre.


