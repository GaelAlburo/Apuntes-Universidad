Links: [[VLSI]]
___

La simulación de modelos en VHDL es una practica eficiente para validar la operación de un sistema antes de pasar a la implantación física en hardware.

Un *testbench* esta formado por un conjunto de entradas, llamadas **patrones de prueba**, que son aplicados a un modelo o circuito en VHDL.
En su forma mas simple, un *testbench* esta formado de entradas y salidas.

___
Para la validacion de las salidas del sistema a evaluar, se pueden utilizar mecanismos de VHDL.
Las notificaciones se dan como consecuencia de evaluar una condicion mediante la estructura `assert`:
```vhdl
assert condicion [report mensaje]
	[severity nivel];
```

Cuando **no** se cumple la condición, aparece el mensaje en pantalla, indicando el nivel de severidad
El mensaje por default es: `Assertion Violation`
El nivel de gravedad es `severity_level` y tiene los valores: `note, warning, error` (default) y `failure`

___
Para la construcción del banco de pruebas se pueden seguir 3 metodologías distintas, en función de como se generen los vectores de pruebas:
1. Método tabular
2. Utilización de archivos
3. Metodología algorítmica

# 1. Método Tabular
Hay que generar una tabla con las entradas y las salidas esperadas del sistema.
Los valores contenidos en esta tabla se aplicaran al dispositivo en evaluación y se comprobara si sus respuestas coinciden con lo esperado
#### Ejemplo:
Se evaluara el funcionamiento de un registro de corrimiento de 4 bits.
El registro tiene las entradas: `clk, rst, inD, inI, mod(1..0), ent(3..0)`; y la salida `sal(3..0)`

___
# 2. Utilización de Archivos
Los patrones de prueba son independientes del modelo a ser simulado, al estar dentro de un archivo externo.

El archivo coon los patrones sera un archivo de texto con los vectores de prueba ordenados por renglón, separando los valores por espacios o tabuladores
Estos archivos serán leídos mediante el paquete `textio` del paquete estándar.

___
# 3. Metodología Algorítmica
Los patrones de prueba se pueden generara automaticamente mediante la aplicacion de un algoritmo. Por ejemplo un ALU, se puede generar todas las combinaciones posibles de entrada, se aplique al componente a evaluar y comprobar la salida.
Esto evita generar los patrones de prueba manualmente.

