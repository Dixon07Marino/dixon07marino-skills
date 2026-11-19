# pstack (fork personal)

Fork de pstack orientado a bajo consumo de tokens y calidad de software. Se trabaja en el hilo principal. Un subagente solo se lanza cuando el usuario lo pide o el trabajo es independiente y demasiado grande para leerlo directamente.

Los PRs funcionan con GitHub (`gh`) y con Azure DevOps (`az repos pr`). La herramienta se elige según `git remote get-url origin`.

## Skills

| Skill | Para qué |
|---|---|
| [`/poteto-mode`](./skills/poteto-mode/SKILL.md) | Punto de entrada. Elige un playbook, lo sigue y verifica con evidencia real. |
| [`/sdd`](./skills/sdd/SKILL.md) | Trabaja un tema de `sdd/` por fases: lista, avanza, crea y cierra. |
| [`/architect`](./skills/architect/SKILL.md) | Fija tipos, firmas y forma de módulos antes de escribir código. |
| [`/how`](./skills/how/SKILL.md) | Explica cómo funciona el código hoy o dónde debe vivir el nuevo. |
| [`/why`](./skills/why/SKILL.md) | Explica por qué el código es como es: decisiones, regresiones, origen de un número. |
| [`/explain-work`](./skills/explain-work/SKILL.md) | Explica un cambio o subsistema ya hecho en lenguaje claro. Para aprender conceptos usa teach, de Matt. |
| [`/recall`](./skills/recall/SKILL.md) | Reconstruye contexto de tus chats recientes sobre un tema. |
| [`/ketchup`](./skills/ketchup/SKILL.md) | Resumen de lo ocurrido en este chat desde tu último mensaje. |
| [`/bro`](./skills/bro/SKILL.md) | Repite la última respuesta en palabras simples. |
| [`/in-your-own-words`](./skills/in-your-own-words/SKILL.md) | Confirma que el agente entendió tu objetivo antes de empezar. |
| [`/sharpen`](./skills/sharpen/SKILL.md) | Reescribe un prompt para hacerlo más profundo, sin hacerlo más grande. |
| [`/typescript-best-practices`](./skills/typescript-best-practices/SKILL.md) | Reglas para `.ts` y `.tsx`. |
| [`/no-comments`](./skills/no-comments/SKILL.md) | Quita comentarios que no aportan antes de la revisión. |
| [`/unslop`](./skills/unslop/SKILL.md) | Quita marcas de texto generado por IA. |
| [`/technical-writing`](./skills/technical-writing/SKILL.md) | Estándar para docs, RFCs, READMEs, descripciones de PR y commits. |
| [`/benchmark-checklist`](./skills/benchmark-checklist/SKILL.md) | Valida una medición de rendimiento antes de reportarla. |
| [`/create-verification-skill`](./skills/create-verification-skill/SKILL.md) | Genera una skill del proyecto que maneja la app como un usuario. |
| [`/maintain-verification-skill`](./skills/maintain-verification-skill/SKILL.md) | Mantiene al día esa skill y su mapa de features. |
| [`/create-formal-verification-skill`](./skills/create-formal-verification-skill/SKILL.md) | Verifica formalmente una propiedad crítica del código. |
| [`/maintain-formal-verification-skill`](./skills/maintain-formal-verification-skill/SKILL.md) | Mantiene al día la verificación formal tras cambios. |
| [`/show-me-your-work`](./skills/show-me-your-work/SKILL.md) | Bitácora de decisiones en trabajo largo o desatendido. |
| [`/automate-me`](./skills/automate-me/SKILL.md) | Genera un modo personal a partir de tu historial. |
| [`/reflect`](./skills/reflect/SKILL.md) | Convierte lo aprendido en una tarea en ediciones de skills. |
| [`/correct`](./skills/correct/SKILL.md) | Evita que los agentes repitan los mismos errores en este repo. |

## Skills de Matt Pocock

