# Parte 2 — El dilema moral y ético en su contexto social y cultural

> **Subgrupo 2 (2-3 alumnos).** Lado: **ACUSACIÓN**. Caso 1 — COMPAS.
> Esta parte no discute "si el algoritmo funciona" (eso es la Parte 3) sino **si está bien usarlo así**, y dentro de qué contexto social y cultural ocurre el daño. Es la dimensión que conecta los números con las personas. Respaldo en [`fuentes/`](fuentes/), especialmente [F09](fuentes/09-contexto-social-racismo-encarcelamiento.md) y [F10](fuentes/10-etica-justicia-algoritmica.md).

---

## 1. Qué necesitan saber (resumen del tema)

El dilema central no es estadístico, es **moral**: ¿es legítimo decidir sobre la **libertad** de una persona usando una probabilidad calculada sobre **grupos**, con una fórmula **secreta**, dentro de un sistema penal que **ya discrimina**?

Tres tensiones éticas atraviesan el caso:

1. **Individuo vs. grupo.** A una persona se la debería juzgar por sus actos, no por el comportamiento estadístico del grupo al que el modelo la asimila. COMPAS predice a partir de características de grupos de referencia. [F10][F03]
2. **Objetividad aparente vs. sesgo real.** Presentar un número "neutral" construido sobre datos socialmente sesgados **lava** la discriminación: la vuelve técnica, fría, difícil de cuestionar. [F09]
3. **Quién decide qué es "justo".** Cuando es matemáticamente imposible ser justo según todas las definiciones a la vez, **alguien tiene que elegir** cuál priorizar. Esa elección es moral y política, y la tomó una empresa privada en secreto. [F04][F10]

---

## 2. El contexto social y cultural (lo que no se puede ignorar)

- **Racismo estructural en el sistema penal de EE.UU.:** las personas negras están encarceladas a **~5 veces** la tasa de las blancas (1.240 vs 261 por 100.000); son ~14% de la población pero ~33% de la población carcelaria. La disparidad se acumula etapa por etapa: más prisión preventiva, más penas de cárcel, condenas más largas. [F09]
- **El dato no es neutral:** COMPAS aprende de arrestos y antecedentes. Si la policía, los fiscales y los tribunales ya tratan distinto a las personas negras, el modelo hereda ese trato y lo proyecta hacia el futuro como "riesgo". La cultura de sobre-vigilancia de ciertos barrios se convierte en un número.
- **El círculo vicioso:** un puntaje alto → más detención/condena → más antecedentes → datos que "confirman" el riesgo. El sistema **profetiza y se autocumple**.
- **Contexto cultural de autoridad técnica:** existe una confianza cultural en que "lo que dice la computadora es objetivo". Esa confianza es la que hace peligroso un número opaco en manos de un juez con sobrecarga de casos.

---

## 3. Nuestros argumentos de ataque (acusación)

1. **Usar estadística de grupo para decidir sobre un individuo viola la individualización de la pena.** Es un principio ético y jurídico: se responde por lo que se hizo, no por lo que "gente parecida" hizo. [F10][F03]
2. **La objetividad aparente es un agravante moral, no una excusa.** Envolver una desigualdad estructural en un número la hace **más difícil de impugnar** que un prejuicio explícito: nadie puede discutir con una caja negra. [F09][F10]
3. **La supervisión humana fue ilusoria.** El **sesgo de automatización** lleva a los operadores a deferir a la máquina aun frente a evidencia contraria. [F10] Un "humano en el bucle" sin tiempo, sin acceso a la fórmula y culturalmente predispuesto a confiar en el número **no es una salvaguarda**, es una formalidad.
4. **La "zona de absorción moral".** Cargar toda la responsabilidad sobre el juez (el operador más cercano) protege a la empresa que diseñó la caja negra. La acusación debe nombrar esto explícitamente: la empresa no puede esconderse detrás del humano que apretó el botón. [F10]
5. **Decidir qué equidad priorizar es un acto moral que se tomó sin legitimidad democrática.** No lo decidió un parlamento ni un tribunal público: lo decidió una empresa, en secreto, optimizando una métrica. Las consecuencias recaen sobre un grupo protegido. [F04][F10]
6. **Responsabilidad profesional como estándar ético.** Aun sin ley, el técnico responsable debía preguntarse: "si esto sale mal, ¿estoy dispuesto a que sea mi nombre?". Diseñar y vender un sistema así sin auditoría es una falla ética, no solo legal. [F08]

