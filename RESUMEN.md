# RESUMEN — Caso 1: COMPAS, el algoritmo que puntúa el riesgo de reincidencia

> Documento de síntesis del Caso 1 del [ENUNCIADO.md](ENUNCIADO.md). Toda la información está respaldada por las fuentes verificadas que se guardan en la carpeta [`fuentes/`](fuentes/) y se referencian al pie. El objetivo es reunir material suficiente para que cualquier persona pueda formar un juicio fundamentado y, al final, ofrecer una hipótesis de los puntos aprovechables en el juicio para cada lado.

---

## 1. Los hechos

COMPAS (*Correctional Offender Management Profiling for Alternative Sanctions*) es un software de evaluación de riesgo creado por **Northpointe Inc.** (desde 2017, **Equivant**) y usado por tribunales de EE.UU. para estimar la probabilidad de que una persona acusada vuelva a delinquir. Ese puntaje influye en decisiones de **fianza, libertad condicional y sentencia**.

- En **mayo de 2016**, una investigación de **ProPublica** ("Machine Bias") analizó más de 7.000 casos del condado de Broward (Florida) y encontró que el sistema marcaba erróneamente como "alto riesgo" a personas negras con **casi el doble de frecuencia** que a personas blancas, mientras subestimaba el riesgo de las personas blancas que sí reincidían. [F01]
- **Northpointe** respondió que el modelo estaba estadísticamente **"calibrado"** (paridad predictiva) y que las diferencias se explican por distintas tasas base de reincidencia. [F02]
- El código es **propietario (secreto comercial)**: nadie fuera de la empresa puede inspeccionarlo. Esto fue central en el caso judicial **State v. Loomis** (Wisconsin, 2016), donde un hombre fue sentenciado a 6 años con un puntaje COMPAS de alto riesgo; la Corte avaló el uso con advertencias, y la Corte Suprema de EE.UU. no revisó el caso (2017). [F03]

La disputa "¿es o no es sesgado?" tiene una explicación matemática: el **teorema de imposibilidad de la equidad** demuestra que, con tasas base distintas entre grupos, ningún modelo imperfecto puede ser justo según todas las definiciones a la vez. [F04] Y un estudio posterior mostró que COMPAS **no es más preciso que personas sin formación** y que 2 variables igualan a sus 137. [F05]

## 2. El sistema técnico (en lenguaje llano)

COMPAS es una herramienta **actuarial** de "cuarta generación". [F06]
- **Entrada:** un cuestionario de **137 ítems** (entrevista/formulario) más los registros penales públicos.
- **Factores:** **estáticos** (historial penal, edad al primer arresto — los más influyentes) y **dinámicos** (empleo, educación, consumo de sustancias, entorno social).
- **Salida:** puntajes de reincidencia general, reincidencia violenta y riesgo previo al juicio, en una escala de **1 a 10** (bajo / medio / alto). El puntaje compara a la persona con grupos de referencia con resultados conocidos.
- **Clave:** **no usa "raza" como variable explícita**, pero muchos ítems (barrio, entorno, antecedentes familiares, historial de arrestos) están correlacionados con la raza y actúan como **proxies**. La fórmula de ponderación es secreta (caja negra).

## 3. El daño

- **A quién afectó:** personas acusadas en EE.UU., en particular **personas negras**, evaluadas en decisiones que afectan su **libertad** (fianza, condena, libertad condicional).
- **De qué manera:** el sesgo en los errores significa que una persona negra que no reincidiría tenía mucha más probabilidad de ser etiquetada "peligrosa" (falso positivo), lo que puede traducirse en más tiempo preso, fianzas más altas o condiciones más duras. [F01]
- **Agravante de opacidad:** la persona afectada **no puede ver ni impugnar** cómo se calculó su puntaje (caja negra + secreto comercial), y a menudo no hay vía clara de apelación específica contra el algoritmo. [F03]
- **Agravante de fiabilidad:** se trata de decisiones graves apoyadas en una herramienta con precisión ~65%, equiparable a la de legos. [F05]

## 4. Mapa de responsabilidad

| Actor | Decisión humana concreta que contribuyó al daño |
|---|---|
| **Northpointe / Equivant (empresa)** | Diseñó y vendió un modelo de alto impacto manteniéndolo como **caja negra** (secreto comercial); eligió priorizar la calibración sin transparentar el trade-off de equidad ni someterlo a auditoría externa. [F02][F04][F06] |
| **Jueces / operadores judiciales** | Usaron el puntaje como si fuera un **dato objetivo**, sin entender sus límites ni ejercer una supervisión humana real con poder de revertir. [F03][F05] |
| **Estado / agencias que lo compraron** | Adquirieron y desplegaron el sistema **sin exigir auditoría, transparencia ni pruebas de no discriminación**. [F03][F07] |
| **Regulador / legislador** | Llegó tarde: no había estándar legal de transparencia, control de sesgo o derecho a explicación aplicable al momento de los hechos. [F07][F08] |
| **Sistema penal "upstream" (datos)** | Los datos de arrestos reflejan disparidades preexistentes del sistema penal que el modelo aprende y reproduce. [F01][F04] |

