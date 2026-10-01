# Acta de acuerdos técnicos y operativos de la primera versión

| Campo | Valor |
| --- | --- |
| Estado | Validada |
| Fecha del acta | 24/09/2026 |
| Producto | Plataforma Simbiosis |
| Documentos de referencia | Documento de Visión y Alcance, acta de A03, SRS, catálogo de requisitos y resultados de las actividades de descubrimiento |
| Finalidad | Consolidar los acuerdos alcanzados sobre el funcionamiento, la operación y las condiciones de uso de la primera versión. |

## Fuentes de los acuerdos

| Actividad o fuente | Aportación |
| --- | --- |
| Entrevistas con representantes de la organización | Necesidades operativas, prioridades y criterios de aceptación. |
| Grupos de discusión con personas implicadas en la plataforma | Expectativas sobre acceso, moderación, contenidos y uso de la información. |
| Análisis del Documento de Visión y Alcance, el acta de A03, la SRS y el catálogo de requisitos | Contexto confirmado, decisiones previas, responsabilidades y relaciones entre requisitos. |
| Análisis y consolidación por el equipo de requisitos | Contraste de las aportaciones de las distintas fuentes, resolución de discrepancias y fijación de los valores acordados. |

## 1. Alcance y procedencia de los acuerdos

Este documento consolida los resultados de entrevistas, grupos de discusión y análisis de documentación realizados en diferentes fechas. Concreta aspectos que estaban formulados de manera general o habían quedado pendientes en el Documento de Visión y Alcance, el acta de A03 y otros artefactos del proyecto.

Los acuerdos se aplican a la primera versión de la plataforma. Cuando un acuerdo de esta acta concreta una formulación anterior, prevalece esta acta.

Los 500 usuarios activos mensuales indicados en el Documento de Visión y Alcance son un criterio de éxito del negocio. No representan el número de usuarios que utilizarán la plataforma al mismo tiempo.

Los acuerdos se recogen agrupados por los ámbitos que se trataron en las sesiones de trabajo, en el orden y con la argumentación con que se alcanzaron. Cada párrafo está numerado para que pueda citarse como procedencia.

## 2. Acuerdos

### 2.1. Capacidad, tiempos de respuesta y continuidad del servicio

**2.1.1.** Al valorar el crecimiento previsto de la comunidad, los representantes de la organización fijaron que la primera versión deberá admitir al menos 100 usuarios conectados al mismo tiempo. Pidieron también que el crecimiento de la carga no dependa del personal: la infraestructura podrá aumentar automáticamente los recursos disponibles cuando crezca la carga, y ese ajuste no requerirá la intervención del personal de la organización.

**2.1.2.** Para comprobar el comportamiento de la plataforma con esa carga se acordó una prueba de rendimiento que simulará 100 usuarios concurrentes y un mínimo de 10 operaciones por segundo durante 30 minutos. En esas condiciones, el 95 % de las operaciones de inicio de sesión, consulta del perfil, búsqueda de recetas, consulta de recetas y consulta del foro deberá completarse en un máximo de 2 segundos, y el 95 % de las operaciones de publicación de recetas, comentarios o mensajes, en un máximo de 3 segundos.

**2.1.3.** Para evitar que cada parte interpretase estos tiempos de un modo distinto, se acordó que se medirán desde que la plataforma recibe la solicitud hasta que envía la respuesta completa, sin incluir el tiempo necesario para transferir archivos ni el tiempo de respuesta de servicios externos.

**2.1.4.** La formulación de un servicio disponible 24/7, recogida en los documentos anteriores, se concretó del siguiente modo. La plataforma ofrecerá servicio durante las 24 horas del día, con una disponibilidad mínima del 99,5 % en cada mes natural. La disponibilidad se medirá mediante una comprobación automática realizada cada cinco minutos desde un sistema externo a la plataforma, y una comprobación se considerará fallida cuando no sea posible acceder a la plataforma o utilizar sus funciones principales.

**2.1.5.** En cuanto al mantenimiento, los periodos de mantenimiento planificado no se incluirán en el cálculo de la disponibilidad si se anuncian con al menos 48 horas de antelación y no superan cuatro horas en un mismo mes; el tiempo de mantenimiento que supere ese límite mensual sí se contará como tiempo de indisponibilidad. La organización pidió además que los mantenimientos planificados se realicen, siempre que sea posible, entre las 02:00 y las 06:00, hora peninsular española.

### 2.2. Protección de la información y ciclo de vida de las cuentas

**2.2.1.** Se acordó realizar al menos una copia de seguridad diaria de la información de salud y de las recetas. Después de un incidente grave, la plataforma deberá recuperar sus funciones principales en un máximo de cuatro horas desde la declaración del incidente, y la pérdida de información no podrá superar las 24 horas anteriores al incidente.

**2.2.2.** Para tener garantías de que las copias de seguridad sirven cuando se necesitan, se comprobarán mediante una prueba de restauración al menos una vez cada tres meses. Cada prueba deberá dejar constancia de la fecha, el resultado y las incidencias encontradas.

**2.2.3.** En los grupos de discusión se trató quién puede acceder a la información de salud de los pacientes. Se acordó que un cuidador solo tendrá acceso a la información de salud de un paciente mientras exista una asociación vigente entre ambos. En el caso de los nutricionistas, la revocación de su acceso a los datos de salud corresponderá al paciente.

**2.2.4.** También se abordó qué ocurre con las cuentas de cuidador que dejan de estar asociadas a pacientes. Una cuenta de cuidador que permanezca tres meses sin asociación con ningún paciente se considerará inactiva y, si permanece un año completo sin asociación con ningún paciente, se eliminará. Aun así, la organización conservará el contenido publicado por un cuidador después de eliminar su cuenta.

