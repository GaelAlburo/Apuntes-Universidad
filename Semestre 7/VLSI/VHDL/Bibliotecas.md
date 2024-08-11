Links: [[VLSI]]
___

Los elementos que pueden ser usados en una aplicación están organizados dentro de bibliotecas
En cualquier sistema existen dos bibliotecas que no necesitan ser invocadas:
- *work*

En las bibliotecas los elementos que la forman se llaman **unidades de diseno**, hay dos tipos:
- **Primarias:** Son de tipo declarativo
	- Entidades
	- Paquetes
	- Configuraciones
- **Secundarias:** De tipo ejecutivo
	- Arquitecturas
	- Cuerpos de los paquetes
___

# Unidades Primarias
- **Entidad**
	- Define la interfaz de un modulo
- **Paquete**
	- Parte declarativa de un almacén de tipos y subprogramas
- **Configuracion**
	- Guarda información sobre la relación de componentes con entidades y arquitecturas

# Unidades Secundarias
- **Arquitectura**
	- Describe el comportamiento de un circuito
- **Cuerpo del paquete**
	- Definición de los elementos de un almacén de tipos y subprogramas

___
La descripción de las unidades se guarda en uno o varios archivos. Cada uno es un *archivo de diseño*

Para sintetizar o simular una aplicación en VHDL, se compilan los archivos de diseño y el resultado constituye de la *biblioteca de diseño*

Al compilar una aplicación, el resultado son integrados a la biblioteca *work*
En VHDL no existe una forma definida para las bibliotecas, depende de cada plataforma.

___
# Paquetes
Colección de declaraciones de tipos, constantes, subprogramas, etc., que son agrupados con la intención de implementar algun servicio o aislar un grupo de elementos relacionados
Un paquete hace visible las interfases de algunos elementos, dejando oculta su descripción

Un paquete se divide en dos partes:
- Declaraciones
- Cuerpo (Definiciones)

```vhdl
--Declaracion del paquete
package nombre is
	[declaraciones]
end [package] [nombre];

--Declaracion del cuerpo
package body nombre is
	declaraciones
	subprogramas, etc.
end [package body] [nombre];
```

___
Una vez declarado el paquete, sus elementos se referencian mediante su nombre y el elemento:
```vhdl
variable pc: work.personal.direccion;
pila := work.personal.inicio + x"FF";
desp := work.personal.datotoint(reg);
```

Se puede simplificar su uso haciendo visible el paquete:
```vhdl
use. work.personal.ALL;
-------
variable pc: direccion;
pila := inicio + x"FF";
desp := datotoint(reg);
```

___
# Unidad de Configuración
Para hacer el enlace de un componente y una entidad (con su arquitectura) se  puede hacer mediante un `for` y un `use`. Esto representa una especificación de configuración, lo que se puede hacer en bloque de configuración.

```vhdl
configuration nombre_conf of nombre_entidad is
	{sentencia_use |
	def_atributo   |
	def_grupos}
	configuracion_bloque
end [configuration] [nombre_conf];
```

Bloque de configuracion:
```vhdl
for especificacion_bloque
	{sentencia_use}
	{conf_bloque | conf_componente}
end for;
```

#### Ejemplo:
```vhdl
configuration sumador_funcional of suma is
	for funcional  --nombre de la arquitectura
	end for;
end configuration sumador_funcional;
```

