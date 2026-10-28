---
title: Analizar el contenido y el rendimiento de Creative con el chat de compañeros
description: Utilice el chat de compañeros para encontrar lo que el contenido ganador tiene en común, atribuir ingresos a las imágenes que ven los clientes y comparar la creatividad en varios canales y audiencias.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 8e88ec793bd4ae6fe4692c1d5107fe01fe14bf7f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 1%
---

# Resumen del rendimiento de contenido

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilice el chat de Adobe CX Enterprise Coworker para comprender qué contenido gana y por qué, según los atributos de cada recurso, para que pueda invertir en lo que funciona. Vaya más allá de los archivos que reciben clics para ver qué imágenes, mensajería y temas generan participación e ingresos en los canales y audiencias.

El rendimiento del contenido es uno de los varios dominios de análisis en Coworker Chat. Para ver todos los dominios, consulta [Comenzar a analizar en el chat de compañeros](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) en Análisis de datos con el chat de compañeros.

**Ideal para:** usuario empresarial

## Requisitos previos

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). High for the third bullet: attribute-level and asset analysis needs Content Analytics components, which are available only in data views that are configured for Content Analytics (report/report.md in analytics-platform.en). This applies whichever skill runs the analysis. It's a shared bullet rather than a table row because it applies to every use case on this page. The SME confirmed (October 2026) that the skill doesn't support paid media yet, so the paid channel use case was rewritten for web and mobile. Support is planned, either in this skill or in a separate add-on skill (not decided). When it ships, consider restoring paid channels to that row with an "Additional prerequisite" note: paid media needs the Paid Media channel enabled in Content Analytics through an Experience Platform paid media source connector, such as Meta Ads or Google Ads, and comparing paid creative with on-site revenue needs custom tracking-key mapping (config/paid-media.md in analytics-platform.en). -->

Para utilizar los casos de uso de esta página, necesita lo siguiente:

* Chat de compañeros conectado a sus vistas de datos de Customer Journey Analytics o a sus grupos de informes de Adobe Analytics. Ver [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Vea el acceso a las vistas de datos o a los grupos de informes que desee analizar. El chat de compañeros hereda sus permisos de Customer Journey Analytics o Adobe Analytics.
* Vista de datos configurada para Content Analytics. Consulte [Configuración de Content Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/content-analytics/configuration/configuration) en la guía de Customer Journey Analytics.

## Casos de uso

| Ejemplo de uso | Función |
| --- | --- |
| Encuentre lo que el contenido ganador tiene en común<p>![Encuentre lo que el contenido ganador tiene en común](assets/content-performance.png)</p> | Muestra qué imágenes y mensajería funcionan en el nivel de atributo, no solo qué archivos reciben clics.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué tienen en común nuestras imágenes con mejor rendimiento?&quot;</li><li>&quot;¿Qué atributos de contenido generan la mayor participación?&quot;</li></ul> |
| Atribuir los ingresos al contenido que ven los clientes | Vincula la exposición de la imagen a los ingresos, las conversiones y la participación con la atribución algorítmica.<p>**Óptimo para:** Analista, usuario empresarial</p><p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué imágenes generaron la mayor cantidad de ingresos el trimestre pasado?&quot;</li><li>&quot;¿Cuántos ingresos están vinculados a la imagen en https://www.example.com/images/spring-sale.jpg?&quot;</li></ul> |
| Comparar contenido creativo entre dispositivos web y móviles | Muestra en una sola vista los elementos visuales y los temas que ganan en el sitio y en la aplicación móvil.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué temas creativos ganan en nuestra aplicación móvil y en nuestro sitio?&quot;</li><li>&quot;Comparar el rendimiento de las imágenes en nuestra aplicación móvil y en nuestro sitio&quot;</li></ul> |
| Saber qué elementos visuales mueven a cada audiencia | Muestra qué imágenes funcionan para cada audiencia como guías para la personalización y los informes creativos.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Qué imágenes funcionan mejor en cada segmento?&quot;</li><li>&quot;¿Qué imágenes funcionan para los nuevos visitantes?&quot;</li></ul> |

## Aptitudes utilizadas

<!-- FLAG: Confidence: Medium. The `analyze-content` skill is a foundational skill for content questions, so it's listed for every use case on this page. Confirm with the PM that it covers all four. -->

El compañero de trabajo emplea las siguientes habilidades en los casos de uso descritos en este artículo. Para obtener una lista de todas las habilidades de análisis, incluidos los permisos que requieren y lo que no cubren, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) en Análisis de datos con el chat de compañeros.

| Habilidad | Se usa para |
| --- | --- |
| `cja`,`analyze-content` <br/> (disponibilidad limitada) | Encuentra lo que el contenido ganador tiene en común<br>Atribuye los ingresos al contenido que ven los clientes<br>Compara los elementos creativos en la web y móviles<br>Sabe qué elementos visuales mueven a cada audiencia<p>Para obtener más información, consulte [Hacer preguntas sobre tu contenido](/help/chat/use-cases/data-insights/ask-content-questions.md).</p> |

## Sugerencias para obtener mejores resultados

<!-- FLAG: Confidence: High for the first bullet (SME feedback, October 2026). Medium for the rest: the second and third bullets are adapted from the best practices in analytics-overview.md, and the fourth bullet is inferred from the row descriptions. -->

* Cuando pregunte por una imagen específica, incluya su URL o ID de recurso. El compañero no puede identificar una imagen por su función en la página, como una imagen a pantalla completa o un titular.
* Asigne un nombre a la métrica y el intervalo de fechas que desea analizar, como los ingresos del último trimestre.
* Especifique los segmentos, audiencias o canales que desea comparar.
* Pregunte por los atributos de contenido, como imágenes, temas o mensajes, en lugar de por archivos individuales cuando desee saber por qué el contenido tiene un buen rendimiento.

## Próximos pasos

* Para saber cómo Coworker responde preguntas sobre contenido, consulta [Hacer preguntas sobre tu contenido](/help/chat/use-cases/data-insights/ask-content-questions.md) (disponibilidad limitada).
* Para obtener una descripción general del análisis de datos con Coworker Chat, incluidos los demás dominios de análisis y prácticas recomendadas, consulte [Analizar datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar el chat de compañeros y ver un ejemplo que funcione, consulta [Análisis de datos con el chat de compañeros](/help/chat/use-cases/data-insights/analytics-chat.md).
