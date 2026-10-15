# Proyecto Simbiosis Plan de iteración E2

| Versión | Fecha | Estado |
| --- | --- | --- |
| 1.3 | 06/10/2026 | Borrador |

Este plan define el trabajo previsto para E2, la segunda iteración de Elaboración. Selecciona las funciones de salud y recetas que se estudiarán. También establece las actividades, los recursos, los productos y los criterios de evaluación.

El plan pertenece a un proyecto simulado. La duración, el equipo, el esfuerzo y el coste son supuestos de la simulación. Los requisitos proceden de los documentos del proyecto. El plan no presenta como realizados los trabajos previstos en E1.

## 1 Punto de partida

| Dato | Valor |
| --- | --- |
| Proyecto | Proyecto Simbiosis |
| Iteración | E2 |
| Fase | Elaboración |
| Duración simulada | Dos semanas de trabajo, con diez días laborables |
| Calendario | Días 1 a 10 de E2. No son fechas del curso. |
| Ámbitos principales | Datos de salud, acceso autorizado, creación y validación de recetas, búsqueda y consulta |
| Equipo simulado | Tres personas, con seis horas disponibles por persona y día |
| Capacidad | 180 horas de trabajo del equipo |
| Esfuerzo asignado | 162 horas para actividades y 18 horas de reserva |

Las referencias de requisitos son la [Visión y Alcance](../vision/vision_y_alcance.md), versión 2.4, la [SRS](../requisitos/srs.md), versión 0.14, y el [catálogo de requisitos](../requisitos/catalogo-requisitos.md), versión 1.13. Se consultan también las actas enlazadas en esos documentos.

UR significa requisito de usuario. FR significa requisito funcional. NFR significa requisito no funcional. Los identificadores de este plan remiten al catálogo. Las descripciones resumen el alcance seleccionado y no sustituyen la redacción canónica de los requisitos.

El [plan de E1](plan-iteracion-e1.md) prevé una primera vista de acceso, cuentas y ayuda. También prevé un prototipo de acceso local y permisos. Al iniciar E2, el equipo revisará la evaluación de E1 y las versiones de sus productos. Comprobará qué funciones están representadas, qué escenarios funcionan y qué riesgos siguen abiertos.

Si algún producto necesario no está disponible, el equipo registrará la carencia. Ajustará el alcance y el esfuerzo antes de iniciar el trabajo que dependa de él. No dará por resuelto un riesgo solo porque aparezca en el plan anterior.

La Visión limita el proyecto a seis meses y 90.000 €. E2 utiliza una parte de ese plazo y presupuesto. El equipo comprobará el consumo real de E1 antes de confirmar el presupuesto disponible para E2.

## 2 Objetivos de E2

E2 tiene tres objetivos:

- Ampliar el modelo de casos de uso con una vista de salud y recetas. Conservar y revisar los elementos de E1 que sigan siendo necesarios.
- Precisar los permisos de acceso a datos de salud, las condiciones de validación de recetas y el uso de alergias e intolerancias en la búsqueda.
- Comprobar la arquitectura mediante un prototipo limitado de acceso autorizado, publicación validada y búsqueda filtrada.

Las vistas pertenecen al mismo modelo. Una nueva vista no implica completar los UR ni los módulos que aborda. El modelo debe indicar qué funciones siguen pendientes.

El prototipo permitirá estudiar los riesgos seleccionados. No será una versión preparada para producción. E2 tampoco representa por sí sola el cierre de Elaboración.

## 3 Riesgos que se abordarán

La prioridad de la tabla es un supuesto del plan. El equipo la revisará al iniciar E2.

