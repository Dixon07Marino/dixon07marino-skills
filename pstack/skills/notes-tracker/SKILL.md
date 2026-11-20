---
name: notes-tracker
description: "Opera el vault de Obsidian 'Dixon's life': anota o actualiza suscripciones, gastos, metas, proyectos, ideas, cursos, peso, fechas y la semana respetando su estructura y estilo. Úsala cuando el usuario pida anotar, registrar, actualizar o revisar algo de sus notas personales. /notes-tracker week hace el repaso semanal."
---

# Notes tracker

El vault está en `~/Documents/Dixon's life`. Si la ruta no existe, pregunta dónde está y no crees uno. Gasta pocos tokens: lee solo la nota que el cambio necesita.

## Reglas duras
1. Las notas son del usuario. Solo añade o cambia lo que pidió, y solo en la nota que corresponde. Nunca muevas, renombres ni borres una nota o carpeta sin que lo pida, y nunca edites nada dentro de `getting-smart/Courses/`.
2. Todo en inglés, minimalista, sin emojis, sin relleno. Si una nota ya tiene un formato, respétalo.
3. No inventes datos. Lo que no sepas se deja en blanco, no se adivina.
4. No toques `.obsidian/`.
5. Para crear una nota nueva o reestructurar, propón el nombre y el lugar y espera el OK. Los nombres son cortos, en minúsculas con guiones y con la misma gracia que los existentes (`do-it`, `i-got-this`). Toda nota nueva se enlaza desde `home-homie/here-we-go`.
6. Los datos de dinero y salud son privados: no salen a ningún servicio externo.

## Mapa
| Carpeta | Nota | Contiene |
|---|---|---|
| `home-homie` | `here-we-go` | Hub: enlaza todo |
| | `week-me`, `week-work` | Foco (máximo 3), notas, cierre de semana |
| | `quick-notes` | Notas rápidas de la semana |
| | `dont-forget` | Trámites y vencimientos que no son pagos |
| `oh-my-money` | `my-month` | Ingresos, gastos fijos, suscripciones, deudas, ahorro, balance |
| `do-it` | `short-term`, `long-term` | Metas, cada una con sus líneas de medida |
| `build-it` | `projects-me`, `projects-work` | Tablas de proyectos |
| | `brainstorm-me`, `brainstorm-work` | Ideas sueltas, una por línea |
| `getting-smart` | `my-courses` | Tabla de cursos y progreso |
| `be-healthy` | `gymbro`, `health` | Ejercicio, peso, chequeos |
| `get-up-clean` | `i-got-this` | Aseo de la habitación y personal |
| `get-attention` | `social` | Redes y su mantenimiento mensual |
| `need-it` | `leisure` | Entretenimiento por ver, en curso, terminado |
| `my-job` | `Data Core` | Proyecto de trabajo |

## Operaciones
- **Suscripción, gasto o ingreso:** añade o edita la fila en su tabla de `my-month`. Después recalcula el `Total` de esa tabla y el `Balance` (ingresos - gastos fijos - suscripciones - cuotas de deudas). Los totales están escritos a mano: muestra la cuenta y verifica la suma antes de escribirla. Cuando un cobro pase, avanza su fecha de `Next charge`.
- **Meta:** va bajo su grupo (`**Personal**`, etc.) en `short-term` o `long-term`, con sus líneas de medida (`Now`, `By`, y las que ya tenga). Cada meta debe poder medirse: si falta el dato, déjalo vacío y dilo.
- **Peso o ejercicio:** una fila nueva en la tabla `Weight` o una línea en `Log` de `gymbro`.
- **Idea:** una línea en `brainstorm-me` o `brainstorm-work`. Promoverla es moverla a una fila de `projects-me` o `projects-work` (estado `idea`, `active`, `paused` o `done`) y quitar la línea del brainstorm.
- **Curso:** fila en `my-courses` (`goal`, `in progress`, `done`, con `Progress`). Enlaza a las notas del curso, no las edites.
- **Semana:** el `Focus` admite 3 cosas como máximo; si piden una cuarta, avisa y pregunta cuál sale. Lo suelto va a `quick-notes`.
- **Fecha o trámite:** línea `YYYY-MM-DD | texto` en `dont-forget`, la más cercana primero.

## `/notes-tracker week`
Repaso semanal, solo lectura hasta el final. Lee `week-me`, `week-work`, `quick-notes` y los pendientes de `i-got-this`. Entrega en pocas líneas lo hecho, lo pendiente y los cobros de los próximos 7 días en `my-month`. Al final pregunta si reinicia la semana: desmarcar los checks semanales de `i-got-this` y limpiar el cierre de `week-me` y `week-work`. Sin el OK, no cambies nada.

## Formato
- Dinero con puntos de miles: `$1.234.567`.
- Fechas en tablas: `19 Dec 2026`. En registros: `2026-12-19`.
- Las tablas de markdown se mantienen alineadas con el resto de su nota.

## Al terminar
Una o dos líneas: qué cambió y en qué nota. Si tocaste dinero, di el nuevo balance. No pegues la nota entera.