## 5. Marco legal

### Unión Europea — AI Act [F07]
Un sistema como COMPAS sería **ALTO RIESGO** bajo el Anexo III (punto 6, aplicación de la ley — evaluar riesgo de reincidencia; y punto 8, administración de justicia). Eso exigiría: gestión de riesgos, **gobernanza y calidad de datos** (control de sesgo), **transparencia**, **supervisión humana** efectiva, **registros/trazabilidad**, exactitud y robustez, y en organismos públicos una **evaluación de impacto en derechos fundamentales (FRIA)**. Matiz: el AI Act es de 2024, posterior a los hechos, y **en mayo de 2026 se pospusieron las obligaciones de alto riesgo hasta diciembre de 2027**.

### Argentina — el vacío [F08]
No hay ley específica de IA. Rige de costado la **Ley 25.326** (2000), pensada para archivos, no para decisiones automatizadas. Hay varios proyectos en el Congreso (inspirados en el RGPD) que introducen **derecho a no ser objeto de decisiones automatizadas con efectos negativos, transparencia algorítmica, derecho a la explicación y evaluaciones de impacto**, pero **ninguno es ley vigente**. Como dice el enunciado: sin ley específica, el único estándar real es la **responsabilidad profesional**.

## 6. Las siete preguntas del técnico aplicadas a COMPAS

1. **¿Con qué datos se entrenó y de dónde salieron?** De registros penales y cuestionarios de poblaciones de referencia de EE.UU. Esos datos arrastran disparidades del sistema penal. Para la persona evaluada y el tribunal, el origen y la representatividad de la muestra de referencia **no son transparentes**. [F03][F06]
2. **¿A quién perjudica si se equivoca y qué tan grave es?** A personas acusadas —desproporcionadamente negras— en decisiones sobre su **libertad**. El error es **muy grave**: más cárcel o fianzas más altas por un falso positivo. [F01]
3. **¿Se puede explicar cómo decide o es una caja negra?** Es una **caja negra**: fórmula propietaria, no auditable ni por la persona ni por el tribunal. [F03][F06]
4. **¿Hay una persona supervisando con poder real de revertir?** Formalmente sí (el juez), pero en la práctica el puntaje se trató como dato objetivo; *Loomis* exige advertencias y que no sea "determinante", reconociendo que el riesgo de sobre-confianza es real. [F03]
5. **¿La persona sabe que hay una IA decidiendo y puede apelar?** Sabe que existe un puntaje, pero **no puede impugnar su mecánica interna** (secreto comercial). [F03]
6. **¿Se probó si funciona peor con algún grupo?** Sí, ProPublica mostró errores asimétricos por raza; Northpointe lo discute con otra métrica. El teorema de imposibilidad muestra que **alguien debió elegir** qué equidad priorizar. [F01][F02][F04]
7. **Si sale mal, ¿quién responde?** Hoy la responsabilidad está **difusa** entre empresa, jueces, Estado y regulador — precisamente lo que el juicio debe repartir. [F03][F07][F08]

---

## 7. Índice de fuentes

