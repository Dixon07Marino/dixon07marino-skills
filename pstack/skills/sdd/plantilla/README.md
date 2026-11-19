# SDD (Spec-Driven Development), versión ágil

Fuera de git (`.git/info/exclude`). Una carpeta por tema: `sdd/<tema>/`. Copia `_plantilla/` para empezar uno nuevo.

| Archivo | Responde | Regla |
|---|---|---|
| `README.md` | ¿En qué estado está? | Una pantalla: estado, fase activa, enlaces. Es lo único que se lee siempre. |
| `spec.md` | ¿Qué y por qué? | Problema, reglas cerradas, criterios de aceptación verificables, fuera de alcance, preguntas abiertas. Sin cómo. |
| `diseno.md` | ¿Cómo? | Módulos tocados, puertos, datos y migraciones, riesgos. Solo decisiones que no se deducen del código. |
| `plan.md` | ¿En qué orden? | Fases pequeñas (cada una termina en algo verificable), tareas con casilla y comando de verificación. |
| `referencia/` | Evidencia | Transcripciones de chats, hallazgos de sandbox, exploraciones. No se lee por defecto. |

Variantes permitidas: `spec/` como carpeta (`NN_tema.md`, más `99_preguntas-abiertas.md`) cuando una spec supera las 150 líneas, y `constitucion.md` si el tema tiene reglas propias que no se negocian.

## Flujo
1. **Spec** corta y aprobada por el usuario antes de diseñar. Las dudas van a "Preguntas abiertas", no se asumen.
2. **Diseño** solo si el cambio cruza módulos, toca datos o es riesgoso. Un cambio pequeño no lo necesita.
3. **Plan** en fases de 1 a 3 días, con tareas en rebanadas verticales. Cada tarea cita el criterio de aceptación que cubre, qué la bloquea y cómo se verifica.
4. **Ejecutar** una fase a la vez en una rama (`feat/<tema>-<fase>`), con PR por fase. Al cerrarla, marca las casillas y actualiza el estado del `README.md`.
5. **Cerrar**: cuando todo esté en `main`, el `spec.md` y el `diseno.md` que sigan vigentes se resumen en `docs/` y el tema pasa a `Estado: cerrado`.

## Reglas
- Un criterio de aceptación sin forma de verificarse no es un criterio.
- Cada archivo cabe en unas 150 líneas. Si crece, parte el tema o mueve detalle a `referencia/`.
- Las decisiones cerradas se escriben una vez, en `spec.md`. No se repiten en otros archivos.
