---
title: Implementación y administración de Analytics con Coworker Chat
description: Planifique la implementación, realice un seguimiento de la misma en una lista de comprobación y valide los datos de Adobe Analytics, Customer Journey Analytics y Experience Platform con Coworker Chat.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 5973a87d21b23d7621366108716cbd476e6f66ae
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 0%
---

# Información general sobre la implementación y administración inteligentes

Use el chat de Adobe CX Enterprise Coworker para configurar, migrar y administrar su implementación de Analytics, y para asegurarse de que puede confiar en los datos detrás de cada respuesta. Sus compañeros pueden planificar su implementación, convertir ese plan en una lista de comprobación que su equipo pueda seguir y validar los datos una vez recopilados.

La implementación y administración inteligentes es uno de los varios dominios de análisis en Coworker Chat. Para ver todos los dominios, consulta [Comenzar a analizar en el chat de compañeros](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) en Análisis de datos con el chat de compañeros.

**Óptimo para:** Administrador

## Cómo encaja el flujo de trabajo de implementación

Los casos de uso de esta página siguen un flujo de trabajo opcional de tres fases. Puede utilizar cualquier escenario por su cuenta. Por ejemplo, puede validar los datos sin generar primero un plan o una lista de comprobación.

1. **Plan:** Obtenga un plan de implementación o actualización personalizado y ordenado. Ver [Planifique su implementación con Coworker](/help/chat/use-cases/data-insights/implementation-guide.md).
1. **Implementar:** Convierta su plan en una lista de comprobación en Proyectos de compañeros que su equipo puede asignar y rastrear. Consulte [Generar una lista de comprobación de implementación con proyectos de compañeros](/help/chat/use-cases/data-insights/intelligent-checklist.md).
1. **Validar:** Confirme que los datos se han configurado y recopilado correctamente. Consulte los casos de uso de validación en la tabla [Casos de uso](#use-cases).

## Requisitos previos

<!-- FLAG: Confidence: Medium for the shared bullets. They differ from the other domain pages on purpose: planning doesn't query your data, and Experience Platform validation uses Experience Platform datasets rather than data views or report suites. The permission inheritance for Experience Platform is inferred. High for the "Additional prerequisite" notes in the Use cases table, which are sourced from the "Before you begin" section of each linked article. Some of those articles flag their own prerequisites as unconfirmed (implementation-guide.md, intelligent-checklist.md, streaming-media-validation.md), so verify those rows when those flags are resolved. Validate dataset quality for Customer Journey Analytics is a video page with no stated prerequisites, so it isn't listed. -->

Para utilizar los casos de uso de esta página, necesita lo siguiente:

* Acceso al chat con compañeros. Ver [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Vea el acceso a los datos que desea validar. El chat de compañeros hereda los permisos de las aplicaciones de Adobe a las que se conecta.

## Casos de uso

| Ejemplo de uso | Función |
| --- | --- |
| [Planifique su implementación](/help/chat/use-cases/data-insights/implementation-guide.md)<p>![Planifique su implementación](../../assets/ui-guide-6.png)</p> | Crea un plan personalizado paso a paso para implementar Customer Journey Analytics, actualizar desde Adobe Analytics o configurar la recopilación de Content Analytics, Marketing Campaign Analytics o medios de streaming en Edge. Los planes incluyen detalles como propietarios, estimaciones de esfuerzo, dependencias y pasos de validación.<p>**Mensaje de ejemplo:** &quot;Ayúdeme a planificar la implementación de Customer Journey Analytics&quot;</p><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere que sepa qué ruta de implementación se aplica a usted y detalles básicos sobre su entorno actual, como su estado de licencia o la ruta de acceso de ingesta de datos planeada.</p><p>Para obtener más información, consulte [Planificar su implementación con el Compañero de trabajo](/help/chat/use-cases/data-insights/implementation-guide.md).</p> |
| [Generar una lista de comprobación de implementación](/help/chat/use-cases/data-insights/intelligent-checklist.md)<p>![Generar una lista de comprobación de implementación](../../assets/data-validation-aa-cja/date-detail.png)</p> <p>Experimental</p> | Convierte el plan de implementación de Customer Journey Analytics en una lista de comprobación en Proyectos de compañeros, donde su equipo puede asignar pasos, rastrear el estado y agregar puertas de aprobación.<p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere una conversación completa sobre la guía de implementación y acceso a los proyectos de compañeros de su organización.</p><p>Para obtener más información, consulte [Generar una lista de comprobación de implementación con proyectos de compañeros](/help/chat/use-cases/data-insights/intelligent-checklist.md).</p> |
| [Validar datos al actualizar de Adobe Analytics a Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)<p>![Validar datos al actualizar de Adobe Analytics a Customer Journey Analytics](../../assets/data-validation-aa-cja/trend-bar-card.png)</p> | Compara dimensiones, métricas y tendencias entre sus grupos de informes de Adobe Analytics y las vistas de datos de Customer Journey Analytics, marca discrepancias y, a continuación, recomienda correcciones para admitir la actualización.<p>**Óptimo para:** Administrador, Analista</p><p>**Mensajes de ejemplo:**</p><ul><li>&quot;Comparar mi grupo de informes AA con mi vista de datos de CJA&quot;</li><li>&quot;¿Qué métricas no coinciden entre AA y CJA?&quot;</li></ul><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere el grupo de informes de Adobe Analytics que desea validar y la vista de datos de Customer Journey Analytics que contiene los mismos datos.</p><p>Para obtener más información, vea [Validar datos con el compañero al actualizar de Adobe Analytics a Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).</p> |
| [Valide su implementación de medios de streaming](/help/chat/use-cases/data-insights/streaming-media-validation.md)<p>![Valide su implementación de medios de streaming](../../assets/ui-guide-8.png)</p> <p>Experimental</p> | Comprueba la secuencia de datos, el esquema, el conjunto de datos, la vista de datos y los datos de sesión para confirmar que el seguimiento de medios de streaming está configurado y recopila datos correctamente.<p>**Mensaje de ejemplo:** &quot;¿Cuán saludable es mi implementación de medios de transmisión en general?&quot;</p><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere que los datos de Experience Platform y Customer Journey Analytics de su organización estén conectados a Coworker. Para algunos modos de validación, también necesita un ID de sesión de vídeo o un archivo de registro.</p><p>Para obtener más información, consulte [Validar la implementación de medios de streaming con Coworker](/help/chat/use-cases/data-insights/streaming-media-validation.md).</p> |
| [Validar la calidad del conjunto de datos para Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)<p>![Validar la calidad del conjunto de datos para Customer Journey Analytics](../../assets/data-validation-aep/dataset-validation.png)</p> <p>Experimental (semana próxima)</p> | Identifica los conjuntos de datos que alimentan los informes de Customer Journey Analytics y, a continuación, comprueba los esquemas, la calidad de la identidad y la calidad del campo para que pueda resolver los problemas antes de crear los paneles.<p>Para obtener más información, consulte [Validar datos de Customer Journey Analytics con la aptitud de validación de datos en el compañero](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md).</p> |
| [Validar datos después de la ingesta en Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md)<p>![Validar datos después de la ingesta en Experience Platform](../../assets/data-validation-aep/null-values.png)</p> | Ejecuta comprobaciones estadísticas y semánticas en conjuntos de datos y campos de Experience Platform para encontrar problemas de calidad de datos, como valores no válidos o problemas de asignación, después de una nueva implementación o como parte de la administración continua de datos.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;Validar el conjunto de datos [dataset name]&quot;</li><li>&quot;Validar el [campo de datos] del conjunto de datos [nombre del conjunto de datos]&quot;</li></ul><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere el nombre o el ID del conjunto de datos que desea validar. De forma opcional, puede proporcionar el nombre de un campo específico para validar.</p><p>Para obtener más información, consulte [Validar los datos de Experience Platform con el colaborador](/help/chat/use-cases/data-insights/data-validation-aep.md).</p> |
| [Acelerar datos](/help/chat/use-cases/data-insights/accelerate-data-insights.md) | Muestra en un vídeo cómo el colaborador planifica la implementación, ejecuta acciones admitidas y guía los pasos de producto y desarrollo en Adobe Experience Manager, Experience Platform, Web SDK y Customer Journey Analytics hasta que los datos de participación del sitio web estén listos para analizarse.<p>Para obtener más información, consulte [Acelerar la obtención de datos con los colaboradores, AEM y CJA](/help/chat/use-cases/data-insights/accelerate-data-insights.md).</p> |

## Aptitudes utilizadas

<!-- FLAG: Confidence: High for `aa-cja-validation` (listed in the Skills and limitations table and in workflows.md). Medium for `data-validation`: workflows.md lists it, but with a TODO to confirm the skill ID with engineering. Medium for the implementation guide skills and the Streaming Media Validation skill: the articles name them but don't give technical skill IDs, so they're listed by display name. Only `aa-cja-validation` currently appears in the Skills and limitations table on analytics-overview.md. Add the others there so the link below covers them. -->

El compañero de trabajo emplea las siguientes habilidades en los casos de uso descritos en este artículo. Para obtener una lista de todas las habilidades de análisis, incluidos los permisos que requieren y lo que no cubren, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) en Análisis de datos con el chat de compañeros.

| Habilidad | Se usa para |
| --- | --- |
| Habilidades de guía de implementación (una para Customer Journey Analytics, una actualización de Adobe Analytics a Customer Journey Analytics, Content Analytics, Marketing Campaign Analytics y medios de streaming) | Planifique su implementación |
| `aa-cja-validation` | Validación de datos al actualizar de Adobe Analytics a Customer Journey Analytics |
| Aptitud de validación de medios de streaming | Validación de la implementación de Streaming Media |
| Aptitud de validación de datos (`data-validation`) | Validar la calidad del conjunto de datos para Customer Journey Analytics<br>Validar los datos después de la ingesta en Experience Platform |

## Sugerencias para obtener mejores resultados

* Asigne un nombre al grupo de informes y a la vista de datos específicos que desea comparar al validar los datos.
* Use los resultados de validación como guía para sus propios cambios. Las habilidades de validación de medios de streaming y validación de datos identifican problemas, pero no cambian la configuración ni los datos.
* Vuelva a ejecutar la validación de medios de streaming después de cada cambio de implementación. Funciona bajo demanda y no proporciona una monitorización continua.
* Utilice las habilidades de la guía de implementación solo para la planificación. No acceden a sus sistemas de Adobe ni realizan la implementación.

## Próximos pasos

* Para obtener una descripción general del análisis de datos con Coworker Chat, incluidos los demás dominios de análisis y prácticas recomendadas, consulte [Analizar datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar el chat de compañeros y ver un ejemplo que funcione, consulta [Análisis de datos con el chat de compañeros](/help/chat/use-cases/data-insights/analytics-chat.md).
