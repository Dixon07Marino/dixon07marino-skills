---
name: sdd
description: "Trabaja un tema de sdd/ por fases: /sdd lista temas, /sdd <tema> avanza la tarea siguiente, /sdd nuevo <tema> lo entrevista, redacta spec y plan en rebanadas verticales, /sdd cerrar <tema> lo cierra."
disable-model-invocation: true
---

# SDD ágil

Los temas viven en `sdd/<tema>/` en la raíz del repo, con la estructura de `sdd/README.md` (`README.md`, `spec.md` o `spec/`, `diseno.md`, `plan.md`, `referencia/`). `sdd/` es el tracker: tareas, bloqueos y estado viven ahí, no en issues externos. Si no existe `sdd/`, ver "Si falta `sdd/`". Gasta pocos tokens: lee solo lo que el paso necesita y nunca `referencia/`.

## Si falta `sdd/`
La carpeta `plantilla/` junto a este archivo trae el método (`README.md`) y el molde de un tema (`_plantilla/`). Para crear `sdd/`, copia su contenido tal cual en `sdd/` (si ya existe, no la toques y no sobrescribas nada: otra skill de planeación puede haberla creado). Pregunta una vez si `sdd/` va fuera de git (se añade a `.git/info/exclude`, por defecto) o versionada. `/sdd nuevo` la crea sola; `/sdd` sin argumentos ofrece crearla; `/sdd <tema>` y `/sdd cerrar <tema>` dicen que falta y paran.

## `/sdd` sin argumentos
Lista los temas: para cada `sdd/*/README.md` (salta `_plantilla`) extrae con `rg` solo las líneas `Estado`, `Rama` y `Siguiente paso`. Muestra una tabla y pregunta cuál continuar.

## `/sdd <tema>`: avanzar
1. Lee `README.md` del tema y su `plan.md`. Busca la **frontera**: las tareas sin terminar cuyas `Bloqueada por` ya están hechas. Toma la primera de la fase activa. Lee solo esa fase (`rg -n "^#+ |\[ \]"`; los planes pueden ser listas con casillas o tablas).
2. De `spec.md` lee únicamente los criterios y reglas que esa fase cita, con `rg -n "CA<n>|R<n>"`. Si la fase depende de una decisión que figura en "Preguntas abiertas", detente y pregúntala; no la asumas.
3. Haz **una tarea**, respetando `CLAUDE.md` y `.claude/rules/`. Si toca código y el plan fija una costura de prueba, trabaja test-first (con la skill `tdd` si está disponible): una prueba que falla en esa costura, el mínimo código para pasarla, repetir. La prueba afirma comportamiento observable, no detalles internos. Corre la verificación de la tarea, o el test del módulo tocado si no la trae. Muestra el resultado real.
4. Con la verificación en verde, marca la casilla en `plan.md`. Si falla, no la marques: corrige o informa.
5. Al terminar la última tarea de la fase: actualiza `Estado` y `Siguiente paso` en `README.md`, resume en 3 líneas qué quedó hecho y propone rama (`feat/<tema>-<fase>`), commit y PR. Sugiere `/code-review` (la de Claude Code) antes del PR. Para comprobar que el diff cumple `sdd/<tema>/spec.md`, existe `/mattpocock-skills:code-review`, que es manual. No hagas commit ni push sin que el usuario lo pida.
6. Una tarea por invocación, salvo que el usuario pida más. Si la tarea es mayor de lo previsto, divídela en `plan.md` antes de seguir.

## `/sdd nuevo <tema>`
1. Copia `sdd/_plantilla/` a `sdd/<tema>/` (nombre en minúscula con guiones).
2. **Entiende antes de redactar.** Si el problema no está claro, usa la skill `grilling`; si no está disponible, haz lo mismo tú: preguntas por rondas, cada ronda con todas las que ya se pueden responder, cada una con tu respuesta recomendada, de modo que un "sí" la acepte. Los hechos del código los buscas tú, no el usuario. Cierra cuando no quede ninguna rama sin revisar.
3. Redacta `spec.md`: problema desde la perspectiva de quien lo sufre, reglas cerradas, criterios de aceptación **verificables**, fuera de alcance. Usa el vocabulario del proyecto. Sin rutas de archivo ni fragmentos de código, que se quedan viejos. Lo que no sepas va a "Preguntas abiertas". Muéstrala y espera aprobación antes de continuar. No escribas `diseno.md` ni `plan.md` sin ella.
4. **Costuras de prueba.** Propón dónde se prueba: prefiere las costuras que ya existen a las nuevas, la más alta posible, idealmente una. Para cada una di en una línea qué atrapa y qué no. Confirma con el usuario antes de planear y anótalas en `diseno.md`, o al inicio de `plan.md` si no hay diseño.
5. `diseno.md` solo si el cambio cruza módulos, toca datos o es riesgoso.
6. **`plan.md` en rebanadas verticales.** Reglas:
   - Cada tarea cruza todas las capas que necesita (datos, lógica, API o pantalla, prueba) y se puede demostrar o verificar sola. Nada de tareas "toda la capa X".
   - Cada tarea cabe en una sesión. Si no, se parte.
   - Si hace falta preparar el código, esa tarea va primero: haz fácil el cambio y luego haz el cambio fácil.
   - Cada tarea declara qué la bloquea y qué criterio cubre, con este formato:
     ```
     - [ ] T2. <resultado de punta a punta.> Cubre: CA1. Bloqueada por: T1 (o ninguna). Verifica: `<comando>`.
     ```
   - Excepción: un cambio mecánico ancho (renombrar una columna, retipar un símbolo compartido) no cabe en una rebanada. Hazlo expandir y contraer: añade la forma nueva junto a la vieja, migra los usos por lotes, borra la vieja.
   - Fases de 1 a 3 días. Muestra el desglose y pregunta si la granularidad es la justa, si los bloqueos son reales y si hay tareas por unir o dividir. Itera hasta que lo apruebe.
7. Actualiza `README.md` con estado y siguiente paso.

## `/sdd cerrar <tema>`
Comprueba que todas las casillas de `plan.md` estén marcadas y que lo vigente de `spec` y `diseno` ya esté resumido en `docs/`; si falta, propón el resumen. Si el diff nunca se revisó contra la spec, sugiérelo con `/mattpocock-skills:code-review`. Pon `Estado: cerrado` en el `README.md`.

## Reglas
- Un criterio de aceptación sin forma de verificarse no es un criterio: reescríbelo.
- Una rebanada que no se puede verificar sola está mal cortada: pártela de otro modo.
- Una decisión cerrada se escribe una vez, en la spec.
- Cada archivo cabe en unas 150 líneas. Si crece, mueve detalle a `referencia/` o parte el tema.
- Las dudas se preguntan al usuario y se anotan; no se resuelven en silencio en el código.
