Links
___
# Registros

## PC (Program Counter)\
Guarda la direccion de la siguiente instruccion a ejecutar

## IR (Instruction Register)
Guarda el codigo de operacion de la instruccion que se esta ejecutando

## MAR (Memory Access Register)
Sirve para direccionar la memoria externa

## MBR (Memory Bidirectional Register)
Sirve para leer y escribir en memoria estatica
## A y B (Registros Acumuladores)
Guardan datos y en ellos podemos hacer operaciones logico-aritmeticas

## T (Temporizador)
En memoria principal

## M (Memoria)
Registro activo de memoria externa

## ROM
Set de instrucciones, maquinas de estados, microprogramación

___
# Logica de Transferencia de Registros

**Registros**: Unidad básica de datos

**Transferencia**: Operacion basica entre registros    A <- B

## 1. Microoperaciones de Transferencia

- **Paralela**
- **Corrimiento**
	- A <- shl A (izq)
	- A <- shr A (der)
	- A< cshl A (corrimiento circular izq)
	- A <- cshr A ("" "" der)

A =  1 0 0 1 0 1 0 1
A <- shl A
A = 0 0 1 0 1 0 1 0

A = 1 0 0 1 0 1 0 1
A <- cshl
A = 0 0 1 0 1 0 1 1


> A <- M (NO)       MBR <- M    A <- MBR  (SI)

## 2. Microoperaciones de Registro

- **Incremento**
	- A <- A + 1
	- PC <- PC + 1 (Mas usado: para pasar de instruccion)

- **Decremento**
	- A <- A - 1

## 3. Microoperaciones logico-aritmeticas

- **Aritmeticas**
	- A <- A + B
	- A <- A- B
	- A <- A \* B
	- A <- A / B

- **Logicas**
	- OR:  A <- A ^ B
	- AND:  A<- A ^ B
	- XOR:  A <- A X B
	- NOT:  A <- not A

> A <- A + MBR (NO. MBR no esta conectado al ALU, no se pueden hacer operaciones con MBR. Se)

___
# Operaciones

| Cod. Operacion | Mnemonico | Descripcion  |
| -------------- | --------- | ------------ |
| 01H            | NOP       | No operation |


- **Ciclo Fetch (fetch y decode)**
$NOP_{t0}$: MAR <- PC
$NOP_{t1}$: MBR <- M  (MBR = NOP) 
$NOP_{t2}$: IR <- MBR,  PC <- PC + 1
- **Ciclo de Ejecucion (execute y write)**
$NOP_{t3}$: T <- 0
(Colocando t en 0, nos coloca en el ciclo fetch nuevamente, buscando la siguiente instruccion)

___

| Cod. Operacion | Mnemonico | Descripcion                      |
| -------------- | --------- | -------------------------------- |
| 02H            | MOVB      | Transfiere el contenido de B a A |

- **Ciclo Fetch**
$MOVB _ {t0}$ : MAR <- PC
$MOVB _ {t1}$ : MBR <- M (MBR = MOVB)
$MOVB _ {t2}$ : IR <- MBR,  PC <- PC + 1  (IR = MOVB)
- **Ciclo de Ejecucion**
$MOVB _ {t3}$ : A <- B, T <- 0

>[!done] El ciclo fetch es el mismo para todas las operaciones. Hasta el t=3 es donde cambian las instrucciones

___

| Cod. Operacion | Mnemonico | Descripcion                                                        |
| -------------- | --------- | ------------------------------------------------------------------ |
| 03H            | LDI       | Guarda el valor enseguida del codigo de operacion en el registro A |

- **Ciclo Fetch**\
`mismas 3 instrucciones`
- **Ciclo de Ejecucion**
$LDI_{t3}$ : MAR <- PC
$LDI _ {t4}$ : MBR <- M
$LDI _ {t5}$ : A <- MBR,  T<- 0,  PC <- PC + 1

___

| Cod. Operacion | Mnemonico | Descripcion                                                                                  |
| -------------- | --------- | -------------------------------------------------------------------------------------------- |
| 04H            | LDB       | Obtiene el valor efectivo con la direccion enseguida del upcode y guardarlo en el registro B |

- **Ciclo Fetch**
`mismas instrucciones`
- **Ciclo de Ejecucion**
$LDB_{t3}$ : MAR <- PC
$LDB _ {t4}$ : MBR <- M
$LDB _ {t5}$ : MAR <- MBR
$LDB _ {t6}$ : MBR <- M
$LDB _ {t7}$ : B <- MBR,   T<- 0,  PC <- PC + 1

___

| Cod. Operacion | Mnemonico | Descripcion                                |                         |
| -------------- | --------- | ------------------------------------------ | ----------------------- |
| 06H            | JMP       | Salto forzado a la direccion proporcionada | PC $\leftarrow$ M (JMP) |

Memoria Externa:

| Dir2  | 8004 |
| ----- | ---- |
| Dir3  | 8005 |
| JMP   | 8006 |
| 80F0H | 8007 |
| ...   |      |
| ...   |      |
| Instr | 80F0 |

- **Ciclo Fetch**
`mismas instrucciones`
- **Ciclo de Ejecución**
$JMP_{t3}$ : MAR $\leftarrow$ PC
$JMP_{t4}$ : MBR $\leftarrow$ M
$JMP_{t5}$ : PC $\leftarrow$ MBR, T $\leftarrow$ 0

___

| Cod. Operacion | Mnemonico | Descripción                                                |
| -------------- | --------- | ---------------------------------------------------------- |
| 07H            | PSHB      | Coloca el valor B en el tope de la pila (apuntado por AP2) |

Memoria Externa:

| Dir2  | 8004 |
| ----- | ---- |
| Dir3  | 8005 |
| JMP   | 8006 |
| 80F0H | 8007 |
| ...   |      |
| ...   |      |
| PSHB  | 80F0 |
| AP1   | 80F1 |

Pila: (Se usan dos apuntadores porque AP2 ira cambiando, AP1 sirve solo de referencia sin importar los cambios de AP2)

| AP2    | AP1 |
| ------ | --- |
| ...    |     |
| ...    |     |
|        | AP2 |
| Dato2  |     |
| Dato1  |     |
| Inicio |     |

- **Ciclo Fetch**
`mismas instrucciones`
- **Ciclo de Ejecución**
$PSHB_{t3}$ : MAR $\leftarrow$ PC
$PSHB_{t4}$ : MBR $\leftarrow$ M (MBR = AP1)
$PSHB_{t5}$ : MAR $\leftarrow$ MBR `Tenemos acceso a AP2`
$PSHB_{t6}$ : MBR $\leftarrow$ M (MBR = AP2) 
$PSHB_{t7}$ : MBR $\leftarrow$ MBR - 1  (MBR = AP2 - 1)
$PSHB_{t8}$ : M $\leftarrow$ MBR  `Actualizamos el tope de la pila`
$PSHB_{t9}$ : MBR $\leftarrow$ MBR + 1  `Se regresa al valor actual de la pila`
$PSHB_{t10}$ : MAR $\leftarrow$ MBR (MAR = AP2)
$PSHB_{t11}$ : MBR $\leftarrow$ B,  PC $\leftarrow$ PC + 1
$PSHB_{t12}$ : M $\leftarrow$ MBR,  T $\leftarrow$ 0

