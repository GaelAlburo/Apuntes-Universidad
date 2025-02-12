
alfabeto = {A, B, C, ..., Z}
n = x
new_msg = ""
for c in s:
	si c en alfabeto:
		new_c = (c + n) % 26
		 new_msg.append(new_c)


**Cifrado**
1. Definir alfabeto
2. Asignar valores a alfabeto
3. Obtener mensaje a cifrar
4. Obtener el valor de la llave n
5. Por cada caracter en el mensaje a cifrar:
	1. Si el caracter es parte del alfabeto:
		1. Sumamos la posicion del caracter mas el valor de n y le aplicamos el modulo de la longitud del alfabeto
		2. A este resultado obtenemos el caracter que representa en el alfabeto
		3. Este caracer se anade al mensaje cifrado
		4. Regresa al paso 1
6. Se tiene el mensaje cifrado

**Descifrar**
1. Obtener alfabeto
2. Asignar valores a alfabeto
3. Obtener mensaje a descifrar
4. Obtener el valor de la llave n
5. Por cada caracter en el mensaje a cifrar:
	1. SI el caracter esta en el alfabeto:
		1. Restamos la posicion del caracter mas el valor de n y le aplicamos el modulo de la longitud del alfabeto
		2. A este resultado obtenemos el caracter que representa en el alfabeto
		3. Este caracer se anade al mensaje descifrado
		4. Regresa al paso 1
6. Se tiene el mensaje descifrado

>[!done] Crear codigo a partir del pseudocodigo. Subir el codigo en github