| Riesgo | Prioridad | Trabajo previsto | Evidencia esperada |
| --- | --- | --- | --- |
| Permitir acceso a datos de salud sin autorización del paciente | Alta | Precisar los permisos por paciente y comprobarlos en el servidor. | Escenarios y pruebas de acceso permitido y denegado. |
| Mantener el acceso de un nutricionista después de su revocación | Alta | Comprobar una consulta posterior a la revocación, incluida una sesión ya iniciada. | Prueba que muestre la denegación de nuevas consultas. |
| Confundir la relación de cuidado con la autorización para consultar datos | Alta | Separar ambas condiciones y probar pacientes con permisos diferentes. | Matriz de pruebas que identifique paciente, participante y datos autorizados. |
| Publicar recetas pendientes o habilitar la validación a un perfil sin aprobar | Alta | Precisar el paso de propuesta a receta validada y comprobar los permisos. | Pruebas de publicación y validación permitidas y denegadas. |
| Mostrar recetas incompatibles con los filtros de alergias o intolerancias | Alta | Aclarar las reglas de correspondencia entre ingredientes y restricciones. Probarlas con datos ficticios. | Resultados contrastados con los filtros aplicados y preguntas pendientes. |
| Superar los tiempos previstos de búsqueda, consulta o publicación | Media | Medir los recorridos implementados con la carga de referencia. | Informe con tiempos, errores, carga y límites de la medición. |

El filtrado no demuestra que una receta sea clínicamente segura para una persona. El sistema no modifica automáticamente ingredientes o cantidades ni realiza recomendaciones médicas. Estas exclusiones proceden de la Visión, la SRS y el acta de requisitos generales.

## 4 Alcance del trabajo de requisitos

E2 estudiará las siguientes funciones. El equipo consultará el catálogo completo para comprobar las reglas y dependencias. Incorporará los nuevos objetivos a una segunda vista del modelo de casos de uso.

### 4.1 Datos de salud e historial

**UR-05.** E2 incluye la introducción manual de datos fisiológicos y resultados de laboratorio. Incluye también las notas de síntomas o estado de salud, con su límite de longitud.

FR seleccionados: FR-041, FR-042 y FR-053.

El paciente podrá consultar su historial, filtrar por tipo de dato y acceder a gráficas. También podrá exportar sus datos en PDF y CSV.

FR seleccionados: FR-047, FR-048, FR-049, FR-050 y FR-216.

La [aclaración de UR-05](../captura/acta-captura-requisitos-ur-05.md) confirma la corrección de datos introducidos por error. Precisa también fechas, unidades y validaciones. El equipo tendrá en cuenta esos acuerdos. Si necesita una regla adicional, la registrará como pregunta y no la atribuirá al catálogo.

### 4.2 Acceso autorizado a datos de salud

**UR-05.** E2 incluye la autorización de nutricionistas específicos para consultar datos de salud. El acceso requiere las verificaciones previstas para el nutricionista. El paciente podrá revocar la autorización en cualquier momento.

FR seleccionados: FR-045, FR-046 y FR-198. Se consultará además el apartado 2.6 del acta de UR-05.

E2 incluye la invitación a un nutricionista que todavía no tiene cuenta. El paciente indicará el correo del nutricionista. Si este ya dispone de cuenta, el sistema mostrará su identidad. Si no dispone de cuenta, el sistema le enviará por correo electrónico una invitación para registrarse.

El **Servicio de correo electrónico** participará como actor de apoyo en el envío de la invitación. Se reutilizará el actor del modelo de E1. Recibir la invitación no concede acceso a datos de salud. El nutricionista deberá verificar su correo, completar la verificación profesional correspondiente y contar con la autorización del paciente.

El respaldo de esta invitación es el apartado 2.6 del [acta de UR-05](../captura/acta-captura-requisitos-ur-05.md). El plan no le asigna un identificador FR nuevo.

E2 incluye la autorización del paciente para que su cuidador consulte los datos de salud que decida compartir.

FR seleccionado: FR-201.

La aprobación del perfil de cuidador, la aceptación de la relación de cuidado y la autorización de acceso a datos son condiciones diferentes. Una relación de cuidado activa no concede acceso automático a todos los datos del paciente. El cuidador no obtiene acceso a la dirección ni al teléfono del paciente.

