Links: [[Lab. Microprocesador]]
___
En la primera dirección 0000 (RESET) debe de haber una instrucción que salte a la dirección donde inicie el programa

Dentro del programa se escribe la instrucción `ORG` donde nos marca el origen del programa. Adicionalmente de un `GOTO`, un salto hacia cualquier etiqueta.

- H'27' - Hexadecimal
- D'20' - Decimal
- A'A' - ASCII
- B'10110101' - Binario

`MOVLW` - move literal to W

Solamente tiene 35 instrucciones

En el diagrama de registros, las que están en gris, son inexistentes. Las blancas existen


00 1000  0010 0000 -> MOVF 0x20,W
00 0000 1010 0001 -> MOVWF 0x21

___
Para ejercicio 4, se va sumando el mismo numero por si mismo. Hacer el algoritmo asi

Para ejercicio 5 no se deben ver en hexadecimal. solo decimales