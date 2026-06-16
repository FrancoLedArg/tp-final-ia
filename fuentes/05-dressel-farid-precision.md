# Fuente 05 — Dressel & Farid: precisión y límites de la predicción

## Identificación de la fuente
- **Autores:** Julia Dressel y Hany Farid (Dartmouth College).
- **Publicación:** "The accuracy, fairness, and limits of predicting recidivism", *Science Advances*, vol. 4, n.º 1, 17 de enero de 2018.
  - Science Advances: https://www.science.org/doi/10.1126/sciadv.aao5580
  - Copia abierta (Dartmouth): https://digitalcommons.dartmouth.edu/cgi/viewcontent.cgi?article=2345&context=facoa
  - PMC: https://pmc.ncbi.nlm.nih.gov/articles/PMC5777393/
- **Cobertura periodística:** Ed Yong, *The Atlantic*; ficha en Privacy International: http://privacyinternational.org/examples-abuse/1962/

## Qué afirma
COMPAS **no es más preciso ni más justo que personas no expertas** en justicia penal. Además, su precisión puede replicarse con un modelo trivial, lo que cuestiona el valor agregado de su complejidad y opacidad.

## Datos clave verificables
- **Humanos no expertos vs COMPAS:** 400 voluntarios reclutados en una plataforma de crowdsourcing (sin experiencia en justicia penal), viendo solo descripciones breves con 7 datos, acertaron en promedio **63%** (y **67%** al agrupar respuestas). COMPAS acierta **~65%**.
- **2 variables ≈ 137 variables:** un clasificador lineal simple con **solo dos variables** (edad y número de condenas previas) alcanza una precisión prácticamente equivalente a la de COMPAS, que usa **137 variables**.
- **Sin mejora con modelos más sofisticados:** clasificadores más complejos no mejoran ni la precisión ni la equidad.
- **Conclusión de los autores:** estos resultados "siembran dudas serias sobre todo el esfuerzo de predicción algorítmica de la reincidencia". No piden prohibir las herramientas, sino exigir que **demuestren que funcionan antes** de usarlas para decidir sobre la vida de las personas.

## Para qué lado del juicio sirve
- **Acusación (clave):** desproporción entre el poder de la herramienta (influir en libertad/fianza/condena) y su fiabilidad real (≈65%, igual que legos y que un modelo de 2 variables). La opacidad y los 137 ítems no aportan valor que justifique su uso en decisiones tan graves.
- **Defensa:** ~65% puede ser comparable o superior a la intuición de operadores con sobrecarga de casos; como apoyo a la decisión humana, ofrece consistencia. Los propios autores no piden prohibirla, sino validarla.
