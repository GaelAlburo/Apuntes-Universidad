BIts
- Unidad minima de informacion de la computacion clasica
- UN bit solo tiene dos posibles estados, 0 o 1
- Los estados son excluyentes entre si

Qubits:
- Unidad minima de computacion cuantica
- El estado posible es una combinacion lineal de los estados clasicos de 1 y 0
- Los estados cuanticos estan en 1 y 0 al mismo tiempo
- El lenguaje en que se describen a los estados de $n$ qubits son los vectores con coeficientes complejos de dimension $2^n$

___
# Notacion de Dirac

Se utiliza para representar a los estados de los qubits para que su manejo sea mas simple y directo

Se definen como:
- Estado clasico 0:
	$|0 \rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$
- Estado clasico 1:
	$|1 \rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}$

A estos estados se les conoce como base. Ya que hay un $\alpha$ como $\beta$ que cumplen que:
$$\alpha \, \begin{pmatrix} 1 \\ 0 \end{pmatrix} \, \beta \begin{pmatrix} 0 \\ 1 \end{pmatrix} \, = \begin{pmatrix} a \\ b \end{pmatrix}$$
Es decir, estos estados crean todos los vectores de dimension 2 con coeficientes $\mathbb{C}$

Todos los estados posibles de los qubits estan dentro del circulo unitario.

___
El estado arbitrario de un qubit se define como:

Tiene tamano 1. 

## Ejercicio
Verificar que son estados cuanticos:

___

# Espacio Vectorial

Los estados cuanticos estan definidos sobre un espacio vectorial con coeficientes en los complejos:

___
# Estados de Bell

Ademas de los estados base, hay otros estados base llamados Estados de Bell sobre el espacio vectorial

Estados de Bell:
- $|+ \rangle = \dfrac{|0 \rangle + |1 \rangle}{\sqrt{2}}$
Representacion en vector:
$notas$

- $|- \rangle = \dfrac{|0 \rangle - |1 \rangle}{\sqrt{2}}$

## Ejercicio:
Operaciones con los estados de Bell:

- $|+ \rangle \, + \, |-\rangle$

Cualquier estado vectorial se puede representar en términos de + ($|+ \rangle$) y - ($|- \rangle$)

___
# Producto Interno

- Producto punto
- Producto cruz

Estado bra:
	$\langle 0 |$
Estado ket:
	$|0 \rangle$

	$\langle \theta | \, = \, | \theta \rangle ^ \dagger$

## Ejercicio:

	$\langle 0|0 \rangle$


___
# Producto Externo

$| \alpha \rangle \langle \phi |$

## Ej