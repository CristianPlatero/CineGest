# Bloque 4 · Arquitectura

En este bloque se describe la arquitectura de **CineGest**: los elementos que forman la aplicación, la forma en que se comunican y el entorno en el que se plantea su despliegue.

[← Volver a la documentación](../README.md)

| | |
| --- | --- |
| **Estado** | 🟡 en curso |
| **Responsable** | Equipo de CineGest |
| **Última actualización** | 03/11/2026 |

## 1. Descripción general

CineGest se plantea como una aplicación web para consultar la cartelera y gestionar la compra o reserva de entradas de un cine. También contempla un panel para que el personal autorizado gestione películas, salas, sesiones y entradas.

La arquitectura representada separa la interfaz web, la lógica de negocio y el almacenamiento de datos:

- **Aplicación web:** interfaz que utiliza el cliente y el personal del cine desde un navegador.
- **API REST:** recibe las peticiones de la aplicación web, valida los datos y aplica las reglas de negocio.
- **Base de datos:** almacena la información de usuarios, películas, salas, sesiones, asientos, ventas y reservas.
- **Servicios externos:** Stripe para los pagos y un servicio de correo para el envío de avisos.
- **Librería de películas:** almacena los datos y carteles de las películas.

Esta separación permite identificar las responsabilidades de cada parte y facilita su desarrollo y mantenimiento.

## 2. Documentos y diagramas

Se han elaborado los siguientes diagramas con diagrams.net (draw.io). Se incluyen tanto los archivos editables como sus exportaciones PNG.

| Diagrama | Archivo editable | Exportación |
| --- | --- | --- |
| Diagrama de contenedores (C4) | [CineGest_Diagrama_Contenedores.drawio](Diagrama_Contenedores/CineGest_Diagrama_Contenedores.drawio) | [Ver PNG](Diagrama_Contenedores/CineGest_Diagrama_Contenedores.drawio.png) |
| Diagrama de despliegue (C4) | [CineGest_Diagrama_Despliegue_C4.drawio](Diagrama_Despliegue/CineGest_Diagrama_Despliegue_C4.drawio) | [Ver PNG](Diagrama_Despliegue/CineGest_Diagrama_Despliegue_C4.drawio.png) |
| Diagrama dinámico: comprar entradas | [CineGest_Diagrama_Dinamico_ComprarEntradas.drawio](Diagrama_Dinamico/CineGest_Diagrama_Dinamico_ComprarEntradas.drawio) | [Ver PNG](Diagrama_Dinamico/CineGest_Diagrama_Dinamico_ComprarEntradas.drawio.png) |

### 2.1. Diagrama de contenedores

Representa los principales elementos que componen CineGest y sus relaciones:

- El cliente consulta la cartelera y compra o reserva entradas.
- El personal autorizado utiliza el panel de administración para gestionar el cine.
- La aplicación web se ejecuta en el navegador y se comunica con la API REST.
- La API REST aplica las reglas de negocio y consulta o modifica la base de datos.
- La API utiliza Stripe para gestionar los cobros y el servicio de correo para enviar avisos.
- La información y los carteles de las películas se obtienen de la librería correspondiente.

### 2.2. Diagrama de despliegue

Representa la distribución prevista de los componentes en el entorno de producción:

- Los usuarios acceden desde sus dispositivos mediante un navegador web.
- El servidor de aplicación aloja el servidor web y los componentes de la aplicación.
- El servidor de base de datos se plantea como un nodo separado, accesible desde el servidor de aplicación mediante una red privada.
- Stripe y el servicio de correo se representan como servicios externos.
- La comunicación con los usuarios se realiza mediante HTTPS. La comunicación con la base de datos se representa mediante SQL sobre TCP.

El diagrama muestra una propuesta de despliegue, no una infraestructura ya instalada. Los productos y tecnologías que aparecen como ejemplo deberán confirmarse antes de considerarlos definitivos.

### 2.3. Diagrama dinámico: comprar entradas

Representa el flujo principal del caso de uso **Comprar entradas**:

1. El cliente selecciona una sesión y los asientos e introduce los datos de pago.
2. La aplicación web envía los datos de la tarjeta a Stripe y obtiene un token de pago.
3. La aplicación web solicita la compra a la API REST, enviando la sesión, los asientos y el token.
4. La API comprueba que la sesión está programada y que los asientos siguen libres.
5. La API solicita el cobro a Stripe y recibe el resultado.
6. Si el pago se aprueba, la API registra las entradas como vendidas.
7. La API devuelve a la aplicación web la confirmación o el error.
8. La aplicación web muestra el resultado al cliente.

El diagrama representa el flujo satisfactorio y la respuesta ante un resultado de compra incorrecto. Los detalles de gestión de errores, concurrencia y posibles reembolsos podrán concretarse durante el diseño y la implementación.

## 3. Tecnologías representadas

La siguiente tabla recoge las tecnologías que aparecen en los diagramas. Se diferencia entre las que están identificadas en la propuesta y las que todavía deben concretarse.

| Capa o elemento | Tecnología | Estado / justificación |
| --- | --- | --- |
| Frontend | HTML, CSS y JavaScript | Representados en la aplicación web. Permiten construir la interfaz que se ejecuta en el navegador. |
| Arquitectura del frontend | Aplicación web / SPA | Se representa una aplicación web de una sola página para la zona de clientes y el panel de administración. |
| Backend | API REST | Interfaz de comunicación entre el frontend y la lógica de negocio. El lenguaje o framework concreto está pendiente de decisión. |
| Base de datos | MySQL | Tecnología representada en el diagrama de contenedores. Debe confirmarse como elección definitiva del equipo. |
| Pagos | Stripe | Servicio externo representado para gestionar cobros y devoluciones con tarjeta. |
| Correo electrónico | Servicio de correo | Servicio externo para enviar avisos a los clientes. El proveedor y el protocolo definitivo están pendientes de concretar. |
| Servidor web | Apache | Tecnología propuesta en el diagrama de despliegue; pendiente de confirmación. |
| Sistema de ficheros | Librería de películas | Almacenamiento de los datos y carteles de las películas. |
| Control de versiones | Git y GitHub | Permiten mantener el código y la documentación del proyecto. |
| Diagramas | diagrams.net (draw.io) | Herramienta utilizada para elaborar y exportar los diagramas. |

## 4. Decisiones y criterios de arquitectura

| Decisión o criterio | Motivo |
| --- | --- |
| Separar frontend y backend mediante una API REST | Permite mantener diferenciada la interfaz de usuario de la lógica de negocio. |
| Centralizar las reglas de negocio en la API | Evita que las validaciones importantes dependan únicamente del navegador. |
| Utilizar una base de datos relacional | La aplicación maneja información relacionada, como usuarios, películas, sesiones, asientos y ventas. |
| Integrar una pasarela de pago externa | Permite delegar el procesamiento del pago en un servicio especializado. |
| Separar el servidor de aplicación del servidor de base de datos en el despliegue propuesto | Facilita limitar el acceso a la base de datos y separar responsabilidades. |
| Utilizar un servicio externo de correo | Permite enviar comunicaciones a los clientes sin implementar un sistema propio de envío de correo. |

Estas decisiones describen los criterios reflejados en los diagramas. La selección definitiva de productos, lenguajes, frameworks y proveedores deberá acordarse por el equipo.

## 5. Aspectos pendientes de concretar

- [ ] Confirmar el lenguaje o framework que se utilizará para implementar la API REST.
- [ ] Confirmar MySQL como sistema gestor de base de datos.
- [ ] Confirmar Apache y el entorno de alojamiento para el despliegue.
- [ ] Elegir el proveedor del servicio de correo.
- [ ] Concretar cómo se almacenarán y gestionarán los carteles de las películas.
- [ ] Revisar que los diagramas se mantienen actualizados cuando cambien las decisiones del proyecto.

---

Los diagramas editables y sus exportaciones se mantienen dentro de sus respectivas carpetas para facilitar su revisión y actualización por parte del equipo.
- [ ] Elegir las tecnologías y rellenar la tabla.
- [ ] Dibujar los diagramas y subir los archivos editables.
- [ ] Copiar la tabla de tecnologías al `README` de [`src/`](../../src/).
