# Juicio a los algoritmos

**Materia:** I.IA — Ing. VB  
**Modalidad:** trabajo grupal.

Cada caso lo trabajan **dos grupos enfrentados**. Uno hace la acusación y otro la defensa. Cada grupo investiga el caso y produce un dossier escrito desde su lado, y luego lo sostiene en un juicio oral. El dossier es la preparación; el juicio es donde se defiende.

La acusación no busca un "culpable" ni la defensa un "inocente". La acusación argumenta sobre qué actores recae la responsabilidad y en qué medida; la defensa alega atenuantes y traslada parte de esa responsabilidad a otros actores. El veredicto final es un reparto de responsabilidad, no un sí o un no.

---

## 1. Objetivo

Al terminar este trabajo deberían poder responder: cuando un sistema de IA causa un daño, ¿quién es responsable? La respuesta casi nunca es "la IA". Detrás de cada sistema hay decisiones humanas, de quién lo diseñó, de quién lo compró, de quién lo usó sin controlarlo y de quién debería haberlo regulado y no lo hizo.

La tecnología no tiene consecuencias por sí sola: las consecuencias dependen de decisiones humanas. Este trabajo es un ejercicio para aprender a rastrear esas decisiones.

---

## 2. Qué se evalúa

- La exactitud de la investigación: los hechos deben ser verdaderos y estar respaldados por fuentes.
- La capacidad de mapear la responsabilidad entre los distintos actores, en vez de buscar un único culpable.
- El manejo del marco legal: qué diría la ley europea (AI Act) y qué ocurre hoy en Argentina.
- El desempeño en el juicio: claridad al exponer y solidez al responder las preguntas del tribunal.

---

## 3. Documentación

Cada grupo entrega un dossier de investigación sobre su caso, escrito desde su lado (acusación o defensa), de entre 3 y 4 páginas, con estas secciones:

1. **Los hechos:** qué pasó, cuándo, a quién. Con fuentes citadas.
2. **El sistema técnico:** qué tipo de IA intervino y, en lenguaje llano, cómo funciona.
3. **El daño:** a quién afectó y de qué manera.
4. **Mapa de responsabilidad:** lista de los actores involucrados y, para cada uno, qué decisión humana concreta contribuyó al daño.
5. **Marco legal:** qué categoría tendría el sistema bajo el AI Act europeo y qué protección existe (o no) hoy en Argentina.
6. **Las preguntas del técnico:** respondan, aplicadas al caso, las siete preguntas de la sección 7.

---

## Parte B — El juicio (oral)

Los dos grupos del caso no defienden "su opinión": defienden un lado. La acusación sostiene que la responsabilidad recae sobre ciertos actores y argumenta cuánto le toca a cada uno; la defensa responde con atenuantes y traslada parte de la carga a otros (el Estado que no auditó, el operador que no supervisó, el vacío legal).

**Quién juzga:** los grupos que no litigan ese caso actúan como jurado. El jurado no vota "ganó la acusación" o "ganó la defensa": define un reparto de responsabilidad entre los actores (por ejemplo: empresa 50%, Estado 30%, operador 20%) y lo justifica.

---

## 4. Mecánica del juicio

- **Apertura de la acusación:** presenta los hechos y sobre qué actores pide responsabilidad, con qué peso.
- **Apertura de la defensa:** responde con atenuantes y propone otro reparto de la responsabilidad.
- **Peritos técnicos:** explican, sin tecnicismos, cómo funciona el sistema y qué se le podía exigir.
- **Réplicas cruzadas:** cada grupo refuta el argumento del otro. Aquí se gana o se pierde el caso.
- **Preguntas del jurado:** los grupos jurado interrogan a ambos lados.
- **Deliberación y veredicto:** el jurado fija el reparto de responsabilidad y lo justifica.

*Unos 30 minutos por juicio.*

---

## 5. Roles dentro del grupo

Los roles dependen del lado que le toque al grupo.

### Grupo acusación:

1. **Fiscal / relator:** presenta los hechos y sostiene sobre qué actores recae la responsabilidad.
2. **Perito técnico:** explica el sistema de IA en lenguaje claro y señala qué controles faltaron.
3. **Vocería de las personas afectadas:** muestra el daño concreto y a quién golpeó.

