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


