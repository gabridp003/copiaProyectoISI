# Proyecto Simbiosis Plan de iteración E1

| Versión | Fecha | Estado |
| --- | --- | --- |
| 1.0 | 05/10/2026 | Vigente |

Este plan define el trabajo previsto para E1, la primera iteración de Elaboración. Selecciona la funcionalidad que se estudiará. También establece las actividades, los recursos, los productos y los criterios de evaluación.

El plan pertenece a un proyecto simulado. La duración, el equipo, el esfuerzo y el coste son supuestos de esta simulación. Los requisitos proceden de los documentos del proyecto.

## 1 Punto de partida

| Dato | Valor |
| --- | --- |
| Proyecto | Proyecto Simbiosis |
| Iteración | E1 |
| Fase | Elaboración |
| Duración simulada | Dos semanas de trabajo, con diez días laborables |
| Calendario | Días 1 a 10 de E1. No son fechas del curso. |
| Ámbitos principales | Gestión de usuarios y Guía interactiva |
| Equipo simulado | Tres personas, con seis horas disponibles por persona y día |
| Capacidad | 180 horas de trabajo del equipo |
| Esfuerzo asignado | 162 horas para actividades y 18 horas de reserva |

El punto de partida es la [Visión y Alcance](../vision/vision_y_alcance.md), versión 2.4. La especificación está formada por la [SRS](../requisitos/srs.md), versión 0.14, y el [catálogo de requisitos](../requisitos/catalogo-requisitos.md), versión 1.13. Se consultan también las actas enlazadas en esos documentos.

UR significa requisito de usuario. FR significa requisito funcional. NFR significa requisito no funcional. Los identificadores de este plan remiten al catálogo. Sus descripciones resumen el alcance seleccionado y no sustituyen el texto de los requisitos.

La Visión limita el proyecto a seis meses y 90.000 €. E1 ocupa una parte de ese plazo y de ese presupuesto. Este plan no distribuye el trabajo de todo el proyecto.

## 2 Objetivos de E1

E1 tiene tres objetivos:

- Aclarar el registro local, la verificación del correo, la aprobación de perfiles y el acceso a la plataforma.
- Crear una primera vista del modelo de casos de uso. La vista incluirá también la gestión básica de cuentas y la ayuda seleccionada.
- Comprobar una primera propuesta de arquitectura mediante un prototipo limitado de registro, acceso y permisos.

El modelo conservará una visión general del sistema. Las iteraciones posteriores añadirán otras vistas y podrán revisar las anteriores. Una nueva vista no completa por sí sola los módulos que aborda.

El prototipo permitirá estudiar decisiones técnicas. No será una versión preparada para producción. E1 tampoco representa el cierre de Elaboración.

## 3 Riesgos que se abordarán

La siguiente prioridad es un supuesto del plan. Se revisará durante E1.

| Riesgo | Prioridad | Trabajo previsto | Evidencia esperada |
| --- | --- | --- | --- |
| Confundir la verificación del correo con la aprobación de un perfil | Alta | Precisar las condiciones de acceso y probar los cambios de estado. | Escenarios y pruebas que distingan ambas condiciones. |
| Habilitar funciones profesionales antes de aprobar la documentación | Alta | Definir los permisos y comprobar su aplicación en el servidor. | Pruebas de acceso permitido y denegado. |
| Activar una relación de cuidado sin autorización | Alta | Precisar la autorización por paciente y representar su estado. | Escenarios revisados y pruebas de la regla con datos ficticios. |
| Confundir la eliminación de cuentas con las sanciones por infracciones | Media | Separar los objetivos y precisar qué información se conserva. | Límites y resultados respaldados por los requisitos. |
| Perder coherencia entre el envío del correo y el estado de la cuenta | Alta | Integrar el registro con un servicio de correo de prueba y provocar un fallo de envío. | Registro del comportamiento observado y de las decisiones pendientes. |
| Obtener un tiempo de acceso superior al previsto | Media | Medir el inicio de sesión del prototipo bajo una carga controlada. | Informe con carga, tiempos, errores y límites de la prueba. |

La integración con Google se aplaza. Para este ejemplo, se supone que no es el riesgo prioritario de E1. El equipo revisará esa suposición antes de confirmar el aplazamiento. Las pruebas del acceso local no validarán la integración con Google.

## 4 Alcance del trabajo de requisitos

E1 estudiará las siguientes funciones. El equipo utilizará el catálogo completo para comprobar sus reglas y dependencias.

