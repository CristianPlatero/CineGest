# 🎬 CineGest

> Aplicación para gestionar un cine desde un único sistema: películas, salas, sesiones, entradas y clientes.

**Proyecto Intermodular · 2º DAW · Curso 2026-27**
**Ciclo formativo:** Técnico Superior en Desarrollo de Aplicaciones Web (DAW)
**Centro:** IES Miguel Herrero · Torrelavega

---

## 📋 Índice

1. [Sobre el proyecto](#-sobre-el-proyecto)
2. [Equipo](#-equipo)
3. [Funcionalidades](#-funcionalidades)
4. [Casos de uso](#-casos-de-uso)
5. [Hoja de ruta](#-hoja-de-ruta)
6. [Calendario](#-calendario)
7. [Estructura del repositorio](#-estructura-del-repositorio)
8. [Tecnologías](#-tecnologías)
9. [Instalación y puesta en marcha](#-instalación-y-puesta-en-marcha)
10. [Normas de trabajo con Git](#-normas-de-trabajo-con-git)
11. [Estado actual](#-estado-actual)

---

## 📖 Sobre el proyecto

CineGest es una aplicación destinada a facilitar la gestión de un cine, centralizando en un único sistema la información relacionada con las películas, las salas, las sesiones y las entradas.

### ¿Qué problema resuelve?

Evita errores de organización y reduce el trabajo manual del personal del cine, y facilita tanto la administración como la consulta y compra de entradas por parte de los clientes.

### Origen de la idea

La idea surge de la necesidad de disponer de una herramienta sencilla que permita gestionar de forma rápida y organizada todos los aspectos de un cine.

### Cómo trabajamos

El módulo se desarrolla de forma incremental: durante las sesiones de clase trabajamos **sin programar**, generando la documentación del proyecto bloque a bloque (definición, requisitos, arquitectura, diseño, planificación y viabilidad). Después, en las **dos semanas de desarrollo intermodular**, construimos la aplicación a partir de esa documentación. Todo el proceso queda registrado en este repositorio.

---

## 👥 Equipo

| Rol | Nombre | Contacto / usuario Git |
| --- | --- | --- |
| **Jefe de equipo** | _[Nombre del jefe de equipo]_ | _[@usuario]_ |
| Miembro | Cristian Platero Zayago | [@CristianPlatero](https://github.com/CristianPlatero) |
| Miembro | Rubén Fernández Carpintero | [@RFCDAW1](https://github.com/RFCDAW1) |
| Miembro | Ossel Santamaría Bustelo | [@Ossel18](https://github.com/Ossel18) |
| Miembro | Joaquin López Pérez | [@joaquinlopezperez](https://github.com/joaquinlopezperez) |
| Miembro | Timur Asecov | [@tiimurr](https://github.com/tiimurr) |

**Tutor del proyecto:** Alejandro López Camus

**Cliente (rol asumido por):** Ossel Santamaría Bustelo (simulacro de entrevista)

> El anteproyecto de CineGest fue presentado por Ossel Santamaría Bustelo y elegido por el equipo.

---

## ✨ Funcionalidades

Funcionalidades previstas según el anteproyecto (el alcance definitivo se cerrará al definir el MVP):

| Módulo | Descripción |
| --- | --- |
| **Gestión de películas** | Añadir, consultar, modificar y eliminar películas, con título, duración, género, clasificación por edades, descripción y estado. |
| **Gestión de salas** | Registrar las salas disponibles y el número de asientos de cada una. |
| **Gestión de sesiones** | Crear, modificar y cancelar horarios de proyección y asignarlos a una película y una sala. |
| **Gestión de entradas** | Consultar la disponibilidad de asientos y registrar la venta o reserva de entradas. |
| **Gestión de clientes** | Almacenar los datos básicos de los usuarios y consultar sus reservas. |
| **Panel de administración** | Permitir al personal del cine controlar películas, salas, sesiones y ventas desde una interfaz sencilla. |
| **Consultas** | Mostrar la cartelera, los horarios disponibles y la ocupación de las salas. |

### Alcance acordado con el cliente

- La primera versión está pensada para **un cine con varias salas**.
- El pago de la primera versión se plantea **mediante tarjeta**.
- Dos tipos de actor: **usuario (cliente)** y **personal autorizado**.

### MVP

_[Rellenar tras los bloques de Requisitos y MVP: qué entra en la primera versión y qué queda para versiones posteriores.]_

---

## 🎯 Casos de uso

Los casos de uso se han obtenido de un **simulacro de entrevista con el cliente** (30 preguntas, con Ossel en el papel de cliente). El documento completo, con la entrevista, las reglas y la descripción detallada de cada caso, está en [`Documents/CineGest - Casos de uso.docx`](Documents/CineGest%20-%20Casos%20de%20uso.docx).

### Actores

| Actor | Descripción |
| --- | --- |
| **Usuario (cliente)** | Consulta películas y sesiones y puede reservar o comprar entradas. |
| **Personal autorizado** | Personal del cine. Inicia sesión, accede al panel de administración y gestiona películas, salas, sesiones, entradas, clientes y consultas. |

### Resumen (21 casos de uso)

| ID | Caso de uso | Actor |
| --- | --- | --- |
| **Acceso al sistema** | | |
| CU-01 | Registrarse | Usuario |
| CU-02 | Iniciar sesión | Usuario / Personal |
| **Casos de uso del usuario** | | |
| CU-03 | Consultar cartelera | Usuario / Personal |
| CU-04 | Consultar horarios y sesiones disponibles | Usuario / Personal |
| CU-05 | Consultar disponibilidad de asientos | Usuario / Personal |
| CU-06 | Comprar entrada | Usuario |
| CU-07 | Reservar entrada | Usuario |
| **Casos de uso del personal autorizado** | | |
| CU-08 | Añadir película | Personal |
| CU-09 | Consultar películas | Personal |
| CU-10 | Modificar película | Personal |
| CU-11 | Eliminar película | Personal |
| CU-12 | Gestionar salas | Personal |
| CU-13 | Crear sesión | Personal |
| CU-14 | Consultar sesiones | Personal |
| CU-15 | Modificar sesión | Personal |
| CU-16 | Cancelar sesión | Personal |
| CU-17 | Cancelar entrada vendida | Personal |
| CU-18 | Consultar reservas activas de un cliente | Personal |
| CU-19 | Consultar datos de clientes | Personal |
| CU-20 | Consultar ocupación de las salas | Personal |
| CU-21 | Consultar ventas y datos de gestión | Personal |

### Reglas de negocio
 
Políticas y restricciones del cine que el sistema debe respetar, extraídas de los casos de uso. No incluyen comportamientos del sistema (validar datos, mostrar mensajes de error), que se recogerán como requisitos, ni decisiones de alcance.
 
| ID | Regla | Casos de uso |
| --- | --- | --- |
| RN&#8209;01 | Un asiento de una sesión solo puede estar vendido o reservado por una persona a la vez. | CU-05, CU-06, CU-07 |
| RN&#8209;02 | Una **venta** es una entrada pagada y confirmada. Una **reserva** guarda un asiento temporalmente sin pago y tiene fecha límite para confirmarse. | CU-06, CU-07 |
| RN&#8209;03 | Una reserva dura como máximo 24 horas. Si faltan menos de 24 horas para la sesión, es válida hasta 2 horas antes de que empiece. Si vence sin pago, se cancela y los asientos se liberan. | CU-07 |
| RN&#8209;04 | Cada compra o reserva admite un máximo de 10 entradas. | CU-06, CU-07 |
| RN&#8209;05 | No se pueden comprar ni reservar entradas de una sesión que ya ha comenzado o que está cancelada. | CU-04, CU-06, CU-07 |
| RN&#8209;06 | Cada sesión tiene un precio, y las entradas se venden al precio de su sesión. | CU-06, CU-13 |
| RN&#8209;07 | Una película aparece en cartelera solo si tiene al menos una sesión activa o programada. | CU-03, CU-08 |
| RN&#8209;08 | Una sala no puede tener dos sesiones que coincidan en horario. | CU-13, CU-15 |
| RN&#8209;09 | No se puede eliminar una película ni una sala que tenga sesiones activas o programadas; primero hay que cancelarlas o reasignarlas. | CU-11, CU-12 |
| RN&#8209;10 | Una película con histórico (sesiones pasadas o entradas vendidas) no se elimina, se marca como inactiva. | CU-11 |
| RN&#8209;11 | Las sesiones no se eliminan, se cancelan. Al cancelar una sesión se devuelven las entradas vendidas, se liberan las reservas y se avisa a los clientes por correo. | CU-16 |
| RN&#8209;12 | Si se cambia la fecha, hora, sala o película de una sesión con entradas vendidas o reservadas, el personal debe confirmarlo y se avisa a los clientes por correo. | CU-15 |
| RN&#8209;13 | Los clientes no pueden cancelar una entrada vendida. Solo el personal autorizado puede hacerlo, y únicamente hasta el inicio de la sesión. | CU-17 |
| RN&#8209;14 | Solo el personal autorizado puede gestionar películas, salas y sesiones, consultar ventas y datos de clientes, y cancelar entradas vendidas. | CU-08 a CU-21 |
| RN&#8209;15 | Para comprar o reservar hay que estar registrado y haber iniciado sesión. Consultar cartelera, horarios y asientos no lo requiere. | CU-01, CU-02, CU-03 a CU-07 |
| RN&#8209;16 | Un correo electrónico solo puede estar asociado a una cuenta. | CU-01 |
| RN&#8209;17 | La contraseña de un usuario no se muestra nunca, ni siquiera al personal autorizado. | CU-19 |
 
---
## 🗺️ Hoja de ruta

El módulo se divide en 7 bloques, y cada uno termina con un entregable. Marcamos cada bloque cuando está terminado y subido al repositorio.

| Bloque | Sesiones | Contenido | Entregable | Estado |
| --- | --- | --- | --- | --- |
| 1. Presentación, equipos y anteproyecto | 1 | Formación de equipos y primera propuesta de proyecto | Anteproyecto | 🟡 |
| 2. Definición | 2 y 3 | Idea, problema, usuarios, solución, casos de uso, justificación y objetivos | Documento de definición y casos de uso | 🟡 |
| 3. Requisitos y MVP | 4 y 5 | Requisitos funcionales y no funcionales, priorización, MVP y roadmap | Documento de requisitos y MVP | ⬜ |
| 4. Arquitectura | 6 y 7 | Arquitectura física/lógica y arquitectura interna de la aplicación | Diagramas de arquitectura | ⬜ |
| 5. Diseño | 8 y 9 | Modelo relacional, bocetos de interfaces y navegación | Modelo de datos y bocetos | ⬜ |
| 6. Planificación y viabilidad | 10, 11 y 12 | Tareas, recursos, Gantt, costes, memoria económica y competencia | Planificación y estudio de viabilidad | ⬜ |
| 7. Gestión del desarrollo | 13 y 14 | Seguimiento con Git, tablero de tareas, revisión global y reparto definitivo | Plan de desarrollo cerrado | ⬜ |

> Leyenda: ⬜ pendiente · 🟡 en curso · ✅ terminado

### Fase de documentación (sesiones de clase)

- [x] Anteproyecto
- [x] Casos de uso (entrevista con el cliente)
- [ ] Definición del proyecto (problema, usuarios, solución, justificación y objetivos)
- [ ] Requisitos, MVP y roadmap
- [ ] Arquitectura
- [ ] Diseño de datos e interfaces
- [ ] Planificación (tareas, recursos, Gantt y costes)
- [ ] Viabilidad y entorno del proyecto
- [ ] Preparación del seguimiento con Git
- [ ] Revisión global de trazabilidad

### Fase de desarrollo (dos semanas de desarrollo intermodular)

- [ ] Preparación del entorno
- [ ] Base de datos
- [ ] Backend
- [ ] Frontend
- [ ] Panel de administración
- [ ] Integración y pruebas
- [ ] Revisión por pares y corrección de incidencias
- [ ] Preparación de la defensa

### Trazabilidad

Durante la revisión global comprobaremos que todo el proyecto es coherente de principio a fin:

**casos de uso → objetivos → requisitos → diseño → tareas**

Para facilitarlo, cada caso de uso lleva su ID (CU-01 a CU-21) y cada regla el suyo (RG-01 a RG-11), y se citarán desde los requisitos y el diseño.

---

## 📅 Calendario

| Hito | Fecha |
| --- | --- |
| Tiempo lectivo del módulo | 15 horas |
| Desarrollo intermodular | Del 27 de enero al 9 de febrero de 2027 |
| Defensas (antes de las FEM) | Semana del 22 de febrero de 2027 |

### Defensa

El proyecto se defiende ante un tribunal formado por parte del equipo docente. Hay que **enseñar la aplicación en ejecución** y habrá un debate con el tribunal. La nota final la pone el profesor del módulo de proyecto.

---

## 📁 Estructura del repositorio

```text
CineGest/
├── README.md
├── Documents/
│   └── CineGest - Casos de uso.docx
└── src/                  ← código de la aplicación (fase de desarrollo, aún no creado)
```

En `Documents/` guardamos **los archivos originales y editables** (`.docx`, `.odt`, `.xlsx`, `.drawio`, `.excalidraw`...), no solo las exportaciones en imagen o PDF, para poder seguir trabajando sobre ellos en cualquier momento.

### Documentos principales

| Documento | Ubicación | Estado |
| --- | --- | --- |
| Anteproyecto | _[pendiente de subir]_ | 🟡 |
| Casos de uso | [`Documents/CineGest - Casos de uso.docx`](Documents/CineGest%20-%20Casos%20de%20uso.docx) | ✅ |
| Definición del proyecto | _[pendiente]_ | ⬜ |
| Requisitos y MVP | _[pendiente]_ | ⬜ |
| Arquitectura | _[pendiente]_ | ⬜ |
| Diseño (datos e interfaces) | _[pendiente]_ | ⬜ |
| Planificación y viabilidad | _[pendiente]_ | ⬜ |
| Gestión del desarrollo | _[pendiente]_ | ⬜ |

---

## 🛠️ Tecnologías

_[Rellenar cuando el equipo las decida durante los bloques de arquitectura y diseño.]_

| Capa | Tecnología |
| --- | --- |
| Frontend | _[HTML, CSS, JavaScript / Angular / React...]_ |
| Backend | _[PHP / Java Spring / Node.js...]_ |
| Base de datos | _[MySQL / PostgreSQL...]_ |
| Control de versiones | Git (GitHub) |
| Gestión de tareas | _[Tablero de tareas utilizado]_ |
| Diagramas | _[draw.io / Excalidraw...]_ |
| Planificación | _[Excel / GanttProject...]_ |

---

## 🚀 Instalación y puesta en marcha

> Esta sección se completará durante la fase de desarrollo.

```bash
# 1. Clonar el repositorio
git clone https://github.com/CristianPlatero/CineGest.git
cd CineGest

# 2. Instalar dependencias
# [comando]

# 3. Configurar la base de datos
# [comando / script]

# 4. Arrancar la aplicación
# [comando]
```

---

## 🔀 Normas de trabajo con Git

Usamos el repositorio para dejar constancia de cómo evoluciona el proyecto, no solo para entregar el resultado final.

- Un único repositorio para todo el equipo, con todos los miembros y el tutor como colaboradores.
- Al llegar la fase de desarrollo, se añade también al resto de profesores implicados.
- Commits **pequeños, frecuentes y concretos**, repartidos a lo largo del proyecto.
- Mensajes que expliquen qué se ha hecho, asociados a tareas cuando sea posible.
- Participación visible de todos los miembros en el historial.

**Ejemplos de mensajes que seguimos:**

```text
Añadidos casos de uso de gestión de usuarios
Actualizado diagrama de base de datos
Añadida planificación inicial del proyecto
Corregidas fechas del diagrama de Gantt
Añadido formulario de registro
```

**Mensajes que evitamos:** `cambios`, `cosas`, `actualizado`, `final`.

---

## 📌 Estado actual

**Fase en curso:** Fase de documentación
**Bloque actual:** Bloque 2: Definición
**Última actualización:** 03/10/2026

Hemos redactado los **21 casos de uso** a partir del simulacro de entrevista con el cliente, con sus 2 actores y 11 reglas de negocio. Lo siguiente es completar el documento de definición (problema, usuarios, solución, justificación y objetivos), subir el anteproyecto al repositorio y enlazar cada objetivo con sus casos de uso.

---

## 📄 Licencia y uso

Proyecto con fines académicos realizado en el marco del ciclo formativo de Desarrollo de Aplicaciones Web en el IES Miguel Herrero.

© 2026-27 · Cristian Platero Zayago, Rubén Fernández Carpintero, Ossel Santamaría Bustelo, Joaquin López Pérez y Timur Asecov
