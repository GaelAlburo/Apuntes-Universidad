Repo lab: https://github.com/clausia/cursofi-comcuantica-2025-II

# Números Complejos:

**Operaciones Unitarias:**
Sea  $z_1 \in \mathbb{C}$  tal que  $z_1 = a+ib$
- Conjugado:  $\bar{z_1}=a-ib$
- Modulo:  $||z_1|| = \sqrt{a^2+b^2}$

**Operaciones Binarias:**
Sea  $z_1, z_2 \in \mathbb{C}$ 
- Suma:  $z_1 + z_2 = (a_1 + a_2) + (b_1 + b_2)i$
- Resta:  $z_1 - z_2 = (a_1 - a_2) + (b_1 - b_2)i$
- Multiplication:  $z_1 * z_2 = (a_1a_2 - b_1b_2) + (a_1b_2 + a_2b_1)i$
- Division:  $\dfrac{z_1}{z_2} = \dfrac{a_1 a_2 + b_1 b_2}{a_2+b_2} + (\dfrac{a_2 b_1 - a_1 b_2}{a_2 + b_2})i$

## Ejercicios:

1. $i * (a + ib)$
$ai + bi^2 \enspace = \enspace ai-b \enspace = \enspace -b + ai$

2. $(a+bi) * (a-bi)$
$a^2−abi+abi−b^2i^2 \enspace = \enspace a^2 - b^2 i^2 \enspace = \enspace a^2 + b^2 \enspace = \enspace (||z_1||)^2 \enspace = \enspace (\,||(a+bi)||\,)^2$

3. $( a+ bi ) * (a+bi)$
$a^2 + abi + abi + b^2i^2 \enspace = \enspace = a^2 + 2abi + b^2 i^2 \enspace = \enspace a^2 + 2abi - b^2$

## Campo de los Complejos

Los complejos con la suma y la multiplicación definida anteriormente forman un campo por lo que cumple con las siguientes propiedades:
+ Cerradura en la suma y el producto.
* Conmutatividad en la suma y en el producto.
* Asociatividad en la suma y en el producto.
* Elemento neutro en la suma y en la multiplicación.
* Inversos para la suma y multiplicación.
* La multiplicación distribuye a la suma.

___

# Formula de Euler

Para cualquier valor $\theta \in \mathbb{R}:$
	$e^{i\theta} = cos \theta + i(sin \theta)$

Una propiedad importante:  $e^{i \phi} e^{i \theta} = e^{i(\phi + \theta)}$
___

# Algebra Lineal

Las compuertas cuánticas corresponden a matrices cuadradas con coeficientes complejos

**Operaciones Unitarias**
![[Pasted image 20250208141824.png|center|450]]

**Operaciones Binarias**
![[Pasted image 20250208141924.png|center|450]]

___

# Compuertas Cuánticas

La propiedad de las matrices que definen a las compuertas cuánticas es que son **unitarias**

Una matriz es **unitaria** si cumple que:
	$U^{\dagger}U = U U^{\dagger} = I_n$
Donde:
- $I_n$ es la identidad de las matrices cuadradas
- $U^{\dagger} \enspace = \enspace (U^t)^{*}$

## Ejercicio

1. Verificar que $\sigma_Y$ es matriz unitaria
$$\sigma_Y \enspace = \enspace \begin{pmatrix}  
0 & -i \\  
i & 0  
\end{pmatrix}$$
- Primero se calcula la matriz transpuesta:
$$\begin{pmatrix}  
0 & i \\  
-i & 0  
\end{pmatrix}$$
- Posteriormente la matriz conjugada:
$$\begin{pmatrix}  
0 & -i \\  
i & 0  
\end{pmatrix}$$
- Finalmente se realiza la multiplicación:
$$\begin{pmatrix}  
0 & -i \\  
i & 0  
\end{pmatrix}
\begin{pmatrix}  
0 & -i \\  
i & 0  
\end{pmatrix} = 
\begin{pmatrix}  
-i^2 & 0 \\  
0 & -i^2  
\end{pmatrix} = 
\begin{pmatrix}  
1 & 0 \\  
0 & 1  
\end{pmatrix}$$