### 4.1 Registro local y condiciones por perfil

**UR-01.** El registro local incluye los datos obligatorios y un alias único. También incluye las validaciones, el CAPTCHA accesible y la aceptación independiente de las condiciones y de la política de privacidad. La cuenta queda pendiente hasta que se verifica el correo.

FR seleccionados: FR-001, FR-002, FR-003, FR-004, FR-005, FR-007, FR-008, FR-009, FR-010, FR-011, FR-012, FR-013, FR-188, FR-189, FR-214 y FR-215.

La solicitud de perfil de nutricionista incluye la documentación profesional en PDF y la comprobación de su formato y tamaño. Mientras la documentación no esté aprobada, se mantienen las limitaciones de publicación profesional.

FR seleccionados: FR-014, FR-191 y FR-213.

La solicitud de perfil de cuidador permite indicar los pacientes. Cada paciente debe autorizar expresamente su relación de cuidado antes de que esta se active.

FR seleccionados: FR-193 y FR-194.

### 4.2 Acceso local y contraseña

**UR-02.** E1 incluye el inicio de sesión con correo y contraseña. Incluye también la recuperación o el restablecimiento de la contraseña mediante un enlace enviado al correo de la cuenta.

FR seleccionados: FR-015 y FR-016.

### 4.3 Perfil y cuenta propia

**UR-03.** E1 incluye la actualización de datos personales y preferencias. El alias y el correo no se pueden modificar. La eliminación de la cuenta propia exige comprobar la identidad con la contraseña actual.

FR seleccionados: FR-019 y FR-020.

### 4.4 Gestión básica de cuentas

**UR-13.** E1 incluye el listado de cuentas y la aprobación de cuentas de cuidador y nutricionista. También incluye la suspensión, la eliminación y el registro de auditoría de esas acciones.

FR seleccionados: FR-181, FR-182, FR-183, FR-184 y FR-185.

Una cuenta puede tener a la vez los perfiles de paciente y cuidador. El contenido publicado por un cuidador se conserva cuando se elimina su cuenta. Esta condición afecta tanto a la eliminación propia como a la realizada por el coordinador.

FR seleccionados: FR-211 y FR-212.

### 4.5 Ayuda y bienvenida

**UR-12.** E1 incluye ayuda sobre las funciones seleccionadas. La ayuda ofrece instrucciones, navegación entre temas y elementos visuales. Se puede pausar, reanudar y cerrar. La ayuda contextual se adapta a la sección de la plataforma.

FR seleccionados: FR-172, la parte de FR-173 correspondiente a E1, FR-174, FR-175, FR-176 y FR-177.

E1 incluye también el recorrido de bienvenida del primer acceso. Este recorrido se puede omitir y es independiente de la ayuda contextual.

FR seleccionado: FR-207.

### 4.6 Reglas y preguntas pendientes

FR-192 exige usar el alias como identidad pública. E1 establece el alias durante el registro. Su uso en el foro y en otros espacios públicos se estudiará cuando se incorporen esas funciones.

La verificación del correo, la aprobación de un perfil y la autorización de una relación de cuidado son condiciones diferentes. El trabajo de requisitos debe mantener esa diferencia.

Antes de programar los escenarios afectados, el equipo debe aclarar los estados de las cuentas y los efectos de la suspensión. También debe precisar el tratamiento de un fallo de correo y las condiciones de los enlaces de verificación y restablecimiento. Las respuestas se registrarán como acuerdos de la simulación. No se atribuirán al catálogo si este no las contiene.

## 5 Profundidad y funcionalidad pendiente

El alcance del trabajo de requisitos es mayor que el alcance del prototipo.

| Trabajo | Profundidad prevista |
| --- | --- |
| Funciones del apartado 4 | Identificar participantes, objetivos y relaciones. Construir la primera vista del modelo de casos de uso. |
| Registro, verificación, aprobación y autorización | Precisar los escenarios y las condiciones necesarias para estudiar los riesgos. |
| Resto de funciones seleccionadas | Registrar las reglas y preguntas necesarias para revisar el modelo. |
| Prototipo | Implementar solo los escenarios técnicos del apartado 7. |
| Pruebas | Comprobar los escenarios implementados y registrar sus límites. |

Las descripciones de los escenarios seleccionados orientarán el desarrollo del prototipo. Las demás funciones no necesitan el mismo nivel de detalle en E1.

