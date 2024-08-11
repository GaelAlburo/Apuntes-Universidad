Sistemas de SW o HW autónomos o semiautónomos

> [!done] **Autonomía:** Habilidad de tomar decisiones basadas en una representación interna del mundo, sin ser controlada por una instancia central

Los agentes se comunican con su ambiente y efectúan cambios al ejecutar sus acciones.

**Racionalidad: Percepciones $\rightarrow$ Razonamiento $\rightarrow$ Acciones**

___
# Capacidad de Agentes
- **Autonomía:**
	- Actuar sin intervención humana directa o de otros agentes
- **Sociabilidad:**
	- Interactuar con otros agentes
- **Reactividad:**
	- Reaccionar en un tiempo preestablecido
- **Proactividad:**
	- Capaces de deliberar que tareas ejecutar para llegar a la meta
- **Iniciativa**
	- Emprendedor y toma iniciativa para actuar según los objetivos
- **Movilidad**
	- Habilidad de trasladarse
- **Veracidad**
	- No comunica información falsa
- **Benevolencia**
	- No tiene objetivos contradictorios e intenta realizar la tarea solicitada
- **Racionalidad**
	- Tiene objetivos específicos y siempre intenta cumplirlos

___
# Ejemplo Agente
$a = f(P, M, A)$

Sus acciones se basan en:
- Percepciones
- Metas
- Ambiente

___
# Percepción
Permite al agente hacerse una idea del entorno donde se mueve
- Puede ser completa o indexada

___
# Acción

___
# Ambientes
- Accesible / Inaccesible
- Determinista / No determinista
- Episódico / No episódico
- Estático / Dinámico
- Discreto / Continuo

___
# Piloto Automático
- **Percepciones**
	- Video
	- Acelerómetro, instrumental del tablero
	- Sensores del motor
	- Teclado
- **Acciones**
	- Gestión del volante
	- Acelerar y frenar
	- Bocina
	- Hablar / Dibujar
- **Metas**
	- Seguridad
	- Llegar a destino
	- Maximizar ganancias
	- Obedecer leyes
- **Ambiente**
	- Calles urbanas
	- Avenidas
	- Trafico
	- Clima
	- Peatones
	- Tipo de cliente

___
# Arquitecturas para Agentes
- **Arquitectura Reactiva:**
	- La acción esta directamente ligada a la percepción
- **Arquitectura Deliberativa:**
	- El agente tiene un modelo del mundo, un estado interno, objetivos y es capaz de predecir el resultado de sus acciones y planificar en consecuencia
- **Arquitectura Hibrida:**
	- Combina dos estrategias anteriores

___
## Agentes Reactivas
**Ventajas:**
- Simples conceptualmente
- Consumen pocos recursos y poco costosas computacionalmente
- Robustas ante fallos
- Imitan comportamientos biológicos

## Agentes Deliberativos
Expresan la informacion sobre el entorno y su comportamiento (estado interno y acciones) en forma de conocimiento simbolico
- Posee un mdelo del entorno y asya de sus dqpacidades
- Dos aproximaciones

Problemas:
- Excesiva revision - El agente no actúa
- Pobre revision - El mundo evoluciona y los objetivos son inalcanzables
- Equilibrio entre pro-actividad y reactividad

___
# IA Distribuida
Es la resolución distribuida de problemas
- Se divide en módulos que cooperan
- El conocimiento del problema se divide y se comparte entre los modulos

## Multiagentes
Es necesario dividir el problema en un multiples agentes autónomos que interactúen de forma dinámica e imprevista

Es necesario definir mecanismos de organización y sociales para regular su interacción

# Multiagentes VS. Agente
- Con un solo agente se centraliza la toma de decisiones