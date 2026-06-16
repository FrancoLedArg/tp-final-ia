# Fuente 02 — Respuesta de Northpointe / Equivant

## Identificación de la fuente
- **Documento técnico de la empresa:** William Dieterich, Christina Mendoza y Tim Brennan (Northpointe Inc.), "COMPAS Risk Scales: Demonstrating Accuracy Equity and Predictive Parity" (julio de 2016).
- **Contexto recogido por terceros:**
  - "Algorithmic Fairness – ProPublica v. Northpointe" (Marcello Di Bello): https://www.marcellodibello.com/algorithmicfairness/handout/ProPublica-Northpointe.html
  - "How to Argue with an Algorithm: Lessons from the COMPAS ProPublica Debate" (Colorado Tech. Law Journal): http://ctlj.colorado.edu/wp-content/uploads/2021/02/17.1_4-Washington_3.18.19.pdf
  - "COMPAS Case Study" (M. Chawla, Medium): https://mallika-chawla.medium.com/compas-case-study-investigating-algorithmic-fairness-of-predictive-policing-339fe6e5dd72

## Qué afirma
Northpointe rechazó la acusación de sesgo racial y sostuvo que COMPAS **es justo** porque cumple la **paridad predictiva (predictive parity) / calibración**: para un mismo puntaje, la tasa real de reincidencia es similar en ambos grupos raciales. Es decir, el puntaje "significa lo mismo" sin importar la raza.

## Datos clave verificables
- **Paridad predictiva:** entre las personas etiquetadas "alto riesgo", la proporción que NO reincide es parecida entre blancas y negras (≈41% blancas vs ≈37% negras); entre las "bajo riesgo", la proporción que sí reincide también es similar (≈29% blancas vs ≈35% negras). Estas diferencias en *prediction errors* (FPP/FNP) no son grandes.
- **Argumento de tasas base:** Northpointe sostiene que ProPublica ignoró que las **tasas base de reincidencia difieren** entre grupos (≈0,51 para personas negras vs ≈0,39 para blancas en esos datos), lo que explica matemáticamente las diferencias en falsos positivos/negativos observadas por ProPublica.
- **Objeción metodológica:** acusó a ProPublica de combinar las categorías "alto" y "medio" en un solo "mayor riesgo", inflando la tasa de falsos positivos.
- **Matiz del propio fundador:** Tim Brennan reconoció después que factores correlacionados con la raza podrían influir, y que COMPAS nunca fue pensado como única prueba para tomar una decisión.
- **Cambio corporativo:** en enero de 2017 Northpointe se fusionó con Courtview Justice Solutions y Constellation Justice Systems para formar **Equivant**, manteniendo las líneas de producto (incluido COMPAS).

## Para qué lado del juicio sirve
- **Defensa:** núcleo del alegato técnico — el modelo es "justo" bajo una definición estadística legítima (calibración/paridad predictiva); el desbalance de errores se deriva de tasas base distintas, no de un sesgo introducido por la empresa.
- **Acusación:** la defensa elige la métrica que la favorece; la calibración no neutraliza el daño concreto de los falsos positivos sobre personas negras, y la opacidad del modelo impide verificar la afirmación de "equidad".