El equipo conservará las condiciones de FR-193 y FR-194 estudiadas en E1. Aplicará también FR-208 como regla de retirada de acceso cuando termine la asociación. E2 no incorpora la gestión completa del ciclo de vida de las cuentas de cuidador.

### 4.3 Creación y validación de recetas

**UR-06.** E2 incluye la creación de recetas con los datos obligatorios, imágenes o vídeos admitidos, categorías y etiquetas. Incluye también la edición, la eliminación con confirmación y la consulta del historial de recetas propias.

FR seleccionados: FR-054, FR-056, FR-057, FR-058, FR-059, FR-060, FR-061, FR-062 y FR-063.

Una receta propuesta por un paciente o cuidador queda pendiente de validación. Un nutricionista puede revisar la propuesta y validarla. Tras la validación, la receta se publica como validada.

FR seleccionados: FR-204 y FR-205.

El nutricionista puede publicar directamente como validadas las recetas que cree. Las recetas validadas muestran la insignia correspondiente, con independencia de quién sea su autor.

FR seleccionados: FR-055 y FR-066.

El equipo aplicará la condición de aprobación profesional de FR-191, estudiada en E1. Contrastará las condiciones de publicación con el apartado 2.4.1 del acta de acuerdos técnicos y operativos. Registrará qué debe aclararse sobre la visibilidad de las propuestas pendientes y el efecto de editar una receta ya validada.

### 4.4 Búsqueda y consulta de recetas

**UR-08.** E2 incluye la búsqueda por palabras clave, ingredientes y autor. Incluye la exclusión de ingredientes y los filtros de tipo de comida, tiempo, dificultad y restricciones dietéticas. El usuario podrá combinar los criterios y consultar los resultados y el detalle de una receta.

FR seleccionados: FR-085, FR-086, FR-087, FR-088, FR-089, FR-090, FR-091, FR-092, FR-093 y FR-095.

E2 incluye el filtrado por alergias e intolerancias declaradas en el perfil. El equipo debe precisar cómo se relacionan esos datos con los ingredientes de las recetas. La representación del perfil de salud sigue pendiente en la documentación del proyecto.

FR seleccionado: FR-094.

Los resultados podrán ordenarse por relevancia o fecha de publicación. Se estudiará también el ajuste de la búsqueda al idioma seleccionado.

FR seleccionados: FR-096, FR-099 y FR-103.

La búsqueda avanzada y los resultados personalizados requieren registro e inicio de sesión.

FR seleccionado: FR-119.

El acta de requisitos generales exige registro para las funciones destinadas a pacientes, cuidadores y nutricionistas. El equipo aplicará esa condición junto con FR-119. No deducirá que una función es pública solo porque el UR utilice el término «usuario».

FR-089 incluye la calificación promedio en la vista previa. Este dato depende de las valoraciones, que no se estudian en E2. El modelo registrará esa dependencia sin incorporar las funciones de UR-11 al alcance seleccionado.

### 4.5 Identidad pública y ayuda

**UR-01.** E2 aplica el alias como identidad visible en los espacios públicos de recetas. Mantiene separada esa identidad de los datos privados de salud y de las comprobaciones profesionales.

FR seleccionado: la parte de FR-192 correspondiente a esos espacios.

**UR-12.** E2 amplía los temas de ayuda con la búsqueda y la publicación de recetas. Conserva las funciones de navegación, ayuda contextual, elementos visuales y control de la guía estudiadas en E1.

FR seleccionados: la parte de FR-173 correspondiente a búsqueda y publicación de recetas. FR-172 y FR-174 a FR-177 mantienen las condiciones de la ayuda.

El equipo revisará el alcance de la ayuda existente. No creará nuevos objetivos de usuario únicamente porque haya nuevos temas.

### 4.6 Reglas y preguntas pendientes

El equipo debe distinguir las siguientes condiciones: verificación del correo, aprobación profesional, aceptación de una relación de cuidado, autorización de acceso a datos y validación de una receta.

Antes de programar los escenarios afectados, aclarará estas cuestiones:

