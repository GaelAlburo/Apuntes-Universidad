Links: [[VLSI]]
___

La síntesis consiste en transformar la descripción realizada con un cierto nivel de abstracción a una puramente estructural, cuyos componentes son elementos de una biblioteca

La complejidad del circuito final, y la posibilidad de implantarlo físicamente, depende del nivel de abstracción inicial

Las herramientas de síntesis reducen el nivel de abstracción hasta llegar a un nivel estructural, haciendo un **mapeo tecnológico**.

Para hacer la síntesis de manera eficiente hay ciertas restricciones y recomendaciones al desarrollar la descripción de un circuito en VHDL.

___
# Restricciones y Recomendaciones
Las restricciones particulares dependen del fabricante.
Sin embargo hay recomendaciones comunes:

- Evitar clausulas temporales
- Utilizar funciones y módulos (diseño modular jerárquico)
- Preferir el uso de listas sensibles a sentencias de espera (`wait`)
- Tener cuidado con las señales de reloj
- Cuidar la inicialización de variables  y señales
- Tener asignaciones únicas a una señal en un proceso
- Recordar que no todos los niveles lógicos (`std_logic`) son sintetizables
- Evitar `IFs` anidados y preferir estructuras `CASE`  
- Utilizar los modelos de maquinas de estado de la herramienta de desarrollo
- Especificar la arquitectura a usar, cuando existan varias
- Recordar que puede haber diferencias entre la simulación y la síntesis de un circuito
- Cuidar cuando se busca una descripción combinacional o secuencial

___
# Construcciones Básicas

### Logica Combinacional
- El objetivo es no introducir elementos de memoria

*En ejecución concurrente:*
- La señal asignada no debe intervenir en la asignación
```vhdl
a <= b when h = '1' else c; --Combinacional
a <= b when h = '1' else a; --Secuencial
```
- No debe haber lazos combinacionales
```vhdl
--Secuencial
d <= b and a;
a <= d or e;
--Combinacional
d <= b and c;
a <= d or e;
```

*En ejecución serial*
- La lista sensible incluye a todas las señales implicadas en las asignaciones
- Se asignan todas las variables y señales que intervienen, y se incluyen todos los casos en las condiciones:
```vhdl
--Combinacional
process(b,c,d,e)
begin
	if b='1' then d<=c;
	else d<=0;
	end if;
	a<=d or e;
end process;
--Secuencial
process(b,c,d,e)
begin
	if b='1' then d<=c;
	end if;
	a<=d or e;
end process;
```

___
### Logica Secuencial
Lo que no se modele como lógica combinacional, sera secuencial. 
Idealmente se debe hacer una buena descripción de los elementos secuenciales

*LATCH: Elementos asíncronos*
- Programación serial
- Programación concurrente

*Registros: Elementos síncronos*
- Con *reset*
- O sin *reset*

*Consideraciones sobre la señal de reloj:*
- La señal de reloj puede ser activa en el flanco de subida o en el de bajada, pero no en ambos
- Solo se permite una señal de reloj por proceso
- En el `IF` que comprueba el flanco del reloj no debe llevar `ELSE`
- No se permite hacer operaciones sobre la senal de reloj cuando se especifica el flanco
```vhdl
if not (clk'event and clk = '1') then... --Incorrecto
```

___
# Errores comunes en VHDL

Existen ciertas acciones que no son permitidas por el lenguaje, o que tengan un comportamiento diferente al esperado.
- Asignación de una misma señal en instrucciones concurrentes diferentes
- Pensar que las señales se comportan como variables dentro de los procesos
- Omitir asignar valores a señales en maquinas de estados
- No considerar las características físicas, mecánicas y temporales de los dispositivos de entrada cuando se trabaja con entradas externas
