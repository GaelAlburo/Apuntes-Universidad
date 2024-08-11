Links: [[VLSI]]
___

# Comentarios

Se realiza empezando dos guiones, termina con fin de linea.
- Al igual que comentarios de bloque con: /* … */ (Solo 2008, no Quartus)

___
# Identificadores

Dan nombre a los elementos en VHDL:
- No tienen longitud max
- Caracteres alfabeticos, numericos y el guion basico
- No hay distincion entre mayus y minus
- Debe iniciar con caracter alfabetico, no puede terminar en guion bajo ni 2 guiones bajos seguidos
- No se pueden usar palabras reservadas

___
# Literales

Símbolo cuyo valor se obtiene de su representación
- **Numéricos**
    - Enteros (4, 54390, 0, 120_000 [guion bajo, separador])
    - Punto flotante (3.1416, 23.2, 0.42)
    - Físicos (5.25ns, 53mm, 0.4V)
    - Se puede usar la notación exponencial (52E2, 42.25E+3, 4.02E-3, 12E3 [kOhm])
    - Se puede representar en cualquier base de 2 a 16 (2#1100, 4#30#, 16#2eE#, 2#101#E2)

> [!done] VHDL es estricto en el tipo de datos. 4 ≠ 4.0

- **Caracter**
    - ASCII encerrado entre apostrofes (_**’a’, ‘M’, ‘5’, ‘ ‘**_)
- **Cadenas de caracteres**
    - Secuencia de caracteres encerrada en comillas (”abcde”, “ i3”)
- **Cadenas de bits**
    - Secuencia de caracteres 0 a 9 y A a F, encerrada en comillas precedida por una letra que indica la base (B”10011”, b”0010_1010”, O“73”, x”f0A3”, X”FF”)

___
# Objetos VHDL

- **Constantes**
    - Mantienen su valor inicial, y su valor no puede ser modificado una vez que son creados
    ```vhdl
constant identificador {, ...} : tipo [:= expresion];
    ```

- **Variables**
    - Pueden cambiar su valor mediante sentencias de asignacion. Se declaran dentro de un proceso
```vhdl
variable indentificador {, …} : tipo [:= expresion] identificador := Indice * Pi + 2;
```

- **Señales**
    - Similares a variables, representan directamente al hardware
    - Se declaran dentro de la arquitectura
    - Los puertos de una entidad son señales que interconectan el dispositivo. Mas utilizados para entradas
    - Valores de entrada (**in**) solo se pueden leer. Valores de salida (_**out**_) solo se pueden escribir
    - Si se quiere leer un estado de salida, existe el tipo *buffer*