- Qué datos puede consultar cada cuidador y cómo selecciona el paciente los datos que comparte.
- Cómo se representa la autorización y cómo se aplica su revocación a nuevas consultas.
- Qué respuesta se ofrece al paciente si falla el envío de la invitación al nutricionista.
- Qué visibilidad tiene una receta pendiente y qué ocurre con su validación cuando se edita.
- Qué información de alergias e intolerancias se utiliza para filtrar y cómo se relaciona con los ingredientes.
- Qué resultado se muestra si faltan datos del perfil, faltan datos de una receta o no hay coincidencias.

Las respuestas se registrarán como acuerdos de la simulación, con su procedencia. Las decisiones aún no confirmadas permanecerán como preguntas. El plan no modifica por sí mismo el catálogo ni la SRS.

## 5 Profundidad y funcionalidad pendiente

El alcance del trabajo de requisitos es mayor que el alcance del prototipo.

| Trabajo | Profundidad prevista |
| --- | --- |
| Funciones del apartado 4 | Identificar participantes, objetivos y relaciones. Añadir la vista de salud y recetas al modelo acumulado. |
| Elementos compartidos con E1 | Revisar nombres, permisos y relaciones. Conservar los identificadores cuando se mantenga el mismo objetivo. |
| Acceso autorizado, validación de recetas y filtrado por alergias | Precisar los escenarios y las condiciones necesarios para estudiar los riesgos. |
| Resto de funciones seleccionadas | Registrar el objetivo, las reglas, el respaldo en requisitos y las preguntas necesarias para revisar el modelo. |
| Prototipo | Implementar solo los recorridos limitados del apartado 7. |
| Pruebas | Comprobar los recorridos implementados y registrar sus límites. |

El producto principal del modelado será el diagrama de la segunda vista. El equipo actualizará el [mismo documento del modelo](../modelos/modelo-casos-de-uso.md). Revisará la primera vista cuando cambien elementos compartidos. Mantendrá la misma frontera del sistema y los mismos nombres de actores.

La segunda vista utilizará la imagen `casos-de-uso-salud-recetas-e2.png`, en `docs/modelos/imagenes/`, conforme a la [guía de modelos](../modelos/README.md). El equipo actualizará las tablas del modelo y su alcance acumulado. No creará una copia del documento para cada iteración.

Las descripciones de los escenarios seleccionados orientarán el desarrollo del prototipo. Las demás funciones no necesitan el mismo nivel de detalle en E2.

| Funcionalidad pendiente | Requisitos | Motivo |
| --- | --- | --- |
| Recordatorios de salud y propuesta profesional de su frecuencia | FR-043, FR-044, FR-199 y FR-200 | Concentrar E2 en registro, consulta y acceso autorizado. |
| Alertas críticas y gestión de umbrales | FR-051, FR-052, FR-202, FR-203 y FR-217 | Precisar después las condiciones, responsabilidades y límites clínicos. |
| Calculadora nutricional y estadísticas completas de recetas | FR-064 y FR-065 | Separar esos objetivos del ciclo básico de creación y validación. |
| Ordenación por popularidad o calificación, sugerencias y recomendaciones | FR-097, FR-098, FR-100, FR-101, FR-102 y FR-104 a FR-108 | Limitar E2 a búsqueda, filtros y ordenación seleccionados. |
| Notificaciones de nuevas recetas e historial de búsqueda | FR-109, FR-110 y FR-111 | Incorporar después las funciones basadas en actividad previa. |
| Favoritas, listas, lectura posterior, descarga, impresión, compartición y estadísticas de consulta | FR-112 a FR-118 | Mantener un alcance limitado de búsqueda y consulta. |
| Foro, consejos de vida saludable, reportes, moderación, valoraciones y comentarios | UR-04, UR-07, UR-09, UR-10 y UR-11 | Incorporar otras vistas en iteraciones posteriores. |
| Integración con Google | FR-006, FR-018, FR-190 y NFR-015 | Mantener el acceso local para el prototipo. Revisar el riesgo de aplazamiento al iniciar E2. |
| Sanciones y gestión automática de cuentas de cuidador sin pacientes | FR-186, FR-187, FR-209 y FR-210 | Estudiar después la moderación y el ciclo de vida completo de las cuentas. |
| Resto de temas y ampliaciones de la guía | Parte pendiente de FR-173; FR-178, FR-179 y FR-180 | Ampliar los temas junto con sus funciones y estudiar después progreso, multimedia y búsqueda. |

