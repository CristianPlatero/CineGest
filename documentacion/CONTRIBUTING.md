# Normas de trabajo con Git

Usamos el repositorio para dejar constancia de cómo evoluciona el proyecto, no solo para entregar el resultado final.

[← Volver al README principal](README.md)

## Principios

- Un único repositorio para todo el equipo, con todos los miembros y el tutor como colaboradores.
- Al llegar la fase de desarrollo se añade también al resto de profesores implicados.
- Commits **pequeños, frecuentes y concretos**, repartidos a lo largo del proyecto.
- Mensajes que expliquen qué se ha hecho, asociados a tareas cuando sea posible.
- Participación visible de todos los miembros en el historial.

## Mensajes de commit

Mensajes que seguimos:

```text
Añadidos casos de uso de gestión de usuarios
Actualizado diagrama de base de datos
Añadida planificación inicial del proyecto
Corregidas fechas del diagrama de Gantt
Añadido formulario de registro
```

Mensajes que evitamos: `cambios`, `cosas`, `actualizado`, `final`.

## Antes de subir cambios

1. Actualiza tu copia local (`git pull`) para no pisar el trabajo de otros.
2. Revisa qué vas a subir (`git status`, `git diff`): sin archivos temporales ni copias duplicadas.
3. Haz un commit por cada cambio con sentido propio, no uno por día.
4. Sube los cambios (`git push`).

## Documentos

- En `documentacion/` guardamos los **archivos originales y editables** (`.docx`, `.odt`, `.xlsx`, `.drawio`, `.excalidraw`...), no solo exportaciones en imagen o PDF.
- Cada documento va en la carpeta de su bloque y se registra en el `README` de esa carpeta.
- Si dos personas necesitan editar el mismo documento, se avisa antes por el canal del equipo.

## Ramas (propuesta, a acordar en el bloque 7)

<!-- Rellenar cuando el equipo decida el flujo de ramas. Si se trabaja solo sobre main, borrar esta sección. -->

_[Flujo de ramas acordado: por ejemplo `main` estable y una rama por tarea con el formato `tipo/descripcion-corta`.]_
