# Bloque 2 · Definición y casos de uso

Define qué es CineGest, a quién va dirigido y qué debe hacer. Incluye el documento del proyecto, la entrevista con el cliente y los casos de uso.

[← Volver a la documentación](../README.md)

| | |
| --- | --- |
| **Estado** | 🟡 en curso |
| **Responsable** | _[@usuario]_ |
| **Última actualización** | 01/11/2026 |

## Documentos

| Documento | Archivo | Estado |
| --- | --- | --- |
| Documento del proyecto | [`CineGest - Documento del proyecto.docx`](CineGest%20-%20Documento%20del%20proyecto.docx) | 🟡 borrador |
| Casos de uso (incluye la primera entrevista y las reglas) | [`CineGest - Casos de uso.docx`](CineGest%20-%20Casos%20de%20uso.docx) | 🟡 en revisión |
| Segunda entrevista con el cliente (P31-P50) | [`CineGest - Segunda entrevista.docx`](CineGest%20-%20Segunda%20entrevista.docx) | 🟡 borrador |

Los casos de uso se han obtenido de un **simulacro de entrevista con el cliente** (30 preguntas, con Ossel en el papel de cliente). La segunda entrevista recoge los datos que los casos de uso incorporan y que no aparecían en la primera.

## Documento del proyecto

| Apartado | Estado |
| --- | --- |
| Portada (faltan curso, jefe de proyecto y fecha) | 🟡 |
| Índice automático | 🟡 |
| Resumen y palabras clave | 🟡 |
| Introducción (origen, contexto, problema y solución) | 🟡 |
| Glosario (opcional) | 🟡 |
| Objetivo general | 🟡 |
| Objetivos específicos | 🟡 |

## Actores

| Actor | Descripción |
| --- | --- |
| **Usuario (cliente)** | Consulta películas y sesiones y puede reservar o comprar entradas. |
| **Personal autorizado** | Personal del cine. Inicia sesión, accede al panel de administración y gestiona películas, salas, sesiones, entradas, clientes y consultas. |

## Casos de uso

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

## Reglas de negocio

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

## Objetivos específicos y casos de uso

Propuesta de agrupación de los casos de uso en objetivos específicos (principio de responsabilidad única). Los dos últimos son objetivos transversales.

| N.º | Objetivo específico | Casos de uso |
| --- | --- | --- |
| 1 | Gestionar el acceso de los usuarios al sistema | CU-01, CU-02 |
| 2 | Gestionar las películas | CU-08, CU-09, CU-10, CU-11 |
| 3 | Gestionar las salas | CU-12 |
| 4 | Gestionar las sesiones | CU-13, CU-14, CU-15, CU-16 |
| 5 | Permitir la consulta de la cartelera, los horarios y la disponibilidad de asientos | CU-03, CU-04, CU-05 |
| 6 | Gestionar la venta y la reserva de entradas | CU-06, CU-07, CU-17, CU-18 |
| 7 | Gestionar los datos de clientes y del personal | CU-19, CU-22 |
| 8 | Ofrecer al personal autorizado información de ocupación y ventas | CU-20, CU-21 |
| 9 | Gestionar la autorización de los usuarios según sus roles (transversal) | CU-02 y todos los del personal |
| 10 | Validar los datos y gestionar el resultado de las operaciones (transversal) | Todos |

## Pendiente de corregir

> [!WARNING]
> Puntos detectados al revisar los casos de uso. Hay que resolverlos antes de dar el bloque por terminado.

- [ ] Hay dos casos de uso numerados como CU-22 (Gestionar personal y Gestionar clientes) y la tabla resumen llega solo a CU-21. «Gestionar clientes» se solapa con CU-19.
- [ ] Los identificadores de las reglas no coinciden: el documento de casos de uso usa RG-01 a RG-11 y la tabla de este README usa RN-01 a RN-17. Unificar el formato.
- [ ] RN-03 dice que una reserva dura como máximo 24 horas, pero CU-07 fija un máximo de 2 horas cuando faltan más de 24 horas para la sesión.
- [ ] Faltan actores en la tabla: el Administrador (gestiona las cuentas del personal) y el Sistema (cancela reservas vencidas y envía correos).
- [ ] Sin definir: los estados de película, sesión y entrada, y cómo se realiza la devolución del importe.
- [ ] Actualizar el campo «Origen» de los casos de uso con las preguntas P31-P50 de la segunda entrevista.
- [ ] Rellenar en la portada del documento del proyecto el curso, el jefe de proyecto y la fecha.