Los pendientes técnicos de E1 se revisarán al inicio. Una función representada en el modelo puede seguir pendiente de implementación. FR-017 está retirado: la autenticación de dos factores no es un pendiente de E2.

Los aplazamientos no eliminan requisitos del proyecto. Las exclusiones siguen siendo las de la Visión y la SRS.

## 6 Requisitos no funcionales

Los NFR condicionan la arquitectura, la interfaz y las pruebas. No se convierten automáticamente en casos de uso.

| NFR | Trabajo previsto en E2 | Límite de la comprobación |
| --- | --- | --- |
| NFR-004 y NFR-005 | Medir acceso local, búsqueda y consulta de recetas con la carga de referencia. | No se comprobarán consultas del foro ni todas las consultas del sistema. |
| NFR-006 | Medir la publicación de una receta creada por un nutricionista aprobado. | No se comprobarán publicaciones de comentarios ni mensajes. |
| NFR-002 | Preparar copias de los datos ficticios de salud y recetas y comprobar una restauración. | Una restauración no demuestra la continuidad de las copias diarias en producción. |
| NFR-008 y NFR-009 | Registrar el tiempo y la información recuperada en esa restauración limitada. | La prueba no demostrará la recuperación de todas las funciones tras un incidente grave. |
| NFR-010 | Revisar formularios, mensajes y recorridos del prototipo con una herramienta automática y una revisión manual. | La revisión no demostrará la conformidad de toda la plataforma con WCAG 2.2 AA. |
| NFR-003 y NFR-014 | Comprobar los recorridos del prototipo en castellano y gallego, incluido el cambio de idioma. | Quedarán pendientes las funciones y los mensajes no implementados. |
| NFR-011, NFR-012 y NFR-013 | Mantener el entorno web de prueba en la nube y comprobar acceso responsivo y estándares abiertos. | El entorno no será el despliegue de producción. |
| NFR-001 y NFR-007 | Conservar las condiciones de disponibilidad y ajuste automático de recursos en la revisión de arquitectura. | E2 no demostrará disponibilidad mensual ni escalado automático completo. |
| NFR-015 | Mantener las condiciones de autenticación externa. | Se comprobarán cuando se aborde Google. |

La prueba de carga utilizará 100 usuarios concurrentes y 10 operaciones por segundo durante 30 minutos. El equipo definirá y registrará la mezcla de operaciones antes de ejecutarla. Incluirá acceso local, búsqueda, consulta y publicación de recetas implementados.

El informe separará los resultados por tipo de operación. El 95 % de los accesos, búsquedas y consultas deberá completarse en un máximo de 2 segundos. El 95 % de las publicaciones deberá completarse en un máximo de 3 segundos. Se usarán los límites de medición del apartado 2.1.3 del acta técnica.

La relación de NFR-005 y NFR-006 con FR concretos sigue pendiente en el catálogo. El informe identificará los recorridos medidos sin presentar esa selección como una actualización de la trazabilidad canónica.

La privacidad y los permisos se comprobarán mediante los requisitos y acuerdos de acceso citados en el apartado 4. El equipo registrará las condiciones de protección de datos que aún deban concretarse. Las pruebas de permisos no demostrarán por sí solas el cumplimiento de todas las obligaciones legales ni la seguridad completa del producto.

## 7 Trabajo de arquitectura y prototipo

### 7.1 Revisión de arquitectura

