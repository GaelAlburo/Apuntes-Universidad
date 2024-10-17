
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


