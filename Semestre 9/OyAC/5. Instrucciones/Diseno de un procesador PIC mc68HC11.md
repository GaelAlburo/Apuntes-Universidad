ziiuhw
Secuenciador Basico - Funcion principal: Controla todos los demas componentes

# Tipos de Acceso

- Acceso inmediato
- Acceso extendido
- Acceso directo
- Acceso indexado
- Acceso relativo
- Acceso inherente

# Instrucciones


| Opcode | Mnemonico | Descripcion       | LTR      | CCR             |
| ------ | --------- | ----------------- | -------- | --------------- |
| 09     | INC       | Incrementa X en 1 | X <- X+1 | - - - - - - - - |


- **Acceso Inherente**
Solo se necesita conocer el codigo de operacion para ejecutar la instruccion.
El codigo de operacion puede ser de 8 a 16 bits


Estados de direccion 00h - 07h son de inicializacion del sistema.
- A partir de la direccion 08h empieza el ciclo fetch, que consiste de 3 estados

La decodificacion se realiza mediante un salto de transformacion. El salto se define como el Opcode de la instruccion adjuntandole 4 ceros a la derecha.  (NOP0h)

Despues de ejecutar la instruccion se realizara un salto de interrupcion. En caso de ser `1` se tratan las interrupciones I y X. Si es `0` se regresa al ciclo fetch.
Las interrupciones siempre son el estado P

___

| Opcode | Mnemonico | Descripcion       | LTR      | CCR                                  |
| ------ | --------- | ----------------- | -------- | ------------------------------------ |
| 09     | INC       | Incrementa X en 1 | X <- X+1 | ![[Pasted image 20241017074748.png]] |

- Se incrementa X con `X0`
- Despues se establecen las banderas marcadas en la tabla
- Ya terminando de ejecutar se realiza el salto de interrupcion, un camino regresa al tratamiento de interrupciones y el otro realiza el primer paso del ciclo fetch

___

| Opcode | Mnemonico | Descripcion                                | LTR  | CCR |
| ------ | --------- | ------------------------------------------ | ---- | --- |
| C6     | LDAB      | Carga el dato inmediato en el acumulador B | B<-M |     |

____

| Opcode | Mnemonico | Descripcion                                                       | LTR    | CCR |
| ------ | --------- | ----------------------------------------------------------------- | ------ | --- |
| 1B     | ABA/      | Suma el dato del ACCA con el ACCB. El resultado se guarda en ACCA | A<-A+B |     |

- ABA se ejecuta despues de LDAB y LDAB, ya que necesita haber valores en ACCA y ACCB
- Activando `Selmux` quitamos el `Cin` de nuestra suma en el UPA. Esto hace que tome en cuenta `ACCSEC` (su valor por default es 0)


# Acceso Directo

Tienen un codigo de operacion de 8 o 16 bits. Tienen una direccion de memoria de 8 bits.

| Opcode | Mnemonico | Descripcion                                              | LTR            | CCR                                  |
| ------ | --------- | -------------------------------------------------------- | -------------- | ------------------------------------ |
| A8     | STAA      | Guarda el dato del acumulador A en la direccion efectiva | M\[00Dir] <- A | ![[Pasted image 20241024072016.png]] |

- Se hara uso del registro RA para hacer el direccionamiento. 
	- Primero se guarda un 00h en la parte alta de RA, en la parte baja se gaurdadra la direccion `Dir`.
- Guardamos la direccion `Dir` en `R.Dir`, para poder tener acceso a este numero. Este se colocara en la parte baja de `RA`.
- Para leer la memoria se usa `!AS`. Y `!R/W` debe estar desactivada (=1).
- Con esto ya se tiene la direccion efectiva en `RA`.

- Ahora esta direccion se transfiere a `R.Dir`

>[!info] Estas 4 primeras instrucciones siempre seran el acceso directo

Ahora se realizara el guardado de A en la direccion efectiva

- Por simplicidad se utiliza siempre la parte baja. Se accesa la parte baja de ACCA
- Se activa `!AS` y `!R/W` para escribir en memoria.

---

| Opcode | Mnemonico | Descripcion                           | LTR            | CCR          |
| ------ | --------- | ------------------------------------- | -------------- | ------------ |
| 7D     | JMP       | Salto forzado a la direccion efectiva | PC <- \[00Dir] | ![[JMP.png]] |

- A diferencia de STAA, el direccionamiento se almacena en `PC`, no en `R.Dir`.

# Acceso Extendido
Tienen un codigo de operacion de 8 o 16 bits. Tienen nua direccion de memoria de 16 bits.

Direccion efectiva:
DPA DP8h

Rango: 0000h .. .. .. FFFFh


___
# Acceso Indexado

Tiene un codigo de operacion de 8 o 16 bits y un desplazamiento de 8 bits.

Se haran suma a complemento a 2 para realizar restas.

| Opcode | Mnemonico | Descripcion                                                          | LTR              | CCR                                  |
| ------ | --------- | -------------------------------------------------------------------- | ---------------- | ------------------------------------ |
| A9     | STAA      | Guarda en la direccion efectiva el dato en el acumulador A. INDEXADO | M\[X+Despl] <- A | ![[Pasted image 20241024072016.png]] |


Para este ejemplo se utiizara desplazamiento negativo

- Primero se hace un backup del CCR en RAbaja
- Los primeros 4 estados son la primera ecuacion
- Despues tendremos que hacer la ec.2 o la ec.3 dependiendo si es desplazamiento positivo o negativo, correspondientemente
	- Se verifica el valor del bit mas significativo Q7 para saber que tipo de desplazamiento
- Despues se reestablece el CCR del valor guardado en RA. Esto ya que el valor de  CCR es del desplazamiento, no del sistema, debemos guardarlo
- Todas estas 7 instrucciones SERAN LAS MISMAS para todo direccionamiento indexado

___
# Acceso Relativo
Tiene un codigo de operacion de 8 a 16 bits y un desplazamiento de 8 bits
`PCbaja = PCbaja + Despl` ... ec(1)

- Despl Positivo:
`PCalta = PCalta + acarreo`  ... ec(2)

- Despl Negativo
`PCalta = PCalta - !Acarreo`  .. (3)


| Opcode | Mnemonico | Descripcion                                           | LTR                  | CCR          |
| ------ | --------- | ----------------------------------------------------- | -------------------- | ------------ |
| 20     | BRA       | Salto forzado a la direccion efectiva.<br>Acceso: REL | PC <- M\[PC+Despl+2] | ![[JMP.png]] |

- Como las 3 ecuaciones son las mismas que en el direccionamiento indexado, la gran mayoria de estados permaneceran intactos.
	- Lo unico que haremos es cambiar de usar X a utilizar PC para almacenar la direccion efectiva.
	- Y se elimina el estado donde se pasa el valor de X a Reg.Dir.

- Es muy parecido a un JMP, pero no le decimos exactamente a que direccion, sino un desplazamiento.
- Todas las isntrucciones de acceso relativo se pueden considerar como saltos


