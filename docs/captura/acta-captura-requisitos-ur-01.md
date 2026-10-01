# Acta de captura de requisitos de UR-01: registro en la plataforma

| Campo | Valor |
| --- | --- |
| Estado | Validada y vigente |
| Versión | 0.2 |
| Fecha de la entrevista | 01/09/2025 |
| Orden de decisión | Aclaración posterior a A03; prevalece sobre sus formulaciones generales relativas al registro y la acreditación profesional. |
| Requisito de usuario | UR-01 · Registro en la plataforma |
| Fuente | [Entrevista UR-01 (registro en la plataforma)](https://ebalonso.notion.site/Entrevista-UR-01-registro-en-la-plataforma-26118e639c1480139154f29c41b3561d) |
| Finalidad | Precisar el flujo de registro y las condiciones que deben derivarse a requisitos funcionales y no funcionales. |

## Participantes

| Rol | Participación |
| --- | --- |
| Coordinadora de la ONG | Representación de la organización y validación de necesidades. |
| Analista | Conducción de la entrevista y registro de acuerdos. |

## 1. Alcance de la aclaración

La entrevista concreta el requisito de usuario UR-01: una persona usuaria podrá registrarse en la plataforma para acceder a sus funciones. Se considera una aclaración posterior al acta de A03: precisa el flujo de registro, la activación de cuenta y la acreditación profesional.

El alcance incluye el registro estándar, la autenticación mediante Google, la verificación del correo, las validaciones del formulario y el tratamiento específico del alta de profesionales. No aborda la moderación posterior, los mecanismos de recuperación de cuenta ni una política completa de conservación de datos.

## 2. Acuerdos confirmados

### 2.1. Datos y modalidades de registro

- El registro estándar solicitará nombre completo, alias, correo electrónico, teléfono y contraseña.
- El alias será obligatorio y podrá ser distinto del nombre real. Será la identidad visible en el foro y otros espacios públicos.
- El teléfono será obligatorio y se utilizará inicialmente como dato de contacto; no se implantará autenticación de doble factor en esta fase.
- El teléfono admitirá prefijos internacionales y validará el formato en tiempo real.
- Se permitirá continuar con Google. Esta modalidad evitará introducir correo y contraseña locales, pero seguirá requiriendo alias y teléfono.
- Una persona que se registró con Google podrá establecer posteriormente una contraseña local.
- Si existe una cuenta local y se usa Google con el mismo correo, ambas identidades se vincularán para evitar duplicados.
- No se guardará un borrador de un registro incompleto en esta primera versión.

### 2.2. Unicidad y validación de campos

- El alias y el correo electrónico deberán ser únicos.
- El alias tendrá un mínimo de tres caracteres, no admitirá espacios y podrá incluir guion o guion bajo.
- Si el alias ya está ocupado, la interfaz podrá proponer alternativas, sin impedir que la persona introduzca manualmente otro alias.
- El formato del correo se comprobará en tiempo real al perder el foco del campo. No se comprobará la existencia del dominio antes del envío: la verificación efectiva será la confirmación por correo.
- Los errores se mostrarán junto a cada campo y, si existen varios, también podrán resumirse en la parte superior del formulario.
- Los mensajes explicarán la corrección necesaria; no se utilizarán mensajes genéricos para errores de validación de campos.

### 2.3. Contraseña y seguridad frente a registros automatizados

- La contraseña local deberá tener, como mínimo, ocho caracteres e incluir mayúsculas, minúsculas, números y un símbolo.
- La interfaz mostrará en tiempo real la fortaleza de la contraseña y qué condición falta por cumplir. El indicador combinará color y texto de forma accesible.
- El registro incorporará un CAPTCHA con alternativa de audio. No se habilitará, por ahora, una vía de omisión del CAPTCHA.
- La política de impedir contraseñas comunes se considera deseable, pero no se ha fijado como requisito de la primera versión.

### 2.4. Confirmación de correo y finalización del registro

- Tras enviar el formulario, se enviará un correo de verificación con enlace de activación.
- El enlace de verificación caducará a las veinticuatro horas.
- Si el enlace caduca o el correo no se recibe, la persona podrá solicitar un nuevo envío. Se limitará a un reenvío por minuto.
- Una cuenta no se considerará activa, ni el registro completado, hasta que se confirme el correo mediante el enlace de verificación.
- La fecha y la hora de registro se guardarán en UTC y corresponderán al instante en que el sistema confirma la verificación del correo.
- La interfaz mostrará una pantalla independiente de confirmación. Antes de verificar el correo, indicará claramente que falta activar la cuenta; una vez verificada, confirmará que el registro se ha completado.

### 2.5. Condiciones legales y comunicaciones

- El formulario mostrará dos casillas separadas: aceptación de términos y condiciones, y aceptación de la política de privacidad.
- Será obligatorio marcar ambas casillas para continuar con el registro.
- No se incorporará en esta versión una suscripción a comunicaciones; si se añadiera en el futuro, deberá estar desmarcada por defecto y ser opcional.

### 2.6. Registro de profesionales

- Quien se registre como profesional deberá aportar durante el registro documentación oficial en formato PDF.
- El archivo PDF será obligatorio para solicitar el perfil profesional, tendrá un tamaño máximo de 10 MB y se validará tanto por formato como por tamaño antes de continuar.
- Hasta que la documentación sea revisada y aprobada manualmente, la cuenta operará como cuenta de usuario general.
- Tras la aprobación, se habilitarán las funciones de publicación profesional.
- Los errores de formato o tamaño del archivo se mostrarán junto al campo de carga mediante mensajes claros.

### 2.7. Errores no atribuibles a un campo

En caso de error del servidor durante el registro, se mostrará el mensaje: «Ha ocurrido un problema. Inténtalo de nuevo o contacta con soporte.»

## 3. Cuestiones abiertas o aplazadas

| Asunto | Estado | Necesidad de decisión posterior |
| --- | --- | --- |
| Detección de contraseñas comunes | Deseable, fuera de la primera versión | Decidir si se incorpora y con qué criterio. |
| Registro de IP y agente de usuario | Admitido solo si es necesario para seguridad | Definir finalidad, conservación y reflejo en la política de privacidad. |
| Acreditación profesional admitida | Se fija carga de documentación oficial en PDF, con máximo de 10 MB y revisión manual | Concretar qué credenciales o documentos oficiales serán aceptados. |

## 4. Relación con A03 y actualización de la línea base

Esta entrevista se considera posterior a A03. Por tanto, sus acuerdos concretan y prevalecen sobre la formulación general anterior en los siguientes aspectos:

| Aclaración posterior | Efecto en la línea base |
| --- | --- |
| Registro estándar | Se concretan campos obligatorios, reglas de alias, validaciones y mensajes de error. |
| Activación de cuenta | Se define la verificación por correo, el plazo de caducidad, el reenvío y el instante que determina el registro completado. |
| Autenticación | Se incorpora el alta mediante Google y la vinculación por correo con cuentas locales existentes. |
| Seguridad y accesibilidad | Se concretan política de contraseña, CAPTCHA con audio, mensajes de validación y criterios de accesibilidad del indicador de fortaleza. |
| Acreditación profesional | Se fija la carga de documentación oficial en PDF, el límite de 10 MB, la revisión manual y el estado de usuario general hasta la aprobación. |

La entrevista no modifica la regla de A03 según la cual pacientes, cuidadores y nutricionistas siguen flujos de aprobación distintos. Solo detalla el registro general y el proceso específico aplicable a quien solicita perfil profesional.

## 5. Impacto esperado en la línea base

La actualización de la línea base deberá considerar, al menos, los siguientes grupos de requisitos:

| Área | Aspectos a especificar |
| --- | --- |
| Registro estándar | Campos obligatorios, validación y mensajes de error. |
| Identidad visible | Alias obligatorio, reglas de formato y unicidad. |
| Autenticación | Registro local, Google y vinculación de identidades por correo. |
| Activación | Verificación por correo, caducidad, reenvío y condición de cuenta activa. |
| Seguridad y accesibilidad | Política de contraseña, CAPTCHA con audio y mensajes comprensibles. |
| Cumplimiento | Aceptación separada de términos y política de privacidad. |
| Perfil profesional | Carga y revisión de documentación, estado provisional y habilitación posterior. |
| Auditoría | Marca temporal de activación en UTC. |

## 6. Trazabilidad y vigencia

Esta acta conserva las decisiones recogidas en la entrevista del 01/09/2025. Una decisión posterior que afecte a cualquiera de estos acuerdos deberá registrarse con su fecha, fuente y alcance, sin alterar silenciosamente este documento.

Esta acta es evidencia de captura para la derivación de requisitos funcionales y no funcionales asociados a UR-01.

## Historial de versiones

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 22/09/2026 | Primera acta elaborada a partir de la entrevista de aclaración de UR-01. |
| 0.2 | 22/09/2026 | Se declara como aclaración posterior a A03 y se actualiza su efecto sobre la línea base. |
