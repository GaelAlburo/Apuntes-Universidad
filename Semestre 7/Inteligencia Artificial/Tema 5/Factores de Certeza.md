Links: [[Inteligencia Artificial]]
___

- Cuantifican el grado de confianza y desconfianza
- En inferencias se combinan y propagan valores de certidumbre
- Factores de certeza se usan reglas de producción (SE)
- FCs en rango de [-1, +1]
- -1: evidencia totalemente en contra de la hipotesis
- +1: evidencia totalmente a favor de la hipótesis
---
#### Ejemplo 1

FC(Cond, Conclu) = Conclu\*max(0,Cond)
1. IF hay-fiebre THEN hay-gripe (0.67)
	FC(R1)=.67
2. IF hay-fiebre (.8) THEN hay-gripe
	FC(R2)=.8
3. Si A (.45) and B(.68) THEN C
	FC(R3)=min(.45,.68)=.45
4. Si A (.45) and B(.68) THEN C(.93)
	FC(R4)=min(.45,.68)\*.93=.45\*.93 = .41
___
#### Ejemplo 2
1. Reglas:
	 R1: if (A or B) and C then H with CF1 = 0.9
	 R2: if D                     then F with CF2 = 0.8
	 R3: if E                      then F with CF3 = 0.6
	 R4: if F                      then H with CF4 = 0.8
2. Hechos reales
	A: CF(A) = 0.7
	B: CF(B) = 0.8
	C: CF(C) = 1
	D: CF(D) = 0.7
	E: CF(E) = 0.6
3. Resultados
	FC(R1) = max(0.7, 0.8) \* 0.9 = 0.8 \* 0.9 = 0.72
	FC(R2) = 0.7 \* 0.8 = 0.56
	FC(R3) = 0.6 \* 0.6 = 0.36
	FC(R4)_R2_ = 0.56 \* 0.8 = 0.448
	FC(R4)_R3_ = 0.36 \* 0.8 = 0.288
---

## Evaluacion de Resultados
- **-1** indica que es seguro que la evidencia **no apoya** la hipotesis
- **1** indica que es seguro que la evidencia **apoya** la hipotesis
- **0** representa la ignorancia, **no se puede inferir** una hipotesis