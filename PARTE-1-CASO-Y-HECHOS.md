# Parte 1 — El caso y los hechos

> **Subgrupo 1 (2-3 alumnos).** Lado: **ACUSACIÓN**. Caso 1 — COMPAS.
> Esta parte cubre la historia, los hechos, las acusaciones, los actores y el daño. Es la base narrativa del juicio: el relato de "qué pasó, cuándo y a quién". Todo está respaldado por las fuentes de la carpeta [`fuentes/`](fuentes/) (referencias `[F0x]`) y sintetizado en [RESUMEN.md](RESUMEN.md).

---

## 1. Qué necesitan saber (resumen del tema)

COMPAS (*Correctional Offender Management Profiling for Alternative Sanctions*) es un software de evaluación de riesgo creado por **Northpointe Inc.** (desde 2017, **Equivant**), usado por tribunales de EE.UU. para estimar la probabilidad de que una persona acusada vuelva a delinquir. Ese puntaje influye en decisiones sobre **fianza, libertad condicional y sentencia**. [F06]

Los tres hitos que hay que dominar:

1. **La investigación de ProPublica (mayo 2016, "Machine Bias").** Analizó más de 7.000 casos del condado de Broward (Florida) y encontró que el sistema marcaba erróneamente como "alto riesgo" a personas negras con casi el doble de frecuencia que a personas blancas. [F01]
2. **La respuesta de Northpointe.** La empresa negó el sesgo y sostuvo que el modelo estaba "calibrado" (paridad predictiva): un mismo puntaje significa lo mismo para cualquier raza. [F02]
3. **El caso judicial *State v. Loomis* (Wisconsin, 2016).** Eric Loomis fue sentenciado a 6 años; el tribunal usó su puntaje COMPAS de alto riesgo. La Corte avaló el uso con advertencias; la Corte Suprema de EE.UU. no revisó el caso (2017). El código es **secreto comercial**: ni la persona ni el tribunal pueden inspeccionarlo. [F03]

---

## 2. Nuestros argumentos de ataque (acusación)

La acusación no busca "un culpable", sino mostrar el daño y **repartir responsabilidad** entre los actores. Cartas principales de esta parte:

1. **El daño está documentado y es desigual.** ProPublica: las personas negras que NO reincidieron fueron marcadas "alto riesgo" en **≈45%** de los casos, frente al **≈23%** de las blancas (falsos positivos). Controlando antecedentes, edad y género, seguían siendo **77% más propensas** a ser marcadas de alto riesgo de delito violento. El daño no es abstracto: se traduce en más cárcel, fianzas más altas y condiciones más duras. [F01]
2. **Decisiones sobre la libertad apoyadas en una caja negra.** *Loomis* reconoce que la naturaleza propietaria del algoritmo impide a la persona y al tribunal evaluar cómo se calcula el puntaje. Un sistema inauditable no debería pesar sobre la libertad de nadie. [F03]
3. **El contexto agrava el daño.** Las personas negras ya están encarceladas a ~5 veces la tasa de las blancas en EE.UU. [F09]; el sistema toma esa desigualdad estructural y la devuelve con apariencia de objetividad numérica.
4. **La empresa eligió la opacidad.** Northpointe mantuvo la fórmula como secreto comercial y se defendió eligiendo la métrica que la favorece (calibración), sin someter el modelo a auditoría externa. [F02][F06]
5. **Responsabilidad difusa = nadie responde.** Hoy la responsabilidad está repartida entre empresa, jueces, Estado y regulador. Precisamente por eso el juicio debe fijar el reparto. [F03][F07][F08]

### Mapa de responsabilidad (a sostener en la apertura)

| Actor | Decisión humana concreta que contribuyó al daño |
|---|---|
| **Northpointe / Equivant (empresa)** | Diseñó y vendió un modelo de alto impacto como **caja negra**; priorizó la calibración sin transparentar el trade-off de equidad ni auditarlo. [F02][F04][F06] |
| **Jueces / operadores judiciales** | Usaron el puntaje como **dato objetivo**, sin supervisión humana real con poder de revertir. [F03] |
| **Estado / agencias compradoras** | Adquirieron y desplegaron el sistema **sin exigir auditoría, transparencia ni pruebas de no discriminación**. [F03][F07] |
| **Regulador / legislador** | Llegó tarde: no había estándar de transparencia, control de sesgo ni derecho a explicación. [F07][F08] |
| **Sistema penal "upstream" (datos)** | Los datos de arrestos reflejan disparidades preexistentes que el modelo aprende y reproduce. [F01][F09] |

**Reparto sugerido (a defender, no dogmático):** empresa como principal responsable (diseñó y vendió la caja negra y eligió el trade-off en secreto), seguida del Estado/comprador (no exigió auditoría) y de los jueces (la usaron como dato objetivo).

