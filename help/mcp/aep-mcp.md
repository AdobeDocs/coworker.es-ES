---
title: Herramientas de Experience Platform en CX Coworker Gateway
description: Descubra qué herramientas de Adobe Experience Platform están disponibles a través de CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '1947'
ht-degree: 6%
---

# Herramientas de Adobe Experience Platform en Adobe CX Coworker Gateway {#aep-mcp}

Puede utilizar las herramientas de producto de Adobe Experience Platform para inspeccionar esquemas, conjuntos de datos, configuración de control de datos, recursos del servicio de consultas y eventos de auditoría desde un cliente compatible con MCP. Estas herramientas están disponibles a través de [Adobe CX Coworker Gateway](overview.md) cuando su organización está habilitada y su cuenta de usuario tiene los permisos de Experience Platform requeridos.

>[!AVAILABILITY]
>
>La herramienta de producto de Experience Platform se encuentra en Beta. El acceso se realiza únicamente por invitación y requiere la habilitación de la organización de Adobe. Consulte [Acceder a las herramientas de CX Coworker Gateway](access.md).

## Resumen

| Herramienta | Descripción | Recurso | Competencias | Estado |
| --- | --- | --- | --- | --- |
| `search_allowed_ip_ranges` | Recuperar restricciones de acceso IP del servicio de consultas | Autenticación de Distiller de datos · Intervalos de IP | list | Activo |
| `search_audit` | Enumerar eventos de auditoría de actividades de usuario en Experience Platform | Consulta de auditoría · eventos de auditoría | lista, filtrar por tipo de recurso, acción, estado, intervalo de tiempo | Activo |
| `search_datasets` | Metadatos de ingesta por lotes y conjuntos de datos de consulta | API de catálogo · dataSets, lotes | lista, obtener, filtrar, enumerar los últimos, enumerar los archivos | Activo |
| `search_class_relations` | Buscar relaciones de clase empresarial de Experience Platform | Relaciones de clase · índice YAML estático | buscar por token, término múltiple, coincidencia parcial | Activo |
| `search_data_access` | Enumerar archivos de lotes de ingesta con errores | API de acceso a datos · lotes con errores | enumerar archivos con errores | Activo |
| `search_data_lake` | Inspeccionar metadatos de conjuntos de datos y estado de lotes | API de Data Lake · conjuntos de datos, lotes | obtener, obtener tamaño, enumerar lotes con errores | Activo |
| `search_dule` | Etiquetas, políticas y acciones de gobernanza de datos de consulta | Administración de datos · etiquetas, políticas, marketing_actions | list, get, list enabled, evaluate | Activo |
| `search_query_service` | Consultas, consultas SQL, plantillas, programaciones, alertas | Servicio de consultas: consultas, plantillas, programaciones y alertas | list, get, filter, get connection params | Activo |
| `search_sandbox_health_assessment` | Recupere los resultados más recientes de la evaluación de la comprobación de estado Ejecutar y operar para la zona protegida actual | Ejecutar y operar · evaluaciones de comprobación de estado | lista, obtener por nombre de cheque | Activo |
| `search_schema_registry` | Esquemas, grupos de campos, clases y tipos de XDM de consulta | Registro de esquemas: esquemas, grupos de campos, clases, data_types, descriptores | lista, obtener, filtrar por contenedor | Activo |
| `execute_observability_metrics_query` | Consultar las métricas de [!DNL Observability Insights] de la zona protegida actual o de todas las zonas protegidas | Observability Insights · métricas | consultas de series temporales y acumuladas, solicitudes multimétricas, filtros de etiquetas, groupBy/exclude, disminución de resolución por métrica | Activo |
| `inspect_observability_breaches` | Detectar intervalos de infracción de [!DNL Observability Insights] en los que una métrica superó su línea de base configurada | Observability Insights · brechas | intervalos de infracción de lista por serie, organización y ámbito de zona protegida | Activo |

## Referencia de herramienta

### search_allowed_ip_range

**Recurso:** Autenticación de Distiller de datos · Intervalos de IP
**Estado:** activo

Recupere todas las restricciones de acceso IP configuradas para el servicio de consulta en la zona protegida actual. Devuelve el ID de organización y la lista de intervalos de IP permitidos. Solo está disponible para los clientes con el complemento Data Distiller.

