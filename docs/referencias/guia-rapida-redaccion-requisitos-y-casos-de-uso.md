# Guía rápida para redacción de requisitos y casos de uso

| Versión | Fecha | Cambios |
| --- | --- | --- |
| 1.0 | (a completar) | Versión inicial: tipos de requisitos (BO/UR/FR/NFR/BR), las nueve características de la ISO/IEC/IEEE 29148:2018 y guía de nomenclatura de casos de uso. |
| 1.1 | 05/07/26 | Corregida la trazabilidad de los ejemplos de la sección 1.3: FR-001 y FR-002 pasan a derivar correctamente de UR-01 y UR-02 (antes UR-01 e Y FR-001 no coincidían). |
| 1.2 | 06/07/26 | Renumerados los epígrafes de la sección 3 (Niveles de formalidad, Ejemplos paso a paso, Errores frecuentes, Conclusión), antes numerados como 6–9 de forma discontinua con el resto de la sección; ahora 3.6–3.9. |
| 1.3 | 29/07/26 | Unificado el patrón del UR: los §3.3 y §3.7 usaban «debe poder» frente al «podrá» que fija el §1.2. Precisado en el §1.3 que un FR necesario para varios UR no se duplica: se escribe una vez y se referencia desde todos ellos, aunque en laboratorio lo habitual sea la asociación a un único UR. Publicada la edición en Word para el alumnado: `Guia_rapida_requisitos_y_casos_de_uso.docx`. |
| 1.4 | 22/09/26 | Se precisa que los FR expresan qué debe hacer el sistema, se corrigen ejemplos que contradecían las reglas de la guía y se establece la secuencia didáctica UR → FR → casos de uso como una opción de la asignatura, no como una regla universal. Se adapta el ejemplo de datos de salud al alcance de Proyecto Simbiosis. |

# 1. Tipos de requisitos

## **1.1. Requisitos u objetivos de Negocio (BO)**

- **Qué son:** Explican **por qué** la organización necesita el sistema y los **beneficios estratégicos** que espera lograr.
- **Cómo se escriben:** Enuncian objetivos de negocio de forma clara, no ambigua y sin entrar en detalles técnicos. En nuestro caso, se encuentran ya escritos en el Documento de Visión y Alcance.
- **Ejemplo:**
    - *BO-01: La organización busca reducir en un 30% el tiempo de atención al cliente mediante la digitalización de trámites.*

## **1.2. Requisitos de Usuario (UR)**

- **Qué son:** Describen **qué necesitan hacer los usuarios** con el sistema, desde su perspectiva, en un nivel alto.
- **Cómo se escriben:** Usan frases en voz activa, centradas en las acciones del usuario. Suelen formularse como *“El [tipo de usuario] podrá [acción] para [finalidad]”*.
- **Ejemplos:**
    - *UR-01: El estudiante podrá descargar el justificante de matrícula en formato PDF desde el portal académico.*
    - *UR-02: El cliente podrá consultar el estado actual de sus pedidos desde su perfil de usuario.*

---

## **1.3. Requisitos Funcionales (FR)**

- **Qué son:** Definen **qué debe hacer el sistema** para satisfacer los requisitos de usuario y otras necesidades o restricciones confirmadas. Expresan responsabilidades observables y verificables del sistema; no describen decisiones de diseño ni de implementación.
- **Relación con UR:** Generalmente, cada requisito funcional está **asociado a uno o varios requisitos de usuario**, ya que traduce las necesidades del usuario en funcionalidades concretas del sistema. Si varios UR necesitan exactamente la misma responsabilidad del sistema —el caso típico es la autenticación—, **el FR no se duplica**: se escribe una sola vez y se referencia desde todos los UR que lo requieran. *En el trabajo de laboratorio, no obstante, lo habitual será que cada FR se asocie a un único UR; la asociación múltiple es la excepción.*
- **Cómo se escriben:** En voz activa, iniciando, por ejemplo, con “El sistema debe…”, “La aplicación deberá…”. Cada requisito debe ser único y verificable.
- **Ejemplos:**
    - *FR-001: El sistema debe generar el justificante de matrícula en formato PDF a partir de los datos de matrícula del estudiante.*
        - Asociado a UR*-01: El estudiante podrá descargar el justificante de matrícula en formato PDF.*
    - *FR-002: El sistema debe mostrar al cliente el estado actual de cada uno de sus pedidos (en preparación, enviado o entregado).*
        - Asociado a *UR-02: El cliente podrá consultar el estado actual de sus pedidos desde su perfil de usuario.*

---

## **1.4. Requisitos No Funcionales (NFR)**

- **Qué son:** Requisitos que especifican propiedades de calidad del sistema, sus interfaces con el entorno o restricciones obligatorias que condicionan su desarrollo y operación. En esta asignatura se clasifican en requisitos de calidad (**NFR-Q**), de interfaz externa (**NFR-I**) y restricciones de diseño e implementación (**NFR-R**). Es importante no confundir estas restricciones con las **restricciones de negocio**, que son un tipo de regla de negocio que restringen o limitan las acciones que la organización, sus usuarios o sistemas pueden realizar.
- **Cómo se escriben:** Deben ser claros, completos y verificables. Los requisitos de calidad se formulan normalmente con una métrica, un umbral y sus condiciones de medida; los de interfaz y las restricciones deben indicar el estándar, sistema externo, condición o límite aplicable y cómo comprobar su cumplimiento.
- **Ejemplos:**
    - *NFR-Q-001: El sistema debe mantener una disponibilidad mensual mínima del 99,9 %, excluidas las ventanas de mantenimiento planificadas.*
    - *NFR-Q-002: Tras un incidente grave, la plataforma recuperará las funciones principales en un máximo de cuatro horas desde la declaración del incidente.*
    - *NFR-I-001: El sistema debe intercambiar los pedidos con la pasarela de pago mediante la API especificada por el proveedor, usando JSON y OAuth 2.0.*
    - *NFR-R-001: El sistema debe cumplir el RGPD en el tratamiento de datos personales.*