### Grupo defensa:

1. **Defensa de la empresa:** argumenta por la compañía que diseñó o vendió el sistema.
2. **Defensa del Estado / operador:** argumenta por quien compró, usó o debería haber controlado el sistema, y traslada parte de la responsabilidad.
3. **Perito técnico:** explica qué era razonable exigirle al sistema y qué no.

---

## 6. Los casos

Hay cuatro casos. Cada uno lo toman dos grupos: uno hace la acusación y otro la defensa. Las descripciones de abajo son el punto de partida, no la investigación terminada: cada grupo debe verificar y ampliar los datos con fuentes propias, desde su lado.

---

### Caso 1: COMPAS (el algoritmo que puntúa el riesgo de reincidencia)

*Sesgos en algoritmos*

**Qué pasó:** COMPAS es un software usado por tribunales de Estados Unidos para estimar la probabilidad de que una persona acusada vuelva a delinquir; ese puntaje influye en decisiones sobre fianza y sentencia. En 2016 una investigación periodística (ProPublica) encontró que el sistema clasificaba como "alto riesgo", de forma errónea, a personas de color con mucha más frecuencia que a personas blancas. La empresa defendió que el modelo estaba estadísticamente "calibrado". El código es propietario: nadie fuera de la empresa puede inspeccionarlo.

**Los imputados:** la empresa que vende el sistema y lo mantiene como caja negra; los jueces que usan el puntaje como si fuera un dato objetivo; el Estado que lo compró sin exigir auditoría ni transparencia.

**Preguntas de responsabilidad:** si nadie programó explícitamente la variable "raza", ¿de dónde sale el sesgo? ¿Puede una decisión que afecta la libertad de una persona apoyarse en un modelo que no se puede revisar?

**Para investigar:** ProPublica "Machine Bias" 2016; caso *State v. Loomis* (Wisconsin); respuesta de Northpointe / Equivant.

---

### Caso 2: Datos de entrenamiento: ¿de quién son?

*Privacidad y propiedad de los datos de entrenamiento*

**Qué pasó:** The New York Times demandó a OpenAI y Microsoft por haber entrenado sus modelos con millones de sus artículos sin licencia ni pago, y argumenta que el modelo puede reproducir su texto casi palabra por palabra. Las empresas de IA invocan el "uso legítimo" (fair use). Un caso paralelo, más ligado a la privacidad: Clearview AI raspó miles de millones de fotos de redes sociales sin consentimiento para vender reconocimiento facial a fuerzas de seguridad, y fue sancionada por varias autoridades de protección de datos en Europa.

**Los imputados:** la empresa de IA que usó los datos; las plataformas de donde salieron; el usuario que aceptó términos sin leerlos; el regulador que llegó tarde.

**Preguntas de responsabilidad:** ¿de quién son los datos con los que se entrena un modelo? ¿Alcanza con que algo esté "público en internet" para que cualquiera pueda usarlo con cualquier fin?

**Para investigar:** demanda *The New York Times c. OpenAI* (2023); sanciones a Clearview AI en Italia, Francia y Reino Unido; concepto de fair use.

---

### Caso 3: La voz clonada que pedía no votar

*Deepfakes y desinformación*

**Qué pasó:** En enero de 2024, antes de las primarias de New Hampshire (EE.UU.), miles de votantes recibieron una llamada automática con la voz clonada del entonces presidente Biden pidiéndoles que no fueran a votar. Se identificó al operador político que la encargó y hubo sanciones; el regulador de telecomunicaciones declaró ilegales los robocalls con voz generada por IA. Un caso paralelo, de impacto social: en el mismo mes circularon masivamente deepfakes sexuales de Taylor Swift, lo que impulsó nuevas leyes contra imágenes íntimas no consentidas hechas con IA.

**Los imputados:** quien encargó o creó el deepfake; la plataforma o la red que lo distribuyó; la herramienta de IA con la que se generó.

**Preguntas de responsabilidad:** cuando el daño se vuelve viral en minutos, ¿quién responde: ¿la herramienta, el autor o quien lo difunde? ¿Alcanzan las herramientas de detección (análisis de artefactos, marcas de agua tipo C2PA) cuando son imperfectas y llegan tarde?

