Se refiere a la asignacion de direcciones fisicas a direcciones logicas

Como nos centramos en la Raspberry PI, podemos mejorar significativamente el rendimiento del sistema y asegurarnos de que funcione eficiente y efectivamente

# Importancia

# Funcionamiento

En la Raspberry PI, el controlador de memoria busca la direccion fisica correspondiente y devuelve los datos almacenados en ella.

Si no hay una direccion fisica correspondiente se produce un error de acceso de memoria

# Tipos

- Mapeo memoria directa
Se asigna una direccion fisica a cada direccion logica

- Mapeo de memoria asociativa

La Raspberry PI utiliza el mapeo  de memoria paginada
Ademas utiliza un S.O. basado en Linux que tiene soporte integrado para el mapeo de memoria paginada, lo que lo hace mas facil de implementar y usar

# Ejemplo Mapeo de Memoria en Raspberry PI

memtool

