---
title: Comparación de audiencias y segmentos de clientes con el chat de compañeros
description: Utilice el chat de compañeros para comparar grupos de clientes, encontrar oportunidades de crecimiento pasadas por alto, rastrear tendencias de audiencia y convertir perspectivas en audiencias que pueda crear.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f914f4a123216985ae9b562413f26e7b8c29eb0f
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 2%
---

# Resumen del análisis de audiencias y segmentos

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Utilice el chat de Adobe CX Enterprise Coworker para comprender qué grupos de clientes se comportan de forma diferente y cómo, de modo que pueda centrarse en los que más importan. Compare canales, períodos de tiempo y segmentos en paralelo, realice un seguimiento de cómo cambian las audiencias con el paso del tiempo y convierta lo que encuentre en una audiencia que pueda crear.

El análisis de audiencias y segmentos es uno de los varios dominios de análisis en Coworker Chat. Para ver todos los dominios, consulta [Comenzar a analizar en el chat de compañeros](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) en Análisis de datos con el chat de compañeros.

**Óptimo para:** Analista, usuario empresarial

## Requisitos previos

<!-- FLAG: Confidence: High for the shared bullets (sourced from the Skills and limitations table and analytics-chat.md). Medium for the "Additional prerequisite" notes on the operational trends rows in the Use cases table: workflows.md lists the operational time-series skill as available for "All Eligible Applications" but doesn't state required permissions. Mapping Track audience size trends to the same requirement is inferred. Low for the "Additional prerequisite" note on the Take an insight into an audience row: inferred from the Audiences section of workflows.md, which lists Real-Time CDP as the application for audience creation. Confirm with the PM. -->

Para utilizar los casos de uso de esta página, necesita lo siguiente:

* Chat de compañeros conectado a sus vistas de datos de Customer Journey Analytics o a sus grupos de informes de Adobe Analytics. Ver [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Vea el acceso a las vistas de datos o a los grupos de informes que desee analizar. El chat de compañeros hereda sus permisos de Customer Journey Analytics o Adobe Analytics.

## Casos de uso

| Ejemplo de uso | Función |
| --- | --- |
| [Comparar rendimiento](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Comparar métricas en varios canales, períodos de tiempo o segmentos en paralelo.<p>**Mensaje de ejemplo:** &quot;Comparar ingresos por canal mes tras mes&quot;</p><p>Para obtener más información, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Comparar grupos de clientes](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Muestra qué grupos se comportan de forma diferente, sin que sea necesario escribir lógica de segmento.<p>**Ideal para:** usuario empresarial</p><p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Los visitantes sociales de pago generan una conversión diferente al correo electrónico?&quot;</li><li>&quot;Comparar los visitantes nuevos y los que regresan con los ingresos&quot;</li></ul><p>Para obtener más información, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Encuentre oportunidades de crecimiento ignoradas | Explora audiencias, recorridos y canales para identificar oportunidades que las cifras de rendimiento general pueden ocultar.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué audiencias se convierten por encima del promedio pero reciben poco tráfico?&quot;</li><li>&quot;¿Qué canales se infrautilizan para su tasa de conversión?&quot;</li></ul> |
| [Analizar tendencias y causas operativas](/help/chat/use-cases/workflows.md#data-insights) | Consulte datos de series temporales históricas para audiencias, conjuntos de datos y recorridos, e identifique la causa del cambio.<p>**Óptimo para:** Administrador, Analista</p><p>**Mensaje de ejemplo:** &quot;Mostrarme las tendencias de tamaño de audiencia durante los últimos 90 días&quot;</p><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere acceso a las audiencias, conjuntos de datos o recorridos que desea analizar.</p><p>Para obtener más información, consulte [Información sobre los datos](/help/chat/use-cases/workflows.md#data-insights) en Casos de uso de Chat del compañero de trabajo.</p> |
| Seguimiento de tendencias de tamaño de audiencia | Detecta audiencias que están creciendo o reduciéndose y analiza la causa.<p>**Óptimo para:** Administrador, Analista</p><p>**Mensaje de ejemplo:** &quot;¿Qué audiencias crecieron más rápido este trimestre?&quot;</p><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere acceso a las audiencias que desea rastrear.</p> |
| Incluir un insight en una audiencia | Pasa de una insight a una audiencia que se puede crear sin tener que volver a empezar.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;Abrir esta comparación en Analysis Workspace&quot;</li><li>&quot;Ayúdeme a crear una audiencia a partir de este grupo&quot;</li></ul><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere acceso a Real-Time Customer Data Platform y permiso para crear audiencias.</p> |

## Aptitudes utilizadas

<!-- FLAG: Confidence: High for Compare performance and Analyze operational trends and causes (skills listed for "Comparative analysis" and "Operational time-series & causal analysis" in workflows.md). Medium for Compare customer groups and Track audience size trends, which are mapped to the same skills based on their descriptions. Low for `audience-creation-flow`: inferred from the Audiences section of workflows.md. No skill is listed for Find overlooked growth opportunities because no source names one. Only `cja`, `aa`, and the root cause analysis skills currently appear in the Skills and limitations table on analytics-overview.md. -->

El compañero de trabajo emplea las siguientes habilidades en los casos de uso descritos en este artículo. Para obtener una lista de todas las habilidades de análisis, incluidos los permisos que requieren y lo que no cubren, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) en Análisis de datos con el chat de compañeros.

| Habilidad | Se usa para |
| --- | --- |
| `cja`, `aa` | Comparar rendimiento<br>Comparar grupos de clientes |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Comparar rendimiento |
| `operational-stats-causal-analysis` | Analizar tendencias y causas operativas<br>Rastrear tendencias de tamaño de audiencia |
| `audience-creation-flow` | Incluir un insight en una audiencia |

## Sugerencias para obtener mejores resultados

* Especifique los segmentos, audiencias, canales o dispositivos que desea incluir, excluir o comparar.
* Segmentos de referencia y otros componentes por su nombre exacto.
* Asigne un nombre a la métrica y el intervalo de fechas en los que quiere comparar, como los ingresos mes tras mes.
* Pregunte por las dimensiones de contribución si desea saber por qué un grupo se comporta de forma diferente a otro.

## Próximos pasos

* Para obtener una descripción general del análisis de datos con Coworker Chat, incluidos los demás dominios de análisis y prácticas recomendadas, consulte [Analizar datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para crear audiencias directamente en el chat de Coworker, consulta [Evaluar el estado de Experience Platform y crear audiencias a partir del lenguaje natural con Coworker](/help/chat/use-cases/audiences/create-audience-from-natural-language.md).