**Capacidades:** enumera los intervalos de IP permitidos para el servicio de consultas

No hay parámetros.

### search_audit

**Recurso:** Consulta de auditoría · eventos de auditoría
**Estado:** activo

Enumere registros con marca de tiempo de actividades de usuario en todos los servicios de Experience Platform. Devuelve el tipo de acción, el correo electrónico del usuario, la información del recurso y el estado del evento. Use `asset_type` y `action` para reducir los resultados. El valor predeterminado son los últimos 7 días cuando no se especifica ningún intervalo de tiempo. Limitado a los últimos 1000 registros y eventos de los últimos 90 días.

**Funciones:** enumerar eventos de auditoría, filtrar por tipo de recurso, acción, estado, intervalo de tiempo, paginación

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `action` | No | Filtrar por tipo de acción. Valores comunes (separados por comas para OR): `Create`, `Delete`, `Update`, `Enable`, `Disable` |
| `asset_type` | No | Filtre por tipo de recurso. Debe ser uno de: `Dataset`, `Schema`, `Segment`, `Destination`, `Source Data Flow`, `Merge Policy`, `Identity Namespace`, `Identity Graph`, `Sandbox`, `Role`, `Query`, `Scheduled Query`, `Datastream`, `Computed Attribute`, `Field Group`, `Class`, `Data Types`, `Account`, `Product Profile`, `Query Template`, `Work Order`, `Audit Logs`, `Access Control Policy` |
| `status` | No | Filtre por estado de evento. Valores: `Success`, `Failure`, `Allow`, `Deny`. Separación por comas para OR |
| `start_time` | No | Marca de hora más temprana. ISO 8601 UTC con ms, p. ej. `2024-01-15T00:00:00.000Z` |
| `end_time` | No | Última marca de tiempo. ISO 8601 UTC con ms |
| `property_filter` | No | Expresión de filtro sin procesar, p. ej. `action==create`. Prefiera los parámetros dedicados anteriores |
| `orderby` | No | Orden: `timestamp` (asc) o `-timestamp` (desc) |
| `limit` | No | Número máximo de resultados (3-1000, predeterminado 50) |
| `start` | No | Desplazamiento de paginación. Incrementar por valor límite para cada página |
| `query_id` | No | ID de consulta de una respuesta anterior para repetir la misma consulta |

### search_datasets

**Recurso:** API de catálogo · dataSets, lotes
**Estado:** activo

Herramienta de envío unificado para el servicio de catálogo de Experience Platform. Metadatos de conjuntos de datos de consulta (referencias de esquema, etiquetas, información de creación) o registros de ingesta por lotes (estado, métricas, listas de archivos). Use `dataset/list` para descubrir conjuntos de datos, `batch/list` para comprobar el estado de la ingesta y `batch/list_files` o `batch/get_meta_files` para inspeccionar el contenido específico del lote. Todas las operaciones son de solo lectura.

**Capacidades:** enumerar conjuntos de datos, obtener conjunto de datos, enumerar lotes, obtener lote, enumerar el último lote por conjunto de datos, enumerar archivos por lotes, obtener archivos meta por lotes (errores de fila, archivos de entrada)

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `dataset` o `batch` |
| `operation` | Sí | `list`, `get`, `list_last`, `list_files`, `get_meta_files`. Combinaciones válidas: conjunto de datos → lista, obtener; lote → los cinco |
| `resource_id` | No | Conjunto de datos o ID de lote. Necesario para `dataset/get`, `batch/get`, `batch/list_files`, `batch/get_meta_files` |
| `query_params.limit` | No | Resultados máximos por página (máximo 100). Se aplica a todas las operaciones de lista |
| `query_params.start` | No | Desplazamiento de paginación. Se aplica a todas las operaciones de lista |
| `query_params.order_by` | No | Dirección del orden, p. ej. `asc:created,updated`. Se aplica a todas las operaciones de lista |
| `query_params.properties` | No | Lista de permitidos de propiedades separadas por comas. Se aplica a dataset/list, dataset/get, batch/list, batch/list_last |
| `query_params.name` | No | Filtrar conjuntos de datos por nombre (solo conjunto de datos/lista) |
| `query_params.tags` | No | Filtrar conjuntos de datos por etiquetas, p. ej. `unifiedProfile:enabled:true` (solo conjunto de datos/lista) |
| `query_params.property_filter` | No | Filtro regex en objetos de respuesta (conjunto de datos/lista y lote/lista) |
| `query_params.status` | No | Filtrar lotes por estado: `success`, `failed`, `loading`, `active` (solo lote/lista) |
| `query_params.dataset_id` | No | Asignar lotes a un conjunto de datos específico (lote/lista y lote/lista_último) |
| `query_params.created_after` | No | Filtrar lotes creados después de la marca de tiempo Unix en ms (solo lote/lista) |
| `query_params.created_before` | No | Filtrar lotes creados antes de la marca de tiempo Unix en ms (solo lote/lista) |
| `query_params.last_batch_status` | No | Filtrar por el último estado del lote (batch/list_last solamente) |
| `query_params.aggregate` | No | Devolver métricas agregadas en el nivel raíz (lote/obtener solo) |
| `query_params.path` | No | Archivo Meta para descargar: `row_errors`, `input_files`, `row_errors_sample.json` (solo batch/get_meta_files) |

