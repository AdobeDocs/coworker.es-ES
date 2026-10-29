---
title: Mida el impacto y la atribución de marketing con el chat de compañeros
description: Utilice el chat de compañeros para medir el impacto incremental de cada canal, encontrar dónde se satura el gasto, crear escenarios de presupuesto hipotéticos y comprobar la calidad del modelo de marketing.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 2%
---

# Resumen de medición y atribución de marketing

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilice el chat de Adobe CX Enterprise Coworker para comprender el impacto incremental de cada canal y campaña de marketing, de modo que pueda asignar gastos para optimizar el retorno de la inversión. Vea cómo funcionan juntos los canales, dónde deja de dar frutos el gasto adicional y cómo se comparan las diferentes asignaciones presupuestarias antes de comprometerse.

La medición y la atribución de marketing es uno de los varios dominios de análisis en Coworker Chat. Para ver todos los dominios, consulta [Comenzar a analizar en el chat de compañeros](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) en Análisis de datos con el chat de compañeros.

**Óptimo para:** Analista, usuario empresarial

## Requisitos previos

<!-- FLAG: Confidence: High for the shared bullets (sourced from analytics-chat.md and the Skills and limitations table). They're confirmed for Measure campaign performance only; whether the marketing mix modeling use cases also need a data view or report suite connection is unknown. Low for the "Additional prerequisite" notes on the four marketing mix modeling rows in the Use cases table: incremental impact, response curves, budget scenarios, and model retraining describe a marketing mix model, but no source names the product or data that these use cases need. It could be Adobe Mix Modeler or Marketing Campaign Analytics (listed as an implementation path in implementation-guide.md). Confirm with the PM before publishing. -->

Para utilizar los casos de uso de esta página, necesita lo siguiente:

* Chat de compañeros conectado a sus vistas de datos de Customer Journey Analytics o a sus grupos de informes de Adobe Analytics. Ver [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Vea el acceso a las vistas de datos o a los grupos de informes que desee analizar. El chat de compañeros hereda sus permisos de Customer Journey Analytics o Adobe Analytics.

## Casos de uso

| Ejemplo de uso | Función |
| --- | --- |
| Descubra el impacto incremental de cada canal | Muestra el valor incremental de cada canal, cómo se amplifican los canales entre sí y la función de los factores externos.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué canales generaron las conversiones más incrementales?&quot;</li><li>&quot;¿Cómo se amplifican la búsqueda de pago y la visualización?&quot;</li></ul><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere un modelo de medición de marketing entrenado. *[Requisitos de producto y configuración por confirmar.]*</p> |
| Encuentre dónde comienza a saturar el gasto<p>![Encuentra dónde empieza a saturar el gasto](assets/marketing-measurement.png)</p> | Muestra las curvas de respuesta que revelan dónde deja de dar resultado el gasto adicional.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Dónde empieza a saturar el gasto en búsqueda de pago?&quot;</li><li>&quot;Mostrar curvas de respuesta para cada canal&quot;</li></ul><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere un modelo de medición de marketing entrenado. *[Requisitos de producto y configuración por confirmar.]*</p> |
| Crear escenarios de presupuesto hipotéticos | Compara las opciones de asignación en paralelo para admitir las decisiones de planificación.<p>**Ideal para:** usuario empresarial</p><p>**Mensajes de ejemplo:**</p><ul><li>&quot;Generar escenarios de presupuesto para el próximo trimestre&quot;</li><li>&quot;¿Qué sucede si cambio el 10 % de los gastos de la visualización a la búsqueda?&quot;</li></ul><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere un modelo de medición de marketing entrenado. *[Requisitos de producto y configuración por confirmar.]*</p> |
| Comprobar la calidad del modelo y cuándo volver a entrenar | Inspecciona la calidad del modelo, los detalles de formación y las métricas de puntuación para que sepa en qué medida confiar en una respuesta.<p>**Mejor para:** Analista</p><p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Hay otros factores que necesitamos para este modelo?&quot;</li><li>&quot;¿Es necesario volver a entrenar este modelo?&quot;</li></ul><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere un modelo de medición de marketing entrenado. *[Requisitos de producto y configuración por confirmar.]*</p> |
| [Medir el rendimiento de la campaña](/help/chat/use-cases/workflows.md#data-insights) | Consulte el rendimiento de las campañas, los canales y las propiedades web durante un periodo determinado.<p>**Mensaje de ejemplo:** &quot;¿Cómo funcionaron nuestras campañas web de Acrobat el mes pasado?&quot;</p><p>Para obtener más información, consulte [Información sobre los datos](/help/chat/use-cases/workflows.md#data-insights) en Casos de uso de Chat del compañero de trabajo.</p> |

## Aptitudes utilizadas

<!-- FLAG: Confidence: High for Measure campaign performance (workflows.md lists `cja`, `aa`, `dx-api`, and `knowledge-graph` for "Campaign performance"). `dx-api` and `knowledge-graph` aren't in the Skills and limitations table on analytics-overview.md. Low for the other four use cases: no source names their skills. Get the skill IDs from the PM, replace the placeholder row, and add the skills to the Skills and limitations table. -->

El compañero de trabajo emplea las siguientes habilidades en los casos de uso descritos en este artículo. Para obtener una lista de todas las habilidades de análisis, incluidos los permisos que requieren y lo que no cubren, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) en Análisis de datos con el chat de compañeros.

| Habilidad | Se usa para |
| --- | --- |
| `cja`, `aa`, `dx-api`, `knowledge-graph` | Medir el rendimiento de campaña |
| *[Aptitud por confirmar]* | Descubra el impacto incremental de cada canal<br>Descubra dónde empieza a saturar el gasto<br>Cree escenarios presupuestarios hipotéticos<br>Compruebe la calidad del modelo y cuándo volver a entrenar |

## Sugerencias para obtener mejores resultados

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the sample prompts. -->

* Asigne un nombre a los canales, las campañas y el intervalo de fechas que desee analizar.
* Mencione cualquier hipótesis que ya tenga, como dos canales trabajando juntos, para que el Chat del compañero pueda validarla o descartarla.
* Indique el cambio de presupuesto específico que desea probar al crear escenarios hipotéticos, como mover el 10 % de la inversión de un canal a otro.

## Próximos pasos

* Para obtener una descripción general del análisis de datos con Coworker Chat, incluidos los demás dominios de análisis y prácticas recomendadas, consulte [Analizar datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar el chat de compañeros y ver un ejemplo que funcione, consulta [Análisis de datos con el chat de compañeros](/help/chat/use-cases/data-insights/analytics-chat.md).
