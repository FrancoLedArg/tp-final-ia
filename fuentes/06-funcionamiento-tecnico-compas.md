# Fuente 06 — Cómo funciona COMPAS (técnico, en lenguaje llano)

## Identificación de la fuente
- **Northpointe (2015/2019), "A Practitioner's Guide to COMPAS Core"** (guía oficial del fabricante).
  - Copia: https://cjdata.tooltrack.org/sites/default/files/2018-10/Practitioners_Guide_COMPASCore_121917.pdf
- **Wikipedia, "COMPAS (software)":** https://en.wikipedia.org/wiki/COMPAS_(software)
- **Grokipedia, "COMPAS (software)":** https://grokipedia.com/page/COMPAS_(software)
- **Manual de uso (State Bar of Michigan):** https://www.michbar.org/file/news/releases/archives17/COMPAS-at-PSI-Manual-2-27-17-Combined.pdf

## Qué es
COMPAS = *Correctional Offender Management Profiling for Alternative Sanctions*. Es una herramienta **actuarial de evaluación de riesgo y necesidades de "cuarta generación"**, creada por Northpointe (Inc.) en 1998 (hoy Equivant). La usan tribunales y agencias correccionales de EE.UU. para informar decisiones de fianza, libertad condicional, supervisión y sentencia.

## Cómo funciona (en lenguaje llano)
- **Entrada de datos:** un cuestionario de **137 ítems** respondido por entrevista o formulario, más los **registros penales públicos** de la persona. Las secciones incluyen cargos actuales, historial penal, incumplimientos, criminalidad familiar, pares, abuso de sustancias, residencia/estabilidad, entorno social, educación, empleo, ocio, aislamiento social, personalidad criminal, enojo y actitudes criminales.
- **Tipos de factores:**
  - **Estáticos** (no cambian): historial penal, edad al primer arresto, antecedentes de incumplimiento. Son los **mayores predictores** del puntaje.
  - **Dinámicos / "criminógenos"** (pueden cambiar): empleo, educación, consumo de sustancias, entorno social.
- **Salidas:** escalas de riesgo que predicen **reincidencia general**, **reincidencia violenta** y **riesgo previo al juicio** (fallo en comparecer / nuevo delito). Se reportan en una escala de **1 a 10** y en categorías **bajo (1-4), medio (5-7) y alto (8-10)**, calibradas contra tasas históricas de muestras de referencia.
- **Lógica:** compara el perfil del individuo con grupos de personas de características similares y resultados conocidos; el puntaje refleja la frecuencia de reincidencia de ese grupo de referencia.

## Puntos críticos para el caso
- **No usa "raza" como variable explícita.** Sin embargo, muchos ítems (barrio, entorno social, antecedentes familiares, historial de arrestos) están **correlacionados con la raza** y actúan como **proxies**; de ahí puede surgir el sesgo aunque nadie lo programe.
- **Caja negra:** la fórmula de ponderación es **secreto comercial**. Ni la persona evaluada ni el tribunal pueden inspeccionar cómo se combinan los factores (ver fuente 03, Loomis).
- **Apoyo, no decisión:** el fabricante sostiene que el puntaje informa decisiones humanas y no debería ser la única prueba.

## Para qué lado del juicio sirve
- **Acusación:** el uso de proxies explica el sesgo "sin variable raza"; la opacidad impide auditar; la complejidad (137 ítems) no se traduce en mejor desempeño (ver fuente 05).
- **Defensa:** es una herramienta validada, estandarizada y pensada como apoyo; no incorpora la raza deliberadamente y su salida es solo una de varias entradas para el operador humano.
