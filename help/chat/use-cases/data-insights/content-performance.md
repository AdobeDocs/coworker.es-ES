---
title: Analizar el contenido y el rendimiento de Creative con el chat de compañeros
description: Utilice el chat de compañeros para encontrar lo que el contenido ganador tiene en común, atribuir ingresos a las imágenes que ven los clientes y comparar la creatividad en varios canales y audiencias.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: e3d485f7cd1c45bf3fd1217ffcceeccfd4242c7b
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%
---

# Resumen del rendimiento de contenido

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilice el chat de Adobe CX Enterprise Coworker para comprender qué contenido gana y por qué, según los atributos de cada recurso, para que pueda invertir en lo que funciona. Vaya más allá de los archivos que reciben clics para ver qué imágenes, mensajería y temas generan participación e ingresos en los canales y audiencias.

El rendimiento del contenido es uno de los varios dominios de análisis en Coworker Chat. Para ver todos los dominios, consulta [Comenzar a analizar en el chat de compañeros](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) en Análisis de datos con el chat de compañeros.

**Ideal para:** usuario empresarial

## Requisitos previos

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). Low for the third bullet: the attribute-level and image exposure descriptions suggest that these use cases rely on Content Analytics data in Customer Journey Analytics, and implementation-guide.md lists Content Analytics as an implementation path, but no source confirms this. It's a shared bullet rather than a table row because it would apply to every use case on this page. The paid channel row ("Compare Meta ad creative to our web banners") may need an additional data source, which would become an "Additional prerequisite" note on that row in the Use cases table. Confirm with the PM. -->

Para utilizar los casos de uso de esta página, necesita lo siguiente:

* Chat de compañeros conectado a sus vistas de datos de Customer Journey Analytics o a sus grupos de informes de Adobe Analytics. Ver [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Vea el acceso a las vistas de datos o a los grupos de informes que desee analizar. El chat de compañeros hereda sus permisos de Customer Journey Analytics o Adobe Analytics.
* Content Analytics se configura en Customer Journey Analytics para que Coworker Chat pueda analizar los atributos de contenido y la exposición a las imágenes. Para planificar una implementación de Content Analytics, consulte [Planificar su implementación con el Compañero de trabajo](/help/chat/use-cases/data-insights/implementation-guide.md).

## Casos de uso

| Ejemplo de uso | Función |
| --- | --- |
| Encuentre lo que el contenido ganador tiene en común<p>![Encuentre lo que el contenido ganador tiene en común](assets/content-performance.png)</p> | Muestra qué imágenes y mensajería funcionan en el nivel de atributo, no solo qué archivos reciben clics.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué tienen en común nuestras imágenes con mejor rendimiento?&quot;</li><li>&quot;¿Qué atributos de contenido generan la mayor participación?&quot;</li></ul> |
| Atribuir los ingresos al contenido que ven los clientes | Vincula la exposición de la imagen a los ingresos, las conversiones y la participación con la atribución algorítmica.<p>**Óptimo para:** Analista, usuario empresarial</p><p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué imágenes de héroe generaron la mayor cantidad de ingresos el trimestre pasado?&quot;</li><li>&quot;¿Cuántos ingresos están vinculados a este banner?&quot;</li></ul> |
| Comparar contenido creativo entre canales pagados y propios | Muestra qué elementos visuales y temáticas ganan en los canales web, móviles y de pago en una sola vista.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué temas creativos ganan en pago y en nuestro sitio?&quot;</li><li>&quot;Comparar la creatividad publicitaria de Meta con nuestros banners web&quot;</li></ul> |
| Saber qué elementos visuales mueven a cada audiencia | Muestra qué imágenes funcionan para cada audiencia como guías para la personalización y los informes creativos.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué imágenes funcionan mejor en cada segmento?&quot;</li><li>&quot;¿Qué imágenes funcionan para los nuevos visitantes?&quot;</li></ul> |

<!--
HIDDEN until the skills are confirmed. To publish, remove this comment wrapper.

## Skills used

FLAG: Confidence: Low. No source in the repo (workflows.md, the Skills and limitations table, or any data insights article) names the skills behind these use cases. Get the skill IDs from the PM, replace the placeholder rows, and add the skills to the Skills and limitations table on analytics-overview.md so that the link above the table covers them. When you unhide this section, wrap this FLAG note in its own HTML comment.

Coworker uses the following skills for the use cases described in this article. For a list of all analytics skills, including the permissions they require and what they don't cover, see [Skills and limitations](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analyze data with Coworker Chat.

| Skill | Used for |
| --- | --- |
| *[Skill to be confirmed]* | Find what winning content has in common<br>Attribute revenue to the content customers see<br>Compare creative across paid and owned channels<br>Know which visuals move each audience |

-->

## Sugerencias para obtener mejores resultados

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the row descriptions. -->

* Asigne un nombre a la métrica y el intervalo de fechas que desea analizar, como los ingresos del último trimestre.
* Especifique los segmentos, audiencias o canales que desea comparar.
* Pregunte por los atributos de contenido, como imágenes, temas o mensajes, en lugar de por archivos individuales cuando desee saber por qué el contenido tiene un buen rendimiento.

## Próximos pasos

* Para obtener una descripción general del análisis de datos con Coworker Chat, incluidos los demás dominios de análisis y prácticas recomendadas, consulte [Analizar datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar el chat de compañeros y ver un ejemplo que funcione, consulta [Análisis de datos con el chat de compañeros](/help/chat/use-cases/data-insights/analytics-chat.md).