### Identificación de los requisitos no funcionales

Para simplificar el trabajo en la asignatura, los NFR podrán identificarse sin incluir el tipo de requisito en el código, usando la numeración `NFR-001`, `NFR-002`, `NFR-003`.

La tabla en la que se describan los NFR debe incluir una columna **Tipo NFR**, con uno de estos valores:

- **Calidad**: especifica una propiedad del sistema, como rendimiento, disponibilidad, seguridad o accesibilidad.
- **Interfaz**: especifica cómo se relaciona el sistema con usuarios, dispositivos, aplicaciones o servicios externos.
- **Restricción**: establece una obligación legal, normativa, organizativa o técnica que limita el desarrollo o la operación.

Por ejemplo:

| ID | Tipo NFR | Requisito |
| --- | --- | --- |
| NFR-001 | Calidad | La plataforma tendrá una disponibilidad mínima del 99,5 % mensual. |
| NFR-002 | Restricción | La plataforma cumplirá las obligaciones aplicables de protección de datos. |
| NFR-003 | Interfaz | Las pantallas cumplirán el nivel AA de WCAG 2.2. |

El tipo forma parte de la información del requisito, aunque no aparezca en su identificador. De esta manera, si la clasificación de un requisito cambia en algún momento, se mantiene su identificador y solo hay que actualizar el campo **Tipo NFR**.

---

## 1.5. Reglas de Negocio (BR)

- **Qué son:** una regla de negocio es una política, pauta, estándar, regulación o fórmula computacional (cálculo de tarifas de envío, descuentos por tramos, fórmulas de cálculo del precio final…) que define o restringe algún aspecto del negocio.
- Las **restricciones de negocio** son un tipo de regla de negocio que restringen o limitan las acciones que la organización, sus usuarios o sistemas pueden realizar. Por ejemplo: *«Un solicitante de préstamo menor de 18 años debe tener un cofirmante» o «Solo los gerentes de laboratorio pueden generar informes de exposición química de otras personas».*
- **Cómo se escriben:** Se deben escribir a un **nivel atómico**, lo que las hace cortas, simples, reutilizables y fáciles de modificar. Para esto, se recomienda no usar lógica "o" en el lado izquierdo de una construcción "si/entonces", y evitar la lógica "y" en el lado derecho. Para lógica compleja, se pueden usar **tablas de decisiones** y **árboles de decisiones**
- **Ejemplos:**
    - *BR-01: "Las ventanas de tiempo de entrega son de 15 minutos, comenzando cada cuarto de hora".*
    - *BR-02: "Las entregas deben completarse entre las 11:00 A.M. y las 2:00 P.M. hora local, inclusive".*
    - *BR-03: "La organización programará las ventanas de mantenimiento planificado entre las 02:00 y las 06:00, hora peninsular española, siempre que sea posible.".*

# **2. Características de un buen requisito (según norma ISO/IEC/IEEE 29148:2018)**