---

## 4. Puntos que la defensa puede usar en nuestra contra

1. **"El sesgo está en la sociedad, no en la herramienta; no se puede culpar a un espejo."** El algoritmo refleja una realidad penal que lo precede. [F09]
2. **"El humano decide y es moralmente responsable."** Hay un juez con agencia que puede ignorar el puntaje; la responsabilidad es suya, no del software (human-in-the-loop). [F03]
3. **"Un juez humano también tiene sesgos, y peores."** La intuición humana es opaca, inconsistente y también discrimina; al menos el algoritmo es consistente y auditable en sus entradas.
4. **"Reducir disparidades es deseable; sin la herramienta, las decisiones serían aún más arbitrarias."** El sistema busca estandarizar y dar consistencia.
5. **"Exigir 'justicia perfecta' es utópico."** Si es matemáticamente imposible satisfacer todas las definiciones de equidad, reprochar la elección de una es injusto. [F04]

---

## 5. Cómo nos defendemos (réplica a cada contraargumento)

1. **Contra "es solo un espejo":** un espejo no decide sobre la libertad de nadie. COMPAS no refleja pasivamente: **proyecta el pasado sesgado hacia el futuro** y lo presenta como predicción objetiva, cerrando el círculo vicioso. Saber que el espejo está deformado y usarlo igual para sentenciar es la negligencia. [F09]
2. **Contra "el humano decide":** de acuerdo, **por eso** acusamos también al juez y al Estado, no solo a la empresa. Pero la decisión humana está **contaminada** por el sesgo de automatización y por la autoridad cultural del número. La empresa no puede crear esa ilusión de objetividad y luego desentenderse: es la lógica de la "zona de absorción moral" que denunciamos. [F10]
3. **Contra "el humano también discrimina":** cierto, y por eso un sistema que **promete** corregir el sesgo y en cambio lo **automatiza y legitima** es peor: agrega una capa de falsa objetividad que vuelve el sesgo más difícil de detectar y de apelar. No reemplazamos un prejuicio por una solución, sino por un prejuicio blindado. [F09][F10]
4. **Contra "da consistencia":** consistencia no es justicia. Ser consistentemente injusto con un grupo protegido (≈45% vs ≈23% de falsos positivos) no es una virtud. [F01] Y la consistencia prometida no se cumple: la precisión es ~65%, igual que la de legos. [F05]
5. **Contra "la justicia perfecta es utópica":** no pedimos perfección; pedimos **transparencia, control de sesgo y supervisión real**. La imposibilidad matemática no obliga a elegir en secreto ni a desplegar sin auditoría. Es precisamente porque hay que elegir un trade-off que la elección debía ser pública, justificada y revisable. [F04]

---

## 6. Las preguntas éticas que el jurado debe oír

- ¿Aceptaríamos que un número secreto influya en **nuestra** condena sin poder discutirlo?
- Si el sistema falla, ¿quién pone su nombre? Hoy: nadie con claridad. [F08]
- ¿Es ético "optimizar" la libertad de las personas como si fuera una métrica de negocio?
- ¿La eficiencia y la consistencia justifican delegar una decisión moral en una caja negra?

---

## 7. Fuentes de esta parte

F01 ([fuentes/01-propublica-machine-bias.md](fuentes/01-propublica-machine-bias.md)) ·
F03 ([fuentes/03-state-v-loomis.md](fuentes/03-state-v-loomis.md)) ·
F04 ([fuentes/04-teorema-imposibilidad-equidad.md](fuentes/04-teorema-imposibilidad-equidad.md)) ·
F05 ([fuentes/05-dressel-farid-precision.md](fuentes/05-dressel-farid-precision.md)) ·
F08 ([fuentes/08-marco-legal-argentina.md](fuentes/08-marco-legal-argentina.md)) ·
F09 ([fuentes/09-contexto-social-racismo-encarcelamiento.md](fuentes/09-contexto-social-racismo-encarcelamiento.md)) ·
F10 ([fuentes/10-etica-justicia-algoritmica.md](fuentes/10-etica-justicia-algoritmica.md))
