Advanced Encryption Standard

DES:
- bloques: 64 bits
- llave: 64 bits
- rondas: 16
- funciones feistel
- String horizontal (bits)

AES:
- bloques: 128 bits
- llaves: 128, 192, 256 bits
- rondas: 10-14
- Campos Galios
- Matrices (bytes)
- Estructura por Capas:
	- Mezcla lineal
		- Desplazar fila
		- Mezclar columnas
	- Capa no lineal
		- byteSub (s-box)
	- Adicion de clave
		- Estado intermedio $\oplus$ Sub llave

AES utiliza 3 algoritmos:
- Generacion de llave
- Cifrado
- Descifrado

# Generacion de llave
1. Calcular $k_0, k_1, k_2, ..., k_n$  de  $k$ 
2. $S \leftarrow B \oplus k_0$
3. Para $i=1$ hasta $n$. Aplicar i-esimas donas del algoritmo con subllave $k_i$

$B$ <- bloque
$S$ <- Matriz estado
$k$ <- llave principal

# Cifrado y Descifrado

1. $S$ <- ByteSub(S)
2. $S$ <- Desplazar_fila(S)
3. $S$ <- Mezclar_columna(S)
4. $S$ <- $k_1 \oplus S$

$k_i$  subllave correspondiente a la i-esima ronda

Para 10 rondas:
- Se tienen 10 rondas completas (4 pasos)
- Ultima ronda