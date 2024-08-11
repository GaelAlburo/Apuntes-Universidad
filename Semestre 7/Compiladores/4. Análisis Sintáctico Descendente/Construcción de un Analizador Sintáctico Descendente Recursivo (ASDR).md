Links: [[Compiladores]]
___

**lapei-f**
Cada no terminal va a tener una función.
Sera dependiendo del tipo de producción que se tenga (pop, avanza, reten, etc.)

| Caso | Tipo Produccion           | Codigo                                    |
| ---- | ------------------------- | ----------------------------------------- |
| 1    | A $\rightarrow$ b         | `c=getchar(). return`                     |
| 2    | A $\rightarrow$ b$\alpha$ | `c=getchar(). procesar`($\alpha$)`. return` |
| 3    | A $\rightarrow \epsilon$  | `return`                                  |
| 4    | A $\rightarrow$ B$\alpha$ | `procesar`(B$\alpha$). `return`                                         |

Procesar ($\alpha$) y procesar (B$\alpha$) consiste en:
1) Por cada no terminal en $\alpha$ y para b, llamar a la funcion que le corresponde
2) Por cada terminal en $\alpha$ :
	```C
	if (c=='x')
		c= getchar();
	else
		rechazar();
	```
	donde x $\in$ $\sum_G$

>[!done] Al ejecutar yylex() ya se debe tener la cadenas de átomos
#### Ejercicio
Codifica las funciones de un ASDR de la siguiente gramática (de expresiones aritméticas de + y \*)
1. E $\rightarrow$ TE'     C.S.(1) = { ( a }
2. E' $\rightarrow$ TE'    C.S. (2) = { + }
3. E' $\rightarrow \epsilon$       C.S.(3) = { + ) }
4. T $\rightarrow$ FT'     C.S.(4) = { ( a }
5. T' $\rightarrow$ \*FT'    C.S.(5) = { \* }
6. T' $\rightarrow \epsilon$       C.S.(6) = { + ) -| }
7. F $\rightarrow$ (E)     C.S.(7) = { ( }
8. F $\rightarrow$ a       C.S.(8) = { a }

**Codificación:**
- Sera sin tipo, y se presenta en seudocódigo
- Se utiliza la pila del sistema al aplicar funciones recursivas
```C
E(){
if(c == 'a' || c == '('){
		T()
		EP() \\E'	
	}
	else{
		rechaza()
		\\Leer el sig. elemento de la cadena de entrada
	}
}
```

```C
EP(){
	if(c == '+'){
		c = getchar();
		T();
		EP();
	}
	else if (c == '-|' || c == ')'){
		return;
	}
	else {
		rechaza()
	}
}
```

```C
T(){
	if (c == ')' || c == 'a'){
		F()
		TP() \\T'
	}
	else{
		rechaza()
	}
}
```

```C
TP(){
	if(c == '*'){
		F()
		TP()
	}
	else if(c == '+' || c == ')' || c == '-|')
		return;
	else
		rechaza()
}
```

```C
F(){
	if(c == '('){
		c = getchar()
		E()
		if (c == ')')
			c = getchar()
		else
			rechazar();
	}
	else if (c == 'a'){
		c = getchar()	
	}
	else{
		rechaza()
	}
}
```

```C
AnaSint(){
	c = getchar() \\Se lee el primer atomo de la cadena
	E() \\Se llama al primer no-terminal
	if (c == '-|') \\Si se encuentra el fin de cadena
		acepta() \\Se acepta la cadena
	else{
		rechaza()
		\\Cerrar archivos, etc.
	}
}
```

___
**Anadiendo a los demas operadores para el PROYECTO, la gramatica queda:**
9. E' $\rightarrow$ FT'        C.S.(9) = { - }
10. T' $\rightarrow$ /FT'     C.S.(10) = { / }
11. T' $\rightarrow$ %FT'    C.S.(11) = { % }
12. F $\rightarrow$ n
13. F $\rightarrow$ [\<Llama>]

Con estos cambios `E` permite obtener un identificador (a), una constante(n), una expresión aritmética o una llamada a  una función
___

**1) Llama**


**5) L: Expresiones Lógicas**
&&: h
||: j
!: ! 

L $\rightarrow$ YL
L $\rightarrow \epsilon$
Y $\rightarrow$ O\<sent>
Y $\rightarrow$ OXO
X $\rightarrow$ R
X $\rightarrow$ E
O $\rightarrow \epsilon$ 
O $\rightarrow$ h
O $\rightarrow$ j
O $\rightarrow$ !
