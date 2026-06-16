# Parte 3 — El funcionamiento técnico de la IA

> **Subgrupo 3 (2-3 alumnos).** Lado: **ACUSACIÓN**. Caso 1 — COMPAS.
> Esta parte explica, en lenguaje llano, **qué tipo de IA es COMPAS y cómo funciona**, para sostener el rol de **perito técnico** en el juicio. El objetivo del perito de la acusación es mostrar qué controles faltaron y por qué la herramienta no merece la confianza que se le dio. Respaldo en [`fuentes/`](fuentes/): [F04](fuentes/04-teorema-imposibilidad-equidad.md), [F05](fuentes/05-dressel-farid-precision.md), [F06](fuentes/06-funcionamiento-tecnico-compas.md).

---

## 1. Qué necesitan saber (resumen del tema)

COMPAS **no es una "inteligencia artificial" sofisticada ni una red neuronal moderna**: es una herramienta **actuarial** de evaluación de riesgo de "cuarta generación". En palabras simples, es un **modelo estadístico** que compara a la persona con grupos de referencia de los que ya se conoce el resultado, y devuelve la frecuencia de reincidencia de ese grupo como "riesgo" del individuo. [F06]

### Cómo funciona, paso a paso

1. **Entrada:** un cuestionario de **137 ítems** (respondido por entrevista o formulario) + los **registros penales públicos** de la persona. Cubre cargos actuales, historial penal, incumplimientos, criminalidad familiar, pares, sustancias, residencia, entorno social, educación, empleo, personalidad, actitudes. [F06]
2. **Factores:**
   - **Estáticos** (no cambian): historial penal, edad al primer arresto, incumplimientos previos. Son los **mayores predictores**.
   - **Dinámicos** ("criminógenos"): empleo, educación, consumo de sustancias, entorno social.
3. **Lógica:** compara el perfil con grupos de personas similares y resultados conocidos; el puntaje refleja la frecuencia de reincidencia de ese grupo de referencia. [F06]
4. **Salida:** puntajes de **reincidencia general**, **reincidencia violenta** y **riesgo previo al juicio**, en una escala de **1 a 10** → bajo (1-4), medio (5-7), alto (8-10). [F06]
5. **Clave:** la **fórmula de ponderación es secreto comercial** (caja negra). Ni la persona ni el tribunal saben cómo se combinan los 137 ítems. [F06][F03]

---

## 2. Los tres pilares técnicos del ataque

### A) El sesgo entra por *proxies*, aunque "raza" no sea una variable
COMPAS **no usa la raza como variable de entrada**. Pero muchos ítems —barrio, entorno social, antecedentes familiares, historial de arrestos— están **fuertemente correlacionados con la raza** y funcionan como **sustitutos (proxies)**. El modelo "aprende" la raza de forma indirecta. [F06][F01] Esto responde a la pregunta del enunciado: *si nadie programó "raza", ¿de dónde sale el sesgo?* → de los proxies y de unos datos de origen ya sesgados. [F09]

### B) El teorema de imposibilidad de la equidad
Es **matemáticamente imposible** que un modelo imperfecto cumpla a la vez, cuando las **tasas base** difieren entre grupos:
- **(A) Calibración:** un mismo puntaje significa el mismo riesgo real en todos los grupos.
- **(B) Igual tasa de falsos negativos** entre grupos.
- **(C) Igual tasa de falsos positivos** entre grupos.

En Broward las tasas base diferían (≈0,51 personas negras vs ≈0,39 blancas), así que **ProPublica (midió B y C) y Northpointe (midió A) podían tener razón a la vez**. [F04] La conclusión clave para el perito de la acusación: como el trade-off es inevitable, **alguien tuvo que elegir** qué equidad priorizar — y esa elección la hizo la empresa, en secreto.

### C) La complejidad no aporta valor (Dressel & Farid)
- **Personas sin formación** (400 voluntarios, viendo solo 7 datos) aciertan ~**63-67%**; COMPAS acierta **~65%**. [F05]
- Un modelo lineal trivial con **2 variables** (edad y número de condenas previas) iguala la precisión de los **137 ítems** de COMPAS. [F05]
- Modelos más sofisticados no mejoran ni precisión ni equidad. [F05]
→ La opacidad y la complejidad **no se justifican** por un mejor desempeño.

---

## 3. Nuestros argumentos de ataque (perito de la acusación)

