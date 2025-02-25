# Puertas Cuánticas de un qubit

- Son matrices cuadradas unitarias de 2x2
$$U^{\dagger} U \, = \, UU^{\dagger} \, = \, In$$
- Son reversibles


# $Id$

$Id \, = \, \begin{pmatrix}  1 & 0 \\  0 & 1 \end{pmatrix}$
$Id \, \ket{0} \, = \, \begin{pmatrix}  1 & 0 \\  0 & 1 \end{pmatrix} \begin{pmatrix}  1 \\  0 \end{pmatrix} \, = \, \begin{pmatrix}  1 \\  0 \end{pmatrix} \, = \, \ket{0}$

$Id \, \ket{1} \, = \, \begin{pmatrix}  1 & 0 \\  0 & 1 \end{pmatrix} \begin{pmatrix}  0 \\ 1 \end{pmatrix} \, = \, \begin{pmatrix}  0 \\ 1 \end{pmatrix} \, = \, \ket{1}$

$Id \, (\, \alpha \ket{0} + \beta \ket{1} \,) \, = \, \alpha \, (Id \, \ket{0}) + \beta \, (Id \, \ket{1}) \, = \, \alpha \ket{0} + \beta \ket{1}$
___
# $\sigma_x$ = NOT

$\sigma_x \, = \, \begin{pmatrix}  0 & 1 \\  1 & 0 \end{pmatrix}$

$\sigma_x \, \ket{0} \, = \, \ket{1}$

$\sigma_x \, \ket{1} \, = \, \ket{0}$

$\sigma_x \, (\, \alpha \ket{0} + \beta \ket{1} \,) \, = \, \alpha \ket{1} + \beta \ket{0}$
___
# $\sigma_z$

$\sigma_z \, = \, \begin{pmatrix}  1 & 0 \\  0 & -1 \end{pmatrix}$

$\sigma_z \, \ket{0} \, = \, \ket{0}$

$\sigma_z \, \ket{1} \, = \, -\ket{1}$

$\sigma_z \, (\, \alpha \ket{0} + \beta \ket{1} \,) \, = \, \alpha \ket{0} - \beta \ket{1}$
___
# $\sigma_y$

$\sigma_y \, = \, \begin{pmatrix}  0 & -i \\  i & 0 \end{pmatrix}$

$\sigma_y \, \ket{0} \, = \, i \, \ket{1}$

$\sigma_y \, \ket{1} \, = \, -i \, \ket{0}$

$\sigma_z \, (\, \alpha \ket{0} + \beta \ket{1} \,) \, = \, \alpha i \, \ket{0} - \beta i \, \ket{1}$
___
# $H$

$H \, = \, \dfrac{1}{\sqrt{2}} \begin{pmatrix}  1 & 1 \\  1 & -1 \end{pmatrix}$

$H \, \ket{0} \, = \, \frac{1}{\sqrt{2}} \, (\ket{0} + \ket{1})$

$H \, \ket{1} \, = \, \frac{1}{\sqrt{2}} \, (\ket{0} - \ket{1})$

$\sigma_z \, (\, \alpha \ket{0} + \beta \ket{1} \,) \, = \, \frac{1}{\sqrt{2}} \, \Bigl( \, (\alpha + \beta) \, \ket{0} + (\alpha - \beta) \, \ket{1} \, \Bigl)$
___
___

# Ejercicios

$\sigma_y \, \, H\,(\ket{0}) \, = \, \sigma_y \, \ket{+} \, = \, \dfrac{1}{\sqrt{2}} \Bigl( \sigma_y \, \ket{0} + \sigma_y \ket{1} \Bigl)$