### search_class_Relations

**Recurso:** relaciones de clase · índice YAML estático
**Estado:** activo

Busque relaciones de clase empresarial de Experience Platform por nombre mediante el índice estático `class_relations_v1.yaml`. No se realizan llamadas a la API de Experience Platform. Acepta un único término o términos separados por comas; cada término se compara con los nombres de clase utilizando la coincidencia de tokens parciales. Devuelve clases coincidentes con relaciones directas (a las que apunta cada clase) y relaciones inversas (a las que las clases apuntan de nuevo). Utilice esto para comprender las relaciones de entidad antes de crear consultas, flujos de datos o composiciones de esquema.

**Capacidades:** búsqueda por token, búsqueda separada por comas de varios términos, coincidencia de token parcial, expansión de sinónimo bidireccional

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `query` | Sí | Nombre de clase empresarial o tipo de objeto que buscar. Admite coincidencias parciales de tokens (`dat` coincide con `dataset`, `data_type`, etc.). Pase varios términos separados por comas para buscar varias clases a la vez (p. ej. `dataset, schema`) |
| `n` | No | Número máximo de resultados coincidentes que se devolverán (predeterminado 5, mínimo 1) |

### search_data_access

**Recurso:** API de acceso a datos · lotes con errores
**Estado:** activo

Acceda a archivos desde lotes de ingesta de datos de Experience Platform con errores. Use `failed_batch/list_failed` para enumerar los archivos que pertenecen a un lote erróneo para el diagnóstico de errores. Requiere un ID de lote para todas las operaciones. Nota: `file/get` y `dataset/preview` están deshabilitados ya que exponen datos de registro reales. Todas las operaciones son de solo lectura.

**Capacidades:** lista archivos de un lote de ingesta fallido

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `failed_batch` — lista de archivos de un lote de ingesta fallido |
| `operation` | Sí | `list_failed`: la única operación compatible |
| `resource_id` | Sí | ID de lote del lote fallido |
| `query_params.start` | No | Índice de inicio de paginación, p. ej. `1` |
| `query_params.limit` | No | Número de resultados por página; p. ej. `10` |
| `query_params.path` | No | Filtro de nombre de archivo completo, p. ej. `profiles.csv` |


### search_data_lake

**Recurso:** API de lago de datos · conjuntos de datos, lotes
**Estado:** activo

Inspeccione los metadatos por lotes y conjuntos de datos de la capa del lago de datos. Use `get` para metadatos completos, `get_size` para métricas de tamaño de ingesta y almacenamiento, y `list_failed` para supervisar errores de ingesta en un período de tiempo. Valores predeterminados de los últimos 7 días cuando no se proporciona ningún intervalo de tiempo para `list_failed`. Todas las operaciones son de solo lectura y requieren un ID de recurso.

**Capacidades:** obtiene metadatos por lotes/conjunto de datos, obtiene métricas de tamaño de almacenamiento y enumera lotes con errores en un intervalo de tiempo

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `dataset` o `batch` |
| `operation` | Sí | `get`, `get_size`, `list_failed`. `list_failed` solo admite `batch` tipo de entidad |
| `resource_id` | Sí | ID de conjunto de datos o ID de lote. Para `list_failed`: el ID del conjunto de datos para el ámbito falla al |
| `query_params.created_after` | No | Inicio de la ventana de tiempo. Marca de tiempo Unix en ms |
| `query_params.created_before` | No | Fin de la ventana de tiempo. Marca de tiempo Unix en ms |
| `query_params.limit` | No | Resultados máximos por página (máximo 100) |
| `query_params.order_by` | No | Dirección del orden, p. ej. `desc:created` |

