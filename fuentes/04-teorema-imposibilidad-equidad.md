# Fuente 04 — El teorema de imposibilidad de la equidad

## Identificación de la fuente
- **Kleinberg, Mullainathan & Raghavan (2016/2017),** "Inherent Trade-Offs in the Fair Determination of Risk Scores."
  - arXiv: https://arxiv.org/pdf/1609.05807
  - Versión ITCS 2017: https://drops.dagstuhl.de/storage/00lipics/lipics-vol067-itcs2017/LIPIcs.ITCS.2017.43/LIPIcs.ITCS.2017.43.pdf
- **Chouldechova (2017),** "Fair Prediction with Disparate Impact" (llega a la misma conclusión de forma independiente).
- **Generalización:** Friedler et al., "The (Im)possibility of Fairness", arXiv: https://arxiv.org/pdf/1707.01195
- **Divulgación:** glosario "Impossibility Theorem": https://www.bestaiweb.ai/glossary/impossibility-theorem/

## Qué afirma
Es **matemáticamente imposible** que un sistema de puntaje de riesgo (que no sea perfecto) cumpla a la vez estas tres condiciones de equidad cuando las **tasas base** del resultado difieren entre grupos:
- **(A) Calibración / paridad predictiva:** para un mismo puntaje, la probabilidad real del resultado es igual en todos los grupos.
- **(B) Balance para la clase positiva:** igual tasa de falsos negativos entre grupos.
- **(C) Balance para la clase negativa:** igual tasa de falsos positivos entre grupos.

Las tres solo coexisten en dos casos irreales: predicción **perfecta** (error cero) o **tasas base idénticas** entre grupos. El resultado es estructural: depende de la estadística, no del diseño del modelo, y vale para cualquier método (algorítmico o no).

## Por qué es el núcleo del caso
Explica directamente la disputa ProPublica vs Northpointe:
- ProPublica midió **(B) y (C)** (balance de errores) y encontró sesgo.
- Northpointe midió **(A)** (calibración/paridad predictiva) y declaró equidad.
- Como las tasas base de reincidencia diferían entre grupos (≈0,51 vs ≈0,39 en Broward), **ambos podían tener razón a la vez**: satisfacer la calibración obligaba a aceptar el desbalance de falsos positivos/negativos. "La matemática no se dobla ante las buenas intenciones."

## Para qué lado del juicio sirve
- **Defensa (clave):** el sesgo no es un "defecto programado" ni una negligencia de la empresa; es una imposibilidad matemática inherente. Elegir calibración es una decisión técnica defendible.
- **Acusación:** justamente porque hay un trade-off inevitable, **alguien tuvo que elegir** qué noción de equidad priorizar; esa elección (favorecer calibración sobre el balance de errores) la tomó la empresa sin transparencia ni participación pública, y sus consecuencias recaen sobre un grupo protegido. La imposibilidad técnica no exime de la responsabilidad por la elección y por desplegar el sistema en decisiones sobre la libertad.
