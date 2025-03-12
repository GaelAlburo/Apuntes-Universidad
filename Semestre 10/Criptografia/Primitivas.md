# Llave Simétrica

$\{ [e: e \in K] \}$ y $\{ [D_d: d \in K] \}$
$k$ es el espacio de llaves

EL cifrado de llave simetrica asocia un **par de llaves** de cifrado/descifrado $(e, d)$ tal que calcularlas sea "facil" tanto que al conocer $e$ se pueda calcular $d$. Es decir, $e = d$

- Key Source: Generador de llaves. 

___
# Cifrado de Sustitucion

- $A$ alfabeto con $q$ elementos
- $M$ mensaje de longitud $t$
- $k$ conjunto todas las permutaciones posibles
- $E_e(m) = (e(m_1)e(m_2)...e(m_t)) = C$
- $D_d(C) \, = \, d(c_1)d(c_2)...d(c_t) = (m_1, m_2, m_3, ... m_t) \, = \, m$

___
# Cifrado por Sustitucion Homofonica

Consideramos $A = \{ a, b\}$ y que sus representaciones homofonicas son: $H(a) = \{ 00, 10 \}$ y $H(b) = \{ 01, 11\}$. El **bloque** de texto es $ab$

____
# Cifrado de Transposición

Conjunto de llaves, o posibles transposiciones:
$A=\{ a,b,c,...,z \}$
$k=\{1, 2, ..., t\}$ -> transformaciones
$e = k$

$E_e(m)=\{m_e(1),\, m_e(2),\, ...,\, m_e(t) \} = C$  -> mensaje cifrado
$d=e^{-1}$   -> inversa de la transformacion          $c=\{c_1, c_2, ..., c_t\}$  -> $t$ mensajes cifrados
$D_d(c)=\{ c_d(1),\, c_d(2),\, ..., c_d(t) \}$  ->  descifrado

___
# Cifrado Playfair

m = hola mundo
k = cifrado

___
# Cifrador Hill

$E = (k,m) = (k*M) \: mod 26$

Algoritmo de cifrado que utiliza matrices

$m =$ morning          $k$ = dcdf

$\begin{pmatrix}   c_1 \\ c_2 \\ c_3  \end{pmatrix} = \begin{bmatrix}   k_{11} & k_{12} & k_{13}\\   k_{21} & k_{22} & k_{23} \\ k_{31} & k_{32} & k_{33}   \end{bmatrix} \begin{bmatrix} m_1 \\ m2_ \\ m_3\end{bmatrix}$
___
# Cifrado Verman

$A = \{0, 1\}$
$k = \{ k_1, k_2, ..., k_m \}$
$m$  tamano del bloque
$M = \{ m_1, m_2, ..., m_t \}$
$t$   tamano del mensaje

$E_k = (k_i \oplus m_i) \, mod \, 26$

m = MAR      k = XYZ
$m_1$ = M = 12
$k_1$ = x = 23

