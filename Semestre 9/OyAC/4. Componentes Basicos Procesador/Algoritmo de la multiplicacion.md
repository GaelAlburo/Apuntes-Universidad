**Pseudocodigo**

```
B = Multiplicando
A = Multipicador
Q = A
Y = 0
A = Y, RESET al contador 
while (FC != 0) then
	if (Q0 == 0) then
		Y = A+0
	else if (Q0 = = 1) then
		Y = A+B
	end if
	A = Y, INCREMENTA contador
	Q = Corrimiento un bit a la derecha
	Y = Corrimiento un bit a la derecha
```

El siguiente codigo se hace implicitamente cuando se realizan los corrimientos
```
Q7 = Y0
if (Q0 == 0) then
	Y7 = Acarreo de A+0 = 0
else if (Q0 == 1) then
	Y7 = Acarreo de A+B
end if

Y = Q //El resultado se almacena en Q originalmente
B = Y //El resultado final se mantiene en B4
```

# Carta ASM

- Para leer el contenido del registro Y, se deben activar E0UPA y DUPA
- Deshabilitamo el DUPA ,m 