1. **Caja negra inauditable en decisiones de libertad.** Nadie puede verificar la ponderación; el secreto comercial impide el control técnico básico. [F06][F03]
2. **Sesgo estructural por proxies.** "No programar la raza" no evita el sesgo: lo esconde. [F06]
3. **Precisión mediocre y desproporcionada al poder.** ~65% (igual que legos) para decidir sobre la libertad es una desproporción inaceptable entre poder y fiabilidad. [F05]
4. **Falsa sofisticación.** 137 ítems que igualan a 2 variables: la complejidad opera como cortina de humo que dificulta la auditoría sin mejorar el resultado. [F05]
5. **La elección del trade-off fue una decisión técnica oculta.** El teorema no exime: obliga a elegir, y la empresa eligió sin transparencia. [F04]

---

## 4. Puntos que la defensa puede usar en nuestra contra

1. **"Está calibrado: técnicamente es justo."** Para un mismo puntaje, el riesgo real es similar entre razas. [F02]
2. **"El sesgo es matemáticamente inevitable, no un defecto."** El teorema de imposibilidad muestra que no se puede satisfacer todo a la vez; no es negligencia. [F04]
3. **"~65% es útil como apoyo."** Puede igualar o superar la intuición de operadores sobrecargados, y aporta consistencia. Los propios autores (Dressel & Farid) **no piden prohibirla**. [F05]
4. **"No incorpora la raza deliberadamente."** Es una herramienta validada y estandarizada; el sesgo, si existe, viene de los datos, no del diseño. [F06]
5. **"Es solo una entrada entre varias para el juez."** La salida no es una decisión, es un insumo. [F03][F06]

---

## 5. Cómo nos defendemos (réplica a cada contraargumento)

1. **Contra "calibrado = justo":** calibración es solo **una** de tres definiciones de equidad, y la empresa la eligió porque la favorece. El teorema prueba que esa elección **sacrifica** el balance de falsos positivos, que es justo lo que daña a las personas negras. [F04][F01]
2. **Contra "el sesgo es inevitable":** inevitable es el **trade-off**, no la **opacidad**. La matemática obliga a elegir; no obliga a elegir en secreto, sin auditoría ni participación pública. La responsabilidad no es por la imposibilidad, es por **cómo y quién** decidió. [F04]
3. **Contra "útil como apoyo":** si una herramienta opaca de ~65% iguala a legos y a un modelo de 2 variables, **no agrega valor que justifique su opacidad** ni su autoridad sobre la libertad de las personas. Los autores no piden prohibirla, pero sí **que demuestre que funciona antes de usarse para decidir** — y eso no se hizo. [F05]
4. **Contra "no incorpora la raza":** técnicamente correcto y **moralmente irrelevante**: el efecto discriminatorio se produce igual por proxies. Lo que importa no es la intención del diseño, sino el **resultado medible** sobre un grupo protegido. [F06][F01]
5. **Contra "es solo una entrada":** en teoría sí; en la práctica, el **sesgo de automatización** convierte la "entrada" en ancla de la decisión, y *Loomis* tuvo que imponer advertencias justamente porque el puntaje pesa demasiado. [F10][F03]

---

## 6. Glosario para el perito (lenguaje llano)

- **Herramienta actuarial:** calcula riesgo comparando a la persona con grupos parecidos, como hacen las aseguradoras. No "razona" sobre el individuo.
- **Falso positivo:** marcar "alto riesgo" a quien **no** reincide. Es el error que daña desproporcionadamente a las personas negras. [F01]
- **Falso negativo:** marcar "bajo riesgo" a quien **sí** reincide.
- **Calibración / paridad predictiva:** un mismo puntaje significa el mismo riesgo real en todos los grupos. [F02]
- **Tasa base:** proporción real de reincidencia en un grupo; cuando difiere entre grupos, dispara el teorema de imposibilidad. [F04]
- **Proxy:** variable que sustituye indirectamente a otra (barrio ≈ raza). [F06]
- **Caja negra:** sistema cuyo funcionamiento interno no se puede inspeccionar. [F06]

---

## 7. Fuentes de esta parte

F01 ([fuentes/01-propublica-machine-bias.md](fuentes/01-propublica-machine-bias.md)) ·
F02 ([fuentes/02-northpointe-equivant-respuesta.md](fuentes/02-northpointe-equivant-respuesta.md)) ·
F03 ([fuentes/03-state-v-loomis.md](fuentes/03-state-v-loomis.md)) ·
F04 ([fuentes/04-teorema-imposibilidad-equidad.md](fuentes/04-teorema-imposibilidad-equidad.md)) ·
F05 ([fuentes/05-dressel-farid-precision.md](fuentes/05-dressel-farid-precision.md)) ·
F06 ([fuentes/06-funcionamiento-tecnico-compas.md](fuentes/06-funcionamiento-tecnico-compas.md)) ·
F09 ([fuentes/09-contexto-social-racismo-encarcelamiento.md](fuentes/09-contexto-social-racismo-encarcelamiento.md)) ·
F10 ([fuentes/10-etica-justicia-algoritmica.md](fuentes/10-etica-justicia-algoritmica.md))
