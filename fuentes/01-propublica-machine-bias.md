# Fuente 01 — ProPublica, "Machine Bias" (2016)

## Identificación de la fuente
- **Autores:** Julia Angwin, Jeff Larson, Surya Mattu y Lauren Kirchner.
- **Publicación:** ProPublica, 23 de mayo de 2016.
- **Artículo principal:** "Machine Bias. There's software used across the country to predict future criminals. And it's biased against blacks."
  - URL: https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing
- **Anexo metodológico:** "How We Analyzed the COMPAS Recidivism Algorithm."
  - URL: https://www.propublica.org/article/how-we-analyzed-the-compas-recidivism-algorithm
- **Réplica al fabricante:** "ProPublica Responds to Company's Critique of Machine Bias Story."
  - URL: https://www.propublica.org/article/propublica-responds-to-companys-critique-of-machine-bias-story

## Qué afirma
La investigación analizó los puntajes de riesgo de COMPAS asignados a más de 7.000 personas arrestadas en el condado de Broward (Florida, EE.UU.) en 2013 y 2014, y verificó cuántas fueron acusadas de nuevos delitos en los dos años siguientes (el mismo horizonte que usan los creadores del algoritmo). Conclusión: el sistema acertaba a tasas globales parecidas para personas negras y blancas, pero **se equivocaba de manera muy distinta según la raza**, perjudicando a las personas negras.

## Datos clave verificables
- **Precisión global:** COMPAS predice correctamente la reincidencia el ~61% de las veces. Por raza, la precisión es casi idéntica: 62,5% para personas blancas y 62,3% para personas negras (otro corte de los datos da 67,0% vs 63,8%).
- **Falsos positivos (marcadas "alto riesgo" pero NO reinciden):** las personas negras tenían casi el doble de probabilidad de ser mal clasificadas como alto riesgo que las blancas: **45% vs 23%** (44,9% vs 23,5% en el cálculo del anexo).
- **Falsos negativos (marcadas "bajo riesgo" pero SÍ reinciden):** las personas blancas tenían casi el doble de probabilidad de ser mal clasificadas como bajo riesgo: **48% vs 28%** (47,7% vs 28,0%).
- **Control estadístico:** usando regresión logística para aislar el efecto de la raza de los antecedentes penales, la edad y el género, las personas negras seguían siendo **77% más propensas** a ser marcadas como de alto riesgo de cometer un futuro crimen violento, y **45% más propensas** a ser marcadas con mayor riesgo de cualquier delito.
- **Ejemplo numérico de Broward:** de 1.795 personas negras que NO cometieron delitos futuros, 805 (≈45%) fueron consideradas alto riesgo; entre las blancas, solo 349 de 1.488 (≈23%).
- **Variable raza:** COMPAS no usa la raza como variable de entrada de forma explícita; el sesgo aparece igual, lo que apunta a variables correlacionadas con la raza (proxies).

## Para qué lado del juicio sirve
- **Acusación:** evidencia central del daño desigual (sesgo por proxies pese a no programar "raza"); la asimetría de errores recae sobre un grupo protegido en decisiones que afectan la libertad.
- **Defensa:** la propia ProPublica reconoce que la precisión global es similar entre razas, lo que abre la puerta al argumento de calibración de Northpointe (ver fuente 02 y 04).
