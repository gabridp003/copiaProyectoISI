# AGENTS.md — Proyecto Simbiosis

## Propósito

Este repositorio contiene la documentación de **Proyecto Simbiosis**.

Los documentos propios del proyecto se mantienen en Markdown y se versionan mediante Git. Antes de realizar cambios, consulta `README.md` y el `README.md` de la carpeta afectada, si existe.

## Fuentes de verdad

- Los documentos propios del proyecto que se encuentran en `docs/` son las fuentes editables.
- `docs/requisitos/catalogo-requisitos.md` contiene la redacción canónica de los requisitos UR, FR y NFR.
- `docs/requisitos/srs.md` y `docs/requisitos/catalogo-requisitos.md` forman conjuntamente la especificación de requisitos.
- `docs/referencias/` contiene documentos externos o recibidos. No deben modificarse como si fueran documentos propios.
- `releases/` contiene copias estables exportadas. No es una fuente editable.
- Las líneas base se identifican mediante una etiqueta de Git y su entrada correspondiente en `CHANGELOG.md`.

Si dos documentos parecen contradecirse, identifica primero cuál es la fuente canónica y expón la discrepancia antes de modificar el contenido.

## Estructura principal

- `docs/vision/`: visión y alcance del proyecto.
- `docs/captura/`: actas de captura y aclaración.
- `docs/requisitos/`: SRS y catálogo de requisitos.
- `docs/calidad/`: criterios de revisión.
- `docs/decisiones/`: registro de decisiones.
- `docs/cambios/`: solicitudes de cambio.
- `docs/modelos/`: modelos y diagramas.
- `docs/referencias/`: documentos externos o recibidos.
- `releases/`: exportaciones de líneas base.
- `CHANGELOG.md`: historial de líneas base.

Consulta únicamente los documentos relacionados con la tarea. No es necesario leer todo el repositorio para realizar un cambio localizado.

## Convenciones documentales

- Redacta en español claro, preciso y coherente con el documento afectado.
- Mantén los documentos en Markdown y con codificación UTF-8.
- Para archivos nuevos, utiliza nombres en minúsculas, sin números de versión y preferentemente separados mediante guiones.
- Conserva los nombres y rutas ya establecidos. No renombres archivos existentes únicamente para uniformar su estilo.
- No incluyas números de versión en los nombres de archivo.
- Utiliza enlaces relativos entre documentos del repositorio.
- Conserva la estructura y el nivel de detalle del documento que estés modificando.
- No inventes fechas, fuentes, decisiones, aprobaciones ni información que no esté documentada.
- Si falta información, conserva el punto abierto o solicita aclaración.
- No incluyas datos personales, credenciales, secretos ni información privada.

## Requisitos y trazabilidad

- Los identificadores UR, FR y NFR son estables.
- No reutilices un identificador eliminado para otro requisito.
- No cambies identificadores sin revisar previamente todas sus referencias.
- El catálogo es la fuente canónica para la redacción atómica de los requisitos.
- La SRS aporta el contexto, alcance, interfaces, atributos de calidad, glosario, modelos y trazabilidad.
- La SRS y el catálogo deben corresponder a la misma línea base.
- Conserva la trazabilidad entre visión, actas, decisiones, requisitos, solicitudes de cambio y modelos.
- Cuando cambie un requisito, revisa sus relaciones y apariciones en otros documentos.
- Distingue entre una corrección editorial y un cambio en el significado del requisito.
- No resuelvas ambigüedades mediante suposiciones.
- Las solicitudes de cambio aprobadas deben reflejarse en los documentos afectados y en `docs/cambios/registro-solicitudes-cambio.md`.

## Forma de trabajo

Antes de modificar archivos:

1. Comprueba el estado de Git.
2. Lee el documento afectado y sus referencias directas.
3. Identifica la fuente canónica del contenido.
4. Determina qué otros documentos pueden depender del cambio.
5. Conserva cualquier modificación previa que no pertenezca a la tarea.

Durante la modificación:

- Limita los cambios al alcance solicitado.
- No reformatees un documento completo por una corrección localizada.
- No hagas reemplazos globales sin revisar las coincidencias en contexto.
- Evita duplicar información que ya tenga una fuente canónica; enlázala cuando sea posible.
- Mantén válidos los enlaces, rutas e identificadores.
- Respeta los cambios existentes que no formen parte de la tarea.
- Si una modificación exige una decisión no documentada, detente y solicita aclaración.

## Git y líneas base

- No realices commits, pushes, etiquetas ni reescrituras del historial salvo que se solicite expresamente.
- No actualices `CHANGELOG.md` por cada cambio ordinario.
- Actualiza `CHANGELOG.md` cuando se prepare o declare una nueva línea base.
- No declares una línea base sin comprobar conjuntamente su contenido, etiqueta y entrada en `CHANGELOG.md`.
- No añadas archivos a `releases/` salvo que se esté preparando una publicación estable.
- Mantén cada cambio acotado y fácil de revisar.

## Verificación

Antes de considerar terminada una tarea:

- Revisa el diff completo.
- Ejecuta `git diff --check`.
- Comprueba que los enlaces relativos y las rutas modificadas siguen siendo válidos.
- Busca las referencias a identificadores, nombres o términos que hayan cambiado.
- Comprueba la coherencia entre la SRS y el catálogo cuando alguno de ellos resulte afectado.
- Verifica que no se haya duplicado información canónica innecesariamente.
- Si existen comprobaciones automáticas aplicables, ejecútalas.
- Explica qué se ha modificado, qué se ha comprobado y qué queda pendiente.

Una tarea está terminada cuando el cambio solicitado está aplicado en la fuente adecuada, las dependencias relevantes han sido revisadas y el resultado puede entenderse y versionarse sin información externa no identificada.
