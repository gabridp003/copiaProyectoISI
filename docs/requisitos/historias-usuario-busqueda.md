# Historias de usuario de búsqueda

| Campo | Valor |
| --- | --- |
| Proyecto | Proyecto Simbiosis |
| Fecha | [dd/mm/aaaa] |
| Versión | [Versión de trabajo] |
| Estado | Borrador |

## Fuentes comunes

- [Acta de UC-21 Buscar recetas](../captura/acta-acuerdos-uc-21-buscar-recetas.md), v1.1, Vigente.
- [Catálogo de requisitos](catalogo-requisitos.md), UR-08 y FR pertinentes.
- [Modelo de casos de uso](../modelos/modelo-casos-de-uso.md), UC-21.

## Épica de búsqueda

Como cliente de una aplicación de consulta de recetas saludables, quiero buscar recetas escribiendo una palabra o frase, además de también poder buscar incluyendo en la búsqueda un ingrediente o exluyéndolo, para poder guardarla en mi sección de favoritos y compartir mi experiencia.

Como [rol], quiero [capacidad amplia], para [beneficio].

**Estado:** descompuesta en US-01, US-02 y US-03. Conserva la necesidad conjunta.

## Justificación de la división

[Divido la épica en historias para poder enfocarme en cada uno de los detalles que debe cumplir la aplicación.]

## US-01

**Título:** [Buscar receta utilizándo una palabra o frase]

Como cliente de una aplicación de consulta de recetas saludables, quiero encontrar la receta con una palabra o frase que la identifique, para encontrar la receta de forma rápida.



Como [rol], quiero [capacidad], para [beneficio].

**Fuentes:** UR-08; UC-21; [FR principal]; acta, [apartado pertinente].

### Criterios de aceptación

- **CA-01.** Dado [que se permite la búsqueda de recetas mediante una palabra o frase], cuando [el cliente introduce una palabra o frase que no está incluída en el título o descripción ], entonces [el sistema notificará al usuario de que no hay resultados para la búsqueda].
- **CA-02.** Dado [que la búsqueda búsqueda contiene una palabra], cuando [el cliente realice la búsqueda], entonces [le aparecerán las recetas cuyo en título o descripción aparezca dicha palabra].
- **CA-03.** Dado [que la búsqueda contiene una frase], cuando [el cliente realice la búsqueda], entonces [aparecerán recetas cuyo título o descripción contienen la frase en el mismo orden].

## US-02

**Título:** [Buscar receta utilizando como filtro un ingrediente]

Como cliente de una aplicación de consulta de recetas saludables, quiero encontrar recetas utilizando como filtro un ingrediente, para encontrar recetas que utilicen dicho ingrediente.

Como [rol], quiero [capacidad], para [beneficio].

**Fuentes:** UR-08; UC-21; [FR principal]; acta, [apartado pertinente].

### Criterios de aceptación

- **CA-01.** Dado [que la búsqueda contiene ingredientes a exluír e incluír], cuando [el cliente quiera incluír y excluír el mismo ingrediente], entonces [el sistema informa de que no puede incluír y excluír un ingrediente al mismo tiempo].
- **CA-02.** Dado [que la búsqueda contiene varios ingrdientes], cuando [el cliente quiera modificar su búsqueda], entonces [el sistema le permitirá tanto incluír como retirar ingrdientes].
- **CA-03.** Dado [que la búsqueda contiene varios ingredientes a incluír], cuando [el cliente ejecute la búsqueda], entonces [el sistema solo informará de recetas que contengan todos los ingredientes seleccionados].

## US-03

**Título:** [Buscar receta utilizando como filtro la exlusión de un ingrediente]

Como cliente de una aplicación de consulta de recetas saludables, quiero encontrar recetas utilizando como filtro la exlusión de un ingrediente, para encontrar recetas que no tengan dicho ingrediente.

Como [rol], quiero [capacidad], para [beneficio].

**Fuentes:** UR-08; UC-21; [FR principal]; acta, [apartado pertinente].

### Criterios de aceptación

- **CA-01.** Dado [que la búsqueda contiene ingredientes a exluír e incluír], cuando [el cliente quiera incluír y excluír el mismo ingrediente], entonces [el sistema informa de que no puede incluír y excluír un ingrediente al mismo tiempo].
- **CA-02.** Dado [que la búsqueda contiene un ingrediente a excluír], cuando [el cliente ejecute la búsqueda], entonces [el sistema mostrará solo los resultados donde no aparezca dicho ingrediente].
- **CA-03.** Dado [que la búsqueda contiene un ingrediente a exluír repetido], cuando [el cliente ejecute la búsqueda], entonces [el sistema lo convertirá en solo un ingrediente].

## Revisión INVEST

La revisión abarca US-01, US-02 y US-03. «Aplicado» indica si se ha realizado la comprobación. «Cumple» indica si todas las historias cumplen el criterio. Si alguna no lo cumple, indicar «No» e identificar la historia y el motivo en la justificación. Si no se ha realizado la comprobación o faltan datos, indicar «Pendiente» en «Cumple».

| Criterio | Pregunta de revisión | Aplicado | Cumple | Justificación |
| --- | --- | --- | --- | --- |
| Independiente | ¿Puede implementarse cada historia y ofrecer un resultado útil sin implementar antes las otras historias del conjunto? Puede compartir infraestructura con ellas. | [Sí/No] | [Sí/No/Pendiente] | [Historias y motivo] |
| Negociable | ¿Cada historia explica qué necesita la persona y deja margen para discutir los detalles de la solución, respetando los acuerdos confirmados? | [Sí/No] | [Sí/No/Pendiente] | [Historias y motivo] |
| Valiosa | ¿La parte «para…» de cada historia explica el beneficio que obtiene la persona al usar esa capacidad? | [Sí/No] | [Sí/No/Pendiente] | [Historias y motivo] |
| Estimable | ¿Están claros el alcance y los datos necesarios para estimar el trabajo de cada historia? | [Sí/No] | [Sí/No/Pendiente] | [Historias y motivo] |
| Pequeña | ¿Se centra cada historia en una única capacidad de alcance manejable? | [Sí/No] | [Sí/No/Pendiente] | [Historias y motivo] |
| Comprobable | ¿Los criterios de aceptación de cada historia describen acciones y resultados observables que permiten distinguir un comportamiento correcto de uno incorrecto? | [Sí/No] | [Sí/No/Pendiente] | [Historias y motivo] |

## Dudas pendientes

[Cuestiones pendientes de aclaración. Si no quedan cuestiones, indicar «Ninguna».]
