Links: [[VLSI]]
___

Cada objeto debe ser de un tipo concreto, lo que determina el conjunto de valores que puede asumir y las operaciones que se pueden realizar con el

Para definir un tipo de dato:
```vhdl
type identificador is definicion_tipo;

type DiaMes is range 1 to 31;
type PuntosCardinales is (norte, sur, este, oeste);
type Calificacion is range 0.0 to 10.0;
```

> [!done] Los tipos de datos de VHDL se definen en bibliotecas

___
# Tipos Predefinidos (paquete estándar)

- **Escalares** - El rango de valores depende de la plataforma
    - INTEGER
    - REAL
- **Enumerados**
    - CHARACTER - 128 caracteres ASCII
    - BOOLEAN - FALSE, TRUE
    - BIT - ‘0’ y ‘1’
- **Arreglos**
    - STRING - Arreglo de caracteres
    - BIT_VECTOR - Arreglo de bits
- **Físicos**
    - TIME - Especifica unidades de tiempo

# Tipos Predefinidos (IEEE 1164)

- Escalares
    - STD_LOGIC
    - STD_ULOGIC
- Arreglos
    - STD_LOGIC_VECTOR
    - STD_ULOGIC_VECTOR

___
# Valores Lógicos IEEE 1164

- ‘U’ - Uninitialized state
- ‘X’ - Forcing Unknown
- ‘0’ - Forcing Zero
- ‘1’ - Forcing One
- ‘Z’ - High Impedance → Circuito abierto
- ‘W’ - Weak Unknown
- ‘L’ - Weak Zero
- ‘H’ - Weak One
- ‘-’ - Dont Care

> [!done] Alta Impedancia - Tanta resistencia que no permite paso de corriente, como si fuera un circuito abierto

___
# Tipos Compuestos

Son aquellos cuyos valores se pueden dividir en unidades mas pequeñas

- **Vectores**
    - Los elementos que lo forman son del mismo tipo
- **Registros**
    - Los elementos que lo forman son un conjunto de objetos diferentes

## Vectores

Del mismo tipo, ordenados mediante uno o mas indices para indicar la posicion de cada objeto
```vhdl
type identificador is array (rango {, ...}) of tipo;

type Byte1 is array (7 to 0) of bit; --Secuancia de indices ascendente. 0,1,2,3
type Byte1 is array (7 downto 0) of bit; --Secuancia de indices descendente. 3,2,1,0

variable Operador1 : Byte1; --Operador1 de tipo Byte1
Operador1 := "01101010";
Operador1(2) := '1';
Operador1(3 to 6) := "1010";

type Memoria is array (0 to 7, 0 to 63) of bit; --Arreglo multidimensional 2D
```

- Se puede asignar valores a un conjunto al mismo tiempo
```vhdl
([posicion {| ...} => ] literal {, ...})

type Coordenada is (X, Y, Z);
type Punto is array (X to Z) of real;
constant Origen : Punto := (0.0, 0.0, 0.0)
constant Punto1 : Punto;
Punto1 := (1 => 2.5, 2 => 7.3, 3=> 2.5); --No importa el orden en que se asignan
Punto1 := (1 | 3 => 2.5, 2 => 7.3);

Punto1 := (2 => 7.3, **others** => 2.5); --Todos las posiciones != 2, valor = 2.5
--La clausula ************others************ se debe usar al ultimo, si es dentro de una lista
```

## Registros

Formado por unidades atómicas de distinto tipo, llamadas *campos*. Los *campos* no se referencian con un índice, sino con un *identificador*
```vhdl
type identificador is record
	identificador {, ...} : tipo;
	{...}
end record [identificador];
---------------------------------
type Fecha is record
	Dia : integer range 1 to 31;
	Mes : integer range 1 to 12;
	Anio : integer range 1 to 2100;
end record;
variable Hoy, Ayer : Fecha;

Ayer.Dia := 15; Ayer.Mes := 5; Ayer.Anio := 2012;
Hoy := Ayer;
Hoy := (5, 6, 2012);
Hoy := (Dia => 5, Mes => 6, Anio => 2012);
```

___
# Subtipos de Datos

Son subconjuntos de tipos existentes.
```vhdl
subtype identificador is tipo definicion;
```

**Heredan las operaciones del tipo original**
```vhdl
subtype otro is integer range 5 to 11;
subtype natural is integer range 0 to mayor_entero;
subtype id id string (1 to 20);
```

___
# Cualificacion de tipos

Cuando un elemtno puede ser de distinos tipos, se puede especificar el tipo al que corresponde
```vhdl
tipo'(valor)
----------------
bit'('0');
character'('0');
```

___
# Conversion de tipos

> [!done] En una operacion todos los operandos deben ser del mismo tipo

Las conversiones deben hacerse de forma explicita
```vhdl
tipo(valor)
-------------
integer(3.14); --3
real(16); --16.0
```

Solo se pude hacer conversiones directamente entre numeros, entre vectores y cadenas. Siempre y cuando sean del mismo tipo y dimensiones

Cuando no se pueden hacer directamente, hay que hacer funciones para ello
```vhdl
to_stdlogicvector (bit_vector);
conv_std_logic_vector (integer, num_bits);
conv_integer (std_logic_vector);
```

____
# Atributos

Los elementos pueden tener informacion adicional
```vhdl
elemento'atributo
```

Hay varios atributos predefinidos. Dependen de la clase de elemento
- Atributos de un tipo enumerado, entero, flotante o fisico:
```vhdl
t'left --Valor a la izquierda
```

- Atributos de un vector, y _N_ un numero dentro de las dimensiones
- Atributos de una senal
---

## Atributos definidos por el usuario

```vhdl
attribute nombre : tipo; --Definicion
attribute nombre of elemento : clase_elemento is valor; --Asignacion
---------------------------------------------------------------------
signal control : std_logic;
component ne555 ... end component;

attribute pin : integer;
attribute encapsulado : string;

attribute pin of control : signal is 5;
attribute encapsulado of ne555 : component is "dip8";
```
