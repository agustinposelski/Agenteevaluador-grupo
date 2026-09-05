# Rúbrica ejecutable v0

## Dimensión 1 — Agente corrector funcionando (25 puntos)

**Criterio oficial:** corre sobre un repo real y devuelve el formato completo.

**Regla de la casa:** el proceso documentado con honestidad vale; las afirmaciones sin evidencia verificable no.

| Nivel | Evidencia exigida | Ejemplo |
|---|---|---|
| **0% — 0/25** | No existe un agente corrector utilizable, o solo hay una descripción de lo que debería hacer. No hay evidencia de que haya sido probado sobre un repositorio real. | `El agente evaluará los repositorios cuando esté terminado.` |
| **25% — 6,25/25** | Existe un prompt o configuración del agente y se documenta al menos un intento real de ejecución, pero falla, queda incompleto o no puede analizar correctamente un repo real. El problema está documentado honestamente. | `Prueba 1: el agente recibió el repo, pero no pudo acceder a todos los archivos.` |
| **50% — 12,5/25** | El agente logra analizar un repositorio real y produce una evaluación, pero falta parte del formato obligatorio: por ejemplo, no cita evidencia concreta, no incluye sugerencias de mejora o la salida es incompleta. | `Resultado: el agente asignó puntajes, pero todavía no cita archivos concretos ni genera una mejora específica.` |
| **75% — 18,75/25** | El agente corre sobre un repo real y devuelve casi todo el formato requerido: puntaje por dimensión, justificación basada en evidencia y sugerencias de mejora. Solo presenta fallas menores de consistencia, precisión o formato, documentadas en las pruebas. | `Agente corrector: 18,75/25 — evalúa correctamente, pero una de las citas es poco específica.` |
| **100% — 25/25** | Hay evidencia verificable de que el agente funciona sobre un repo real y devuelve el formato completo y consistente: puntaje por dimensión, justificación breve citando evidencia concreta del repo y una sugerencia de mejora. Las afirmaciones de funcionamiento están respaldadas por resultados o registros de prueba. | `Agente corrector: 25/25 — evidencia: agente/system_prompt.md y resultado de prueba; salida completa y consistente.` |
