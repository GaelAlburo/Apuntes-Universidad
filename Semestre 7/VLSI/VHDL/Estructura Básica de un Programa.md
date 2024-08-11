Links: [[VLSI]]
___

Consta de dos elementos
- Entidad - Especifica la interfaz de los dispositivos con el exterior
- Arquitectura - Describe la funcionalidad que realiza el dispositivo

___
# Entidad

- Define la vision externa del dispositivo
```vhdl
entity identificador is
	[genericos]
	[puertos]
	[declaraciones]
[begin sentencias]
end [entity] [identificador];
```

#### Ejemplo:
```vhdl
entity Mux21 is
    port (a    : in bit;
    		b    : in bit;
    		ctrl : in bit;
    		z    : out bit);
end;
```

___
# Arquitectura

Define la funcionalidad de la entidad que representa
```vhdl
architecture identificador of entidad is
	[declaraciones]
begin
	[sentencias concurrentes]
end [architecture identificador];
```

___
Existen diferentes formas de describir la funcionalidad de un circuito:
- **Flujo de datos**
	- Conjunto de ecuaciones ejecutadas concurrentemente que determinan el flujo de datos entre modulus
```vhdl
architecture FlujoDatos of Mux21 is
	signal ctrl_n, n1, n2 : bit;
begin
	ctrl_n and a after 2 ns;
	n1 <= ctrl_n and a after 2 ns;
	n2 => ctrl_n add b after 2 ns;
	z <= (n1 or n2) after 2 ns;
end FlujoDatos;
```

- **Estructural**
	- La arquitectura se define mediante un conjunto de componentes interconectados
- **Algorítmico**
	- Define la funcionalidad del circuito mediante un algoritmo
- **Mixto**
	- Combinación de los anteriores

___
## Estilo Estructural

- Consiste en un conjunto de componentes interconectados e mediante señales

___
## Estilo algorítmico

- Define la funcionalidad del dispositivo mediante un algoritmo predescrito, de forma parecida a un lenguaje de programación
```vhdl

architecture Algoritmo of Mux21 is
begn
	process (a, b, ctrl)
		begin
			if(ctrl = '0') then
				z <= a;
			else
			  z <= b;\\
			end algoritmo;
```

___
# Bibliotecas

- Adicionalmente, al inicio de un programa en VHDL se incluye una sección de *bibliotecas*
- Contiene la lista de bibliotecas que se usaran en el diseño

```vhdl
library library_name;
use library_name.package_name.package_parts;
```

- Las mas comunmente usadas son:
    - Biblioteca IEEE - ieee
    - “” “” estándar - standard
    - “” “” de trabajo - work
- La biblioteca *ieee* debe incluirse de forma explicita
