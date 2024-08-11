Links: [[Inteligencia Artificial]], [[4. Conocimiento]]
___

- Estructuras del conocimiento
- Describen objetos o conceptos
- Contienen atributos (**slots**) y sus valores
- los atributos pueden tener procedimientos (**demons**)
- Los marcos tienen jerarquía
- Las relaciones de herencia establecen la inferencia
	- *es-un (clase / subclase)*
	- *instancia-de (instancia / clase)*

![[Pasted image 20230925185104.png | 500]]

## Estructura de un *Slot*
- **Nombre**
	- Cada *slot* tiene un nombre único en el *Frame*
- **Valor del *slot***
	- Puede ser inicializado o vacío para darle valor en procesos de búsqueda y razonamiento
- **Procedimientos anexos**
	- **If-needed**
		- Antes de obtener el valor del *slot* en una consulta, se debe ejecutar el procedimiento con éxito
	- ***If-added***
		- Antes de asignar un valor al *slot*, se debe ejecutar con éxito el procedimiento
	- ***Id-deleted***
		- Antes de borrar el valor del *slot* se debe ejecutar con éxito el procedimiento