| Funcionalidad pendiente | Requisitos | Motivo |
| --- | --- | --- |
| Registro, acceso y vinculación de cuentas con Google | FR-006, FR-018, FR-190 y NFR-015 | Concentrar E1 en el acceso local. Revisar antes el riesgo de aplazar esta integración. |
| Aplicación del alias en espacios públicos | Parte pendiente de FR-192 | Incorporar la regla al estudiar esos espacios. |
| Ayuda sobre recetas, foro, valoraciones y comentarios | Parte pendiente de FR-173 | Incorporar los temas junto con esas funciones. |
| Progreso de ayuda entre sesiones, multimedia y búsqueda de temas | FR-178, FR-179 y FR-180 | Ampliar la guía en una iteración posterior. |
| Bloqueo temporal y expulsión por infracciones | FR-186 y FR-187 | Estudiar estas acciones con las políticas de moderación. |
| Fin de la relación de cuidado y gestión automática de cuentas sin pacientes | FR-208, FR-209 y FR-210 | Ampliar el estudio del ciclo de vida de la relación y de la cuenta. |
| Salud, recetas, foro, publicaciones y moderación de contenidos | UR-04 a UR-11 | Incorporar otras vistas en iteraciones posteriores. |

FR-017 está retirado. La autenticación de dos factores no es una tarea pendiente de E1.

Los aplazamientos no eliminan requisitos del proyecto. Las exclusiones del proyecto siguen siendo las de la Visión y la SRS. Las próximas iteraciones aún no tienen un alcance detallado.

## 6 Requisitos no funcionales

Los NFR condicionan la arquitectura, la interfaz y las pruebas. No se convierten automáticamente en casos de uso.

| NFR | Trabajo previsto en E1 | Límite de la comprobación |
| --- | --- | --- |
| NFR-004 y NFR-005 | Preparar la carga de referencia y medir el inicio de sesión del prototipo. | La prueba no cubrirá las consultas ni otras funciones todavía ausentes. |
| NFR-010 | Revisar los formularios y mensajes del prototipo con una herramienta automática y una revisión manual. | La revisión no demostrará la conformidad de toda la plataforma con WCAG 2.2 AA. |
| NFR-003 y NFR-014 | Prever castellano y gallego. Comprobar el cambio de idioma en las pantallas del prototipo. | Quedarán pendientes las pantallas y los mensajes de las demás funciones. |
| NFR-011 y NFR-013 | Comprobar el acceso web responsivo y el uso de estándares web abiertos. | La comprobación se limitará a los recorridos y navegadores de prueba. |
| NFR-012 | Preparar un entorno de prueba en infraestructura en la nube. | El entorno no será el despliegue de producción. |
| NFR-001, NFR-007, NFR-008 y NFR-009 | Registrar las condiciones de disponibilidad, ajuste de recursos y recuperación que afectan al diseño. | E1 no demostrará disponibilidad mensual, escalado automático ni recuperación completa. |
| NFR-002 y NFR-006 | Conservar las condiciones de copias de salud y recetas y de rendimiento de publicaciones. | Esas funciones quedan fuera de las pruebas de E1. |
| NFR-015 | Mantener las condiciones de autenticación externa. | Se comprobarán cuando se aborde Google. |

NFR-004 define 100 usuarios concurrentes y 10 operaciones por segundo durante 30 minutos. NFR-005 fija un máximo de 2 segundos para el 95 % de los inicios de sesión y de las consultas definidas para la prueba. E1 comprobará solo el inicio de sesión. El informe indicará el entorno, la mezcla de operaciones, los errores y los límites de medición del acta técnica.

La relación de NFR-005 con FR concretos sigue pendiente en el catálogo. E1 propone comprobar su aplicación al acceso local sin modificar esa trazabilidad canónica.

El catálogo no contiene un NFR específico de seguridad de credenciales. El equipo registrará esa cuestión para su aclaración. El CAPTCHA y las reglas de contraseña no bastan para demostrar la seguridad del producto.

## 7 Trabajo de arquitectura y prototipo

### 7.1 Propuesta inicial

El equipo estudiará una aplicación web modular. Como hipótesis inicial, separará la interfaz, la lógica de la aplicación y la persistencia. Preverá una integración con el servicio externo de correo.

La propuesta debe permitir distinguir identidad, perfiles, permisos y relaciones de cuidado. Las comprobaciones de permisos se realizarán en el servidor. La interfaz no será la única barrera de acceso.