### search_dule

**Recurso:** Control de datos · etiquetas, políticas, marketing_actions
**Estado:** activo

Consulte la API del servicio de directivas para ver las etiquetas de uso de datos, las directivas y las acciones de marketing. Use `marketing_action/evaluate` para comprobar si una acción de marketing en datos con etiquetas específicas infringe alguna directiva de gobernanza. Todas las operaciones son de solo lectura.

**Funciones:** enumerar/obtener etiquetas de uso de datos, enumerar/obtener directivas, enumerar directivas habilitadas, enumerar/obtener acciones de marketing, evaluar acciones de marketing contra etiquetas

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `label`, `policy` o `marketing_action` |
| `operation` | Sí | `list`, `get`, `list_enabled` (solo directiva), `evaluate` (solo marketing_action). `list_enabled` no requiere ámbito |
| `scope` | No | `core` (definido por Adobe) o `custom` (definido por org). Necesario para `list`, `get`, `evaluate`; no se usa para `list_enabled` |
| `resource_id` | No | Nombre de etiqueta, ID de política o nombre de acción de marketing. Necesario para `get` y `evaluate` |
| `query_params.dule_labels` | No | Etiquetas separadas por comas (p. ej. `C1,C3`). Necesario para `marketing_action/evaluate`; filtro opcional para `policy/list` |
| `query_params.limit` | No | Resultados máximos |
| `query_params.start` | No | Cursor de paginación a partir del valor `_page.next` de una respuesta anterior |
| `query_params.orderby` | No | Campos de ordenación separados por comas |
| `query_params.property_filter` | No | Expresión de filtro, p. ej. `name==C1` |
| `query_params.marketing_action` | No | Restringir la lista de directivas a las directivas que hacen referencia a esta acción de marketing (solo directiva/lista) |
| `query_params.include_draft` | No | Incluir directivas de BORRADOR en `marketing_action/evaluate` (predeterminado: solo directivas HABILITADAS) |

### search_query_service

**Recurso:** Servicio de consultas · consultas, plantillas, programaciones, ejecuciones de programación, conexiones, suscripciones de alerta
**Estado:** activo

Herramienta unificada para recursos del servicio de consultas. Mostrar y recuperar consultas Ad hoc, plantillas SQL guardadas, consultas programadas y sus ejecuciones, parámetros de conexión interactivos (para clientes psql/JDBC) y suscripciones de alertas. Para las listas de consulta, el valor predeterminado es `isService==false,isParentLevel==true` para filtrar el tráfico interno. Todas las operaciones son de solo lectura.

**Capacidades:** consultas list/get, plantillas list/get, programaciones list/get, ejecuciones list/get de programación, obtener parámetros de conexión, enumerar suscripciones de alerta

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `query`, `query_template`, `schedule`, `schedule_run`, `connection`, `alert_subscription` |
| `operation` | Sí | `list`, `get`, `get_connection_params`, `list_by_u...` |

### execute_observability_metrics_query

**Recurso:** Perspectivas de observabilidad · métricas
**Estado:** activo

Consulte las métricas de [!DNL Observability Insights] de la zona protegida actual o de todas las zonas protegidas de su organización. Admite varias métricas en una sola solicitud, filtros basados en etiquetas y disminución de resolución por métrica. Para `scope=org`, incluya al menos un filtro `groupBy` en cada métrica. Todas las operaciones son de solo lectura.