Copiadas de [mattpocock/skills](https://github.com/mattpocock/skills) (MIT, texto en `LICENSE`). Cambios locales en `NOTICES.md` de la raíz del repo.

| Skill | Qué hace |
|---|---|
| [`/grilling`](./skills/grilling/SKILL.md) | Te interroga por rondas para poner a prueba un plan o una idea. |
| [`/grill-me`](./skills/grill-me/SKILL.md) | Lanza esa entrevista a mano. |
| [`/tdd`](./skills/tdd/SKILL.md) | Rojo, verde, refactor: prueba que falla, código mínimo, repetir. |
| [`/diagnosing-bugs`](./skills/diagnosing-bugs/SKILL.md) | Método para bugs difíciles: primero un bucle que falle justo con el bug. |
| [`/code-review`](./skills/code-review/SKILL.md) | Revisión en dos ejes (estándares y spec). Manual: manda el `/code-review` nativo. |
| [`/codebase-design`](./skills/codebase-design/SKILL.md) | Vocabulario de diseño: módulo profundo, interfaz, costura. |
| [`/domain-modeling`](./skills/domain-modeling/SKILL.md) | Glosario y decisiones (ADR) del proyecto. |
| [`/prototype`](./skills/prototype/SKILL.md) | Prototipo desechable para responder una duda de diseño. |
| [`/improve-codebase-architecture`](./skills/improve-codebase-architecture/SKILL.md) | Informe HTML de oportunidades de mejora y entrevista sobre una. |
| [`/pr`](./skills/pr/SKILL.md) | Plantilla para el cuerpo de un PR: Summary, Evidence, Merge Danger. |
| [`/retro`](./skills/retro/SKILL.md) | Retrospectiva de una sesión de código. |
| [`/teach`](./skills/teach/SKILL.md) | Te enseña un concepto nuevo dentro de tu workspace. |
| [`/wizard`](./skills/wizard/SKILL.md) | Genera un asistente en bash para pasos que solo un humano puede hacer. |
| [`/to-questionnaire`](./skills/to-questionnaire/SKILL.md) | Convierte una decisión que no puedes responder en un cuestionario para otra persona. |

## Playbooks

Viven dentro de [`/poteto-mode`](./skills/poteto-mode/SKILL.md). Describir la tarea elige uno.

| Playbook | Para qué |
|---|---|
| [investigation](./skills/poteto-mode/playbooks/investigation.md) | Entender un comportamiento sin cambiar código. |
| [bug-fix](./skills/poteto-mode/playbooks/bug-fix.md) | Reproducir, hallar la causa raíz, corregir y verificar. |
| [feature](./skills/poteto-mode/playbooks/feature.md) | Trazar, definir la forma, implementar y verificar. |
| [refactoring](./skills/poteto-mode/playbooks/refactoring.md) | Cambio estructural pequeño o mediano con el comportamiento fijado. |
| [prototype](./skills/poteto-mode/playbooks/prototype.md) | Resolver una duda construyendo en vez de preguntar. |
| [perf-issue](./skills/poteto-mode/playbooks/perf-issue.md) | Rendimiento, con medición antes y después. |
| [hillclimb](./skills/poteto-mode/playbooks/hillclimb.md) | Iterar sobre una métrica con un arnés congelado. |
| [runtime-forensics](./skills/poteto-mode/playbooks/runtime-forensics.md) | Fallos en ejecución con evidencia del runtime. |
| [trace-forensics](./skills/poteto-mode/playbooks/trace-forensics.md) | Investigar a partir de trazas. |
| [visual-parity](./skills/poteto-mode/playbooks/visual-parity.md) | Igualar una UI contra una referencia. |
| [opening-a-pr](./skills/poteto-mode/playbooks/opening-a-pr.md) | Abrir un PR listo para revisión (`gh` o `az repos pr`). |
| [babysit](./skills/poteto-mode/playbooks/babysit.md) | Llevar un PR a merge-ready, sin mergear. |
| [shipping](./skills/poteto-mode/playbooks/shipping.md) | Aterrizar una pila de PRs verificados. |
| [autopilot-stack](./skills/poteto-mode/playbooks/autopilot-stack.md) | Autopilot sobre una pila de PRs, sin mergear. |
| [autopilot-full](./skills/poteto-mode/playbooks/autopilot-full.md) | Autopilot sobre una cola: un dueño por PR y un verificador independiente. |
| [autonomous-run](./skills/poteto-mode/playbooks/autonomous-run.md) | Llevar una tarea a una condición de término. |
| [session-pickup](./skills/poteto-mode/playbooks/session-pickup.md) | Retomar el trabajo de otra sesión. |
| [pause-safely](./skills/poteto-mode/playbooks/pause-safely.md) | Pausar dejando todo en estado seguro. |
| [multi-phase-plan](./skills/poteto-mode/playbooks/multi-phase-plan.md) | Escribir un plan por fases, sin implementar. |
| [authoring-a-skill](./skills/poteto-mode/playbooks/authoring-a-skill.md) | Escribir o cambiar una skill. |
| [worktree-cleanup](./skills/poteto-mode/playbooks/worktree-cleanup.md) | Limpiar worktrees. |

## Principios

Reglas de una línea que `poteto-mode` cita cuando aplican.

| Principio | Regla |
|---|---|
| [boundary-discipline](./skills/principle-boundary-discipline/SKILL.md) | Guardas en los bordes del sistema; el interior confía en sus tipos. |
| [encode-lessons-in-structure](./skills/principle-encode-lessons-in-structure/SKILL.md) | Codifica la regla en un lint o chequeo en vez de repetir la instrucción. |
| [experience-first](./skills/principle-experience-first/SKILL.md) | Prioriza al usuario sobre la comodidad de implementar. |
| [explain-the-number](./skills/principle-explain-the-number/SKILL.md) | Antes de confiar en una medición, encuentra qué la limita. |
| [fix-root-causes](./skills/principle-fix-root-causes/SKILL.md) | Corrige en el primer punto donde el sistema falló. |
| [foundational-thinking](./skills/principle-foundational-thinking/SKILL.md) | Estructuras de datos y tipos primero. |
| [laziness-protocol](./skills/principle-laziness-protocol/SKILL.md) | El cambio más pequeño que resuelve el problema. |
| [make-operations-idempotent](./skills/principle-make-operations-idempotent/SKILL.md) | Mismo estado final tras fallos y reintentos. |
| [minimize-reader-load](./skills/principle-minimize-reader-load/SKILL.md) | Menos capas y menos estado oculto. |
| [model-the-domain](./skills/principle-model-the-domain/SKILL.md) | Modela el dominio en una estructura, no en condicionales dispersos. |
| [prove-it-works](./skills/principle-prove-it-works/SKILL.md) | Verifica contra el artefacto real antes de declarar listo. |
| [sequence-verifiable-units](./skills/principle-sequence-verifiable-units/SKILL.md) | Unidades pequeñas, cada una verificada antes de la siguiente. |
| [subtract-before-you-add](./skills/principle-subtract-before-you-add/SKILL.md) | Elimina primero lo muerto y construye sobre lo simple. |
| [test-behavior-not-implementation](./skills/principle-test-behavior-not-implementation/SKILL.md) | Los tests afirman lo observable, no los internos. |
| [type-system-discipline](./skills/principle-type-system-discipline/SKILL.md) | Haz irrepresentables los estados ilegales. |

## Agentes

| Agente | Para qué |
|---|---|
| [`poteto-agent`](./agents/poteto-agent.md) | Subagente para delegar trabajo acotado. Solo si de verdad hace falta. |
| [`comment-sicko`](./agents/comment-sicko.md) | Revisor de comentarios que usa `no-comments`. |

## Instalar en Claude Code

Las rutas y nombres de herramientas de Cursor se mapean en [el adaptador de Claude Code](./docs/harness/claude-code.md). `harness/` se genera con `node scripts/generate-pstack-harness-trees.mjs` y no se edita a mano.
