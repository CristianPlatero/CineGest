# Documentación

Índice de la documentación del proyecto CineGest, organizada en siete bloques. Cada bloque termina con un entregable y tiene su propia carpeta.

[← Volver al README principal](../README.md)

## Cómo trabajamos

El módulo se desarrolla de forma incremental. Durante las sesiones de clase trabajamos **sin programar**, generando la documentación del proyecto bloque a bloque. Después, en las **dos semanas de desarrollo intermodular**, construimos la aplicación a partir de esa documentación. Todo el proceso queda registrado en este repositorio.

## Hoja de ruta

| Bloque | Sesiones | Contenido | Entregable | Carpeta | Estado |
| --- | --- | --- | --- | --- | --- |
| 1. Presentación, equipos y anteproyecto | 1 | Formación de equipos y primera propuesta | Anteproyecto | [`01-anteproyecto`](01-anteproyecto/) | ✅ |
| 2. Definición | 2 y 3 | Idea, problema, usuarios, solución, casos de uso, justificación y objetivos | Documento de definición y casos de uso | [`02-definicion`](02-definicion/) | 🟡 |
| 3. Requisitos y MVP | 4 y 5 | Requisitos funcionales y no funcionales, priorización, MVP y roadmap | Documento de requisitos y MVP | [`03-requisitos-mvp`](03-requisitos-mvp/) | ⬜ |
| 4. Arquitectura | 6 y 7 | Arquitectura física/lógica e interna de la aplicación | Diagramas de arquitectura | [`04-arquitectura`](04-arquitectura/) | ⬜ |
| 5. Diseño | 8 y 9 | Modelo relacional, bocetos de interfaces y navegación | Modelo de datos y bocetos | [`05-diseno`](05-diseno/) | ⬜ |
| 6. Planificación y viabilidad | 10, 11 y 12 | Tareas, recursos, Gantt, costes, memoria económica y competencia | Planificación y estudio de viabilidad | [`06-planificacion-viabilidad`](06-planificacion-viabilidad/) | ⬜ |
| 7. Gestión del desarrollo | 13 y 14 | Seguimiento con Git, tablero de tareas, revisión global y reparto definitivo | Plan de desarrollo cerrado | [`07-gestion-desarrollo`](07-gestion-desarrollo/) | ⬜ |

> Leyenda: ⬜ pendiente · 🟡 en curso · ✅ terminado

## Trazabilidad

Durante la revisión global comprobaremos que todo el proyecto es coherente de principio a fin:

**casos de uso → objetivos → requisitos → diseño → tareas**

Para facilitarlo, cada elemento lleva un identificador y se cita desde los documentos posteriores:

| Elemento | Formato del ID | Dónde se define |
| --- | --- | --- |
| Caso de uso | `CU-nn` | [`02-definicion`](02-definicion/) |
| Regla de negocio | _[formato por unificar]_ | [`02-definicion`](02-definicion/) |
| Requisito funcional | `RF-nn` | [`03-requisitos-mvp`](03-requisitos-mvp/) |
| Requisito no funcional | `RNF-nn` | [`03-requisitos-mvp`](03-requisitos-mvp/) |

## Calendario

| Hito | Fecha |
| --- | --- |
| Tiempo lectivo del módulo | 15 horas |
| Desarrollo intermodular | Del 27 de enero al 9 de febrero de 2027 |
| Defensas (antes de las FEM) | Semana del 22 de febrero de 2027 |

### Defensa

El proyecto se defiende ante un tribunal formado por parte del equipo docente. Hay que **enseñar la aplicación en ejecución** y habrá un debate con el tribunal. La nota final la pone el profesor del módulo de proyecto.

## Convenciones

- Se guardan los archivos **originales y editables** (`.docx`, `.xlsx`, `.drawio`...), no solo PDF o imágenes.
- Nombre de los documentos: `CineGest - <Nombre del documento>.<extensión>`.
- Formato de los documentos escritos: Aptos 11 pt, interlineado 1,5, títulos con los estilos Título 1, 2 y 3, fondo blanco e índice automático.
- Cada carpeta de bloque tiene un `README` con el mismo esquema: propósito, documentos, estado y pendientes. Se actualiza al subir o cambiar un documento.
- El jefe de proyecto realiza una única entrega en Moodle en nombre de todo el equipo.