**Para investigar:** robocall de New Hampshire 2024 y sanciones de la FCC; deepfakes de Taylor Swift y respuesta legislativa; herramientas y estándares de detección y marcado de contenido.

---

### Caso 4: "Lo decidió el sistema", deudas automáticas

*Toma de decisiones automatizada*

**Qué pasó:** En Australia, el programa conocido como Robodebt usó un sistema automatizado para calcular supuestas deudas de beneficiarios sociales y emitió cientos de miles de reclamos erróneos; una Comisión Real lo declaró ilegal y se lo vinculó con daños graves. En Países Bajos, un algoritmo de la agencia tributaria para detectar fraude en asignaciones por hijos marcó injustamente a decenas de miles de familias —muchas de origen migrante o con doble nacionalidad— y el escándalo provocó la caída del gobierno en 2021.

**Los imputados:** la agencia estatal que desplegó el sistema; los funcionarios que confiaron en sus resultados sin revisión humana; los técnicos que lo diseñaron sin controles de sesgo ni vías de apelación.

**Preguntas de responsabilidad:** ¿"lo decidió el sistema" exime al funcionario que lo aplicó? ¿Dónde debería haber estado la supervisión humana?

**Para investigar:** Robodebt Royal Commission (Australia, 2023); "toeslagenaffaire" / Dutch childcare benefits scandal.

---

## 7. Las siete preguntas del técnico

Antes de implementar cualquier sistema de IA, un profesional responsable debería poder responder estas preguntas. Aplíquenlas a su caso: en cada daño que estudien, casi siempre falta la respuesta a alguna de ellas.

1. ¿Con qué datos se entrenó el sistema, y de dónde salieron?
2. ¿A quién puede perjudicar si se equivoca, y qué tan grave es ese error?
3. ¿Puedo explicar cómo toma sus decisiones, o es una caja negra?
4. ¿Hay una persona supervisando y con poder real de revertir la decisión?
5. ¿La persona afectada sabe que hay una IA decidiendo, y puede apelar?
6. ¿Probé si funciona peor con algún grupo de personas que con otro?
7. Si esto sale mal, ¿quién responde — y estoy dispuesto a que sea mi nombre?

---

## 8. Marco legal de referencia

### La Unión Europea: el AI Act

Es la primera ley integral de IA del mundo y la referencia que copian otros países. Clasifica los sistemas por nivel de riesgo y exige más cuanto mayor es el riesgo:

- **Riesgo inaceptable:** prohibido (por ejemplo, ciertos usos de puntaje social).
- **Alto riesgo:** permitido pero con obligaciones fuertes, gestión de riesgos, control de la calidad de los datos, supervisión humana y registros. Aquí entran usos como contratación, crédito o justicia.
- **Riesgo limitado:** obligación de transparencia, avisar que el contenido o la conversación los genera una IA.
- **Riesgo mínimo:** sin obligaciones especiales.

Entró en vigor en 2024 con aplicación por etapas. **En mayo de 2026 se acordó posponer las obligaciones de los sistemas de alto riesgo hasta diciembre de 2027.** Es decir: hasta la ley más avanzada del mundo corre sus propios plazos. La regulación va, casi siempre, detrás de la tecnología.

### Argentina: el vacío y lo que viene

A mediados de 2026, Argentina no tiene una ley específica de IA. Lo que rige de costado es la **Ley 25.326 de Protección de Datos Personales** (del año 2000, hoy en proceso de reforma). En el Congreso hay varios proyectos sin sancionar, varios inspirados en el modelo europeo de niveles de riesgo, más una mesa interministerial de trabajo. Nada de eso es aún ley vigente.

> **La consecuencia para ustedes como futuros técnicos:** si no hay una ley específica que les diga qué pueden y qué no pueden hacer, el único estándar real que les queda es su propia responsabilidad profesional.

---

## 9. Entrega

- Dossier escrito (PDF o Word), con las seis secciones de la Parte A y las fuentes citadas.
- Presentación en el juicio oral.
- Reparto de roles del grupo entregado por escrito al inicio del juicio.