Estas son decisiones propuestas para la simulación. El equipo las revisará con las pruebas. Los módulos de la Visión no obligan a crear un componente ni un servicio independiente por módulo.

La arquitectura tendrá en cuenta el sistema completo, aunque el prototipo sea pequeño. La descripción inicial registrará las necesidades futuras de salud, recetas y comunidad y las restricciones globales del apartado 6.

### 7.2 Escenarios del prototipo

El prototipo recorrerá el registro local, el envío y la verificación del correo y el inicio de sesión. Incluirá datos persistentes y una interfaz mínima para completar ese recorrido.

El equipo usará cuentas de prueba para comprobar perfiles simultáneos y aprobación profesional. También comprobará la autorización por paciente antes de activar una relación de cuidado.

La función profesional protegida podrá ser una operación técnica de prueba. Su presencia no implica implementar publicaciones profesionales. La comprobación de la relación de cuidado no implica implementar datos de salud.

El equipo provocará un fallo del servicio de correo. Registrará el estado de la cuenta y la respuesta del prototipo. Si el resultado requiere una regla nueva, documentará la propuesta y solicitará su revisión.

El prototipo no implementará la ayuda completa, la recuperación de contraseña, la edición del perfil, la eliminación ni la suspensión. Esas funciones sí forman parte del trabajo de requisitos de E1.

### 7.3 Entorno y recursos

El equipo utilizará un repositorio Git, una herramienta de modelado, un entorno web de prueba, una base de datos y un servicio de correo de prueba. Necesitará también herramientas para pruebas automáticas, carga y revisión de accesibilidad.

Los datos serán ficticios. Las versiones del código, la configuración y los datos de prueba quedarán identificadas. El informe permitirá repetir las comprobaciones. La selección de tecnologías y proveedores se registrará durante E1.

## 8 Equipo esfuerzo y coste

Los roles siguientes pertenecen al equipo de desarrollo simulado. No son los actores del sistema.

| Persona | Responsabilidades | Horas asignadas | Reserva |
| --- | --- | --- | --- |
| P1 | Coordinación y análisis de requisitos | 54 | 6 |
| P2 | Arquitectura y desarrollo | 54 | 6 |
| P3 | Desarrollo, integración y pruebas | 54 | 6 |
| Total | Equipo de tres personas | 162 | 18 |

Cada persona dispone de 60 horas durante E1. Las 18 horas de reserva cubren incidencias y ajustes. Si la reserva no basta, la coordinación reducirá escenarios secundarios del prototipo y registrará el cambio. Se conservarán las comprobaciones prioritarias de registro y permisos.

Para calcular el coste se supone una tarifa interna de 35 € por hora. Las 180 horas cuestan 6.300 €, incluida la reserva. Se asignan otros 300 € al entorno y a los servicios de prueba. El coste máximo previsto de E1 es **6.600 €**.

La tarifa y los costes son datos simulados. No son una oferta ni una estimación aprobada del proyecto completo.

## 9 Actividades calendario y revisiones

Las horas de la tabla son horas de trabajo de cada persona. No son la duración de la actividad. Varias actividades pueden coincidir en el calendario.

| ID | Actividad | Días | Responsable | P1 | P2 | P3 | Total |
| --- | --- | --- | --- | --- | --- | --- | --- |
| T1 | Revisar el plan, los riesgos y los criterios | 1 | P1 | 6 | 3 | 3 | 12 |
| T2 | Construir y revisar el modelo de casos de uso y precisar los escenarios | 1–6 | P1 | 30 | 6 | 6 | 42 |
| T3 | Proponer y revisar la arquitectura | 2–7 | P2 | 6 | 15 | 3 | 24 |
| T4 | Preparar el entorno y los datos de prueba | 1–5 | P3 | 0 | 6 | 6 | 12 |
| T5 | Construir e integrar el prototipo | 4–8 | P2 | 0 | 18 | 18 | 36 |
| T6 | Ejecutar las pruebas y analizar sus resultados | 7–10 | P3 | 3 | 3 | 12 | 18 |
| T7 | Consolidar los productos y registrar los pendientes | 9 | P1 | 6 | 3 | 3 | 12 |
| T8 | Revisar y evaluar la iteración | 10 | P1 | 3 | 0 | 3 | 6 |
| Total | Trabajo asignado | 1–10 | P1 | 54 | 54 | 54 | 162 |

