#VLSI #VHDL
Es un tipo muy similar a un *netlist*, usado por herramientas CAD para el intercambio de información.
Un lenguaje de este tipo debe ser capaz de hacer al menos dos cosas:
1. Hacer la definición y la referencia de componentes
2. La especificación de interconexión entre ellos
## Mecanismos de Descripción Estructural en VHDL
### Definición de componentes
Un componente corresponde a una entidad declarada en otra parte del diseño o en biblioteca

```vhdl
component nombre_componente [is]
	[generic (lista_genericos);]
	[port (lista_puertos);]
end component [nombre_componente];
```
La declaración de un componente es igual a la de una entidad
#### Ejemplo:
```vhdl
component rom is
	generic (palabra : integer);
	port (dir: in bit_vector(7 downto 0);
		  dat: out bit_vector(7 downto 0));
end component
```
___
### Referencia de componentes
Instanciación o referencia de componentes consiste en copiar un componente dentro de un arquitectura tantas veces como sea necesario.

```vhdl
etiqueta:
	[component] nombre_componente |
	entity nombre_entidad [(nom_arq)] |
	configuration nombre_configuracion
	[generic map (parametros_genericos)]
	[port map (lista_puertos)];
```
#### Ejemplo:
```vhdl
U2: MedioSumador port map (B, CIn, C, Sum);
U2: MedioSumador port map (Cout => C, T1 => B, I2 => CIn, Sum => Sum);
U2: MedioSumador port map (Cout => open, T1 => B, I2 => CIn, Sum => Sum);
```
- Es posible dejar puertos de salida desconectados usando la palabra `open`
___
### Enlace entre componentes y entidades
Un componente simple es una interfaz sin ninguna funcionalidad. Para que tenga sentido es necesario asociarlo a una entidad y una arquitectura

```vhdl
for lista_refs: nombre_componente
	use entity nombre_entidad [(nom_arq)] |
	use configuration nombre_configuracion
	[generic map (parametros_genericos)]
	[port map (lista_puertos)];
```
- La `lista refs` es una lista separada por comas, y se puede usar `all` y `others` para completar las referencias
#### Ejemplo:
```vhdl
for U1: or2 use entity work.or2;
for all: inv use entity work.inversor;
for U3,U8: and2 use entity c_and2(concurr);
for others: and2 use entity c_and2(algorithm);
```
- Se puede omitir la sentencia `for` si el componente y la entidad tienen el mismo nombre
___
### Repetición de Estructuras
En ocasiones el hardware se compone de muchas estructuras repetidas. En VHDL se puede generar múltiples instancias de un elemento mediante la estructura `generate`

```vhdl
etiqueta:
	for especificacion | if condicion
generate
	[declaraciones
begin]
	[sentencias concurrentes]
end generate [etiqueta];
```
#### Ejemplos

**Clausula `for`**
```vhdl
entity Registro is
	generic (N: positive);
	port (Reloj: in bit;
		  Entrada: in bit_vector(0 to N-1);
		  Salida: out bit_vector(0 to N-1));
end Registro;

architecture Estructural of Registro is
	component FF_D
		port (Reloj, D: in bit;
			  Q: out bit);
	end component;
begin
	GeneraRegistro: for I in 0 to N-1 generate
		Reg: FF_D port map (Reloj, Entrada(I), Salida(I));
	end generate;
end Estructural;
```
___
**Clausula `if`**
```vhdl
--Genera N registros donde solo el primero y el ultimo son distintos
reg_desplazamiento
for I in 0 to N-1 generate
	primero: if (I=0) generate
		pff: FF_D port map (Reloj, Entrada, Conect(I));
	end generate;
	medio: if (I\=0 and I\=N-1) generate
		mff: FF_D port map (Reloj, Conect(I-1), Conect(I));
	end generate;
	ultimo: if (I=N-1) generate
		uff: FF_D port map (Reloj, Conect(I-1), Salida);
	end generate;
end generate reg_desplazamiento;
```
