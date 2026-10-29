---
title: Analizar el rendimiento empresarial y los KPI con el chat de compañeros
description: Utilice el chat de compañeros para explicar por qué se movieron las métricas, prever hacia dónde se dirigen, preparar revisiones de rendimiento y convertir los análisis repetidos en habilidades reutilizables.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 2%
---

# Resumen del rendimiento empresarial

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Use el chat de Adobe CX Enterprise Coworker para comprender el rendimiento de la empresa, por qué se movió una métrica, hacia dónde se dirige y qué hacer a continuación. Investigue los cambios en las métricas clave, proyéctelas y convierta sus conclusiones en resúmenes preparados para las partes interesadas y habilidades reutilizables.

El rendimiento empresarial es uno de los varios dominios de análisis en Coworker Chat. Para ver todos los dominios, consulta [Comenzar a analizar en el chat de compañeros](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) en Análisis de datos con el chat de compañeros.

**Óptimo para:** Analista, usuario empresarial

## Requisitos previos

Para utilizar los casos de uso de esta página, necesita lo siguiente:

* Chat de compañeros conectado a sus vistas de datos de Customer Journey Analytics o a sus grupos de informes de Adobe Analytics. Ver [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Vea el acceso a las vistas de datos o a los grupos de informes que desee analizar. El chat de compañeros hereda sus permisos de Customer Journey Analytics o Adobe Analytics.

## Casos de uso

| Ejemplo de uso | Función |
| --- | --- |
| [Explorar tendencias y causas básicas](/help/chat/use-cases/data-insights/root-cause-analysis.md)<p>![Explorar tendencias y causas básicas](../../assets/data-validation-aa-cja/trend-line-card.png)</p> | Identifica las tendencias en los datos de Customer Journey Analytics y Adobe Analytics y los factores que impulsan los cambios en el rendimiento, sin consultas manuales.<p>**Mensaje de ejemplo:** &quot;¿Por qué cayeron las conversiones la semana pasada?&quot;</p><p>Para obtener más información, consulte [Customer Journey Analytics y compañeros](/help/chat/use-cases/data-insights/root-cause-analysis.md).</p> |
| [Explicar por qué se movió una métrica](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Ejecuta un análisis de causa raíz que muestra las dimensiones y segmentos detrás de un cambio y descarta el resto.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Por qué los ingresos aumentaron el martes?&quot;</li><li>&quot;¿Cuál fue el motivo del cambio en las sesiones de este mes?&quot;</li></ul><p>Para obtener más información, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Preparar revisiones de rendimiento empresarial](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Convierte las métricas de confianza en una historia de rendimiento explicada, con conclusiones y pasos recomendados a continuación.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;Dame un resumen ejecutivo del mes pasado&quot;</li><li>&quot;Resumir el rendimiento para el equipo de liderazgo&quot;</li></ul><p>Para obtener más información, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Previsión a la que se dirige una métrica](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Proyecta una métrica a partir de datos históricos para que pueda ver una pérdida.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;Prever sesiones para los próximos 30 días&quot;</li><li>&quot;¿Estamos en camino de alcanzar nuestra meta de ingresos?&quot;</li></ul><p>Para obtener más información, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Crear aptitudes de Customer Journey Analytics personalizadas](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Convierta un análisis que repita en una habilidad reutilizable que persiste entre sesiones.<p>**Mensaje de ejemplo:** &quot;Convierta este análisis de ingresos semanal en una aptitud reutilizable&quot;</p><p>**Requisito previo adicional:** Además de los [requisitos previos generales](#prerequisites), este caso de uso también requiere el permiso Administrar habilidades.</p><p>Para obtener más información, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Repetir el análisis correcto entre mercados](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Aplica un enfoque analítico probado en todas las marcas, regiones o unidades de negocio.<p>**Mejor para:** Analista</p><p>**Mensaje de ejemplo:** &quot;Ejecute mi aptitud semanal de funnel para la vista de datos de EMEA&quot;</p><p>Para obtener más información, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |

## Aptitudes utilizadas

<!-- FLAG: Confidence: High for the root cause analysis skills, `cja-executive-summary`, forecasting with `cja` and `aa`, and `cja-skill-creator` for creating skills. All are listed in the Skills and limitations table and in workflows.md. Medium for mapping Repeat successful analysis across markets to `cja-skill-creator`: the row describes running a saved skill, which is inferred. workflows.md also lists `cja-bacom-anomaly-tracker-v2`, `cja-cno-weekly-pulse`, and `cja-reporting` for executive summaries. They're left out because they look org-specific. Confirm with the PM. -->

El compañero de trabajo emplea las siguientes habilidades en los casos de uso descritos en este artículo. Para obtener una lista de todas las habilidades de análisis, incluidos los permisos que requieren y lo que no cubren, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) en Análisis de datos con el chat de compañeros.

| Habilidad | Se usa para |
| --- | --- |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Explorar tendencias y causas básicas<br>Explicar por qué se movió una métrica |
| `cja-executive-summary` | Preparar revisiones de rendimiento empresarial |
| `cja`, `aa` | Previsión hacia la que se dirige una métrica |
| `cja-skill-creator` | Crear habilidades personalizadas de Customer Journey Analytics<br>Repetir el análisis correcto entre mercados |

## Sugerencias para obtener mejores resultados

* Asigne un nombre a la métrica y al periodo del cambio que desee investigar. El análisis de la causa raíz funciona en una métrica conocida durante un periodo conocido.
* Pregunte por las dimensiones de contribución si desea un desglose de un cambio de métrica.
* Solicite un horizonte de previsión, como &quot;próximos 30 días&quot;, al proyectar métricas.
* Especifique la audiencia para un resumen, como el liderazgo o el equipo de marketing, y solicite una descripción del paquete de diapositivas si planea presentar los resultados.
* Complete primero un análisis y, a continuación, pídale al chat de compañeros que lo guarde como una aptitud. Asigne un nombre claro y descriptivo a la aptitud y anote la frecuencia con la que planea reutilizarla.

## Próximos pasos

* Para obtener una descripción general del análisis de datos con Coworker Chat, incluidos los demás dominios de análisis y prácticas recomendadas, consulte [Analizar datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para ver el análisis de la causa raíz en acción, consulte [Customer Journey Analytics y compañeros](/help/chat/use-cases/data-insights/root-cause-analysis.md).