El equipo revisará la propuesta y las evidencias disponibles de E1. Mantendrá como hipótesis una aplicación web modular, con interfaz, lógica de aplicación y persistencia separadas. Revisará esa hipótesis cuando las pruebas aporten evidencia nueva.

La propuesta debe permitir asociar datos de salud a un paciente, comprobar autorizaciones y distinguir recetas propuestas y validadas. Los permisos se comprobarán en el servidor en cada operación protegida.

El equipo estudiará la coherencia entre una autorización y el acceso posterior. También estudiará la coherencia entre la validación de una receta y su publicación. La búsqueda aplicará las reglas de filtrado que se hayan confirmado.

Estas decisiones pertenecen a la simulación. No obligan a utilizar una tecnología concreta ni a crear un servicio independiente por módulo de la Visión.

### 7.2 Escenarios del prototipo

El prototipo ampliará la base técnica disponible de E1. Utilizará datos persistentes, cuentas ficticias y una interfaz mínima. Implementará estos recorridos:

1. **Acceso a datos de salud.** Un paciente registrará una medición y consultará su historial. Autorizará a un nutricionista para consultar sus datos. Después revocará la autorización y se comprobará la denegación de una nueva consulta.
2. **Consulta por un cuidador.** Se utilizarán dos pacientes y permisos distintos. El cuidador podrá consultar solo los datos autorizados mientras exista la asociación correspondiente. Se probarán la ausencia de autorización y la retirada de acceso al terminar la asociación.
3. **Propuesta y validación de una receta.** Un paciente o cuidador propondrá una receta con los datos obligatorios. Un nutricionista aprobado la validará. Se comprobarán su publicación y su insignia. Se probará también la publicación directa por un nutricionista aprobado y la denegación de una operación profesional a un perfil pendiente.
4. **Búsqueda filtrada.** Un usuario autenticado buscará recetas por palabras clave y combinará un filtro de ingredientes con alergias o intolerancias ficticias. Consultará el detalle de un resultado. Se comprobarán los resultados esperados y una búsqueda sin coincidencias.

El recorrido de datos de salud se limitará a una variable fisiológica. El de recetas utilizará contenido de texto, sin carga de archivos. El de búsqueda utilizará un conjunto pequeño de recetas con ingredientes y restricciones conocidos.

Las pruebas de acceso utilizarán nutricionistas que ya tengan cuenta. La invitación se estudiará en el modelo de casos de uso, pero su envío no se implementará en el prototipo de E2.

El equipo debe confirmar antes las reglas necesarias del apartado 4.6. Si una regla sigue abierta, registrará el límite y ajustará el recorrido afectado. No incorporará una decisión sin identificarla.

Los datos de alergias del prototipo serán datos de prueba. Su uso no resolverá por sí solo la representación del perfil de salud del producto completo. Si un resultado necesita información de valoraciones aún ausente, se identificará como dato de prueba; no se afirmará que UR-11 está implementado.

El prototipo no implementará todo el apartado 4. Quedarán fuera las exportaciones, las gráficas completas, los resultados de laboratorio, las notas, la gestión completa de recetas propias, los archivos multimedia y la ayuda. Tampoco implementará todos los filtros, formas de ordenación e idiomas del contenido de recetas.

### 7.3 Entorno y recursos

El equipo reutilizará, cuando esté disponible, el entorno de prueba de E1. Necesitará un repositorio Git, una herramienta de modelado, un entorno web, una base de datos y herramientas de pruebas automáticas, carga y accesibilidad.

El conjunto de prueba incluirá pacientes, un cuidador, un nutricionista aprobado y un perfil profesional pendiente. Incluirá datos de salud y recetas ficticios. Las comprobaciones de permisos utilizarán consultas directas al servidor, además del recorrido de la interfaz.

El informe identificará las versiones del código, la configuración, los datos y las herramientas. Incluirá los pasos necesarios para repetir las pruebas y la restauración.

## 8 Equipo esfuerzo y coste

Las personas siguientes forman el equipo de desarrollo simulado. No son los actores del sistema.

