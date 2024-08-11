Links: [[VLSI]]
___

VHDL cuenta con la capacidad de trabajar con archivos de datos.
El uso de archivos no se utiliza en la síntesis de HW, es algo reservado para la simulación

Una aplicación donde es importante usar archivos de entrada y salida es en los "bancos de pruebas"                  (*testbench*), donde automáticamente se puede probar el funcionamiento de un dispositivo, donde se lee un archivo y se guardan las salidas en otro.

Un archivo en VHDL puede almacenar casi cualquier tipo de dato. Los únicos que no se pueden guardar son arreglos multidimensionales, apuntadores y archivos.
<mark class="hltr-pink">En un archivo solamente se pueden almacenar datos de un mismo tipo.</mark> 
Por esto se debe declarar el tipo de datos que manejara un archivo:
```vhdl
type tipo_archivo is file of tipo;
```

___
# Apertura de Archivos
Una vez declarado el tipo de archivo, se debe hacer la declaración del archivo.
Al momento de hacerlo, el archivo puede ser abierto:
```vhdl
file nombre_logico:
	tipo_archivo [[open modo] is "nombre.ext"]; --Abre el archivo
```

El modo viene descrito por el tipo enumerado `file_open_kind` y puede tomar los valores:
- `write_mode`
- `read_mode` (por defecto)
- `append_mode`

La forma de abrir el archivo mas adelante explícitamente se hace de la siguiente manera:
```vhdl
procedure file_open (file f: tipo_archivo);
	external_name: in string;
	open_kind: in file_open_kind := read_mode);
```

Adicionalmente, es posible pasarle un primer parámetro donde devuelve el resultado de la operación:
```vhdl
procedure file_open(status: out file_open_status;
		file f: tipo_archivo;
		external_name: in string;
		open_kind: in file_open_kind := read_mode);
```

## Cerrar un Archivo
```vhdl
procedure file_close (file f: tipo_archivo);
```

___
### Ejemplos:
```vhdl
--Declaracion de tipo
type arch_ent is file of integer;
--Declaracion de archivo y apertura al momento
file datos: arch_ent open read_mode is "datos.txt";
--Declaracion de archivo y apertura posterior
file datos: arch_ent;
...
file_open (datos, "mis_Datos.txt", read_mode);
```

```vhdl
--Apertura en el programa con validacion de errores
variable resulta: file_open_status;
...
file_open (resulta,datos,"mis_datos.txt",read_mode);
if resulta = _open_ok then ...
else ..      --Abrio bien
end if;...   --Hubo error
--Cerrar archivos
file_close(datos);
```

___
# Lectura y Escritura de Archivos

Las operaciones que se pueden realizar con los archivos son de lectura, escritura y comprobación de fin de archivo.

```vhdl
procedure read(file f: tipo_archivo;
		  valor: out tipo);
```

```vhdl
procedure write(file f: tipo_archivo;
		  valor: in tipo);
```

```vhdl
procedure endfile(file f: tipo_archivo)
		  return boolean;
```

___
# Archivos de texto y E/S estándar

VHDL escribe en archivos en binario.
Si se requiere manejarlos externamente es conveniente definirlos con el tipo de dato `text`, definido en el paquete `textio` en la biblioteca estándar `std`.