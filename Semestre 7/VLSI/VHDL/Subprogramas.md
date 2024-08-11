Links: [[VLSI]]
___

Para el desarrollo de proyectos complejos es necesario organizar el código relacionado.
VHDL permite estructurar el código mediante el uso de subprogramas.

Un subprograma es una **función** o un **procedimiento** que contiene una porción de código.

___
# Función v. Procedimiento

| Función                                                      | Procedimiento                                              |
| ------------------------------------------------------------ |:---------------------------------------------------------- |
| Siempre devuelve un valor                                    | Sólo puede devolver valores a través de los parámetros     |
| Sus argumentos siempre son de entrada                        | Sus argumentos pueden ser de entrada o bidireccionales     |
| No puede provocar cambios en elementos externos              | Se pueden provocar cambios en elementos externos (señales) |
| Se usan en una expresión (devuelven valor)                   | Se llaman como una sentencia secuencial o concurrente      |
| Debe contener la sentencia `return` seguida de una expresión | Puede contener la sentencia `return` sin valor de retorno  |
| No puede contener la instrucción `wait`                      | Se puede contener la instrucción `wait`                    |

___
# Definición de un Procedimiento
Se realiza en la zona declarativa del elemento donde está contenida (arquitectura, bloque, etc.)
```vhdl
procedure nombre [(parametros)] is
	[declaraciones]
begin
	[sentencias_seriales]
end [procedure] [nombre];
```

___
# Definición de una Función
Se realiza en la zona declarativa del elemento donde está contenida. Se declara el tipo del valor del retorno
```vhdl
[pure | impure]
function nombre [(parametros)] return tipo is
	[declaraciones]
begin
	[sentencias_seriales] --Debe incluir al menos un return
end [function] [nombre];
```

___
# Lista de Parámetros
Tanto en procedimientos como en funciones, esta lista es opcional.
Es una lista separada por punto y coma.

```vhdl
[clase] nombre: [modo] tipo
--Donde:
clase - constant, variable, signal
modo - in, out, inout
```

| Función                                                                | Procedimiento                                                                       | 
| ---------------------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| Sólo es válido el modo `in`, se puede omitir                           | Por defecto el modo es `in`, pero `out` e `inout` son válidos                       |
| Un parámetro por defecto es de la clase `constant`, puede ser `signal` | Por defecto la clase es `constant` para el modo `in`, y `variable` para otros casos |

No es aconsejable usar señales como parámetros debido a como se asignan valores.
Además, algunos atributos no se pueden utilizar al interior de funciones.

___
# Características Subprograma

En un subprograma se pueden incluir las mismas sentencias que se usan en un proceso, se trata como un bloque de ejecución secuencial.

No se pueden declarar señales al interior del subprograma

Los elementos que se declaren dentro sólo serán visibles dentro del mismo

En las funciones, la declaración `pure` o `impure` es opcional y no tiene efecto en el funcionamiento de la función

___
# Declaración de Procedimientos y Funciones

Por visibilidad, es necesario declarar el subprograma antes de definirlo

**Procedimiento:**
```vhdl
procedure nombre [(parametros)];
```

**Función:**
```vhdl
[pure|impure] function nombre [(params)]
return tipo;
```

#### Ejemplo:
```vhdl
procedure limites (constant conjutno: in vector;
				   variable min, max: inout integer) is
--procedure limites (conjunto: vector;
--					min, max: inout integer) is
	variable I: integer;
begin
	min = conjunto(conjunto'left);
	max = conjunto(conjunto'right)
	for I in conjunto'range loop
		if min > conjunto(I) then
			min := conjunto(I);
		end if;
		if max < conjunto (I) then
			max := conjunto (I);
		end if;
	end loop;
end limites;
```