Links:
___
`ORG X`: Dice al ensamblador, que las próximas instrucciones se ensamblen (almacenen) a partir de la dirección X

En la ventana VIEW > WATCH, nos muestra una ventana donde nos permite observar un registro en especifico y asignarle valores.

Para revisar si un registro es igual a 0
```asm
INICIO:
	MOVF REGISTRO W   ;W <-- REGISTRO
	BTFSS STATUS,Z    ;REGISTO = 0?
	GOTO NO_ES_CERO
ES_CERO:
	CLRW
	GOTO INICIO
NO_ES_CERO:
	MOVLW 1
	GOTO INICIO

	END
```

| Operacion | Resultado | Bits de Carry y Zero |
| --------- | --------- | -------------------- |
| A>B       | Positivo  | C=1 y Z=0            |
| A<B       | Negativo  | C=0 y Z=0            |
| A=B          | Cero          | C=1 y Z=1                     |
___
```asm
INICIO:
	MOVF RB,W
	SUBWF RA,W
	BTFSS STATUS,C
	GOTO A_MENOR_QUE_B
A_MAYORIGUAL_QUE_B
	;Se debe verificar que no sea 0
	BTFSS STATUS,Z
	GOTO A_IGUAL_B
A_MENOR_QUE_B
	MOVLW H'1'
A_IGUAL_B
	GOTO INICIO
```

A-B
B = W
SUBWF A = A-W(B) 


51-W