# Proyecto SIMBIOSIS · Documento de Visión y Alcance

| Campo | Valor |
| --- | --- |
| Versión | 2.4 |
| Fecha | 21/09/2026 |
| Fuente | [Página de Notion](https://app.notion.com/p/7ef13df4e4514a7eb9e661e88f76f4c1) |
| Estado de la fuente | No verificada en Notion |

## Historial de versiones

| Versión | Fecha | Cambios |
| --- | --- | --- |
| 1.0 | 19/09/2024 | — |
| 1.1 | 26/09/2024 | Se añaden funcionalidades principales o módulos. |
| 1.2 | 01/09/2025 | Se han modificado levemente algunos apartados. Se han añadido aclaraciones. |
| 2.0 | 09/09/2025 | Se ha modificado la estructura del documento y se han corregido y añadido apartados, para adecuarlo al tipo de Documento de Visión utilizado en el libro *Software Requirements*, de Wiegers y Beatty. |
| 2.1 | 29/07/2026 | Edición en Word para distribución al alumnado (`Proyecto_Simbiosis_documento_vision_alcance.docx`), con el contenido íntegro de la versión 2.0, incluidos los recuadros didácticos. Se unifica la nomenclatura de requisitos a UR y FR, conforme a la convención del curso, y se corrige la cita bibliográfica: Wiegers, no Wieger. |
| 2.3 | 21/09/2026 | Se añade el apartado 2.5, «Requisitos legales y normativos», como fuente común para identificar las obligaciones de protección de datos aplicables a Proyecto Simbiosis. La copia Word vigente, v2.2, no se actualiza todavía. |
| 2.4 | 21/09/2026 | El recuadro didáctico del apartado 2.5 pasa a explicar el papel de los requisitos legales y normativos en el Documento de Visión, sin referencias a una sesión concreta. La copia Word vigente, v2.2, no se actualiza todavía. |

## 1. Requisitos de negocio

> **¿Qué son los requisitos de negocio?**
>
> Describen los objetivos estratégicos que la organización espera alcanzar con el sistema. Representan el **por qué** del proyecto: el valor que se busca generar y los beneficios que justifican su desarrollo. A diferencia de los requisitos de usuario o funcionales, no detallan tareas ni características técnicas, sino que marcan la dirección que guiará la definición posterior de las necesidades de los usuarios y de las funcionalidades del sistema.

### 1.1. Objetivos de negocio

Los siguientes objetivos de negocio se derivan de la visión y los objetivos estratégicos del proyecto. Establecen el **por qué** del sistema Simbiosis y definen el valor que la organización busca alcanzar con su desarrollo:

- **BO-01:** La organización busca mejorar la calidad de vida de los pacientes con Enfermedades Inflamatorias Intestinales (EII) mediante el acceso a recetas adaptadas a sus necesidades de salud.
- **BO-02:** La organización pretende ofrecer a los pacientes con EII una herramienta que les permita gestionar mejor su dieta para controlar los síntomas de la enfermedad.
- **BO-03:** La organización busca asegurar la calidad clínica de las recetas compartidas en la aplicación.
- **BO-04:** La organización busca fomentar la colaboración entre pacientes, cuidadores y profesionales de la salud, creando una comunidad activa que comparta conocimiento y experiencias.
- **BO-05:** La organización quiere fomentar una comunidad activa y de apoyo mutuo para pacientes con EII.
- **BO-06:** La organización debe asegurar un entorno seguro y confiable para la comunidad EII.

> **¿Qué es un objetivo de negocio?**
>
> Un objetivo de negocio es una meta cuantificable y medible que la organización busca alcanzar con el desarrollo de un sistema o proyecto. Define el propósito y el valor esperado en términos estratégicos, como mejorar la calidad de vida de los usuarios, aumentar la eficiencia, reducir costes o garantizar la seguridad. No describe funcionalidades ni requisitos técnicos, sino el «para qué» del proyecto. Debe establecer el contexto y permitir la medición de los beneficios esperados.

### 1.2. Visión o propuesta de valor

El sistema *Simbiosis* será una plataforma en línea colaborativa, diseñada para ayudar a pacientes con Enfermedades Inflamatorias Intestinales (EII) a controlar sus síntomas a través de una alimentación adecuada. La plataforma permitirá a los pacientes, cuidadores, nutricionistas y médicos compartir, buscar y personalizar recetas según las necesidades alimenticias específicas de los usuarios. El objetivo principal es mejorar la calidad de vida de los pacientes, proporcionando un acceso fácil a recetas validadas y adaptadas a sus condiciones de salud. En concreto:

- Permitirá apoyar a los pacientes con EII ofreciéndoles herramientas para gestionar mejor su dieta, contribuyendo a la mejora de su calidad de vida.
- Permitirá la contribución de profesionales de la salud, como nutricionistas y médicos, asegurando la calidad y adecuación clínica de las recetas compartidas.
- Fomentará la colaboración entre pacientes, cuidadores y profesionales para compartir recetas que se ajusten a las necesidades y restricciones dietéticas de la comunidad EII.
- Permitirá crear una comunidad interactiva donde los usuarios puedan calificar, comentar y compartir recetas, promoviendo un ambiente colaborativo y de apoyo mutuo.

> **¿Qué es la visión o propuesta de valor?**
>
> Es una declaración clara y concisa que describe los **beneficios únicos** o el **valor** que un producto, servicio o sistema ofrece a sus usuarios o clientes. Responde a la pregunta: «¿Por qué debería un usuario elegir este producto en lugar de otro?»

### 1.3. Criterios de éxito

- **Uso activo de la plataforma:** se considera exitoso si en los tres primeros meses de lanzamiento la plataforma cuenta con al menos 500 usuarios activos mensuales.
- **Satisfacción de los usuarios:** se realizarán encuestas de satisfacción, buscando que al menos el 80 % de los usuarios estén satisfechos con la funcionalidad del sistema.
- **Contribución de profesionales:** al menos el 10 % de las recetas disponibles en la plataforma deben ser aportadas por profesionales de la salud, nutricionistas y médicos, en los primeros seis meses.
- **Calificaciones y comentarios positivos:** las recetas deben recibir una valoración positiva en al menos el 75 % de las interacciones de los usuarios.

> **¿Qué son los criterios de éxito?**
>
> Indican cómo se evaluará el resultado del proyecto: usuarios activos, satisfacción, contribución de profesionales y valoraciones. Son indicadores de calidad y métricas de validación, no requisitos del sistema.

### 1.4. Riesgos de negocio

- **Bajo nivel de adopción por parte de los usuarios:** si los pacientes y cuidadores no utilizan activamente la plataforma, la inversión en su desarrollo no logrará los resultados esperados.
- **Falta de participación de profesionales de la salud:** la calidad de las recetas puede verse afectada si los nutricionistas y médicos no contribuyen de manera significativa.
- **Problemas técnicos o de escalabilidad:** la plataforma debe ser robusta y escalar adecuadamente para manejar un crecimiento en la base de usuarios sin comprometer la experiencia de usuario.

> Los riesgos señalan posibles problemas que podrían comprometer el éxito del proyecto. Se utilizan para planificar su gestión, no para definir requisitos.

### 1.5. Supuestos y dependencias

- Los usuarios tendrán acceso a dispositivos con conexión a internet para utilizar la plataforma, siendo prioritaria la versión web responsiva para su uso en móviles.
- Los profesionales de la salud estarán dispuestos a contribuir activamente con recetas y participar en la moderación del contenido.
- Los usuarios estarán familiarizados con el uso básico de plataformas web colaborativas y redes sociales para interactuar con el sistema.

> Las suposiciones son condiciones que se consideran ciertas en la fase inicial, aunque no estén completamente verificadas. Las dependencias son factores externos de los que el proyecto depende. Ambas deben revisarse a lo largo del proyecto.

## 2. Alcance y limitaciones del proyecto

### 2.1. Alcance

El proyecto *Simbiosis* abarca el desarrollo de una plataforma software centrada en mejorar la calidad de vida de los pacientes con EII a través de la alimentación y el apoyo comunitario.

**Incluido en el alcance:**

- La plataforma debe proporcionar herramientas que ayuden a los pacientes a gestionar mejor su dieta, facilitando el acceso a recetas adecuadas para controlar los síntomas de la EII.
- Se permitirá la participación de nutricionistas y médicos en la creación y validación de recetas, de forma que el contenido disponible tenga una garantía de calidad y adecuación clínica.
- Se fomentará la colaboración entre pacientes, cuidadores y profesionales de la salud, con el objetivo de compartir recetas y conocimientos adaptados a las restricciones dietéticas de la comunidad con EII.
- La plataforma ofrecerá mecanismos de interacción entre los usuarios, por ejemplo comentar, valorar o recomendar recetas, que permitan generar un entorno de apoyo mutuo y mejora continua del contenido.
- El sistema deberá estar disponible desde distintos dispositivos, ordenador y móvil, priorizando un diseño web responsivo y seguro.

**Excluido del alcance:**

- La integración con sistemas externos de historia clínica electrónica.
- El seguimiento automático de la dieta o la conexión con dispositivos de salud.
- El desarrollo de aplicaciones móviles nativas; se prioriza la accesibilidad web responsiva.

> **¿Qué es el alcance?**
>
> El alcance establece los límites de lo que se va a desarrollar: qué objetivos, necesidades y características se incluyen y cuáles quedan fuera. Ofrece un marco compartido entre cliente y equipo de desarrollo y sirve como base para la planificación de requisitos, plazos y recursos.

### 2.2. Características principales

Las características de la plataforma se agruparán en los siguientes módulos funcionales:

1. **Gestión de usuarios.** Incluirá las funcionalidades relacionadas con el registro, autenticación y gestión de perfiles de los usuarios en la plataforma.
2. **Foro.** Incluirá las funcionalidades del foro colaborativo donde los usuarios pueden interactuar, compartir información y colaborar.
3. **Gestión de datos de salud.** Funcionalidades que permitirán a los pacientes introducir y gestionar sus datos fisiológicos y de salud de manera segura y organizada.
4. **Gestión de recetas.** Incluirá las funcionalidades relacionadas con la creación, publicación, búsqueda, valoración y gestión de recetas en la plataforma.
5. **Gestión de publicaciones de salud.** Incluirá las funcionalidades para que los profesionales de la salud creen y difundan consejos de vida saludable en la plataforma.
6. **Moderación de contenidos.** Funcionalidades que garantizan un entorno seguro y apropiado dentro de la plataforma.
7. **Guía interactiva.** Funcionalidad de ayuda a los usuarios para comprender y utilizar eficientemente todas las funcionalidades disponibles.

> **¿Qué es un módulo funcional?**
>
> Un módulo funcional es un bloque de alto nivel que agrupa funcionalidades relacionadas del sistema. Los módulos identificados en esta fase inicial orientan el diseño y la planificación, pero pueden evolucionar al obtener nueva información de las partes interesadas.

### 2.3. Entregables

- **Plataforma web funcional Simbiosis**, accesible desde dispositivos móviles y de escritorio, que incluya todas las funcionalidades clave descritas.
- **Documentación técnica y de usuario** que explique cómo utilizar el sistema y cómo los usuarios pueden crear, filtrar y compartir recetas.
- **Sistema de retroalimentación** para que los usuarios puedan calificar y comentar las recetas, y para que los coordinadores de la plataforma supervisen su calidad.

> Los entregables son los productos finales del proyecto. No son requisitos de usuario ni funcionales, aunque pueden contener información de contexto relacionada.

### 2.4. Restricciones y limitaciones

- **Tiempo:** el desarrollo de la plataforma debe completarse en un plazo de seis meses desde la fecha de inicio del proyecto.
- **Presupuesto:** el proyecto tiene un presupuesto limitado de 90.000 €, que debe cubrir el desarrollo, diseño, pruebas e implementación inicial de la plataforma.
- **Recursos humanos:** el equipo de desarrollo estará limitado a un número reducido de ingenieros de software, diseñadores y analistas de negocio.

> Estas restricciones marcan límites de tiempo, presupuesto y recursos. Son contexto de planificación y no requisitos funcionales o de usuario.

### 2.5. Requisitos legales y normativos

La plataforma trata datos personales y puede tratar datos de salud. Estos últimos tienen una protección reforzada. Para este caso, el marco de referencia es el Reglamento General de Protección de Datos (RGPD) y, en España, la Ley Orgánica 3/2018 de Protección de Datos Personales y garantía de los derechos digitales.

Las obligaciones que proceden de una ley o una norma se registran en el catálogo como requisitos no funcionales (NFR), no como reglas de negocio. Esta sección permite identificarlas. No sustituye una revisión jurídica antes de desplegar el sistema.

| Obligación aplicable | Qué debe tener en cuenta Proyecto Simbiosis |
| --- | --- |
| Tratamiento de datos de salud | Antes de recoger o usar datos de salud, la organización debe definir y documentar la base jurídica y la condición que permite tratar esta categoría de datos. El sistema no debe tratar esos datos hasta que esa decisión esté aprobada. |
| Finalidad, minimización y conservación | El sistema solo debe recoger los datos necesarios para una finalidad definida. La organización debe establecer cuánto tiempo se conservan y cuándo se eliminan o anonimizan. Si falta ese plazo, se registra como decisión pendiente; no se inventa. |
| Información y derechos de las personas | Antes de recoger datos, la plataforma debe informar de forma clara sobre quién los trata, para qué y cómo pueden las personas ejercer sus derechos. Debe prever mecanismos para atender, cuando correspondan, solicitudes de acceso, rectificación, supresión, limitación, oposición y portabilidad. |
| Protección desde el diseño y seguridad | La solución debe incorporar medidas técnicas y organizativas adecuadas al riesgo. El diseño debe considerar, entre otros aspectos, el control de acceso, la protección de los datos y la recuperación ante incidentes. Las medidas concretas se decidirán en fases posteriores. |
| Evaluación antes del despliegue | Antes de poner en producción funciones que traten datos de salud, la organización debe valorar si el tratamiento puede generar un riesgo alto y si exige una evaluación de impacto en protección de datos. |

**Fuentes de referencia:** [Reglamento (UE) 2016/679, artículos 5, 9, 12–15, 25, 32 y 35](https://eur-lex.europa.eu/legal-content/ES/TXT/?uri=CELEX:32016R0679) y [Ley Orgánica 3/2018, de Protección de Datos Personales y garantía de los derechos digitales](https://www.boe.es/buscar/act.php?id=BOE-A-2018-16673).

> Los requisitos legales y normativos son obligatorios porque los impone una ley, norma o autoridad competente. En el catálogo se registran como NFR y pueden afectar al tratamiento de datos, seguridad, conservación de información o derechos de las personas.

## 3. Contexto de negocio

### 3.1. Partes interesadas

- **Pacientes con EII:** usuarios principales del sistema, que buscan recetas personalizadas para mejorar su dieta y controlar los síntomas de su enfermedad.
- **Cuidadores:** familiares o profesionales que asisten a los pacientes en la gestión de su dieta, actuando como usuarios secundarios que buscan y administran recetas en nombre de los pacientes.
- **Nutricionistas y médicos:** profesionales de la salud que contribuyen con recetas especializadas y validan la calidad de las recetas disponibles en la plataforma.
- **Representantes de la organización sin ánimo de lucro:** partes interesadas clave que impulsan la creación del proyecto y velan por su alineación con la misión de mejorar la vida de los pacientes con EII.
- **Coordinador:** usuario responsable de supervisar la actividad en la plataforma. Gestiona reportes de contenido inadecuado, aplica reglas de uso, apoya el correcto funcionamiento de la comunidad y gestiona cuentas de usuario, incluida la aprobación, suspensión y eliminación de cuentas. La adscripción organizativa del coordinador se decidirá en la fase de despliegue.

> Una parte interesada es cualquier persona, grupo u organización que tiene interés, influencia o se ve afectado por un proyecto de software. Puede aportar necesidades, expectativas y requisitos.

### 3.2. Prioridades del proyecto

Las partes interesadas han definido las prioridades del proyecto en torno a cinco dimensiones: características, calidad, cronograma, coste y personal. Cada dimensión se clasifica como controlador, restricción o parámetro libre.

- **Características:** **controlador**. La plataforma debe incluir las funcionalidades clave necesarias para cumplir los objetivos de negocio y responder a las necesidades de pacientes, cuidadores y profesionales de la salud.
- **Calidad:** **controlador**. La seguridad, fiabilidad y validación clínica de las recetas no pueden comprometerse. La calidad del contenido y de la experiencia de usuario es crítica para generar confianza y fomentar la adopción.
- **Cronograma:** **restricción**. El desarrollo debe completarse en un plazo máximo de seis meses.
- **Coste:** **restricción**. El presupuesto disponible de 90.000 € marca un límite claro para la asignación de recursos y el alcance del desarrollo.
- **Personal:** **parámetro libre**. Aunque el equipo de desarrollo cuenta con un tamaño reducido, existe cierta flexibilidad para asignar roles y redistribuir esfuerzos según las necesidades de cada fase.

Esta priorización permitirá tomar decisiones fundamentadas cuando surjan conflictos o cambios, sin comprometer los límites de tiempo y presupuesto.

### 3.3. Condiciones de despliegue

El despliegue de la plataforma Simbiosis debe planificarse cuidadosamente para garantizar un funcionamiento estable desde el primer día y facilitar la adopción por parte de los distintos perfiles de usuario.

#### Acceso de los usuarios

- La plataforma será accesible a través de un navegador web desde cualquier dispositivo con conexión a internet, priorizando el acceso móvil gracias a un diseño web responsivo.
- Los usuarios principales, pacientes, cuidadores y profesionales de la salud, están geográficamente dispersos, aunque mayoritariamente en un mismo huso horario. Se garantiza disponibilidad 24/7 para permitir la interacción en cualquier momento.

#### Infraestructura técnica

- El sistema se desplegará en una infraestructura en la nube, con capacidad de escalado automático para soportar picos de carga en función del crecimiento de la comunidad.
- Se requerirá configurar mecanismos de copia de seguridad diaria y recuperación ante desastres para proteger la información de salud y recetas compartidas.
- Será necesaria la integración con un servicio seguro de mensajería y correo electrónico para notificaciones de alta de usuarios, recuperación de contraseña y confirmación de publicaciones.

#### Migración y datos iniciales

- No se prevé una migración masiva de datos históricos, dado que la plataforma comenzará sin repositorios previos.
- Será necesario preparar un conjunto inicial de recetas validadas por nutricionistas antes del lanzamiento. La forma de captación de este conjunto inicial y la vía de carga están pendientes de definir.

#### Capacitación y soporte

- Se desarrollarán materiales de formación en línea, guías interactivas y tutoriales en vídeo, para facilitar el aprendizaje de los usuarios en el uso de la plataforma. Los idiomas en que estará disponible la plataforma están pendientes de decidir en función del alcance geográfico definitivo del proyecto.
- El personal de soporte de la organización recibirá capacitación específica sobre la administración de cuentas y la moderación de contenidos.
- Los procesos de atención al usuario deberán ajustarse para canalizar dudas y reportes de incidencias técnicas de manera eficiente.

#### Procesos de negocio

- Se actualizarán los procedimientos internos de validación de recetas para incluir la revisión y aprobación dentro de la plataforma.
- Se definirán protocolos de moderación y de gestión de reportes de contenido inapropiado, alineados con las políticas de uso de la comunidad. Los mecanismos concretos de reporte de contenido inadecuado, a nivel de receta, comentario, publicación de salud y usuario, se definirán durante el desarrollo.

Estas consideraciones de despliegue establecen el marco técnico, organizativo y operativo necesario para que la solución funcione de manera efectiva y logre la adopción esperada por parte de la comunidad EII.