---

## 3. Puntos que la defensa puede usar en nuestra contra

1. **"La precisión global es pareja entre razas."** La propia ProPublica reconoce que COMPAS acierta a tasas similares para personas negras y blancas (~62%). [F01]
2. **"El modelo es justo por calibración."** Para un mismo puntaje, la tasa real de reincidencia es similar entre grupos: el puntaje "significa lo mismo". [F02]
3. **"Es apoyo, no decisión."** *Loomis* establece que el puntaje no puede ser determinante y que el juez decide y justifica con otros factores: la responsabilidad final es del operador humano. [F03]
4. **"El daño viene del sistema penal, no del software."** Las disparidades provienen de patrones de arresto y condena previos; el algoritmo solo refleja una realidad social. [F01][F09]
5. **"No había ley que obligara a auditar."** En 2016 no existía un estándar legal de transparencia o no discriminación algorítmica; el AI Act es posterior. [F07][F08]

---

## 4. Cómo nos defendemos (réplica a cada contraargumento)

1. **Contra "precisión pareja":** la precisión global parecida **oculta** que los errores se reparten de forma desigual. A una persona no la afecta la tasa global, sino **el error concreto que recae sobre ella**: ser marcada peligrosa sin serlo. Igualar el promedio no iguala el daño. [F01]
2. **Contra "calibración = justicia":** la calibración es **una** definición de equidad, no la única. El teorema de imposibilidad demuestra que, con tasas base distintas, cumplir calibración **obliga** a aceptar el desbalance de falsos positivos. [F04] Que la empresa eligiera —en secreto— la métrica que la favorece es justamente la decisión humana que reprochamos.
3. **Contra "es solo apoyo":** lo dice el papel, no la práctica. El **sesgo de automatización** hace que los operadores favorezcan la sugerencia de la máquina aun frente a evidencia en contra. [F10] *Loomis* impuso advertencias precisamente porque el riesgo de sobre-confianza es real: si hizo falta advertir, es porque el puntaje pesa. [F03]
4. **Contra "el daño es del sistema penal":** cierto que los datos vienen sesgados —eso no exime, **agrava**. Desplegar un sistema sobre datos que se sabían sesgados, sin control de sesgo ni auditoría, es una decisión humana negligente. Reflejar una injusticia con apariencia de objetividad la **amplifica y legitima**. [F09]
5. **Contra "no había ley":** la ausencia de ley no es ausencia de deber. El estándar profesional existía igual; el propio enunciado lo dice: sin ley específica, "el único estándar real que queda es la responsabilidad profesional". El vacío legal reparte responsabilidad hacia el regulador, pero **no borra** la de quien diseñó y desplegó el sistema. [F08]

---

## 5. Datos clave para tener a mano en el juicio

- **Broward, ProPublica (2016):** de 1.795 personas negras que NO reincidieron, 805 (≈45%) fueron marcadas alto riesgo; entre las blancas, 349 de 1.488 (≈23%). [F01]
- **Falsos negativos invertidos:** personas blancas marcadas "bajo riesgo" que SÍ reincidieron: ≈48% vs 28% de las negras. [F01]
- **Loomis:** 6 años de prisión; puntaje de alto riesgo; cert. denegado por la Corte Suprema de EE.UU. (2017). [F03]
- **Contexto:** personas negras encarceladas a **4,8×** la tasa de las blancas; ≈14% de la población pero ≈33% de la población carcelaria. [F09]
- **Cambio corporativo:** Northpointe → **Equivant** (enero 2017), manteniendo COMPAS. [F02]

---

## 6. Fuentes de esta parte

F01 ([fuentes/01-propublica-machine-bias.md](fuentes/01-propublica-machine-bias.md)) ·
F02 ([fuentes/02-northpointe-equivant-respuesta.md](fuentes/02-northpointe-equivant-respuesta.md)) ·
F03 ([fuentes/03-state-v-loomis.md](fuentes/03-state-v-loomis.md)) ·
F04 ([fuentes/04-teorema-imposibilidad-equidad.md](fuentes/04-teorema-imposibilidad-equidad.md)) ·
F06 ([fuentes/06-funcionamiento-tecnico-compas.md](fuentes/06-funcionamiento-tecnico-compas.md)) ·
F07 ([fuentes/07-marco-legal-ai-act.md](fuentes/07-marco-legal-ai-act.md)) ·
F08 ([fuentes/08-marco-legal-argentina.md](fuentes/08-marco-legal-argentina.md)) ·
F09 ([fuentes/09-contexto-social-racismo-encarcelamiento.md](fuentes/09-contexto-social-racismo-encarcelamiento.md)) ·
F10 ([fuentes/10-etica-justicia-algoritmica.md](fuentes/10-etica-justicia-algoritmica.md))