| Persona | Responsabilidades | Horas asignadas | Reserva |
| --- | --- | --- | --- |
| P1 | Coordinación, requisitos y modelo de casos de uso | 54 | 6 |
| P2 | Arquitectura y desarrollo | 54 | 6 |
| P3 | Integración, datos y pruebas | 54 | 6 |
| Total | Equipo de tres personas | 162 | 18 |

Cada persona dispone de 60 horas durante E2. Las 18 horas de reserva cubren incidencias y ajustes. Si la reserva no basta, la coordinación reducirá el tamaño de los datos o los recorridos secundarios del prototipo. Registrará el cambio y conservará las comprobaciones prioritarias de permisos, validación y filtrado.

Se mantiene como supuesto una tarifa interna de 35 € por hora. Las 180 horas cuestan 6.300 €, incluida la reserva. Se asignan otros 300 € al entorno y a los servicios de prueba. El coste máximo previsto de E2 es **6.600 €**.

La suma de los presupuestos previstos de E1 y E2 es 13.200 €. Esta cifra no representa el gasto real ni el coste total del proyecto. El equipo revisará el presupuesto restante con los datos de cierre de E1.

## 9 Actividades calendario y revisiones

Las horas de la tabla son horas de trabajo de cada persona. No son la duración de la actividad. Varias actividades pueden coincidir en el calendario.

| ID | Actividad | Días | Responsable | P1 | P2 | P3 | Total |
| --- | --- | --- | --- | --- | --- | --- | --- |
| T1 | Revisar los resultados disponibles de E1, el plan y los riesgos | 1 | P1 | 6 | 3 | 3 | 12 |
| T2 | Ampliar y revisar el modelo y precisar los escenarios prioritarios | 1–6 | P1 | 30 | 6 | 6 | 42 |
| T3 | Revisar la arquitectura y las decisiones de acceso y publicación | 2–7 | P2 | 6 | 15 | 3 | 24 |
| T4 | Preparar el entorno y los datos de permisos, recetas y filtros | 1–5 | P3 | 0 | 6 | 6 | 12 |
| T5 | Construir e integrar los recorridos del prototipo | 4–8 | P2 | 0 | 18 | 18 | 36 |
| T6 | Ejecutar las pruebas y analizar los resultados | 7–10 | P3 | 3 | 3 | 12 | 18 |
| T7 | Consolidar los productos y registrar los pendientes | 9 | P1 | 6 | 3 | 3 | 12 |
| T8 | Revisar y evaluar E2 | 10 | P1 | 3 | 0 | 3 | 6 |
| Total | Trabajo asignado | 1–10 | P1 | 54 | 54 | 54 | 162 |

T2, T3 y T4 comenzarán tras la revisión inicial de T1. T5 necesita los primeros escenarios revisados de T2, las decisiones iniciales de T3 y el entorno mínimo de T4. Esas primeras versiones deberán estar disponibles en el día 3. Las tres actividades podrán continuar después.

T6 comenzará con los recorridos integrados que estén disponibles. La prueba de carga y la revisión final requerirán una versión integrada de T5. Los resultados podrán exigir ajustes. T7 conservará los pendientes conocidos; T8 incorporará los resultados finales de las pruebas al cierre.

| Revisión | Día | Resultado previsto |
| --- | --- | --- |
| Inicio | 1 | Resultados y carencias de E1 identificados; alcance y riesgos de E2 revisados. |
| Escenarios y arquitectura | 3 | Reglas necesarias, primeros escenarios y entorno mínimo disponibles para iniciar el prototipo. |
| Demostración interna | 8 | Recorridos integrados y primeras pruebas de permisos, publicación y filtros registrados. |
| Cierre de E2 | 10 | Productos contrastados con el plan; riesgos, esfuerzo y trabajo siguiente revisados. |

La coordinación comprobará cada día el avance, el esfuerzo consumido y los obstáculos. Cada cambio de alcance indicará su motivo, su efecto y el trabajo aplazado. El equipo mantendrá identificadas las versiones revisadas de los productos.