| # | Fuente | Archivo |
|---|---|---|
| F01 | ProPublica, "Machine Bias" (2016) + anexo metodológico + réplica | [fuentes/01-propublica-machine-bias.md](fuentes/01-propublica-machine-bias.md) |
| F02 | Respuesta de Northpointe/Equivant (Dieterich et al., 2016) | [fuentes/02-northpointe-equivant-respuesta.md](fuentes/02-northpointe-equivant-respuesta.md) |
| F03 | *State v. Loomis* (Wisconsin, 2016; cert. denegado 2017) | [fuentes/03-state-v-loomis.md](fuentes/03-state-v-loomis.md) |
| F04 | Teorema de imposibilidad de la equidad (Kleinberg; Chouldechova) | [fuentes/04-teorema-imposibilidad-equidad.md](fuentes/04-teorema-imposibilidad-equidad.md) |
| F05 | Dressel & Farid, *Science Advances* (2018) | [fuentes/05-dressel-farid-precision.md](fuentes/05-dressel-farid-precision.md) |
| F06 | Funcionamiento técnico de COMPAS (Practitioner's Guide y otros) | [fuentes/06-funcionamiento-tecnico-compas.md](fuentes/06-funcionamiento-tecnico-compas.md) |
| F07 | AI Act europeo (Anexo III, alto riesgo) | [fuentes/07-marco-legal-ai-act.md](fuentes/07-marco-legal-ai-act.md) |
| F08 | Marco legal argentino (Ley 25.326 y proyectos 2025/2026) | [fuentes/08-marco-legal-argentina.md](fuentes/08-marco-legal-argentina.md) |
| F09 | Contexto social: disparidad racial y encarcelamiento en EE.UU. (The Sentencing Project) | [fuentes/09-contexto-social-racismo-encarcelamiento.md](fuentes/09-contexto-social-racismo-encarcelamiento.md) |
| F10 | Ética de la justicia algorítmica (Elish "moral crumple zones"; automation bias; justicia actuarial) | [fuentes/10-etica-justicia-algoritmica.md](fuentes/10-etica-justicia-algoritmica.md) |

---

## 8. Hipótesis: puntos aprovechables en la mecánica del juicio

Recordatorio del enunciado: el veredicto **no** es "ganó la acusación o la defensa", sino un **reparto de responsabilidad** entre actores. Cada lado debería ordenar sus mejores cartas según los momentos del juicio (apertura, peritos, réplicas cruzadas, preguntas del jurado).

### 8.1. Para la ACUSACIÓN (contra la IA y sus responsables humanos)

**Mejores cartas (de más fuerte a más matizable):**
1. **Caja negra + libertad en juego.** Un sistema que influye en la libertad de las personas no puede ser inauditable. *Loomis* admite que ni la persona ni el tribunal pueden revisar la fórmula. [F03] Es el argumento más sólido porque la propia empresa y la propia justicia lo reconocen.
2. **Daño desigual demostrado.** Las cifras de ProPublica (falsos positivos ≈45% vs 23%; 77% más riesgo violento controlando variables) muestran un perjuicio concreto y medible sobre un grupo protegido. [F01]
3. **Sesgo por proxies pese a no programar "raza".** Responde directamente a la pregunta del enunciado: el sesgo entra por variables correlacionadas (barrio, entorno, arrestos previos). [F06]
4. **Desproporción poder/fiabilidad.** Decisiones gravísimas apoyadas en una herramienta con ~65% de acierto, igual que legos y replicable con 2 variables. La complejidad y opacidad no se justifican. [F05]
5. **Estándar de "lo exigible".** Bajo el AI Act, COMPAS es alto riesgo y habría incumplido transparencia, gobernanza de datos, control de sesgo y supervisión humana. Sirve como vara de lo que un profesional responsable debía hacer aunque no fuera obligatorio aún. [F07]
6. **Reparto sugerido (a defender, no dogmático):** empresa como principal responsable (diseñó y vendió la caja negra y eligió el trade-off de equidad sin transparencia), seguida del Estado/comprador (no exigió auditoría) y de los jueces (la usaron como dato objetivo).

**Cómo anticipar la réplica de la defensa:** reconocer que la calibración existe, pero sostener que **elegir** calibración por sobre el balance de errores fue una decisión humana de la empresa, tomada en secreto, cuyas consecuencias recaen sobre personas negras. La imposibilidad matemática no borra la responsabilidad por la **elección** ni por **desplegar** el sistema sin transparencia.

### 8.2. Para la DEFENSA (de la IA / la empresa, y traslado de responsabilidad)

**Mejores cartas (de más fuerte a más matizable):**
1. **Equidad por calibración / paridad predictiva.** El modelo es "justo" bajo una definición estadística legítima: un mismo puntaje significa lo mismo sin importar la raza. [F02]
2. **Imposibilidad matemática (carta pericial fuerte).** Es imposible cumplir calibración + igualdad de falsos positivos + igualdad de falsos negativos a la vez cuando las tasas base difieren. El "sesgo" no es un defecto programado ni negligencia: es una propiedad estructural de la estadística. [F04]
3. **Es apoyo, no decisión → traslado al operador.** *Loomis* establece que el puntaje no puede ser determinante y que el juez decide y debe justificar con otros factores. La responsabilidad de la decisión final es del **operador judicial**, que tiene supervisión humana. [F03]
4. **Vacío legal → traslado al Estado/regulador.** Al momento de los hechos no había norma que obligara a auditar, explicar o evitar decisiones automatizadas; el AI Act es posterior y ni siquiera está plenamente vigente (prórroga a 2027), y Argentina no tiene ley. La omisión es del regulador. [F07][F08]
5. **Responsabilidad "upstream" de los datos.** Las disparidades provienen del sistema penal (patrones de arresto), no de una intención del algoritmo: el modelo refleja una realidad social que lo precede. [F01][F04]
6. **Reparto sugerido (a defender, no dogmático):** distribuir la carga hacia el Estado que compró sin auditar y el regulador ausente, y hacia los jueces que sobre-confiaron, atenuando la cuota de la empresa, que vendió una herramienta validada y de uso estándar pensada como apoyo.

**Cómo anticipar la réplica de la acusación:** aceptar que hubo daño, pero enmarcarlo como **falla del sistema sociotécnico completo** (datos sesgados + Estado que no auditó + jueces que no supervisaron + regulador ausente), no como culpa exclusiva de la empresa; y subrayar que la transparencia total chocaría con la imposibilidad de "resolver" la equidad por completo.

### 8.3. Síntesis para el jurado

El punto de fricción donde "se gana o se pierde" (réplicas cruzadas) es la tensión **calibración vs balance de errores**: ambos lados tienen razón técnica, así que el debate real no es estadístico sino de **responsabilidad por las decisiones humanas**: quién eligió la métrica en secreto, quién compró sin auditar, quién usó sin supervisar y quién no reguló a tiempo. Ese es el terreno donde el jurado debe fijar el reparto. [F04][F03][F07]