La norma [**ISO/IEC/IEEE 29148:2018**](https://www.iso.org/es/contents/data/standard/07/20/72089.html) define un conjunto de características que todo requisito debe cumplir para considerarse adecuado. Estas propiedades aseguran que los requisitos sean claros, consistentes, útiles y gestionables durante todo el ciclo de vida del sistema. Entre ellas se incluyen: necesario, apropiado, no ambiguo, completo, singular, factible, verificable, correcto y conforme. Aplicar estas características permite transformar necesidades de negocio y de usuario en especificaciones precisas, reduciendo riesgos de interpretación, mejorando la trazabilidad y garantizando que el sistema desarrollado satisfaga realmente los objetivos planteados.

### 1. **Necesario: Existe porque satisface una necesidad real.**

El requisito define una capacidad, característica, restricción o factor de calidad esencial. Si no se incluye, existirá una deficiencia que no podrá ser satisfecha por otros requisitos. Debe estar **alineado con los objetivos de negocio, misión o necesidades de las partes interesadas.** Debe ser aplicable actualmente y no haber quedado obsoleto.

- **✅ UR necesario:**
    
    *El cliente podrá descargar la factura de su pedido en formato PDF desde su perfil de usuario.*
    
    - Está directamente vinculado a un **objetivo de negocio** (cumplimiento fiscal y confianza del cliente) y a una **necesidad real del usuario** (guardar su comprobante).
- ❌ **UR innecesario**:
    
    *El usuario podrá personalizar el sonido de notificación del sistema con cualquier archivo MP3 de su preferencia.*
    
    - No responde a una necesidad de negocio ni mejora la misión del sistema.
    - No aporta valor real a la tarea principal del usuario (ej. gestión de trámites, compras, consultas).
    - Incrementa la complejidad técnica (subida de archivos, compatibilidad, almacenamiento).
    - Puede incluso introducir riesgos de seguridad (archivos maliciosos).
    - *Nota*: Si existiera un requisito de accesibilidad auditiva o personalización para usuarios con discapacidad, podría volverse necesario, pero sin esa justificación es innecesario
- ✅ **FR necesario**:
    
    *El sistema debe permitir al paciente registrar su presión arterial diariamente.*
    
    - Es necesario para el seguimiento clínico.
- ❌ **FR innecesario**:
    
    *El sistema debe permitir al usuario cambiar el color de fondo de la pantalla de inicio entre 50 tonalidades diferentes.*
    
    - Si el sistema no tiene requisitos de accesibilidad o usabilidad ligados a contraste visual, sería innecesario, pues:
        - No responde a un objetivo de negocio ni a una necesidad de usuario relevante.
        - No contribuye a la misión, metas o restricciones identificadas.
        - Introduce complejidad en el diseño, desarrollo y pruebas.
        - Podría incluso distraer recursos de requisitos realmente necesarios (como seguridad, rendimiento o usabilidad).
        - No existe una necesidad de negocio o usuario que justifique esa funcionalidad, por lo tanto no es necesaria
    - Si el sistema tuviera requisitos de accesibilidad o usabilidad ligados a contraste visual, podría ser necesario un FR como este: “*El sistema debe permitir al usuario seleccionar entre un tema de alto contraste y un tema estándar para cumplir con los criterios de accesibilidad WCAG 2.1.”*
- ✅ **NFR necesario**:
    
    *El sistema debe suprimir los datos personales asociados a una cuenta eliminada en un máximo de 30 días, salvo los que deba conservar por una obligación legal identificada.*
    
    - Existe porque responde a una obligación legal, una restricción externa obligatoria (legislación). Sin él, la organización se expone a sanciones y pérdida de confianza de los usuarios.
- **❌ NFR innecesario:**
    
    *El sistema debe responder en menos de 1 milisegundo para todas las operaciones.*
    
    - No existe una necesidad real de negocio o de usuario que justifique un rendimiento tan extremo.
    - El requisito es técnicamente irrealizable para muchas operaciones complejas (violando también las características de “Factible” y “Verificable”).
    - Genera costes excesivos en infraestructura y desarrollo sin aportar valor.
    - No está alineado con los objetivos del sistema (ejemplo: en un portal de trámites administrativos, un tiempo de 1 ms no cambia la experiencia del usuario).

---

### 2. Apropiado: Expresa fielmente lo que se requiere

La intención específica y el nivel de detalle del requisito son adecuados al nivel de la entidad a la que se refiere (nivel de abstracción adecuado al nivel de la entidad). Esto incluye evitar restricciones innecesarias en la arquitectura o el diseño, al tiempo que se permite la independencia de la implementación en la medida de lo posible. Un requisito es adecuado si define *qué* características debe cumplir el sistema (ej. “El sistema debe soportar al menos 1.000 transacciones concurrentes con una latencia máxima de 2 segundos”), permitiendo que las decisiones de *cómo* lograrlo queden en manos del equipo de diseño y arquitectura. 

- ✅ **UR apropiado**:
    
    *El estudiante podrá inscribirse en las asignaturas disponibles desde el portal académico.*
    
    - Expresa el **qué** desde la perspectiva del usuario: inscribirse en asignaturas.
    - Está en el nivel de **usuario**, no técnico.
    - Evita imponer restricciones de implementación (no dice si será un formulario web, una app móvil o integración con otro sistema).
    - Refleja fielmente la intención del usuario y es independiente de la solución tecnológica.
- **❌ UR no apropiado:**
    
    *El estudiante podrá inscribirse en las asignaturas disponibles mediante un formulario web desarrollado en Angular con conexión directa a la base de datos Oracle de la universidad.*
    
    - Mezcla necesidades del usuario con **detalles de diseño e implementación** (tecnología Angular, base de datos Oracle).
    - Restringe innecesariamente la arquitectura, violando la independencia de implementación.
    - No se mantiene en el nivel de abstracción adecuado para un **UR** (usuario).
- ✅ **FR apropiado**:
    
    *El sistema debe permitir al usuario recuperar su contraseña a través de un mecanismo de restablecimiento que incluya verificación mediante correo electrónico o mensaje de texto, garantizando la autenticación del solicitante.*
    
    - Define el *qué*: recuperación segura de contraseña.
    - Está al nivel funcional correcto (requisito del sistema).
    - No entra en detalles de *cómo* implementar el proceso (ej. si se usa un token JWT, un enlace de 256 bits o un proveedor de correo específico).
    - Permite que el diseño y la arquitectura decidan los mecanismos técnicos.
- ❌ **FR no apropiado**:
    
    *El sistema debe enviar un enlace de restablecimiento de contraseña generado con un hash SHA-256, válido durante 15 minutos, utilizando el servicio Amazon SES.*
    
    - Baja al nivel de diseño/implementación, cuando el requisito debería estar en un nivel funcional.
    - Restringe innecesariamente la arquitectura (obliga a usar Amazon SES).
    - La elección de algoritmo y proveedor de correo son **decisiones de diseño técnico**, no requisitos funcionales.
    - Viola el principio de independencia de implementación que la norma recomienda para requisitos.
- ✅ **NFR apropiado**:
    
    *El sistema debe soportar al menos 1.000 usuarios concurrentes manteniendo un tiempo de respuesta máximo de 2 segundos en las operaciones de consulta.*
    
    - Define el **qué** debe cumplir el sistema en términos de rendimiento.
    - Está en el nivel de requisitos (métricas claras de concurrencia y latencia).
    - Es **verificable** mediante pruebas de carga.
    - No condiciona la arquitectura ni la tecnología específica para lograrlo.
- ❌ **NFR no apropiado**:
    
    *El sistema debe usar balanceadores de carga Nginx configurados con 4 servidores de aplicaciones en paralelo para soportar a los usuarios concurrentes.*
    
    - Baja a **diseño/implementación** (tecnología concreta, cantidad de servidores, configuración).
    - Limita la independencia de la arquitectura y restringe opciones de solución.
    - No expresa el **qué** del comportamiento esperado, sino un **cómo** técnico.

---

### 3. **No ambiguo: Admite una sola interpretación.**

El requisito se formula de tal manera que solo puede interpretarse de una única forma. El requisito se formula de forma sencilla y es fácil de entender.

- **✅ UR no ambiguo:**
    
    *El pasajero podrá seleccionar su asiento durante el proceso de compra del billete aéreo.*
    
    - Está claro **quién** (pasajero), **qué** acción (seleccionar asiento), **cuándo** (durante la compra).
    - No deja margen a distintas interpretaciones.
- ❌ **UR ambiguo:**
    
    *El pasajero podrá elegir cómodamente su asiento.*
    
    - La palabra **“cómodamente”** es subjetiva: puede significar rapidez, facilidad de uso, cantidad de opciones o incluso ergonomía de la interfaz.
    - Distintos stakeholders podrían interpretarlo de forma diferente.
    - Tampoco es verificable: no hay una métrica para “cómodamente”.
- ✅ **FR no ambiguo**:
    
    *El sistema debe enviar un correo electrónico de confirmación al cliente en un máximo de 1 minuto tras registrar el pedido en la base de datos.*
    
    - El **evento** que dispara la acción está claro: registro de un pedido en la base de datos.
    - Especifica la **acción concreta**: envío de correo electrónico de confirmación.
    - El plazo máximo de **1 minuto** elimina la ambigüedad temporal y permite comprobar el requisito mediante una prueba.
- ❌ **FR ambiguo**:
    
    *El sistema debe enviar rápidamente una confirmación al cliente después de que haga un pedido.*
    
    - El término “rápidamente” es subjetivo: ¿1 segundo, 10 segundos, 1 minuto?
    - No especifica el medio de confirmación (correo electrónico, notificación en pantalla, SMS).
    - Distintos equipos podrían interpretarlo de maneras diferentes, lo que afectaría la implementación y la validación.
- **✅ NFR no ambiguo:**
    
    *El sistema debe tener una disponibilidad mínima del 99,95 % medida mensualmente.*
    
    - Define claramente la **métrica** (99,95 %).
    - Especifica el **criterio temporal** de medición (mensualmente).
    - Puede verificarse objetivamente mediante monitorización de disponibilidad.
- ❌ **NFR ambiguo**:
    
    *El sistema debe ser altamente disponible.*
    
    - Altamente disponible” puede interpretarse de muchas formas: ¿99 %, 99,9 %, 99,999 %?
    - No indica **cómo ni cuándo se mide**.
    - Distintos stakeholders (usuario, desarrollador, proveedor) podrían tener interpretaciones distintas.

---

### 4. **Completo: Contiene toda la información necesaria, incluyendo condiciones, unidades de medida, límites, etc.**

El requisito describe suficientemente la capacidad, característica, restricción o factor de calidad necesarios para satisfacer la necesidad de la entidad sin necesidad de otra información para comprender el requisito.

- **✅ UR completo:**
    
    *El cliente podrá pagar su pedido en línea utilizando tarjeta de crédito, tarjeta de débito o PayPal, durante el proceso de compra.*
    
    - Define claramente la **acción del usuario**: pagar su pedido.
    - Especifica el **momento**: durante el proceso de compra.
    - Incluye los **métodos de pago disponibles**, sin dejar la interpretación abierta.
- **❌ UR incompleto:**
    
    *El cliente podrá pagar su pedido en línea.*
    
    - No indica **cómo** o con qué métodos puede pagar.
    - No aclara si el pago ocurre durante la compra, después o en otro canal.
    - Distintos equipos podrían asumir implementaciones diferentes (solo tarjeta, solo PayPal, etc.).
- ✅ **FR completo**:
    
    *El sistema debe enviar un correo electrónico de confirmación al cliente dentro de los 5 minutos posteriores al registro de un pedido, incluyendo el número de pedido y el importe total.*
    
    - Define claramente la **acción del sistema**: enviar un correo.
    - Indica el **momento exacto**: dentro de los 5 minutos posteriores al registro.
    - Especifica el **contenido mínimo**: número de pedido e importe total.
    - No deja vacíos de interpretación.
- ❌ **FR incompleto**:
    
    *El sistema debe enviar un correo electrónico de confirmación al cliente.*
    
    - No dice **cuándo** debe enviarse (¿inmediatamente, al día siguiente?).
    - No indica **qué información debe contener** el correo.
    - Puede dar lugar a múltiples implementaciones distintas, algunas insuficientes para el negocio.
- ✅ **NFR completo**:
    
    *La aplicación debe cumplir con el nivel AA de accesibilidad según las directrices WCAG 2.1, verificable mediante auditoría de conformidad realizada con herramientas automáticas y pruebas con usuarios.*
    
    - Define el estándar de referencia: WCAG 2.1.
    - Especifica el nivel requerido: AA.
    - Incluye el método de verificación: auditoría automática y pruebas con usuarios.
    - No deja dudas sobre qué se espera ni cómo demostrar cumplimiento.
- **❌ NFR incompleto:**
    
    *La aplicación debe ser accesible para todos los usuarios.*
    
    - El término “accesible” es demasiado genérico y abierto a múltiples interpretaciones.
    - No indica qué estándar se aplica (WCAG, ADA, normativa local).
    - No define nivel de conformidad (A, AA, AAA).
    - No establece cómo se verificará.

---

### 5. **Singular: Expresa un único aspecto o condición; evita combinar varios requisitos en uno solo.**

Expresa una única capacidad, característica, restricción o factor de calidad. Puede incluir condiciones, pero no debe mezclar múltiples requisitos en uno solo.

- **✅ UR singular:**
    
    *El estudiante podrá descargar el comprobante de matrícula en formato PDF desde el portal académico.*
    
    - Expresa **una sola acción del usuario**: descargar el comprobante de matrícula.
    - Es claro, directo y verificable.
    - No mezcla otras funcionalidades adicionales.
- **❌ UR no singular:**
    
    *El estudiante podrá descargar el comprobante de matrícula en formato PDF desde el portal académico y actualizar sus datos personales en línea.*
    
    - Contiene **dos acciones distintas**: Descargar el comprobante de matrícula, y actualizar los datos personales.
    - Deberían ser **dos requisitos separados** para garantizar claridad, trazabilidad y verificabilidad.
- ✅ **FR singular**:
    
    *El sistema debe registrar cada intento fallido de inicio de sesión con la fecha, la hora y la dirección IP del usuario.*
    
    - Expresa una **única funcionalidad**: registrar intentos fallidos de inicio de sesión.
    - Incluye las condiciones y los datos necesarios dentro del mismo contexto.
    - Es claro y verificable.
- **❌ FR no singular:**
    
    *El sistema debe registrar cada intento fallido de inicio de sesión y bloquear al usuario tras tres intentos fallidos.*
    
    - Contiene dos funcionalidades distintas: Registrar intentos fallidos, y bloquear al usuario tras tres intentos.
    - Estas deberían separarse en dos requisitos:
        - *“El sistema debe registrar cada intento fallido de inicio de sesión con la fecha, la hora y la dirección IP del usuario.”*
        - *“El sistema debe bloquear al usuario tras tres intentos fallidos de inicio de sesión consecutivos.”*
- ✅ **NFR singular**:
    
    *El sistema debe tener una disponibilidad mínima del 99,9 % medida trimestralmente.*
    
    - Expresa una sola condición de calidad: disponibilidad.
    - Define claramente la métrica (99,9 %) y el período de medición (trimestral).
    - Es claro, verificable y no mezcla con otros aspectos (rendimiento, seguridad, etc.).
- ❌  **NFR no singular**:
    
    *El sistema debe tener una disponibilidad mínima del 99,9 % y responder en menos de 2 segundos a las consultas.*
    
    - Mezcla **dos factores de calidad distintos**: Disponibilidad y rendimiento (tiempo de respuesta).
    - Deben separarse en requisitos diferentes:
        - *“El sistema debe tener una disponibilidad mínima del 99,9 % medida trimestralmente.”*
        - *“El sistema debe responder en menos de 2 segundos a las consultas bajo una carga de 500 usuarios concurrentes.”*

---

### 6. **Factible (viable): Puede implementarse dentro de las restricciones de tiempo, coste y tecnología disponibles.**

El requisito puede cumplirse dentro de las limitaciones del sistema (por ejemplo, costes, plazos, aspectos técnicos) con un riesgo aceptable.

- ✅ **UR factible**:
    
    *El paciente podrá acceder a su historial clínico en línea desde el portal web del hospital.*
    
    - Es técnicamente viable con soluciones actuales (portales web con autenticación segura).
    - Está alineado con necesidades reales del usuario y objetivos de negocio (transparencia, acceso a la información).
    - Puede implementarse en plazos y costes razonables.
    - Los riesgos asociados (seguridad, privacidad) son gestionables con medidas estándar (ej. RGPD, cifrado).
- ❌ **UR no factible**:
    
    *El paciente podrá acceder a su historial clínico en cualquier idioma del mundo de manera instantánea.*
    
    - Pretende cobertura para todos los idiomas del mundo, lo que es técnicamente y económicamente inviable (no existen traductores automáticos perfectos, y mantener localizaciones completas sería prohibitivo).
    - Impone una expectativa imposible de cumplir dentro de plazos y presupuestos razonables.
    - Aun con IA de traducción, el requisito no podría garantizar exactitud clínica en todos los idiomas, lo que añade un riesgo inaceptable.
- ✅ **FR factible**:
    
    *El sistema debe permitir a los usuarios autenticarse mediante usuario y contraseña, validando las credenciales contra la base de datos corporativa en menos de 3 segundos.*
    
    - La tecnología para autenticación con usuario y contraseña está disponible y es madura.
    - El tiempo de respuesta (3 segundos) es razonable y alcanzable en la mayoría de entornos.
    - Se ajusta a prácticas habituales de seguridad.
    - Puede implementarse dentro de plazos y costes razonables.
- ❌ **FR no factible**:
    
    *El sistema debe permitir a los usuarios autenticarse mediante reconocimiento de huella dactilar, retina y voz simultáneamente en menos de 1 segundo.*
    
    - Requiere una combinación de tres métodos biométricos simultáneos, lo cual es excesivamente complejo e innecesario para la mayoría de sistemas.
    - El tiempo de respuesta (<1 segundo) es irreal dadas las operaciones que implican la captura y verificación biométrica múltiple.
    - Costes de hardware y software serían altísimos.
    - Riesgo de usabilidad: la exigencia haría casi imposible que los usuarios accedan al sistema.
- ✅ **NRF factible**:
    
    *El sistema debe garantizar una disponibilidad mínima del 99,9 % medida mensualmente, excluyendo las ventanas de mantenimiento planificadas.*
    
    - Una disponibilidad del 99,9 % (máx. ~43 minutos de caída al mes) es un objetivo alcanzable con tecnologías actuales de alta disponibilidad.
    - Puede lograrse con arquitecturas estándar (clústeres, redundancia, balanceadores).
    - El periodo de medición está definido y permite verificación objetiva.
    - Supone un coste razonable en comparación con objetivos más exigentes (ej. 99,999 %).
- ❌ **NFR no factible**:
    
    *El sistema debe garantizar una disponibilidad del 100 % en todo momento, sin interrupciones ni mantenimientos.*
    
    - Técnicamente imposible: todo sistema requiere mantenimientos, actualizaciones o puede sufrir fallos imprevistos.
    - Implica costes infinitos para intentar acercarse a ese ideal.
    - Riesgo inaceptable: la expectativa de 100 % genera incumplimientos inevitables.
    - No existe tecnología que asegure disponibilidad absoluta sin cortes.

---

### 7. **Verificable: Puede comprobarse objetivamente mediante prueba, inspección, análisis o demostración.**

El requisito está estructurado y redactado de tal manera que su cumplimiento pueda demostrarse (verificarse) a satisfacción del cliente en el nivel en que existe el requisito. La verificabilidad mejora cuando el requisito es medible.

- **✅ UR verificable:**
    
    *El pasajero podrá descargar su tarjeta de embarque en formato PDF desde el portal web una vez completado el check-in en línea.*
    
    - Se puede comprobar mediante una **prueba funcional: e**l pasajero hace check-in, accede al portal y descarga el PDF.
    - Es medible (el archivo se descarga o no).
    - No hay lugar a interpretaciones subjetivas.
- **❌ UR no verificable:**
    
    *El pasajero podrá descargar fácilmente su tarjeta de embarque.*
    
    - El término “fácilmente” es subjetivo: para un usuario experto puede ser “fácil”, pero para otro no.
    - No establece métricas ni criterios de aceptación.
    - No puede comprobarse objetivamente en una prueba: la facilidad no es medible sin definir parámetros concretos (ej. número de pasos, tiempo máximo, usabilidad según norma).
- ✅ **FR verificable**:
    
    *El sistema debe bloquear la cuenta de usuario después de tres intentos consecutivos fallidos de inicio de sesión.*
    
    - Se puede comprobar mediante prueba funcional: intentar tres accesos fallidos y observar si la cuenta queda bloqueada.
    - El criterio está claro (tres intentos consecutivos).
    - El resultado esperado es binario: o se cumple o no se cumple.
- ❌ **FR no verificable**:
    
    *El sistema debe bloquear la cuenta del usuario si detecta múltiples intentos de acceso sospechosos.*
    
    - El término “múltiples” es ambiguo (¿3, 5, 10 intentos?), y por lo tanto impide una verificación clara.
    - “Sospechosos” es subjetivo: no define criterios objetivos para identificar lo sospechoso.
    - Distintos evaluadores podrían interpretar el comportamiento de manera diferente.
- ✅ **NFR verificable**:
    
    *El sistema debe responder en menos de 2 segundos para consultas de hasta 500 usuarios concurrentes, medido en pruebas de carga.*
    
    - Contiene una métrica clara: tiempo de respuesta < 2 segundos.
    - Define las condiciones de prueba: 500 usuarios concurrentes.
    - Es medible objetivamente mediante pruebas de rendimiento.
    - Permite un resultado binario: cumple / no cumple.
- ❌ **NFR no verificable**:
    
    *La aplicación debe tener un rendimiento adecuado.*
    
    - “Rápido” y “eficiente” son términos subjetivos y abiertos a interpretación.
    - No existen métricas ni condiciones de medición.
    - Distintos stakeholders podrían entender diferentes umbrales de “rápido” (0,5 s, 2 s, 5 s).
    - No puede validarse de manera objetiva en pruebas.

---

### 8. **Correcto: Refleja fielmente lo que debe expresar y no contradice el dominio del problema.**

El requisito es una representación precisa de la necesidad de la entidad a partir de la cual se transformó.

- **✅ UR correcto:**
    
    *El paciente podrá solicitar una cita médica en línea desde el portal del hospital.*
    
    - Refleja una necesidad real del dominio de salud: gestión de citas médicas.
    - Está alineado con los objetivos de negocio (agilizar atención, reducir llamadas telefónicas).
    - No contradice el dominio: es algo esperado y practicable en un portal hospitalario.
    - Representa fielmente lo que el usuario necesita hacer.
- **❌ UR no correcto:**
    
    *El paciente podrá modificar el historial clínico almacenado en el sistema desde el portal del hospital.*
    
    - Contradice el dominio clínico: los pacientes no deben poder modificar directamente su historial médico, ya que es información controlada por profesionales de salud.
    - No refleja fielmente la necesidad real del paciente ni los procesos del negocio.
    - Generaría riesgos legales y de seguridad en el manejo de datos clínicos.
- ✅ **FR correcto**:
    
    *El sistema debe registrar cada prescripción médica emitida por un profesional autorizado, almacenando la fecha, la hora, el identificador del médico y el detalle del tratamiento.*
    
    - Refleja fielmente un proceso del dominio de la salud (registro de prescripciones).
    - Limita la acción a profesionales autorizados, respetando normativas.
    - Está alineado con la necesidad real: trazabilidad y control en la emisión de recetas.
    - No contradice el dominio ni la legislación aplicable.
- ❌ **FR no correcto**:
    
    *El sistema debe permitir que cualquier paciente edite las prescripciones médicas almacenadas en su historial.*
    
    - Contradice directamente el dominio clínico y la normativa sanitaria: solo los profesionales pueden emitir/modificar prescripciones.
    - No representa una necesidad real del usuario ni del negocio.
    - Podría generar graves riesgos de seguridad, salud y legales.
- ✅ **NFR correcto**:
    
    *El sistema debe suprimir los datos personales asociados a una cuenta eliminada en un máximo de 30 días, salvo los que deba conservar por una obligación legal identificada.*
    
    - Refleja una necesidad real del dominio (cumplimiento legal en el ámbito sanitario).
    - Está alineado con el negocio y los stakeholders (evitar sanciones, proteger la privacidad).
    - No contradice ninguna norma o práctica del dominio, sino que se ajusta a ellas.
- ❌ **NFR no correcto**:
    
    *El sistema debe almacenar indefinidamente todos los datos personales de los pacientes, incluso si estos solicitan su eliminación.*
    
    - Contradice directamente el dominio legal y normativo (RGPD exige el derecho al olvido).
    - No representa una necesidad válida del negocio ni de los usuarios.
    - Genera riesgos legales y reputacionales.

---

### 9. **Conforme: Cumple con las reglas de redacción, formato y convenciones establecidas para los requisitos.**

Los elementos individuales se ajustan a una plantilla y un estilo estándar aprobados para los requisitos de redacción, cuando procede.

- ✅ **UR conforme**:
    
    *El cliente podrá consultar el estado actual de sus pedidos desde su perfil de usuario.*
    
    - Sigue una estructura estándar: *[Actor] podrá [acción] [objeto] [condición/contexto]*.
    - Usa voz activa y verbo en futuro (“podrá consultar”).
    - Redacción clara, concisa y sin ambigüedad.
    - Se ajusta a la convención típica de requisitos de usuario (perspectiva del actor, no del sistema).
- **❌ UR no conforme:**
    
    *Se debería poder ver de alguna manera cómo va lo del pedido.*
    
    - No sigue ninguna estructura estándar.
    - Usa términos vagos (“debería”, “de alguna manera”, “lo del pedido”).
    - Emplea voz pasiva/impersonal, lo que introduce ambigüedad.
    - No se ajusta a un estilo de redacción consistente con los demás requisitos.
- ✅ **FR conforme**:
    
    *El sistema debe enviar un correo electrónico de confirmación al cliente en un máximo de 1 minuto tras registrar el pedido en la base de datos.*
    
    - Sigue una estructura estándar: *[El sistema debe + verbo en infinitivo + objeto + condición]*.
    - Redacción clara, precisa y sin ambigüedades.
    - Usa verbo en **voz activa** (“enviar”) y obligación clara (“debe”).
    - Se ajusta al estilo uniforme de requisitos funcionales.
- ❌ **FR no conforme**:
    
    *Se mandará un correo al cliente cuando se haga un pedido (si es posible).*
    
    - No respeta la convención de redacción (no empieza por *“El sistema debe…”*).
    - Emplea voz pasiva/impersonal (“se mandará”).
    - Introduce ambigüedad con *“si es posible”*.
    - No sigue un formato estándar ni estilo uniforme con otros requisitos.
- ✅ **NFR conforme**:
    
    *El sistema debe garantizar una disponibilidad mínima del 99,9 % medida mensualmente, excluyendo las ventanas de mantenimiento planificadas.*
    
    - Sigue la estructura estándar: *“El sistema debe [verbo en infinitivo] [condición medible] [contexto de aplicación]”*.
    - Usa terminología clara, sin ambigüedades.
    - Contiene métrica verificable (99,9 %).
    - Está escrito en voz activa, con formato consistente respecto a otros requisitos.
- ❌ **NFR no conforme**:
    
    *El sistema será muy estable y no debería fallar casi nunca.*
    
    - No sigue un formato estándar ni consistente.
    - Usa términos vagos (“muy estable”, “casi nunca”).
    - Emplea condicional impreciso (“no debería”).
    - No contiene métricas ni condiciones objetivas de verificación.

# 3. Nombrar y describir brevemente casos de uso

## 3.1. Qué es un caso de uso y para qué sirve

Un caso de uso es una técnica para capturar qué debe hacer un sistema desde el punto de vista de los usuarios y otros actores. Representa una secuencia de interacciones entre un actor y el sistema que produce un resultado de valor para ese actor o para otra parte interesada.

Podemos entenderlos como historias sobre cómo se utiliza un sistema para lograr un objetivo concreto.

- Son descripciones de “caja negra”: explican qué hace el sistema, no cómo lo hace.
- Se centran en los requisitos funcionales.
- Sirven de puente entre requisitos de usuario (qué quiere conseguir la persona) y requisitos funcionales (qué debe implementar el sistema).

## 3.2. Elementos clave

Un caso de uso debe incluir:

- **Nombre conciso**: describe el objetivo del usuario.
- **Actor(es)**: quién o qué interactúa con el sistema.
- **Descripción breve**: explica el propósito y el valor que aporta.
- **Escenarios**: posibles secuencias de éxito o fallo.
- **Condición de inicio y resultado esperado**: qué lo dispara y qué se obtiene al finalizar.

En fases iniciales, basta con un **nombre y una breve descripción**, sin detallar aún flujos completos.

## 3.3. Relación entre requisitos de usuario y casos de uso

- Un **requisito de usuario** expresa lo que un tipo de usuario quiere poder hacer con el sistema.
    
    Ejemplo: “El usuario podrá registrarse en la aplicación”.
    
- A partir de él, se formula un **caso de uso** que describe la interacción necesaria.
    
    Ejemplo: **Registrar Usuario**.
    

En esta asignatura, la secuencia es UR → FR → casos de uso: los casos de uso modelan e interpretan los UR y FR relacionados, sin sustituirlos ni ser la fuente de la que se derivan los FR. Es una secuencia didáctica, no la única válida en un proyecto de software.

## 3.4. Cómo nombrar casos de uso

Para que los nombres sean claros y consistentes, sigue estas pautas:

1. **Empieza con un verbo**
    
    Refleja que es una acción.
    
    Ejemplos: **Autenticar Usuario**, **Procesar Venta**, **Crear Receta**.
    
2. **Expresa un objetivo de usuario**
    
    El caso de uso debe corresponder a un **proceso de negocio elemental**: una tarea breve, con valor y resultado observable.
    
    Ejemplo: en lugar de “Escanear producto”, usar **Introducir Artículo**.
    
3. **Mantén independencia de la interfaz**
    
    No menciones pantallas, botones o tecnologías.
    
    Ejemplo: **Gestionar Usuarios**, mejor que “Rellenar formulario de alta”.
    
4. **Describe la intención, no la técnica**
    
    El nombre refleja lo que quiere lograr el actor, no cómo lo hace el sistema.
    
5. **Agrupa operaciones CRUD**
    
    Si el caso incluye crear, editar, eliminar y consultar, nómbralo como **Gestionar + Entidad**.
    
    Ejemplo: **Gestionar Recetas**.
    
6. **Usa el vocabulario del dominio**
    
    Elige palabras habituales en el negocio o en el contexto del problema.
    
    Ejemplo: **Emitir Factura**, no “Generar documento de pago”.
    
7. **Excepciones a nivel subfunción**
    
    Algunas subfunciones repetidas, como **Autenticar Usuario**, merecen un caso de uso independiente porque son precondiciones frecuentes.
    

## 3.5. Cómo redactar la descripción breve

La descripción breve debe responder a estas preguntas en unas pocas frases:

- ¿Qué objetivo persigue el actor?
- ¿Qué valor obtiene?
- ¿Cuál es el resultado observable?

Ejemplos:

- **UC-01: Registrar usuario**: El usuario crea una cuenta en la plataforma proporcionando sus datos básicos de identificación y acceso. El sistema valida la información introducida, solicita la aceptación de las condiciones de uso, verifica que el correo no esté registrado previamente y envía un mensaje de confirmación. A partir de este registro, el usuario obtiene credenciales válidas que le permitirán acceder a los distintos servicios de la aplicación.
- **UC-02: Procesar venta**: El cajero atiende una compra registrando los artículos seleccionados por el cliente. El sistema calcula automáticamente el importe total aplicando precios, descuentos o impuestos correspondientes, y muestra el monto final a pagar. Una vez completado el pago en el método elegido, el sistema genera y entrega un recibo como comprobante de la transacción, dejando registrada la operación en el sistema de ventas.
- **UC-03: Publicar Calendario de exámenes**: La vicedecana accede al sistema para introducir las fechas, horas y asignaturas del nuevo calendario de exámenes. El sistema valida la información, registra los datos y los hace visibles de forma centralizada para todo el profesorado y alumnado. De este modo, los usuarios disponen de un calendario oficial actualizado al que pueden acceder en cualquier momento para planificar sus actividades académicas.

## 3.6. Niveles de formalidad

Un caso de uso puede documentarse en distintos niveles:

- **Breve/informal**: solo nombre y una descripción de un párrafo o con un párrafo más amplio con escenarios básicos y alternativos (adecuado en fases iniciales).
- **Completo**: especificación detallada con pasos, flujos alternativos, excepciones, precondiciones y postcondiciones.

En esta guía nos centramos en el **nivel breve/informal**, suficiente para empezar a trabajar a partir de requisitos de usuario y parte de los requisitos funcionales.

## 3.7. Ejemplos paso a paso

Tomemos algunos requisitos de usuario y transformémoslos en casos de uso con nombre y descripción breve:

- **Requisito de usuario**: “El usuario podrá registrarse en la aplicación”.
    - **Caso de uso**: Registrar Usuario
    - **Descripción**: El usuario crea una nueva cuenta introduciendo sus datos básicos y aceptando las condiciones de uso. El sistema valida la información y confirma el alta, otorgando al usuario credenciales que le permitirán acceder a los distintos servicios de la aplicación.
- **Requisito de usuario**: “El paciente podrá introducir y actualizar los datos de salud que decida proporcionar para facilitar la búsqueda de recetas adecuadas a su perfil”.
    - **Caso de uso**: Gestionar Datos de Salud
    - **Descripción**: El paciente incorpora o actualiza los datos de salud que decida proporcionar. El sistema los conserva como datos privados y los utiliza para ajustar los resultados de búsqueda de recetas, sin realizar recomendaciones médicas o clínicas automáticas.
- **Requisito de usuario**: “El cliente podrá pagar con tarjeta”.
    - **Caso de uso**: Realizar Pago
    - **Descripción**: El cliente selecciona el pago con tarjeta como método de abono de su compra. El sistema solicita y valida los datos de la tarjeta, procesa la operación con la entidad bancaria y confirma la transacción, generando un comprobante que cierra la venta de forma segura.
- **Requisito de usuario**: “El usuario podrá valorar recetas publicadas por otros”.
    - **Caso de uso**: Valorar Receta
    - **Descripción**: El usuario asigna una puntuación a una receta publicada en la plataforma. El sistema registra la valoración, actualiza la calificación promedio visible para toda la comunidad y contribuye a destacar las recetas más apreciadas por los usuarios.

## 3.8. Errores frecuentes a evitar

- **Nombres demasiado técnicos**: “Ejecutar script de autenticación” en vez de **Autenticar Usuario**.
- **Escenarios demasiado pequeños**: “Introducir contraseña” no es un caso de uso independiente, sino un paso dentro de **Autenticar Usuario**.
- **Dependencia de interfaz**: “Hacer clic en botón de búsqueda” debe ser **Buscar Receta**.
- **Casos de uso redundantes**: dividir innecesariamente lo que debería estar agrupado bajo un **Gestionar**.

## 3.9. Conclusión

Los casos de uso son una herramienta central en la ingeniería de requisitos porque:

- Permiten pasar de los requisitos de usuario a una representación clara y estructurada.
- Se enfocan en los objetivos y el valor para el usuario.
- Ayudan a interpretar y mantener la trazabilidad de los requisitos funcionales, y sirven de base para diseñar pruebas.

La clave está en **nombrarlos con verbos claros, al nivel de procesos de negocio elementales, y describir brevemente el objetivo y el valor para el actor**.

A lo largo del Tema 3 se profundizará en el Modelo de Casos de Uso de UML.
