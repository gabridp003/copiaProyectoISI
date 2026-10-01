# Proyecto Simbiosis

## Especificación de requisitos de software

**Versión:** 0.10  
**Fecha:** 23/09/2026  
**Estado:** Base documental con UR y FR consolidados; NFR y glosario pendientes  
**Destinatarios:** partes interesadas del proyecto

Este documento reúne la especificación de requisitos de software (SRS) de
Proyecto Simbiosis. El texto canónico de cada requisito se mantiene en el
catálogo de requisitos, al que esta SRS enlaza sin duplicarlo. El glosario forma
parte de esta SRS, en la sección 9.

En esta versión se fija la estructura y se incorpora el contexto confirmado en
el Documento de Visión y Alcance y en el acta de captura de A03. Los requisitos
de usuario y funcionales ya están consolidados en el catálogo. Los requisitos
no funcionales y el glosario permanecen pendientes. Ningún apartado pendiente
autoriza a completar información por suposición.

## Índice

1. [Introducción](#1-introducción)
2. [Descripción general](#2-descripción-general)
3. [Requisitos funcionales](#3-requisitos-funcionales)
4. [Requisitos de datos](#4-requisitos-de-datos)
5. [Requisitos de interfaz externa](#5-requisitos-de-interfaz-externa)
6. [Atributos de calidad](#6-atributos-de-calidad)
7. [Internacionalización y localización](#7-internacionalización-y-localización)
8. [Decisiones pendientes y exclusiones](#8-decisiones-pendientes-y-exclusiones)
9. [Glosario](#9-glosario)
10. [Modelos de análisis](#10-modelos-de-análisis)
11. [Trazabilidad y control de cambios](#11-trazabilidad-y-control-de-cambios)

## 1. Introducción

### 1.1 Propósito

Proyecto Simbiosis es una plataforma web colaborativa orientada a mejorar la
calidad de vida de personas con Enfermedades Inflamatorias Intestinales (EII)
mediante recetas adaptadas, información de salud y participación comunitaria.

Esta SRS describe qué debe proporcionar el producto y las condiciones que debe
cumplir. Los modelos de análisis ayudan a interpretar los requisitos, pero no
los sustituyen.

### 1.2 Convenciones del documento

- `BO-0X` identifica un objetivo de negocio.
- `UR-0X` identifica un requisito de usuario.
- `FR-0XX` identifica un requisito funcional.
- `NFR-0X` identifica un requisito no funcional.
- `UC-0X` identifica un caso de uso cuando sea necesario enlazarlo desde otro
  artefacto.

Los requisitos de usuario se redactan en voz activa y desde la perspectiva de
la persona usuaria: «El [tipo de usuario] podrá [acción] [finalidad]». Cada UR
expresa una única acción o necesidad de alto nivel; no mezcla acciones distintas
ni anticipa decisiones de diseño o implementación.

Los requisitos funcionales se redactan en voz activa con el patrón «El sistema
debe…». Cada FR expresa una única responsabilidad del sistema y es verificable.
Un FR puede estar asociado a más de un UR cuando ambos necesitan la misma
responsabilidad del sistema.

Los requisitos no funcionales describen cómo debe funcionar el sistema en
términos de calidad, rendimiento, seguridad, disponibilidad u otras
restricciones. Se redactan como una única condición medible y verificable,
indicando una métrica o estándar y, cuando corresponda, el umbral, la unidad,
el período o condiciones de medida y el método de comprobación. Evitan términos
vagos como «rápidamente», «fácilmente», «seguro» o «adecuado». Cada NFR señala
además si su ámbito es global o está ligado a un UR o FR concreto.

Los identificadores no se reutilizan ni se renumeran al modificar el
documento. Los cambios aceptados conservan la identidad del requisito y quedan
registrados en la sección 11.

### 1.3 Alcance

El producto cubre una plataforma web responsiva para compartir, buscar y
gestionar recetas, apoyar la interacción entre pacientes, cuidadores y
nutricionistas, y ofrecer contenido relacionado con alimentación y hábitos de
vida saludable.

Quedan fuera del alcance actual la integración con historias clínicas
electrónicas, los planes dietéticos automáticos, el seguimiento o los diarios
de alimentación, las recomendaciones médicas o clínicas automáticas, el
desarrollo de aplicaciones móviles nativas y una aplicación de escritorio
independiente.

### 1.4 Referencias

- [Documento de Visión y Alcance](../vision/vision_y_alcance.md), v2.4.
- [Catálogo de requisitos](./catalogo-requisitos.md), registro canónico de UR,
  FR y NFR.
- [Acta de captura de requisitos generales](../captura/acta-captura-requisitos-generales.md) y
  [actas de entrevistas posteriores, como las de UR-01 y UR-05](../captura/README.md), evidencia de procedencia.
- [Guía rápida para redacción de requisitos y casos de uso](../referencias/guia-rapida-redaccion-requisitos-y-casos-de-uso.md), convenciones de redacción aplicadas en esta SRS.
- [Modelos de análisis](../modelos/README.md).

## 2. Descripción general

### 2.1 Perspectiva del producto

Proyecto Simbiosis es una plataforma en línea orientada a la alimentación y al
apoyo comunitario de personas con EII. El producto debe ofrecer recetas
adaptadas, facilitar la colaboración de nutricionistas y permitir interacciones
entre las personas usuarias.

### 2.2 Clases de usuario

Las clases de usuario identificadas hasta ahora son:

- paciente;
- cuidador;
- nutricionista;
- coordinador.

El rol de nutricionista reúne las funciones y permisos que inicialmente se
atribuían por separado a médicos y nutricionistas. La SRS v1.0 precisará los
permisos y las necesidades específicas de cada clase mediante los requisitos
de usuario y funcionales correspondientes.

### 2.3 Entorno operativo

La solución prevista es una plataforma web responsiva, utilizable desde
ordenadores y dispositivos móviles con conexión a internet. Debe funcionar en
navegadores actuales de uso habitual; se consideran Chrome, Safari, Brave,
DuckDuckGo, Opera y Edge.

Las versiones concretas compatibles y otros límites técnicos no están
confirmados todavía y no se especifican en esta versión.

### 2.4 Restricciones de diseño e implementación

El proyecto tiene un plazo inicial de seis meses, un presupuesto limitado a
90.000 € y un equipo reducido de desarrollo, diseño y análisis. Estas
condiciones acotan el proyecto, pero no son por sí mismas requisitos
funcionales.

La infraestructura se desplegará en la nube y será gestionada por un proveedor
externo. Las decisiones de tecnología, arquitectura, proveedor concreto y
diseño de base de datos quedan fuera del alcance de esta SRS mientras no estén
confirmadas.

### 2.5 Suposiciones y dependencias

- Las personas usuarias disponen de conexión a internet y de un dispositivo
  compatible con un navegador web.
- Se prevé participación activa de nutricionistas en la plataforma.
- Se presupone familiaridad básica con plataformas web colaborativas.

Estas condiciones deberán revisarse si un cambio de alcance o una fuente nueva
las contradice.

## 3. Requisitos funcionales

El [catálogo de requisitos](./catalogo-requisitos.md) contiene el texto
canónico de los requisitos de usuario y funcionales. Es la única fuente de
verdad para sus identificadores, redacción, asociaciones, fuentes y estado.

Esta sección explica cómo se organizan esos requisitos dentro de la SRS y cómo
se relacionan con los modelos de análisis. No reproduce el texto de los UR ni
de los FR.

### 3.1 Requisitos de usuario

El catálogo agrupa los UR por necesidad de usuario. Cada UR enlaza a los FR que
concretan la responsabilidad necesaria del sistema.

### 3.2 Requisitos funcionales asociados

El catálogo registra cada FR una sola vez, con sus asociaciones a uno o varios
UR. Cuando exista un modelo, el FR podrá enlazar también al caso de uso o al
apartado de modelo que lo interpreta.

### 3.3 Reglas de trazabilidad funcional

Cada requisito funcional indicará el requisito o requisitos de usuario a los
que está asociado. Cuando un requisito funcional responda a varias necesidades,
se registrará una única vez y se enlazará desde todas ellas.

## 4. Requisitos de datos

Esta sección recogerá los requisitos confirmados sobre datos personales, datos
de salud, integridad, conservación, exportación, eliminación y auditoría.

El modelo de dominio conceptual que se elabore en L10 y L11 será un modelo de
análisis. No se interpretará automáticamente como diseño de base de datos.

Los requisitos confirmados sobre datos se registrarán como FR o NFR en el
[catálogo de requisitos](./catalogo-requisitos.md), según expresen una
responsabilidad del sistema o una condición de calidad o restricción.

## 5. Requisitos de interfaz externa

### 5.1 Interfaces de usuario

La plataforma debe ser web responsiva. Los requisitos concretos de interfaz,
accesibilidad y navegación se incorporarán cuando estén confirmados.

### 5.2 Interfaces de software

Se han identificado como apoyos externos una cuenta de Google para
autenticación y un servicio de correo electrónico para verificación,
recuperación de credenciales y notificaciones. Los protocolos, formatos y
condiciones de integración permanecen pendientes de especificación.

### 5.3 Interfaces de hardware

No se han identificado interfaces hardware específicas en el alcance actual.

### 5.4 Interfaces de comunicación

No se han confirmado todavía requisitos específicos de comunicación más allá
del uso de una plataforma web conectada a internet y de los servicios de correo
identificados en la sección 5.2.

## 6. Atributos de calidad

Los requisitos no funcionales canónicos se mantienen en el
[catálogo de requisitos](./catalogo-requisitos.md). Cada uno incluye
identificador, condición comprobable, fuente y ámbito global o local.

Los atributos que se revisarán incluyen rendimiento, seguridad, disponibilidad
y fiabilidad, usabilidad y accesibilidad, compatibilidad y portabilidad, y
obligaciones legales y normativas.

Los requisitos legales y normativos se registrarán como NFR y no se duplicarán
en la sección 8.

### 6.1 Organización por atributo

El catálogo clasifica los NFR por rendimiento; seguridad y privacidad;
disponibilidad y fiabilidad; usabilidad y accesibilidad; compatibilidad y
portabilidad; y obligaciones legales y normativas.

### 6.2 Obligaciones legales y normativas

La plataforma trata datos personales y puede tratar datos de salud. Las
obligaciones aplicables se concretarán como requisitos verificables conforme a
la información confirmada para el proyecto.

## 7. Internacionalización y localización

La primera versión estará disponible en castellano y gallego. El inglés se
incorporará en una fase posterior, sin fecha confirmada. Los formatos regionales
y las condiciones verificables que correspondan se concretarán en el catálogo.

## 8. Decisiones pendientes y exclusiones

Esta sección registra preguntas abiertas que afectan a la especificación. Una
pregunta pendiente no es un requisito y no debe transformarse en una decisión
sin una fuente confirmada.

| Identificador | Decisión o pregunta | Fuente | Estado |
| --- | --- | --- | --- |
| DP-01 | Precisar versiones compatibles de los navegadores de uso habitual. | Acta de A03, §7.4 | Pendiente |
| DP-02 | Precisar protocolos y formatos de las integraciones externas. | Sección 5.2 de esta SRS | Pendiente |
| DP-03 | Precisar formatos regionales y condiciones verificables de localización. | Acta de A03, §7.2 | Pendiente |

## 9. Glosario

Este apartado contiene las definiciones vigentes de los términos del dominio
que pueden interpretarse de más de una manera. Cada entrada indicará su fuente
para conservar la procedencia de la definición. El catálogo de requisitos podrá
enlazar a los términos de esta sección, pero no los definirá de nuevo.

| Término | Definición en Proyecto Simbiosis | Fuente |
| --- | --- | --- |

## 10. Modelos de análisis

Los modelos hacen visible la interpretación de los requisitos y deben mantener
trazabilidad hacia ellos. No sustituyen el texto de los requisitos.

### 10.1 Modelo de casos de uso

El repositorio incorporará un diagrama común de casos de uso y las descripciones
esenciales de los casos seleccionados.

### 10.2 Diagramas de actividad

Se incorporarán diagramas de actividad para procesos seleccionados y se
registrarán los huecos que el modelo permita descubrir.

### 10.3 Modelo de dominio conceptual

El modelo de dominio conceptual se elaborará y refinará progresivamente,
incluidas las asociaciones, multiplicidades y organización conceptual en
paquetes.

## 11. Trazabilidad y control de cambios

La trazabilidad se usará para justificar decisiones y analizar el impacto de un
cambio; no se exigirá como una matriz exhaustiva de todos los elementos. Las
relaciones atómicas se mantienen en el
[catálogo de requisitos](./catalogo-requisitos.md): objetivo de negocio → UR;
UR → FR; y FR o NFR → modelo, historia o criterio de aceptación.

Esta estructura permite analizar una solicitud de cambio y proponer una
evolución controlada de la línea base. Las historias de usuario, el backlog,
las tareas y la Definition of Done se gestionan fuera de la SRS, aunque puedan
mantener enlaces hacia sus requisitos de origen.

## Estado de la versión

Esta versión 0.10 define la arquitectura documental, el contexto confirmado y
las convenciones de redacción de UR, FR y NFR. Incorpora los acuerdos de A03
sobre el rol de nutricionista, el alcance, los idiomas, los navegadores y la
infraestructura. También separa la SRS, que explica la especificación integrada,
del catálogo, que es la fuente canónica de los requisitos atómicos. Los
requisitos de usuario y funcionales ya están consolidados en el catálogo. El
glosario forma parte de esta SRS.

Antes de publicar la línea base v1.0 se consolidarán los requisitos no
funcionales, el glosario y los enlaces de trazabilidad.
