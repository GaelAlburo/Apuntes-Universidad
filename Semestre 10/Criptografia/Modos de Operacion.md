## Operaciones y Funciones

1. Concatenacion   `|`
`0001 | 1110 = 00011110`

2. OR exclusiva $\bigoplus$
3. LSB$_S$
4. MSB$_S$

___
### Nomenclatura
- `b` - tamano del bloque
- `n` - numero de bloques total
- `j` - numero de bloques de ronda
- `IV` - vector de inicializacion
- `CTR` - contador
- `CIPH_k` - funcion cifrado con llave k
- `P` - texto plano (bloque)

____
## Electronic Codebook Mode (ECB)

- ECB Encryption
$$C_j = CIPH_k \, (P_j) \; \; \text{para} \; \; j=1,...,n$$
- ECB Decryption
$$P_j = CIPH_k^{-1} \, (C_j) \; \; \text{para} \; \; j=1,...,n$$

## Cipher Block Chaining (CBC)

- CBC Encryption
$$C_1 = CIPH_k (P_1 \oplus IV)$$
$$C_j = CIPH_k (P_j \oplus C_{j-1}) \;\; \text{para} \;\; j=2, ..., n$$
- CBC Decryption
$$P_1 = CIPH_k^{-1} (C_1) \oplus IV$$
$$P_j = CIPH_k^{-1} (C_j) \oplus C_{j-1} \;\; \text{para} \;\; j=2, ..., n$$

## Output Feedback Mode (OFB)


## Cipher Feedback Mode (CFB)

