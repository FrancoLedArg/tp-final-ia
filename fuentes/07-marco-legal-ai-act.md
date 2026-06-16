# Fuente 07 — Marco legal europeo: el AI Act

## Identificación de la fuente
- **Reglamento (UE) 2024/1689 — "AI Act"**, Anexo III (sistemas de alto riesgo).
  - AI Act Service Desk (Comisión Europea): https://ai-act-service-desk.ec.europa.eu/en/ai-act/annex-3
  - Texto del Anexo III: https://www.aiact-info.eu/regulation/aiact/annex/2 — https://en.ai-act.io/goto/appendix/III
- **Guías:** EU AI Risk, "High-Risk Classification Guide": https://euairisk.com/resources/eu-ai-act-high-risk-classification-guide
- **Obligaciones y calendario:** https://www.linkedin.com/pulse/high-risk-ai-systems-strict-compliance-obligations-you-zunic-maric-e1ilf

## Cómo clasificaría a COMPAS el AI Act
El AI Act ordena los sistemas por nivel de riesgo. Un sistema tipo COMPAS encaja en **ALTO RIESGO** por dos vías del Anexo III:
- **Punto 6 — Aplicación de la ley (law enforcement):** letra (d), sistemas usados por las fuerzas del orden para "evaluar el riesgo de que una persona física delinca o reincida" (no basado únicamente en perfilado).
- **Punto 8 — Administración de justicia:** letra (a), sistemas usados por una autoridad judicial (o en su nombre) para ayudar a investigar e interpretar hechos y a aplicar la ley. Una herramienta de riesgo de reincidencia que influye en fianza o sentencia entra claramente aquí.

La guía aclara el criterio: un mero buscador de jurisprudencia podría no ser alto riesgo si el juez conserva todo el poder de decisión, pero **un algoritmo de riesgo cuyo puntaje influye significativamente en sentencia o libertad condicional sí supera el umbral** porque incide en derechos fundamentales.

## Qué obligaciones impondría (alto riesgo)
- Sistema de **gestión de riesgos** a lo largo del ciclo de vida.
- **Gobernanza y calidad de los datos** de entrenamiento (representatividad, control de sesgos).
- **Documentación técnica** y **registros** (logs) que permitan trazabilidad.
- **Transparencia** e información al usuario/operador.
- **Supervisión humana** efectiva (human oversight), con capacidad real de revertir.
- **Exactitud, robustez y ciberseguridad.**
- **Evaluación de impacto en los derechos fundamentales (FRIA)** para ciertos desplegadores, especialmente organismos públicos, antes del primer uso.

## Calendario y matiz relevante para el caso
- El AI Act **entró en vigor en 2024** con aplicación por etapas. Las obligaciones para sistemas de alto riesgo del Anexo III comenzarían a aplicarse en torno a **agosto de 2026**.
- Según el [ENUNCIADO.md](../ENUNCIADO.md): **en mayo de 2026 se acordó posponer las obligaciones de alto riesgo hasta diciembre de 2027.** Es decir, ni la ley más avanzada del mundo tenía estas exigencias plenamente operativas en la época del caso, y aun corre sus propios plazos.

## Para qué lado del juicio sirve
- **Acusación:** bajo el estándar europeo, COMPAS es **inequívocamente alto riesgo** y habría incumplido casi todas las obligaciones clave (transparencia, gobernanza de datos, control de sesgo, supervisión humana real, registros). Sirve como vara de "lo que debería haberse exigido".
- **Defensa:** el AI Act es **posterior** a los hechos (2016) y sus obligaciones de alto riesgo **ni siquiera están vigentes aún** (prórroga a dic. 2027). No se puede exigir retroactivamente un estándar que el propio legislador europeo todavía no aplica → traslada responsabilidad al vacío regulatorio.