## 10 Productos y criterios de evaluación

| Producto previsto | Responsable | Criterio para su revisión |
| --- | --- | --- |
| Modelo de casos de uso acumulado | P1 | Incorpora los objetivos del apartado 4. Conserva la coherencia con E1 y declara la cobertura parcial. |
| Escenarios y preguntas de requisitos | P1 | Distinguen las autorizaciones y la validación. Identifican las reglas confirmadas y las preguntas abiertas. |
| Descripción revisada de arquitectura | P2 | Explica las decisiones de acceso, persistencia, publicación y búsqueda, con sus requisitos y riesgos. |
| Prototipo integrado | P2 | Permite repetir los recorridos limitados del apartado 7 con datos ficticios. |
| Informe de pruebas | P3 | Identifica versión, entorno, datos, carga y resultados. Registra fallos y límites de cada comprobación. |
| Evaluación de E2 | P1 | Compara objetivos, alcance, esfuerzo y coste previstos con los resultados. Registra cambios y trabajo siguiente. |

La revisión del modelo comprobará que los elementos representan objetivos y participantes externos. Los participantes y las relaciones deben tener respaldo en los requisitos. No se exigirá un caso de uso independiente por FR o NFR ni una cantidad mínima de relaciones `include` o `extend`.

La revisión comprobará también que las dos vistas usan nombres compatibles y la misma frontera del sistema. Los casos que mantengan su objetivo conservarán su identificador. El modelo indicará qué incorpora E2 y qué revisa de E1.

Las pruebas funcionales deben mostrar acceso permitido y denegado. Incluirán consultas después de revocar una autorización, permisos diferentes para dos pacientes y operaciones profesionales intentadas por un perfil pendiente. También comprobarán que la receta propuesta no se publica antes de cumplir la condición de validación.

Las pruebas de filtrado contrastarán las recetas obtenidas con los ingredientes y las restricciones del conjunto de prueba. Las mediciones técnicas y la restauración indicarán qué demuestran y qué queda pendiente. Si un objetivo no se alcanza, el equipo registrará el resultado y propondrá una acción.

## 11 Evaluación y continuidad previstas

La evaluación se realizará en el día 10. Este plan establece cómo se evaluará E2; no registra resultados ya obtenidos.

El equipo comparará el trabajo realizado con el plan. Registrará los objetivos alcanzados, las desviaciones de esfuerzo y coste, las incidencias y las lecciones aprendidas. Revisará qué riesgos se han reducido y cuáles permanecen abiertos.

La evaluación se conservará como un documento separado. Identificará el commit que contiene el estado revisado del modelo, sus imágenes y sus archivos editables disponibles. Cerrar E2 no declarará automáticamente una línea base formal.

El equipo seleccionará el trabajo siguiente a partir de los riesgos y pendientes de E1 y E2. El modelo conservará sus elementos válidos al incorporar otras vistas. Las nuevas evidencias podrán exigir cambios de arquitectura.

E2 no permite declarar completos los módulos de salud y recetas. Tampoco permite aprobar la arquitectura del sistema completo. La evaluación indicará si se puede continuar o si hace falta trabajo adicional antes de la siguiente iteración.

## 12 Documentos de referencia

- [Plan de iteración E1](plan-iteracion-e1.md).
- [Documento de Visión y Alcance](../vision/vision_y_alcance.md).
- [SRS](../requisitos/srs.md) y [catálogo canónico de requisitos](../requisitos/catalogo-requisitos.md).
- [Acta de captura de requisitos de UR-05](../captura/acta-captura-requisitos-ur-05.md).
- [Acta de captura de requisitos generales](../captura/acta-captura-requisitos-generales.md).
- [Acta de acuerdos técnicos y operativos](../captura/acta-acuerdos-tecnicos-operativos.md).
- [Modelo de casos de uso](../modelos/modelo-casos-de-uso.md) y [guía de modelos](../modelos/README.md).
