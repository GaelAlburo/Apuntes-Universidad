Links: [[Inteligencia Artificial]], [[4. Conocimiento]]
___

# Lógica Proposicional
## Conectivas

- Unarias (o monadicas):
    - Negacion
- Binarias (o diadicas):
    - Conjuncion (^)
    - Disyuncion ()
    - Condicional (→)
    - Bicondicional (↔)

- Del lenguaje natural a I.A. mediante la logica de preposiciones
- Creacion de oraciones proposicionales
- Formalizar mediante formulas bien formadas
- Variables proposicionales, conectivas logicas y cuando es necesario parentesis

![[Pasted image 20230924214243.png]]
___
## Reglas de Inferencia
- **Inferencia** - Proceso para obtener una conclusión a partir de unas premisas de modo que el razonamiento valido
    - Modus Pollens
    - Modus Tollens
    - Y-eliminación
    - Resolución unitaria

___
# Lógica del Predicado
- Extiende de la lógica proposicional, permite expresar conocimiento de múltiples objetos
- Permite utilizar variables para los términos
- Las proposiciones son divididas en términos

- Un **predicado** (términos) es una relación entre los términos
    - Pueden haber 1 o N términos separados por “_,_”
        - Los términos son constantes
        - O son variables

- El predicado es la relación entre los términos
- Generalmente es un verbo (excepto ser/estar)

### Cuantificadores
- Expresar propiedades de grupos de objetos
    - Universal → Se generaliza la característica $\forall$
    - Existencial → $\exists$

#### Ejemplos
- (Universal)X niño(X) → juega(X): Todos los niños juegan.
    - niño(juan): juega juan
- (Existencial)gato(X) ^ toma(X,leche): Al menos uno de los gatos toma leche

- Razonamiento por particularización:
    - Predicado 1: (Universal)X hombre(X) → mortal(X)
    - Predicado 2: hombre(marco)
    - Conclusión: mortal(marco)

-  madre(ana,luis) → Preposicion: Ana es madre de Luis
-   padre(juan,ana) → Preposicion: Juan es padre de Ana
-   ($\forall$ X) ($\forall$ Y) ($\forall$ Z) padre(X,Y) $\land$ (padre(Y,Z) $\lor$madre(Y,Z)) → abuelo(X,Z)
- Conclusión: abuelo(juan, luis)