**Dependencias.** T2 y T3 comienzan tras la revisión inicial de T1. T5 necesita el primer conjunto de escenarios revisados de T2, una propuesta inicial de T3 y el entorno mínimo de T4. Esas primeras versiones estarán disponibles en el día 3. T2, T3 y T4 podrán continuar después. T6 necesita una versión integrada de T5. Sus resultados podrán exigir ajustes del prototipo y de la arquitectura. T8 necesita los productos y las evidencias disponibles al final de E1.

| Revisión | Día | Resultado previsto |
| --- | --- | --- |
| Inicio | 1 | Plan y criterios revisados; tareas distribuidas. |
| Escenarios y arquitectura inicial | 3 | Escenarios prioritarios, decisiones iniciales y entorno mínimo disponibles para iniciar el prototipo. |
| Demostración interna | 8 | Recorrido integrado disponible y primeras pruebas registradas. |
| Cierre de E1 | 10 | Resultados contrastados con el plan; riesgos y trabajo siguiente revisados. |

La coordinación comprobará cada día el avance, el esfuerzo consumido y los obstáculos. Un cambio de alcance indicará su motivo, su efecto y el trabajo aplazado. El equipo mantendrá identificadas las versiones de los productos revisados.

## 10 Productos y criterios de evaluación

| Producto previsto | Responsable | Criterio para su revisión |
| --- | --- | --- |
| Modelo de casos de uso | P1 | Representa los objetivos del apartado 4. Sus participantes y relaciones se justifican con requisitos. Declara la cobertura parcial. |
| Escenarios y preguntas de requisitos | P1 | Distinguen verificación, aprobación y autorización. Identifican los acuerdos necesarios para el prototipo. |
| Descripción inicial de arquitectura | P2 | Explica las decisiones propuestas, los requisitos que las condicionan y los riesgos que siguen abiertos. |
| Prototipo integrado | P2 | Permite completar el recorrido previsto y repetir las comprobaciones de permisos con datos ficticios. |
| Informe de pruebas | P3 | Identifica la versión probada, el entorno, los datos y los resultados. Incluye fallos y límites. |
| Evaluación de E1 | P1 | Compara objetivos, alcance, esfuerzo y coste previstos con los resultados. Registra riesgos, cambios y trabajo siguiente. |

La revisión funcional comprobará que una cuenta pendiente, un perfil profesional pendiente y una relación de cuidado sin autorización no se confunden. Las pruebas de permisos deben mostrar resultados tanto de acceso permitido como de acceso denegado.

La revisión técnica comprobará el recorrido integrado, el fallo de correo y las mediciones previstas. Si el rendimiento no alcanza el objetivo, el equipo registrará el resultado y propondrá una acción. No declarará resuelto el riesgo sin evidencia.

La revisión del modelo comprobará que los elementos representan objetivos y participantes externos. Cada decisión debe tener respaldo. La revisión no exigirá que un FR produzca un caso de uso independiente.

## 11 Evaluación y continuidad previstas

La evaluación se realizará en el día 10. Este plan fija cómo se evaluará E1; no registra resultados ya obtenidos.

La coordinación comparará el trabajo realizado con este plan. Registrará los objetivos alcanzados, las desviaciones de esfuerzo y coste, las incidencias y las lecciones aprendidas. El equipo revisará qué riesgos se han reducido y qué riesgos permanecen abiertos.

La evaluación se conservará como un documento separado. Indicará si se puede continuar con la siguiente iteración o si antes se necesita trabajo adicional. Los pendientes de E1 y los riesgos del sistema completo servirán para seleccionar ese trabajo.

El modelo de casos de uso conservará sus elementos al incorporar otras vistas. La arquitectura podrá cambiar cuando aparezcan nuevas evidencias. E1 no permite declarar completados los módulos de usuarios y ayuda ni aprobar la arquitectura de todo el sistema.

## 12 Documentos de referencia

- [Documento de Visión y Alcance](../vision/vision_y_alcance.md).
- [SRS](../requisitos/srs.md) y [catálogo canónico de requisitos](../requisitos/catalogo-requisitos.md).
- [Acta de captura de requisitos de UR-01](../captura/acta-captura-requisitos-ur-01.md).
- [Acta de captura de requisitos generales](../captura/acta-captura-requisitos-generales.md).
- [Acta de acuerdos técnicos y operativos](../captura/acta-acuerdos-tecnicos-operativos.md).