**Capacidades:** puntos de datos de métricas de consulta, series de tiempo o agregados, solicitudes de varias métricas, filtros de etiquetas, groupBy/exclude, disminución de resolución por métrica

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `metrics` | Sí | Matriz de especificaciones de métricas. Cada uno incluye `name` (nombre de métrica completo), `aggregator` (`sum`, `avg`, `min`, `max`, `count`, `last`, `p50`, `p95`, `p99`, variantes de histograma o `absent`), `filters` opcional y `downsample` opcional |
| `start` | Sí | Inicio de ventana, ISO 8601, p. ej. `2026-01-15T00:00:00.000Z`. Debe ser anterior a `end`. Ventana máxima: 31 días |
| `end` | Sí | Fin de ventana, ISO 8601. Debe ser posterior a `start` |
| `granularity` | No | Tamaño del bloque de tiempo: `MINUTE`, `FIVE_MINUTE`, `TEN_MINUTE`, `FIFTEEN_MINUTE`, `THIRTY_MINUTE`, `HOUR`, `FOUR_HOUR`, `TWELVE_HOUR`, `DAY`, `TWO_DAY`, `WEEK`, `MONTH` o `ALL` (contrae la ventana en un solo agregado). Omitir para permitir que el servidor elija |
| `scope` | No | `sandbox` (predeterminado) consulta la zona protegida actual. `org` consulta todas las zonas protegidas de su organización y recomienda un filtro `groupBy` en cada métrica |

Cada filtro de `metrics[].filters` incluye `name` (nombre de etiqueta), `value` (coincidencia exacta, comodín o regex) y `groupBy` y `exclude` booleanos opcionales.

### inspect_observability_breves

**Recurso:** Observability Insights · Incumplimientos
**Estado:** activo

Detectar intervalos de brecha [!DNL Observability Insights], ventanas de tiempo en las que una métrica excedió su línea de base configurada, para la zona protegida actual o en todas las zonas protegidas de su organización. Devuelve intervalos coincidentes previamente por serie. Las infracciones abiertas que aún están en curso al final de la ventana se devuelven con `end: null`. Todas las operaciones son de solo lectura.

**Capacidades:** intervalos de infracción de lista por serie, organización y ámbito de zona protegida

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `metrics` | Sí | Matriz de especificaciones de infracción. Cada uno incluye `name` (nombre de métrica completo) y `filters` opcional |
| `start` | Sí | Inicio de ventana, ISO 8601. Debe ser anterior a `end`. Ventana máxima: 31 días |
| `end` | Sí | Fin de ventana, ISO 8601 |
| `granularity` | No | Tamaño del bloque de tiempo, mismos valores que `execute_observability_metrics_query` excepto `ALL`. Cada contenedor se evalúa de forma independiente respecto a la línea de base |
| `scope` | No | `sandbox` (predeterminado) o `org`. En `org` sin un filtro de espacio aislado, incluya al menos un filtro con `groupBy: true` por métrica para que los resultados se dividan por esa dimensión en lugar de contraerse en la organización |

`inspect_observability_breaches` no acepta `aggregator` o `downsample` en `metrics[]`. La herramienta los configura internamente para evaluar la condición de infracción.

>[!NOTE]
>
>Ambas herramientas de Observability Insights también están limitadas a un estimado de 10 000 puntos de datos por solicitud. Reduzca el intervalo de tiempo, agregue filtros o utilice un elemento más grueso `granularity` si se rechaza una solicitud por exceder este límite.

### search_sandbox_health_evaluation

**Recurso:** Ejecutar y operar · evaluaciones de comprobación de estado
**Estado:** activo

Recupere los resultados más recientes de la evaluación de la comprobación de estado Ejecutar y Operar para la zona protegida actual. Devuelve los resultados de todas las categorías admitidas, incluidos los esquemas y las identidades, la segmentación, la ingesta y el perfil. Para identificar la causa raíz sin una búsqueda independiente, cada resultado incluye los recursos afectados tras una comprobación errónea. Solo se devuelven comprobaciones con un nombre publicado y legible en lenguaje natural. Todas las operaciones son de solo lectura.

>[!NOTE]
>
>Esta herramienta sólo recupera los resultados de la evaluación. Para solucionar un problema marcado, utilice el panel de detalles de comprobación de estado en la interfaz de usuario de [!DNL Experience Platform]. Ver [Comprobaciones de estado](https://experienceleague.adobe.com/es/docs/experience-platform/run-and-operate/health-checks). La guía de corrección automática para las comprobaciones de estado admitidas está disponible como aptitud en [CX Coworker Chat](../chat/overview.md).

**Capacidades:** muestran todos los resultados de las comprobaciones de estado de la zona protegida actual y obtienen los resultados de una comprobación con nombre

No hay parámetros.
