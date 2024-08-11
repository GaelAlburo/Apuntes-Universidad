#VLSI #VHDL 
### Asignación a señal
Cuando se utiliza como una sentencia secuencial (en un proceso o subprograma) tiene la siguiente sintaxis:
```vhdl
[etiqueta :] nombre_señal <= valor {after expresion_tiempo};
```
No es posible usarlo en compilación para tarjeta DE10-Lite.

Las señales son objetos que consisten en un valor actual y un conjunto de pares tiempo-valor que forman una cola de eventos de la señal.
La asignación del nuevo valor se producirá hasta que haya pasado un retardo delta, aun cuando no se especifique un retardo.
##### Ejemplo: Intercambio de valor de dos señales
					process
					begin
						a <= b;
						b <= a;
						wait on a, b;
					end process;
El intercambio se puede realizar porque al momento de hacer la segunda, aun no se refleja la primera asignacion, solo se agrega a la cola de eventos de la señal.
Es hasta la suspension de **wait** que se realiza el intercambio.

---
### Asignación a variable
Reemplaza el valor actual con el valor especificado por una expresión
```vhdl
[etiqueta :] nombre_variable := expresion;
```
La asignación a variable es instantaneo.
Es necesario utilizar una variable temporal para intercambiar valores de dos variables.
___
### Sentencia if
Escoge en funcion de una condicion que conjunto de sentencias deben ejecutarse
```vhdl
if condicion then
	sentencias_secuenciales
{elsif condicion then
	sentencias_secuenciales}
[else 
	sentencias_secuenciales]
end if;
```
___
### Sentencia case
Se utiliza para escoger el grupo de sentencias que se ejecutara de entre un grupo de posibilidades, a partir del rango de valores que tome una expresion
```vhdl
[etiqueta :] case expresion is
	when valor =>
		sentencias_secuenciales;
	end case;
```

Se pueden utilizar listas o rangos de valores para seleccionar que sentencias se ejecutaran
```vhdl
process
begin
	case Seleccion is
		when "00"|"01" =>
			Salida <= E1;
		...
	end case;
	wait on Seleccion, E1, E2, ...;
end process;
```
- No puede haber valores repetidos en las opciones. 
- Todos los valores posibles deben ser considerados en las opciones.

Es posible usar la opción **others** para representar los valores no considerados. **Debe ser la ultima en la lista**.
___
### Sentencia *loop*
Ejecuta un conjunto de sentencias secuenciales de forma repetida
```vhdl
[etiqueta :] [while condicion booleana
			 | for control de repeticion] loop
	sentencias_secuenciales
end loop [etiqueta];
```
- El numero de repetición esta determinado por las opciones de control

#### Ejemplos
##### Ciclo infinito
```vhdl
entity Contador_0_15 is
port (Reloj : in bit;
	 Cuenta : out natural);
end Contador_0_15;

architecture Ejemplo of Contador_0_15 is
	signal Contador : natural;
begin
	process
	begin
		Contador <= 0;
		loop
			wait until Reloj='1';
			Contador <= (Contador + 1) mod 16;
		end loop;
	end process;
	Cuenta <= Contador; --Instruccion concurrente, no se afecta por el ciclo
end Ejemplo;
```
##### Clausula *while*
```vhdl
entity Contador_0_15 is
port (Reloj : in bit;
	 Cuenta : out natural);
end Contador_0_15;

architecture Ejemplo of Contador_0_15 is
	signal Contador : natural;
begin
	process
	begin
		Contador <= 0;
		wait until Reloj = '1';
		while Contador < 15 loop
			Contador <= Contador + 1;
			wait until Reloj='1'; --Clausula de control
		end loop;
	end process;
	Cuenta <= Contador; --Instruccion concurrente, no se afecta por el ciclo
end Ejemplo;
```
##### Clausula *for*
```vhdl
entity Contador_0_15 is
port (Reloj : in bit;
	 Cuenta : out natural);
end Contador_0_15;

architecture Ejemplo of Contador_0_15 is
	signal Contador : natural;
begin
	process
	begin
		Contador <= 0;
		for I in 1 to 15 loop
			wait until Reloj='1';
			Contador <= Contador + 1;
		end loop;
	end process;
	Cuenta <= Contador; --Instruccion concurrente, no se afecta por el ciclo
end Ejemplo;
```

___
### Sentencia *exit*
Termina con un ciclo.
```vhdl
[etiqueta :] exit [etiqueta_loop] [when condicion_booleana];
```

Cuando se tienen varios ciclos anidados, la sentencia *exit* se utiliza para salir de aquel que se indique por la etiqueta.
___
### Sentencia *next*
Se utiliza para detener la ejecucion del ciclo y pasa a la siguiente iteracion
```vhdl
[etiqueta :] next [etiqueta_loop] [when condicion_booleana];
```
#### Ejemplo
```vhdl
process
begin
	Contador <= 0;
	for I in 0 to 15 loop
		next when I=8;
		Contador <= I;
		wait until Reloj = '1';
	end loop;
end process;
```


___
