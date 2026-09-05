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

## Dimensión 2 — Rúbrica ejecutable (25 puntos)

**Criterio oficial:** precisión, escalas y evidencia exigida por nivel.

| Nivel | Evidencia exigida | Ejemplo |
|---|---|---|
| **0% — 0/25** | No hay una rúbrica utilizable, o solo enumera criterios sin explicar cómo asignar puntajes. | `Se evaluará la calidad del agente.` |
| **25% — 6,25/25** | Hay criterios y algunos niveles, pero son vagos o no indican qué evidencia concreta corresponde a cada puntaje. | `Excelente si el agente funciona muy bien.` |
| **50% — 12,5/25** | La mayoría de los criterios tiene niveles de puntaje, pero algunas diferencias entre niveles son ambiguas o faltan evidencias verificables. | `75%: funciona casi completamente, aunque puede tener algunos problemas.` |
| **75% — 18,75/25** | Todos los criterios tienen escalas claras y evidencia exigida. Quedan pequeñas ambigüedades que podrían hacer que dos evaluadores puntúen distinto. | `75%: corre sobre un repo real y devuelve todos los campos, salvo una falla menor documentada.` |
| **100% — 25/25** | Todos los criterios tienen niveles inequívocos, evidencia concreta y ejemplos. Dos evaluadores deberían poder aplicar la rúbrica y llegar prácticamente al mismo resultado. | `100%: existe evidencia verificable de ejecución y la salida contiene puntaje, justificación con evidencia y mejora concreta.` |

## Dimensión 3 — Casos de prueba (20 puntos)

**Criterio oficial:** los tres existen y el corrector los distingue, incluido el tramposo.

| Nivel | Evidencia exigida | Ejemplo |
|---|---|---|
| **0% — 0/20** | No existen los tres casos, o son archivos vacíos o sin contenido evaluable. | `casos/excelente/README.md` solo contiene el título. |
| **25% — 5/20** | Existen los tres casos, pero son muy básicos o no permiten distinguir claramente excelente, flojo y tramposo. | Los tres casos tienen casi el mismo contenido y solo cambian algunas frases. |
| **50% — 10/20** | Los tres casos tienen diferencias reales, pero el agente no logra clasificarlos correctamente o el tramposo no pone a prueba la verificación de evidencia. | El excelente recibe nota alta y el flojo baja, pero el tramposo también recibe alta. |
| **75% — 15/20** | Los tres casos son distintos y el agente los diferencia correctamente en general, incluido el tramposo, aunque queda alguna inconsistencia menor. | Excelente: alto; flojo: bajo; tramposo: detectado, pero alguna dimensión queda sobrevalorada. |
| **100% — 20/20** | Existen los tres casos completos y están diseñados para probar conductas diferentes. El corrector puntúa alto al excelente, bajo al flojo y detecta explícitamente afirmaciones sin evidencia del tramposo. Hay resultados documentados. | `Caso tramposo: afirma tener pruebas completas, pero no existen archivos que lo demuestren. El agente detecta la contradicción y reduce el puntaje.` |

## Dimensión 4 — Calibración documentada (15 puntos)

**Criterio oficial:** desacuerdos encontrados, ajustes hechos y resultado posterior.

| Nivel | Evidencia exigida | Ejemplo |
|---|---|---|
| **0% — 0/15** | No hay calibración documentada, o solo se afirma que el agente funciona bien sin comparar contra criterio humano. | `El agente fue probado y funciona correctamente.` |
| **25% — 3,75/15** | Hay al menos una comparación entre nota del agente y nota humana, pero sin explicar diferencias ni ajustes. | `Agente: 70. Humano: 80.` |
| **50% — 7,5/15** | Se comparan varias evaluaciones y se identifican desacuerdos concretos, pero los ajustes son incompletos o no se muestra el resultado posterior. | `El agente penalizó demasiado la documentación; decidimos revisar ese criterio.` |
| **75% — 11,25/15** | Se documentan desacuerdos, causas probables, ajustes realizados en la rúbrica o en el agente y una nueva corrida con mejora visible. | `Antes: agente 65 / humano 80. Se ajustó el criterio de evidencia. Después: agente 77 / humano 80.` |
| **100% — 15/15** | Hay una secuencia clara de calibración: nota humana vs. agente, análisis del desacuerdo, cambio específico, nueva corrida y resultado final. El proceso es honesto y permite entender por qué cambió el sistema. | `Caso flojo: agente 55 / humano 35. Se modificó la regla que premiaba afirmaciones no verificadas y la nueva corrida dio 38.` |

## Dimensión 5 — Proceso grupal (15 puntos)

**Criterio oficial:** historia de commits, iteraciones de la rúbrica y decisiones registradas.

| Nivel | Evidencia exigida | Ejemplo |
|---|---|---|
| **0% — 0/15** | No hay evidencia de proceso grupal. El repositorio aparece prácticamente terminado de una sola vez, sin evolución visible ni decisiones registradas. | `Un único commit final con todos los archivos.` |
| **25% — 3,75/15** | Hay varios commits, pero son poco descriptivos o no muestran claramente quién hizo qué ni cómo evolucionó el trabajo. | `Update files` / `changes` / `final.` |
| **50% — 7,5/15** | La historia de commits muestra avances reales y algunos cambios de criterio, pero la documentación del proceso es parcial. | `Agregar primera versión de rúbrica` → `Ajustar caso tramposo.` |
| **75% — 11,25/15** | Se observa una secuencia clara de trabajo: distintas personas aportan, la rúbrica evoluciona y quedan registradas decisiones o ajustes importantes. | `Diego agrega caso excelente` → `Eliana ajusta rúbrica` → `Gustavo modifica agente según prueba.` |
| **100% — 15/15** | El repositorio cuenta claramente la historia del proyecto: aportes distribuidos, commits descriptivos, iteraciones de la rúbrica, pruebas, desacuerdos y decisiones documentadas. Se puede reconstruir cómo evolucionó el agente. | `Calibración v1: agente sobrevalora caso flojo` → `Ajustar criterio de evidencia` → `Calibración v2: diferencia reducida.` |
