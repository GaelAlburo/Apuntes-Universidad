Una computadora digital consta:
- Memoria
- Unidad ejecutiva - Procesador
- Control (Bus datos, direcciones, control)

# Tipos

Arquitectura Von Neuman
- Procedimientos de manera secuencial

Arquitectura Harvard
- Procesos en pipeline

> [!info] Se codificara en codigo maquina, no se usan mnemónicos sino su codigo en hexadecimal

# Arquitectura VonNeumman

- 1 solo CPU
- 1 instruccion a la vez
- Solo se puede buscar o almacenar un dato a la vez
	- Se debe cumplir
		- Datos e instrucciones codificados
		- Datos e instrucciones en memoria

**Jerarquia de Memoria** (tiempos de acceso):
- Registros internos
- Memoria Principal (RAM, ROM)
	- RAM - Programa principal
- Memoria Secundaria (optica, magnetica)
- Memoria de otros dispositivos

## Pasos de Ejecucion de Instruccion:
- **Fetch:** Trae el codigo a ejecutar
- **Decode:** Sabe que micro-operaciones debe realizar para ejecutarla
- **Execute:** Se obtienen los operandos que requiere y se ejecuta
- **Write**: Si lo requiere, se escribe el resultado en memoria externa.  <mark class="hltr-pink">Se calcula la direccion de la sig. instruccion</mark>

# Microprogramacion

**Macro**
> En RAM, Ensamblador, pseudocodigo

**Micro**
> En ROM, LTR, carta ASM

- Requiere el diagrama esquematico del procesador
- El microprograma se desarrolla con logica de transferencia de registros y cartas ASM
- Microprograma debe quedar documentado en el worksheet de microprogramacion