### 2.3. Acceso a la plataforma y aprobación de cuentas

**2.3.1.** Sobre la integración con una cuenta de Google, se acordó que la autenticación se realizará utilizando OAuth 2.0 u OpenID Connect sobre HTTPS y que la plataforma no almacenará la contraseña de Google. El cumplimiento se comprobará mediante una prueba de autenticación con una cuenta de prueba y la revisión de la configuración de la integración.

**2.3.2.** La organización quiere mantener el control sobre la incorporación de cuidadores y nutricionistas a la plataforma. Por ello, solo el coordinador podrá aprobar la cuenta de un cuidador, y solo el coordinador podrá aprobar la cuenta de un nutricionista.

### 2.4. Publicación de contenidos y experiencia de uso

**2.4.1.** Respecto a las recetas y al foro, la organización insistió en supervisar lo que se publica. Una receta solo podrá publicarse después de haber sido aprobada por un nutricionista, y el coordinador será responsable de revisar los reportes de contenido inapropiado. Cuando se elimine un contenido, su autor podrá apelar la decisión.

**2.4.2.** La formulación de una plataforma fácil de utilizar y accesible, recogida en los documentos anteriores, se concretó en que todas las pantallas y funciones incluidas en la primera versión deberán cumplir las Pautas de Accesibilidad para el Contenido Web, WCAG 2.2, con nivel de conformidad AA. La accesibilidad se evaluará antes de aceptar la primera versión y después de cualquier cambio importante en la interfaz, combinando una herramienta automática y una revisión manual.

**2.4.3.** La revisión manual comprobará, como mínimo, la navegación con teclado, el orden del foco, los textos alternativos, las etiquetas de los formularios, los mensajes de error, el contraste y el uso con lector de pantalla, e incluirá los recorridos de registro, inicio de sesión, búsqueda y consulta de recetas, publicación en el foro y consulta del perfil. La primera versión no se considerará aceptada mientras existan incumplimientos de nivel A o AA en las pantallas o recorridos evaluados.

**2.4.4.** La primera versión estará disponible en castellano y gallego, y la persona usuaria podrá cambiar el idioma de la interfaz entre ambos. Cuando se seleccione un idioma, los textos de navegación, formularios, validaciones y mensajes de la interfaz se mostrarán íntegramente en ese idioma. La comprobación se realizará revisando todas las pantallas y mensajes de la primera versión en ambos idiomas.

### 2.5. Plataforma cliente y despliegue

**2.5.1.** Se confirmó que el acceso a la plataforma se realizará mediante una interfaz web responsiva, sin que sea necesario instalar una aplicación móvil nativa ni una aplicación de escritorio independiente en el dispositivo de la persona usuaria. La interfaz cliente utilizará estándares web abiertos (HTML5, CSS y ECMAScript), no dependerá de plugins propietarios ni requerirá la instalación de software adicional en ese dispositivo.

**2.5.2.** La plataforma se desplegará en una infraestructura en la nube gestionada por un proveedor externo.

**2.5.3.** El cumplimiento de los acuerdos de los párrafos 2.5.1 y 2.5.2 se comprobará revisando la arquitectura, la configuración del despliegue, las dependencias del cliente y el acceso desde los navegadores compatibles.

## 3. Relación con los documentos anteriores

| Documento anterior | Concreción aportada por esta acta | Párrafos |
| --- | --- | --- |
| Crecimiento de la comunidad y escalado automático | Se fija la carga que debe soportar la primera versión y las condiciones de la prueba de rendimiento. | 2.1.1 a 2.1.3 |
| Servicio disponible 24/7 | Se fija el porcentaje mensual, la forma de medirlo y el tratamiento de los mantenimientos planificados. | 2.1.4, 2.1.5 |
| Copia diaria y recuperación ante desastres | Se fijan el tiempo máximo de recuperación, la pérdida máxima de datos y la prueba periódica de restauración. | 2.2.1, 2.2.2 |
| Plataforma fácil de utilizar y accesible | Se fija WCAG 2.2, nivel AA y el método de evaluación. | 2.4.2, 2.4.3 |
| 500 usuarios activos mensuales | Se confirma que es un criterio de éxito del negocio y no una carga concurrente. | Apartado 1 |
| Primera versión en castellano y gallego | Se concreta el cambio de idioma y la cobertura lingüística de los textos de la interfaz. | 2.4.4 |
| Plataforma web responsiva | Se concreta que no se exigirán aplicaciones nativas, aplicaciones de escritorio ni software adicional en el dispositivo cliente. | 2.5.1, 2.5.3 |
| Infraestructura en la nube | Se concreta que el despliegue será gestionado por un proveedor externo. | 2.5.2, 2.5.3 |
| Integración con una cuenta de Google | Se concreta el protocolo de autenticación, el uso de HTTPS y que no se almacenará la contraseña. | 2.3.1 |
| Funcionamiento de la comunidad y gestión de cuentas | Se concreta quién aprueba las cuentas y las recetas, quién revisa los reportes, en qué condiciones se accede a la información de salud y quién revoca ese acceso, la posibilidad de apelar, y qué ocurre con las cuentas de cuidador sin asociación y con el contenido que publicaron. | 2.2.3, 2.2.4, 2.3.2, 2.4.1 |

## 4. Trazabilidad y vigencia

Esta acta es fuente de los elementos que se incorporen al catálogo de requisitos de la plataforma Simbiosis. Cada elemento derivado de ella deberá conservar una referencia al párrafo del que procede.

Los valores acordados se aplican a la primera versión. Cualquier cambio deberá registrarse en una decisión posterior, con su fecha, justificación y efecto sobre los requisitos.
