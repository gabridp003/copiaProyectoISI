# Acta de captura de requisitos de UR-05: gestión de datos de salud

| Campo | Valor |
| --- | --- |
| Estado | Validada y vigente |
| Versión | 0.2 |
| Fecha de la entrevista | No indicada en la fuente |
| Orden de decisión | Aclaración posterior a A03; prevalece sobre sus formulaciones generales relativas a datos de salud. |
| Requisito de usuario | UR-05 · El paciente podrá introducir y gestionar sus datos fisiológicos y de salud, accediendo a un historial detallado y actualizando la información según sea necesario. |
| Fuente | [Entrevista UR-05 (gestión de datos de salud)](https://app.notion.com/p/26118e639c148000aa0ad905b752e0f6) |
| Finalidad | Precisar la gestión de datos de salud y los requisitos funcionales y no funcionales que pueden derivarse de UR-05. |

## Participantes

| Rol | Participación |
| --- | --- |
| Paciente | Necesidades de registro, consulta y control de acceso. |
| Médico nutricionista | Necesidades de estructura, visualización y uso profesional autorizado. |
| Analista | Conducción de la entrevista y registro de acuerdos. |

## 1. Alcance de la aclaración

La entrevista aborda el registro manual de datos fisiológicos y de laboratorio, notas diarias, recordatorios, historial, gráficas, exportación y compartición autorizada de datos con profesionales. Se considera una aclaración posterior al acta de A03: concreta el alcance de la información de salud y las condiciones de acceso autorizado.

Las integraciones con dispositivos conectados quedan fuera de esta fase. La entrevista incorpora además alertas basadas en umbrales como alcance funcional posterior; su aplicación deberá especificar condiciones, responsabilidad y límites clínicos.

## 2. Acuerdos confirmados

### 2.1. Registro manual de datos fisiológicos

- El paciente podrá introducir peso, altura, presión arterial, frecuencia cardíaca y temperatura corporal.
- La presión arterial se registrará separando valor sistólico y diastólico.
- Las unidades se mostrarán junto al campo y se fijan inicialmente en kg, mmHg, lpm y ºC, respectivamente.
- La altura podrá corregirse cuando sea necesario.
- La fecha y hora de una medición se propondrán como el momento actual, pero podrán modificarse para registrar datos anteriores.
- El paciente podrá corregir datos introducidos por error. La conservación de la fecha original de la medición y de la fecha de introducción se considera deseable, pero no imprescindible para la primera versión.

### 2.2. Resultados de laboratorio y notas

- Se podrán registrar valores de laboratorio, incluidos glucosa, colesterol y otros parámetros definidos por el paciente.
- Cada resultado de laboratorio incluirá fecha y hora, valor numérico y unidad obligatoria seleccionada de una lista.
- El sistema recordará la última unidad utilizada por el paciente para cada parámetro.
- Se podrán definir parámetros de laboratorio adicionales.
- Se permitirá añadir una nota breve de contexto, por ejemplo «en ayunas».
- Las notas diarias de síntomas o estado tendrán texto libre, un límite de 500 caracteres y un contador de caracteres restantes.
- Las etiquetas estructuradas para síntomas se aplazan a una iteración posterior.

### 2.3. Validación de datos

- La interfaz mostrará mensajes de validación junto al campo afectado.
- En los campos numéricos, las unidades se seleccionarán por separado; el sistema indicará que solo debe introducirse el valor numérico.
- Se aplicarán validaciones básicas de rango para evitar valores manifiestamente erróneos, como temperaturas fuera del intervalo de 30 a 45 ºC.

### 2.4. Recordatorios

- Los recordatorios se mostrarán dentro de la plataforma, mediante avisos en el panel o notificaciones internas; no se priorizan correos electrónicos ni notificaciones *push* en esta fase.
- Se podrán configurar por tipo de dato con frecuencia diaria, semanal o mensual.
- El profesional podrá proponer una frecuencia y el paciente podrá modificarla.
- Un recordatorio no atendido quedará pendiente hasta que el paciente complete o descarte el registro asociado.

### 2.5. Historial, gráficas y exportación

- El historial se mostrará por defecto de más reciente a más antiguo y permitirá filtrar por tipo de dato.
- Desde el perfil del paciente se podrá acceder rápidamente a gráficas por variable, con rango de fechas y series visibles u ocultables.
- Se podrá exportar el historial en PDF y CSV.
- El PDF incluirá un resumen por periodo y, cuando sea posible, gráficas.
- El CSV incluirá cabeceras claras, fecha y hora, valor, unidad y fuente del dato, diferenciando entrada manual y laboratorio.

### 2.6. Acceso de profesionales autorizado por el paciente

- El paciente decidirá qué profesionales pueden acceder a sus datos.
- Para conceder acceso, el paciente indicará el correo del profesional. Si ya dispone de cuenta, se mostrará su identidad; si no, se le enviará una invitación para registrarse.
- El profesional no accederá a datos hasta verificar su correo y completar la verificación de identidad profesional que corresponda.
- El paciente podrá revocar el acceso en cualquier momento.

### 2.7. Alertas y umbrales

- La entrevista propone alertas automáticas cuando una medición supere un umbral crítico.
- La alerta se registraría en el historial y se mostraría al paciente dentro de la plataforma con un mensaje que indique expresamente que debe buscar atención médica si el valor persiste o se encuentra mal.
- Se partiría de umbrales generales y un profesional autorizado podría ajustarlos para un paciente concreto.
- Los cambios de umbral quedarían registrados, se aplicarían desde ese momento, identificarían a quien los realizó y generarían una notificación al paciente.

## 3. Límites y decisiones aplazadas

| Asunto | Estado |
| --- | --- |
| Integración con básculas, relojes u otros dispositivos conectados | Fuera de esta fase; se centra en entrada manual y recordatorios internos. |
| Etiquetas estructuradas para síntomas | Aplazadas; se mantiene texto libre de hasta 500 caracteres. |
| Fecha de introducción de una medición distinta de la fecha de medición | Deseable, pero no imprescindible para la primera versión. |
| Umbrales clínicos concretos y criterios de alerta | No definidos. |
| Gobierno de la modificación de umbrales por profesionales | Requiere reglas de autorización, responsabilidad y trazabilidad. |

## 4. Relación con A03 y actualización de la línea base

Esta entrevista se considera posterior a A03. Por tanto, sus acuerdos concretan y prevalecen sobre la formulación general anterior en los siguientes aspectos:

| Aclaración posterior | Efecto en la línea base |
| --- | --- |
| Información de salud | El perfil de salud se amplía con registro manual, historial, notas, recordatorios, gráficas y exportación. |
| Acceso de profesionales | El acceso no es automático: requiere autorización expresa y revocable del paciente, además de la verificación del profesional. |
| Alertas por umbral | Se incorpora una alerta de seguridad registrada y visible para el paciente. No sustituye el juicio clínico ni habilita recomendaciones dietéticas o diagnósticos automáticos. |
| Umbrales personalizados | Se requiere especificar quién puede modificarlos, con qué evidencia y bajo qué trazabilidad. |

La introducción de alertas exige concretar sus condiciones, responsabilidad y límites clínicos antes de construirla, pero no queda pendiente de decidir si forma parte del alcance: esta entrevista la incorpora como funcionalidad posterior.

## 5. Impacto esperado en la línea base

Si se validan los hallazgos de esta entrevista, la línea base deberá incluir requisitos relativos a:

| Área | Aspectos a especificar |
| --- | --- |
| Datos fisiológicos | Campos, unidades, corrección y validación de rangos. |
| Laboratorio | Parámetros, unidades, fecha y hora, notas y fuente del dato. |
| Notas diarias | Límite de longitud y tratamiento de texto libre. |
| Recordatorios | Configuración por tipo de dato, frecuencia y tratamiento de pendientes. |
| Consulta | Historial cronológico, filtros y gráficas. |
| Exportación | Contenido, formato y privacidad de PDF y CSV. |
| Control de acceso | Autorización, invitación, verificación y revocación. |
| Alertas | Condiciones, mensaje, registro y trazabilidad de umbrales. |

## 6. Trazabilidad y vigencia

Esta acta conserva las decisiones expresadas durante la entrevista. Una decisión posterior que confirme, modifique o descarte cualquiera de sus hallazgos deberá registrarse con fecha, fuente y alcance, sin reescribir silenciosamente esta evidencia de captura.

Aunque la página de Notion de origen no está marcada como verificada, esta acta está validada y vigente como evidencia para derivar requisitos vinculados a UR-05.

## Historial de versiones

| Versión | Fecha | Cambio |
| --- | --- | --- |
| 0.1 | 22/09/2026 | Primera acta elaborada a partir de la entrevista de aclaración de UR-05. |
| 0.2 | 22/09/2026 | Se declara como aclaración posterior a A03 y se actualiza su efecto sobre la línea base. |
