___

En maquinas de estado *alambradas* se sigue el método tradicional de diseño:
- Obtención del diagrama/tabla de estados
- Especificación del bloque de memoria
	- Numero y tipo de flip flops
- Diseño del bloque combinacional
	- Funciones de activación de los flip flops
	- Funciones de salida

___
Existen diversas herramientas para el diseño:
- Herramientas propietarias de las plataformas de diseño
	- Interpretes de diagramas de estado
- **Plantillas de diseño**

# Estructura de maquina de estados en VHDL

**Modelo de Mealy:**
```vhdl
entity MaquinaEstados is
	Port (Reloj: in std_logic;
		  Reset: in std_logic;
		  Entrada: in std_logic_vector(n downto 0);
		  Salida: in std_logic_vector(m downto 0));
end MaquinaEstados;

architecture Mealy of MaquinaEstados is
	type estados is (lista estados);
	signal EdoPres, EdoSig: estados;
	signal SigSalida: std_logic_vector(m downto 0);
begin
	process(reloj, reset)
	begin
		if reset = '1' then
			EdoPres <= E0;
		elsif rising_edge (reloj) then
			EdoPres <= EdoSig;
			Salida <= SigSalida;
		end if;
	end process;

	process(EdoPres, Entrada) --Decodificacion de Esatdos
	begin
		case EdoPres is
			when E0 =>
				if Entrada = valor1 then
					EdoSig < En;
					SigSalida <= valorA; --Depende de entradas
				elsif Entrada = valor2 then
					EdoSig < Em;
					SigSalida <= valorB;
				...
				else
					EdoSig < Ex;
					SigSalida <= valorX;
				end if;
			when E1 =>
				if Entrada = valor3 then
					EdoSig < Ep;
					SigSalida <= valorC; --Depende de entradas
				elsif Entrada = valor2 then
					EdoSig < Eq;
					SigSalida <= valorD;
				...
				else
					EdoSig < Ez;
					SigSalida <= valorZ;
				end if;
			...
		end case;
	end process;
```

**Modelo de Moore**
```vhdl
entity MaquinaEstados is
	Port (Reloj: in std_logic;
		  Reset: in std_logic;
		  Entrada: in std_logic_vector(n downto 0);
		  Salida: in std_logic_vector(m downto 0));
end MaquinaEstados;

architecture Mealy of MaquinaEstados is
	type estados is (lista estados);
	signal EdoPres, EdoSig: estados;
	signal SigSalida: std_logic_vector(m downto 0);
begin
	process(reloj, reset)
	begin
		if reset = '1' then
			EdoPres <= E0;
		elsif rising_edge (reloj) then
			EdoPres <= EdoSig;
			Salida <= SigSalida;
		end if;
	end process;

process (EdoPres, Entrada)
begin
	case EdoPres is
		when E0 =>
			SigSalida <= valorA;
			if Entrada = valor1 then
				EdoSig <= En;
			elsif Entrada = valor2 then
				EdoSig <= Em;
			...
			else
				EdoSig <= Ex;
			end if;
		when E1 =>
			SigSalida <= valorB;
			if Entrada = valor3 then
				EdoSig <= Ep;
			elsif Entrada = valor4 then
				EdoSig <= Eq;
			...
			else
				EdoSig <= Ez;
			end if;
		...
	end case;
end process;``         
end Moore;
```

**IES Project Navigator**
Examen 7nov: Hasta Cartas ASM