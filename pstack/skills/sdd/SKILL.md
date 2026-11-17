---
name: sdd
description: "Trabaja un tema de sdd/ por fases: /sdd lista temas, /sdd <tema> avanza la fase activa, /sdd nuevo <tema> crea uno, /sdd cerrar <tema> lo cierra."
disable-model-invocation: true
---

# SDD ágil

Los temas viven en `sdd/<tema>/` en la raíz del repo, con la estructura de `sdd/README.md` (`README.md`, `spec.md` o `spec/`, `diseno.md`, `plan.md`, `referencia/`). Si no existe `sdd/`, dilo y para. Gasta pocos tokens: lee solo lo que el paso necesita y nunca `referencia/`.

## `/sdd` sin argumentos
Lista los temas: para cada `sdd/*/README.md` (salta `_plantilla`) extrae con `rg` solo las líneas `Estado`, `Rama` y `Siguiente paso`. Muestra una tabla y pregunta cuál continuar.

## `/sdd <tema>`: avanzar
1. Lee `README.md` del tema y su `plan.md`. Encuentra la primera fase con tareas sin terminar (`rg -n "^#+ |\[ \]"`; los planes pueden ser listas con casillas o tablas). Lee solo esa fase.
2. De `spec.md` lee únicamente los criterios y reglas que esa fase cita, con `rg -n "CA<n>|R<n>"`. Si la fase depende de una decisión que figura en "Preguntas abiertas", detente y pregúntala; no la asumas.
3. Haz **una tarea**, la siguiente sin terminar, respetando `CLAUDE.md` y `.claude/rules/`. Corre el comando de verificación de la tarea, o el test del módulo tocado si no lo trae. Muestra el resultado real.
4. Con la verificación en verde, marca la casilla en `plan.md`. Si falla, no la marques: corrige o informa.
5. Al terminar la última tarea de la fase: actualiza `Estado` y `Siguiente paso` en `README.md`, resume en 3 líneas qué quedó hecho y propone rama (`feat/<tema>-<fase>`), commit y PR. No hagas commit ni push sin que el usuario lo pida.
6. Una tarea por invocación, salvo que el usuario pida más. Si la tarea es mayor de lo previsto, divídela en `plan.md` antes de seguir.

## `/sdd nuevo <tema>`
1. Copia `sdd/_plantilla/` a `sdd/<tema>/` (nombre en minúscula con guiones).
2. Pide al usuario el problema en pocas líneas y redacta `spec.md`: problema, reglas cerradas, criterios de aceptación **verificables**, fuera de alcance. Lo que no sepas va a "Preguntas abiertas".
3. Muestra la spec y espera aprobación antes de continuar. No escribas `diseno.md` ni `plan.md` sin ella.
4. `diseno.md` solo si el cambio cruza módulos, toca datos o es riesgoso. Luego `plan.md` en fases de 1 a 3 días; cada tarea cita el criterio que cubre y cómo se verifica.
5. Actualiza `README.md` con estado y siguiente paso.

## `/sdd cerrar <tema>`
Comprueba que todas las casillas de `plan.md` estén marcadas y que lo vigente de `spec` y `diseno` ya esté resumido en `docs/`; si falta, propón el resumen. Pon `Estado: cerrado` en el `README.md`.

## Reglas
- Un criterio de aceptación sin forma de verificarse no es un criterio: reescríbelo.
- Una decisión cerrada se escribe una vez, en la spec.
- Cada archivo cabe en unas 150 líneas. Si crece, mueve detalle a `referencia/` o parte el tema.
- Las dudas se preguntan al usuario y se anotan; no se resuelven en silencio en el código.
