
KEM - Mecanismo de encapsulamiento de llave 

Todos los algoritmos de cifrado necesitan una llave

___
# Algoritmo Diffie-Hellman

Es un protocolo criptográfico que permite a dos usuarios (Alice y Bob), establecer de forma segura una llave secreta compartida a través de un canal de comunicación inseguro.

La llave secreta se utiliza para encripción simétrica.

Fue creado en 1976 por **Whitfield Diffie** y **Martin Hellman**. El algoritmo está basado en las propiedades matemáticas de la exponenciación modular y problemas logarítmicos discretos.

## Funcionamiento

1. Alice y Bob acuerdan dos números primos grandes $P$ y $G$ (raíz primitiva módulo $P$). Estos dos números son compartidos públicamente
2. Alice elige un número aleatorio $a$ privado. Posteriormente calcula $A=g^a \ mod \ p$ y lo envía a Bob
3. Bob elige un número aleatorio $b$ privado. Posteriormente calcula $B=g^b \ mod \ p$ y lo envía a Alice
4. Alice calcula la llave secreta compartida: $k=B^a \ mod  \ p$
5. Bob calcula la llave secreta compartida: $k=A^b \ mod  \ p$

![[Pasted image 20250331164601.png|center|500]]


___
# Ejemplo

$0 < g < p$
$g = 12$
$p = 15$

$a = 3$             $b = 6$
$\alpha = 12^3 \:mod 15 = 3$
$\alpha = 3$

$\beta = 12^6 \: mod 15 =9$
$\beta = 9$

$k = 9^3 \: mod15 = 9$         $k = 3^6 \: mod 15 = 9$

$k = 9^2 \: mod 15 = 6$         $k = 3^6 \: mod 15 = 3$

___
$P = 23$  y  $G = 9$
$a=4$  y  $b=3$

Alice: $A=9^4 \ mod \ 23 = 6$
Bob: $B=9^3 \ mod \ 23 = 16$

Alice recibe $B=16$
Bob recibe $A=6$

Alice: $k_a = 16^4 \ mod \ 23 = 9$
Bob: $k_b=6^3 \ mod \ 23 = 9$
$$k_a = k_b$$

>[!done] Programar algoritmo DIffie-Helman

____

>[!info] PKE - Public Key Encription