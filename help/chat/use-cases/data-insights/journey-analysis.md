---
title: Analizar los Recorridos del cliente y la entrega con el chat de compañeros de trabajo
description: Use el chat de compañeros para crear canales, encontrar dónde abandonan los clientes, diagnosticar caídas de conversión y comparar recorridos entre periodos en los datos de análisis.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: b54085a497ca4bbf0003d5837d816206a4d40396
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 2%
---

# información general sobre análisis de recorrido

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilice el chat de Adobe CX Enterprise Coworker para averiguar dónde abandonan los clientes el recorrido para convertirlo y por qué en distintos canales, dispositivos y segmentos. Describa el recorrido en un lenguaje sencillo y Coworker Chat crea el funnel, muestra la lista desplegable en cada paso y le ayuda a investigar la causa.

El análisis de recorrido es uno de los varios dominios de análisis en Coworker Chat. Para ver todos los dominios, consulta [Comenzar a analizar en el chat de compañeros](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) en Análisis de datos con el chat de compañeros.

**Óptimo para:** Analista, usuario empresarial

## Requisitos previos

Para utilizar los casos de uso de esta página, necesita lo siguiente:

* Chat de compañeros conectado a sus vistas de datos de Customer Journey Analytics o a sus grupos de informes de Adobe Analytics. Ver [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).
* Vea el acceso a las vistas de datos o a los grupos de informes que desee analizar. El chat de compañeros hereda sus permisos de Customer Journey Analytics o Adobe Analytics.

## Casos de uso

| Ejemplo de uso | Función |
| --- | --- |
| [Analizar datos de Customer Journey Analytics y Adobe Analytics](/help/chat/use-cases/data-insights/analytics-chat.md)<p>![Analizar datos de Customer Journey Analytics y Adobe Analytics](../../assets/coworker-funnel-response-card.png)</p> | Responde preguntas en lenguaje natural acerca de las vistas de datos o los grupos de informes, crea canales y otras visualizaciones y encuentra dónde abandonan los clientes. Puede abrir cualquier visualización en Analysis Workspace para un análisis más detallado.<p>**Mensaje de ejemplo:** &quot;Mostrarme vistas de página de los últimos 30 días&quot;</p><p>Para obtener más información, consulte [Introducción al análisis de datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-chat.md).</p> |
| [Buscar dónde entregan los clientes](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Crea un funnel a partir de una pregunta en lenguaje simple, clasifica las filtraciones más grandes y sugiere los pasos siguientes.<p>**Ideal para:** usuario empresarial</p><p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Dónde estamos perdiendo gente en el camino a comprar?&quot;</li><li>&quot;Guíame a través del funnel de pago y envío&quot;</li></ul><p>Para obtener más información, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Diagnosticar rechazos de conversión | Investiga dónde abandonan los clientes y evalúa qué contribuyó al cambio.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿Por qué cayeron las conversiones la semana pasada?&quot;</li><li>&quot;¿Dónde abandonaron los clientes después del cambio del sitio?&quot;</li></ul> |
| Aislar la causa de una entrega | Descartar hace que, de uno en uno, se aísle el canal, dispositivo o segmento detrás del problema.<p>**Mensajes de ejemplo:**</p><ul><li>&quot;¿El abandono del carro de compras es peor en móviles o equipos de escritorio?&quot;</li><li>&quot;¿Qué canales tienen la mayor pérdida entre el carro de compras y la compra?&quot;</li></ul> |
| Comparar recorridos entre periodos | Muestra paso a paso si los cambios enviados movieron el funnel.<p>**Ideal para:** usuario empresarial</p><p>**Mensajes de ejemplo:**</p><ul><li>&quot;Comparar la conversión de cierre de compra de este trimestre con la anterior&quot;</li><li>&quot;¿Cómo cambió mi funnel después del rediseño?&quot;</li></ul> |

## Ejemplo: Encuentre el lugar de entrega de los clientes

Para ver una conversación de ejemplo completo, desde la primera pregunta hasta una recomendación, consulte [Ejemplo: Encuentre dónde entregan los clientes](/help/chat/use-cases/data-insights/analytics-chat.md#example-find-where-customers-drop-off) en Introducción al análisis de datos con Chat del compañero.

## Aptitudes utilizadas

<!-- FLAG: Confidence: High for `cja` and `aa` (the Skills and limitations table lists funnel and fallout analysis and side-by-side comparison of time periods). Medium for the root cause analysis skills: workflows.md maps the prompt "Why did conversions drop last week?" to them, but the mapping to the slide rows "Diagnose conversion declines" and "Isolate the cause of a drop-off" is inferred. Confirm with the PM. -->

El compañero de trabajo emplea las siguientes habilidades en los casos de uso descritos en este artículo. Para obtener una lista de todas las habilidades de análisis, incluidos los permisos que requieren y lo que no cubren, consulte [Habilidades y limitaciones](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) en Análisis de datos con el chat de compañeros.

| Habilidad | Se usa para |
| --- | --- |
| `cja`, `aa` | Analizar datos de Customer Journey Analytics y Adobe Analytics<br>Encuentre dónde entregan los clientes<br>Compare recorridos entre períodos |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Diagnosticar rechazos de conversión<br>Aislar la causa de una entrega |

## Sugerencias para obtener mejores resultados

<!-- FLAG: Confidence: High, except the first bullet (Medium), which moved here from Prerequisites and is inferred from how funnel prompts work. The rest are adapted from the best practices in analytics-overview.md. -->

* Asigne un nombre a los pasos del recorrido que desee analizar, como la página del producto, el carro de compras, el cierre de compra y la compra.
* Asigne un nombre a las dimensiones, métricas e intervalos de fechas que desee analizar y haga referencia a los componentes por su nombre exacto.
* Pida una visualización de funnel o de abandonos si eso es lo que desea ver.
* Especifique los segmentos, canales o dispositivos que desea incluir, excluir o comparar.
* Mencione cualquier hipótesis que ya tenga, como un cambio reciente en el sitio, para que Coworker Chat pueda validarla o descartarla.
* Pida los siguientes pasos recomendados si desea que Coworker Chat le sugiera preguntas de seguimiento.
* Abra cualquier visualización en Analysis Workspace cuando desee tener un mayor control manual. Ver [Analizar en Customer Journey Analytics](/help/chat/use-cases/data-insights/analytics-chat.md#analyze-in-customer-journey-analytics).

## Próximos pasos

* Para obtener una descripción general del análisis de datos con Coworker Chat, incluidos los demás dominios de análisis y prácticas recomendadas, consulte [Analizar datos con Coworker Chat](/help/chat/use-cases/data-insights/analytics-overview.md).
* Para configurar el chat de compañeros y ver un ejemplo que funcione, consulta [Análisis de datos con el chat de compañeros](/help/chat/use-cases/data-insights/analytics-chat.md).
