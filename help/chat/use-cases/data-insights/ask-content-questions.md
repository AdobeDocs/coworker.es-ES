---
title: Haga preguntas sobre su contenido con Coworker Chat
description: Pregunte en Coworker Chat sobre su contenido en un lenguaje sencillo, desde general hasta específico, y obtenga respuestas precisas de Content Analytics sin la experiencia del analista.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f1ffc050071fc0ca48ae36c7aea8bc66eff2a147
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 2%
---

# Haga preguntas sobre su contenido

<!-- FLAG: Confirm with the PM: (1) availability (GA, beta, or experimental) and whether this page needs an AVAILABILITY note or `hide: true` until launch, and (2) any required Coworker entitlement. Content Analytics itself has no separate permission: users get access through data views that are configured for Content Analytics (Access control section of analytics-platform.en/help/content-analytics/config/configuration.md). -->

Use el chat de Adobe CX Enterprise Coworker para obtener respuestas precisas sobre el contenido de Adobe Content Analytics. Haga una pregunta específica, como &quot;¿Qué imágenes de héroe generaron la mayor cantidad de ingresos el trimestre pasado?&quot;, o una pregunta general, como &quot;¿Qué tipo de contenido debo priorizar?&quot;. Coworker convierte su pregunta en un análisis sólido.

Su compañero comprende cómo se estructuran los datos de Content Analytics y aplica las reglas de creación de informes que haría un analista experimentado, de modo que los especialistas en marketing y otros usuarios comerciales obtienen resultados fiables sin una profunda experiencia en Content Analytics.

Para otros casos de uso de rendimiento de contenido, consulte [Resumen de rendimiento de contenido](/help/chat/use-cases/data-insights/content-performance.md).

**Ideal para:** usuario empresarial, analista

## Requisitos previos

<!-- FLAG: Confidence: High. The first two bullets match the other data insights pages. The third bullet follows the Content Analytics docs in analytics-platform.en: Content Analytics components are available only in data views that are configured for Content Analytics (report/report.md), and there's no separate Content Analytics permission (config/configuration.md). -->

Para hacer preguntas sobre su contenido, necesita:

* Chat de compañeros conectado a las vistas de datos de Customer Journey Analytics. Ver [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Ver el acceso a las vistas de datos que desea analizar. El chat de compañeros hereda sus permisos de Customer Journey Analytics.
* Vista de datos configurada para Content Analytics. Consulte [Configuración de Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/configuration/configuration) en la guía de Customer Journey Analytics.

## Formular una pregunta de contenido

1. Inicie sesión en Coworker.

1. Seleccione **[!UICONTROL Nuevo chat]**.

1. En el campo de texto, haga una pregunta sobre el contenido. Por ejemplo:

   **Mensaje**

   > ¿Qué tipo de contenido debo priorizar?

   <!-- FLAG: The skill includes activation words and phrases, but they weren't provided. Confirm with the PM whether customers need to use specific words to trigger the skill, or whether any content question routes to it automatically. If specific words are needed, list them here. -->

   El compañero de trabajo usa la habilidad `analyze-content` para responder preguntas de contenido.

1. (Condicional) Si su pregunta está abierta a más de una interpretación, responda las preguntas aclaratorias que el Compañero hace, como a qué tipo de contenido, canal o intervalo de fechas se refiere.

1. Revise los resultados.

1. (Opcional) Haga preguntas de seguimiento en la misma conversación para profundizar o abra una visualización en Analysis Workspace para obtener más control manual. Consulte [Abrir una visualización en Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Ejemplos de peticiones

En la tabla siguiente se muestran ejemplos de peticiones de datos para diferentes tipos de preguntas de contenido. Utilícelos como punto de partida y adáptelos a su propio contenido.

| Tipo de pregunta | Ejemplos de peticiones |
| --- | --- |
| Amplio o exploratorio | <ul><li>&quot;¿Qué tipo de contenido debo priorizar?&quot;</li><li>&quot;¿Qué rendimiento tiene nuestro contenido?&quot;</li></ul> |
| Nivel de atributo | <ul><li>&quot;¿Qué tienen en común nuestras imágenes con mejor rendimiento?&quot;</li><li>&quot;¿Qué atributos de contenido generan la mayor participación?&quot;</li></ul> |
| Ingresos y conversiones | <ul><li>&quot;¿Qué imágenes de héroe generaron la mayor cantidad de ingresos el trimestre pasado?&quot;</li><li>&quot;¿Cuántos ingresos están vinculados a este banner?&quot;</li></ul> |
| Canales y audiencias | <ul><li>&quot;¿Qué temas creativos ganan en pago y en nuestro sitio?&quot;</li><li>&quot;¿Qué imágenes funcionan para los nuevos visitantes?&quot;</li></ul> |

## Respuesta de los compañeros a las preguntas de contenido

<!-- FLAG: Confidence: High for the list of what the skill includes, metric matching, filtering pages by Experience ID, and choosing an attribution model per question (sourced from the PM's skill description and feature summary). Medium for the remaining details, which combine the skill description with the Content Analytics component reference in the Customer Journey Analytics guide. The skill's specific query defaults, attribution models, and visualization rules weren't provided. Confirm with the PM before adding them. -->

El compañero responde a preguntas de contenido con la aptitud `analyze-content`, que incluye el siguiente contexto y protecciones. La aptitud se empareja con la aptitud `cja` y ejecuta todas las consultas en las vistas de datos de Customer Journey Analytics a través de las mismas herramientas de Customer Journey Analytics.

### Valores predeterminados de consulta y aclaración de preguntas

Si su pregunta no incluye ningún detalle, la aptitud aplica un valor predeterminado razonable. Si la habilidad no está segura de lo que quiere decir, hace una pregunta aclaratoria en lugar de adivinar.

### Coincidencia de métricas para recursos y experiencias

<!-- FLAG: The table covers web and mobile content. Paid media content uses separate summary metrics, such as Impressions, Clicks, and Spend with a reporting-level suffix (for example, Clicks | Asset Summary), that can't be combined with event metrics such as Asset Views (config/paid-media.md in analytics-platform.en). Confirm with the PM how the skill handles paid media, then add a row or note. -->

Content Analytics realiza un seguimiento de dos tipos de contenido: recursos y experiencias. Cada uno tiene sus propias métricas. La aptitud siempre vincula la métrica con el tipo de contenido que pregunta.

| Tipo de contenido | Qué es | Métricas que utiliza la aptitud |
| --- | --- | --- |
| Recursos | Un fragmento individual de contenido, como una imagen | Vistas de recursos, Clics en recursos, Tasa de clics en recursos (CTR) |
| Experiencias | Todo el texto de una página web o la combinación de texto, recursos y llamadas a la acción en una aplicación móvil | Vistas de experiencias, Clics en experiencias, Tasa de clics en experiencias (CTR) |

### Arquitectura de datos de Content Analytics

La aptitud comprende cómo se estructuran los datos de Content Analytics. Por ejemplo:

* **ID de experiencia:** Cuando pregunta por una página específica, la aptitud filtra por el ID de experiencia de contenido que identifica esa página.
* **Atributos generados por IA:** Cada recurso y experiencia se describe mediante atributos como estilo fotográfico, colores, tono y estrategia de persuasión. La aptitud utiliza estos atributos para explicar por qué el contenido tiene un buen rendimiento, no solo qué contenido lo tiene bien.

Para obtener la lista completa de componentes, consulte [Componentes de Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/report/components) en la guía de Customer Journey Analytics.

### Atribución

La aptitud elige el modelo de atribución que mejor se adapte a su pregunta. Por ejemplo, una pregunta sobre los clics en una imagen se responde de forma diferente a una pregunta sobre la cantidad de ingresos que contribuyó esa imagen. Para obtener más información, consulte [Modelos de atribución](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/attribution/models#attribution-models) en la guía de Customer Journey Analytics.

### Análisis y flujos de trabajo comunes

La aptitud incluye instrucciones para análisis de contenido comunes, como:

* Encuentre los atributos que tienen en común los recursos o experiencias de mayor rendimiento.
* Vincular la exposición al contenido a conversiones e ingresos.
* Comparación de contenido entre canales de medios web, móviles y de pago.
* Comparar qué contenido funciona para diferentes audiencias y segmentos.
* Identificación del contenido que se utiliza en exceso o en exceso.

### Visualizaciones

La aptitud selecciona visualizaciones que se ajustan a la pregunta y a los datos, de modo que los resultados sean fáciles de leer y compartir.

## Sugerencias para obtener mejores resultados

* Empieza en grande si no estás seguro de qué preguntar. Los compañeros de trabajo pueden convertir una pregunta general en un análisis centrado y puede refinar a partir de ahí.
* Diga si se refiere a recursos individuales, como imágenes, o experiencias completas, como páginas, cuando sepa cuál desea.
* Asigne un nombre a la métrica y el intervalo de fechas que desea analizar, como los ingresos del último trimestre.
* Especifique los segmentos, audiencias o canales que desea comparar.
* Pregunte por los atributos de contenido, como imágenes, temas o mensajes, en lugar de por archivos individuales cuando desee saber por qué el contenido tiene un buen rendimiento.
* Agregue su vista de datos preferida a la memoria de Chat de Coworker si siempre analiza la misma. Ver [Agregar una vista de datos o una preferencia de grupo de informes en la memoria](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory).

## Próximos pasos

* Para ver más casos de uso de rendimiento de contenido, consulte [Resumen de rendimiento de contenido](/help/chat/use-cases/data-insights/content-performance.md).
* Para obtener más información sobre Content Analytics, consulte [Información general de Content Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/content-analytics/content-analytics) en la guía de Customer Journey Analytics.
* Para obtener una descripción general del análisis de datos con Coworker Chat, incluidas las prácticas recomendadas, consulte [Analizar datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
