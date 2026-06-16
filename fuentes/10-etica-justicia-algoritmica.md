# Fuente 10 — Ética de la justicia algorítmica: supervisión, individualización y responsabilidad

## Identificación de la fuente
- **Madeleine Clare Elish, "Moral Crumple Zones: Cautionary Tales in Human-Robot Interaction", *Engaging Science, Technology, and Society* (2019).**
  - Artículo: https://estsjournal.org/index.php/ests/article/view/260
  - PDF: https://estsjournal.org/index.php/ests/article/download/260/177/
  - Pre-print (WeRobot 2016): https://robots.law.miami.edu/2016/wp-content/uploads/2015/07/ELISH_WEROBOT_cautionary-tales_03212016.pdf
- **"Automation bias" (revisión y definiciones).**
  - Wikipedia (síntesis con referencias a Mosier & Skitka, Parasuraman & Manzey): https://en.wikipedia.org/wiki/Automation_bias
  - Alan Turing Institute, "Bias Mitigation" (decision-automation bias): https://alan-turing-institute.github.io/turing-commons/skills-tracks/aeg/chapter4/bias/
  - Revisión sistemática (PMC): https://pmc.ncbi.nlm.nih.gov/articles/PMC7651899/

## Qué afirman
Reúne los conceptos éticos que conectan el funcionamiento técnico con la responsabilidad humana, y que dan nombre a las fallas morales del caso COMPAS.

### 1. "Zona de absorción moral" (moral crumple zone) — Elish
Cuando el control de una acción se distribuye entre componentes humanos y automáticos, la responsabilidad tiende a recaer injustamente sobre el **operador humano más cercano**, que en realidad tiene **conocimiento y control limitados** del sistema. Igual que la zona de deformación de un auto absorbe el impacto para proteger el habitáculo, el humano "en el bucle" absorbe la culpa **para proteger la integridad del sistema técnico** (y a quienes lo diseñaron y vendieron). La retórica del "humano en el bucle" crea una **ilusión de supervisión** que no se corresponde con la agencia real del operador.

### 2. Sesgo de automatización (automation bias)
Tendencia de las personas a **favorecer las sugerencias de un sistema automatizado** e ignorar información contradictoria, aun cuando esta sea correcta (Mosier & Skitka; Parasuraman & Manzey). Se agrava bajo carga cognitiva, presión de tiempo y cuando se percibe a la máquina como analíticamente superior. Produce **errores de omisión** (no detectar el fallo que el sistema no señaló) y **errores de comisión** (actuar según un consejo incorrecto). Es central para evaluar si la "supervisión humana" del juez sobre COMPAS era real o nominal.

### 3. Justicia individualizada vs. predicción actuarial
COMPAS predice a partir de **características de grupos de referencia**, no del individuo (ver Fuente 03, *Loomis*, agravio 2). Esto choca con un principio ético-jurídico básico: a una persona se la debe juzgar por sus actos, no por la conducta estadística de un grupo al que se la asimila. Decidir sobre la **libertad** de alguien con una probabilidad grupal plantea un dilema moral, no solo técnico.

## Cómo se conectan con el caso
- La elección de qué definición de equidad priorizar (ver Fuente 04) es una **decisión moral con apariencia de decisión técnica**: alguien decide, en secreto, sobre quién recaerá el error.
- El juez que usa el puntaje puede convertirse en la "zona de absorción moral" del sistema: carga con la decisión final mientras la empresa que diseñó la caja negra queda fuera de foco. La acusación debe evitar que la responsabilidad se concentre solo allí.
- El sesgo de automatización explica por qué la salvaguarda de *Loomis* ("no determinante", "el juez decide") puede ser insuficiente en la práctica: el puntaje "ancla" la decisión humana.

## Para qué lado del juicio sirve
- **Acusación:** da nombre técnico a por qué la "supervisión humana" fue ilusoria (automation bias) y por qué la empresa no puede escudarse en el juez (moral crumple zone); fundamenta el reproche ético de usar estadística de grupo para decidir sobre individuos.
- **Defensa:** puede invocar que la decisión final y la responsabilidad moral son del operador humano que conserva agencia (human-in-the-loop), y que el sesgo de automatización es una falla de capacitación y uso del operador/Estado, no un defecto del producto.
