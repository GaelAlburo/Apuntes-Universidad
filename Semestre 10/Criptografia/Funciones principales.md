Principal de criptografia de llave publica

Conjunto: $X=\{a, b, c\}$
Funcion: $X, Y, f$

$X$ <- dominio de $f$
$Y$ <- codominio

$x \in X$ -> $y \in Y : f$
$y = f(x)$

$f$ cada elemento $X$ a $Y$ es:
	$f: X$ -> $Y$

$y \in Y$  preimagen $y$ -> $x \in X$
$Im(f) = f(x) = y$   

___
# Funciones 1-way

$f: X$ -> $Y$

1-way function si:
- $f(x)$ es facil para toda $x \in X$ 
- pero para toda $y \in Im(f)$

$f(x) = y$ -> Muy facil de calcular
$y = Im(f)$  -> Muy difical de calcular 

**Trapdoor**

Funcion similar a 1-way pero que contiene una pista para poder desencriptar

Almacenar la tabla donde se transformaron los valores. Asi podriamos transformar una funcion 1-way en una funcion trapdoor

___
# 1-1 Function

Tdos los elementos de X tienen una imagen en Y. Pero no todos los elementos en Y tienen una X

$Im(f) = y$

$f(x) = y$     $x \in X$
$g(y) = x$     $y \in Y$
$g = f^{-1}$

___
# Permutaciones

Se tiene un conjunto $S$ con elementos finitos biyectivo. Con $p$ permutaciones. 

$S \rightarrow S$
$S = \{1, 2, 3, 4, 5\}$
$p(1) = 3, \, p(2) = 5, \, p(3) = 4, \, p(4) = 2, \, p(5) = 1$

Mensaje cifrado: $S = \{3, 5, 4, 2, 1\}$

$p = \begin{Bmatrix} 1, & 2, & 3, & 4, & 5,\\ 3, & 5, & 4, & 2, & 1, \end{Bmatrix}$

$p^{-1} = \begin{Bmatrix} 1, & 2, & 3, & 4, & 5,\\ 5, & 4, & 1, & 3, & 2, \end{Bmatrix}$


$0 0 1 1 0 1 1 0 = mensaje$
$01010101 = p(s)$
======
$01100011 = p$
$01010101$
======
$00110110 = mensaje$

Se aplica la compuerta XOR

___
# Involuciones

$S$ elementos finitos biyectivos
$f: \, S \rightarrow S$
$f_{\text{involucion}}: f = f^{-1}$
$f(f(x)) = x$          $x \in S$

$f(x) = \begin{Bmatrix} 1, & 2, & 3, & 4, & 5,\\ 4, & 2, & 5, & 1, & 3, \end{Bmatrix}$

$f(x)^{-1} = \begin{Bmatrix} 1, & 2, & 3, & 4, & 5,\\ 4, & 2, & 5, & 1, & 3, \end{Bmatrix}$

En las involuciones, la funcion inversa obtiene los valores originales.
En las permutaciones no


___
# Dominio y Codominio del Cifrado

- $A$ se denomina alfabeto
	- $A = \{0, 1\}$  $2^5 = 36$

$00000 - a$
$00001 - b$
...
$01110 - z$

- $M$ se denomina el espacio del mensaje. $M$ también es llamado el mensaje en texto plano
- $C$ se denomina el espacio de cifrado. $C$ también es llamado el texto cifrado

Dominio ($M$) -> Codominio ($C$)


# Transformación de cifrado y descifrado

- $K$  espacio de la llave
- $e \in K$  determina la biyeccion.    $E_e: M \rightarrow C$
	- $E_e$  llamada la funcion de cifrado. Transformacion de cifrado
- $d \in K$  determina la biyeccion.    $D_d:  C \rightarrow M$
	- $D_d$   llamada la funcion de descifrado. Transformacion de descifrado
- Proceso de transformar $E_e$ a un $m \in M$ se llama **cifrado de m**
- Proceso de transformar $D_d$ a un $c \in C$ se le llama **descifrado de c**


# Esquema criptografico

- Consiste en un conjunto $\{ E_e: e \in K\}$ para cifrar y $\{D_d: d \in K\}$
- Para cada $e \in K$ existe una unica $d \in K$ tal que $D_d= E_e ^{-1}$ esto es $D_d (E_e(m)) = m$ donde $m \in M$
- Esquema criptografico = cifrado
- $d$ y $e$ se define como llaves y se representan como $(e, d)$.
	- Las llaves pueden ser distintas o las mismas


>[!info] 


___
- Alfabeto
$A = \{a, b, c, ..., z\}$
- Llaves
$k = \{e_1, e_2, ..., e_t\}$      $e \in k$
$t$ : longitud del mensaje
- Mensaje
$M=\{m_1, m_2, ..., m_t\}$     $m \in M$
- Funcion Cifrado
$E_e(m) = \{ c \}$     $e, d \in k$
- Funcion descifrado
$D_d(m) = m$       $d = e^{-1}$

- Mensaje cifrado
$C = \{ c_1, c_2, ..., c_t \}$     $c \in C$

