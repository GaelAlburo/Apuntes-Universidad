**Sentencias:**

	1. Declarativas:
	- flutuador
	- inteiro

	2. De asignacion
	- quebrar
	- retorno

	De control:
	3. trocar-caso
	4. enquanto
	5. fazer-enquanto
	6. se
	7. para

Átomos de cadenas:
r: expresión relacional
l: expresión lógica
e: expresión aritmética
s: cualquier sentencia

___
# Átomos
identificador $\rightarrow$ a
constante $\rightarrow$ n


# 1) Declarativas
\<tipo\><\identificador>[\=\<cte\>]
		  [,\<identificador>[=..]...];

\<Decl> $\rightarrow$ \<Tipo>a\<valorIni>\<listVar>;     C.S.(1)={fi}
\<Tipo> $\rightarrow$ f                                                 C.S.(2) = {f}
\<Tipo> $\rightarrow$ i                                                C.S. (3) = {i}
\<valorIni> $\rightarrow$ =\<tipoVal>                         C.S.(4) = {=}
\<valorIni> $\rightarrow$ $\epsilon$                                          C.S.(5) = {,;}
\<listVar> $\rightarrow$ a\<valorIni>\<listVar>             C.S.(6) = {,}
\<listVar> $\rightarrow$ $\epsilon$                                            C.S.(7) = {;}
\<tipoVal> $\rightarrow$ n
\<tipoVal> $\rightarrow$ v

# 2.1) Asignación
\<identif>\<opArit>E;

\<Asig> $\rightarrow$ a\<opArit>E;
\<opArit> $\rightarrow$ =
\<opArit> $\rightarrow$ x
\<opArit> $\rightarrow$ y
\<opArit> $\rightarrow$ k
\<opArit> $\rightarrow$ r
\<opArit> $\rightarrow$ o

# 2.2) Quebrar
quebrar;

Q $\rightarrow$ u;

# 2.3) Retorno
retorno [\<expArit> ó \<expCaedena>]

\<Ret> $\rightarrow$ t\<valRet>;
\<valRet> $\rightarrow$ E
\<valRet>  $\rightarrow$ [\<expCadenas>]
\<valRet> $\rightarrow \epsilon$

# 3) trocar-caso
trocar(\<identif>):
\#
	caso(n) {listaS}
	[caso () {listaS}]
\#

\<Troc> $\rightarrow$ b(a):#c(n){\<listaS>}\<casos>#
\<listaS> $\rightarrow$ $\epsilon$
\<listaS> $\rightarrow$ \<sent>\<listaS>
\<casos> $\rightarrow$ $\epsilon$
\<casos> $\rightarrow$ c(n){\<listaS>}\<casos>
\<casos> $\rightarrow$ (){\<listaS>}

# 4) enquanto
enquanto(\<expLogica>)
\#
	\<listaS>
\#

\<Enq> $\rightarrow$ q(\<expLogicas>)#\<listaS>#

**Hacer las gramáticas LL para 3. Entregar sintaxis y gramática para JUEVES en papel**

![[020819_0506_SwitchCaseS2.webp]]

trocar: t
caso: c

A $\rightarrow$ t(B)
B $\rightarrow$ a){C
C $\rightarrow$ cn:DE
D $\rightarrow$ s;D
D $\rightarrow$ $\epsilon$
D $\rightarrow$ CE
E $\rightarrow$ }

___
___
___
# Ejemplo Codigo de ASDR

- Operadores aritmeticos: +-\*/%

___
___
# Correcion de la Gramatica
42. F $\rightarrow$ x  **SE ELIMINA**


Al usar el NOT (!), debe ir entre llaves:
- {!{a>9}}
A menos de que solo se negué una expresión
- !a


























te quiero      ⣠⣤⣶⣶⣶⣶⣶⣤⣄⡀⠀⠀⠀⠀⠀⠀⠀⠀⠀ ⠀⠀⠀⠀⠀⠀
          ⣠⣴⣾⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣶⣄⡀⠀⠀⠀⠀⠀ ⠀⠀⠀
   ⣠⣴⣴⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣮⣵⣄⠀⠀⠀ ⠀
⠀⢾⣻⣿⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⢿⣿⣿⡀⠀ ⠀
⠸⣽⣻⠃⣿⡿⠋⣉⠛⣿⣿⣿⣿⣿⣿⣿⣿⣏⡟⠉⡉⢻⣿⡌⣿⣳⡥⠀ ⠀
⢜⣳⡟⢸⣿⣷⣄⣠⣴⣿⣿⣿⣿⣿⣿⣿⣿⣿⣧⣤⣠⣼⣿⣇⢸⢧⢣⠀ ⠀
⠨⢳⠇⣸⣿⣿⢿⣿⣿⣿⣿⡿⠿⠿⠿⢿⣿⣿⣿⣿⣿⣿⣿⣿⠀⡟⢆⠀ ⠀
⠀⠈⠀⣾⣿⣿⣼⣿⣿⣿⣿⡀⠀⠀⠀⠀⣿⣿⣿⣿⣿⣽⣿⣿⠐⠈⠀⠀ ⠀
⢀⣀⣼⣷⣭⣛⣯⡝⠿⢿⣛⣋⣤⣤⣀⣉⣛⣻⡿⢟⣵⣟⣯⣶⣿⣄⡀⠀ 
⣴⣿⣿⣿⣿⣿⣿⣿⣿⣿⣷⣶⣶⣶⣾⣶⣶⣴⣾⣿⣿⣿⣿⣿⣿⢿⣿⣿⣧ 
⣿⣿⣿⠿⢿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⣿⠿⠿⣿⡿....