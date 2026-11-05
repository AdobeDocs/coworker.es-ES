---
title: Analizar causas básicas con Adobe Analytics y Customer Journey Analytics
description: Utilice Adobe CX Enterprise Coworker para investigar los cambios de las métricas, identificar las dimensiones y los segmentos que contribuyen y probar hipótesis en Adobe Analytics y CJA.
feature: AI Tools
role: User
level: Beginner
doc-type: Feature Video
duration: 186
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22082
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 7e096fc9cda2157c02501ee909a80bf4df9a2f32
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%
---

# Analizar causas raíz con [!DNL Adobe Analytics] y [!DNL Customer Journey Analytics]

Use el chat de Adobe CX Enterprise Coworker para investigar por qué ha cambiado una métrica en Adobe Analytics o Customer Journey Analytics (CJA). El colaborador analiza el cambio que especifique, muestra las dimensiones y los segmentos que aportan, y ayuda a probar hipótesis utilizando un lenguaje natural.

## Uso de datos de Customer Journey Analytics para el análisis de causas raíz

El siguiente vídeo muestra cómo Coworker combina la IA conversacional con Customer Journey Analytics. Aprenda a hacer preguntas en lenguaje natural, visualizar resultados, identificar tendencias significativas y descubrir factores que impulsan el rendimiento sin crear consultas manuales.

>[!VIDEO](https://video.tv.adobe.com/v/3496847/?learn=on&enablevpops)

### Requisitos previos

Antes de empezar:

1. **Tener acceso al chat de compañeros y conectar con Customer Journey Analytics.** Confirme que su organización ha configurado la integración necesaria.
1. **Tenga acceso de visualización a la vista de datos de CJA que desee analizar.** Los compañeros de trabajo solo pueden utilizar las vistas de datos y los componentes disponibles para usted.
1. **Elija la vista de datos que contiene la métrica y las dimensiones relevantes.** Si puede acceder a varias vistas de datos, asigne un nombre al que desee que utilice Compañero de trabajo.
1. **Identifique el cambio que desea que se investigue.** Especifique la métrica, el intervalo de fechas y el período de comparación. También puede proporcionar dimensiones, segmentos o una hipótesis para enfocar el análisis.

### Ejemplos de peticiones de datos para Customer Journey Analytics

Reemplace el texto entre corchetes con nombres de componentes y periodos de tiempo desde la vista de datos.

* En la vista de datos **[nombre de vista de datos]**, ¿por qué cambió **[métrica]** durante **[intervalo de fechas]** en comparación con **[intervalo de fechas de comparación]**? Desglose el cambio por **[dimensión]** y muestre los segmentos que más contribuyeron.
* En la vista de datos **[nombre de vista de datos]**, ¿contribuyó **[dimensión o segmento]** a la disminución de **[métrica]** desde el **[intervalo de fechas A]** hasta el **[intervalo de fechas B]**? Compare los valores de ambos periodos y explique los cambios.
* En la vista de datos **[nombre de vista de datos]**, compare **[métrica]** para **[segmento A]** y **[segmento B]** durante **[intervalo de fechas]**. ¿Qué dimensiones contribuyeron más a la diferencia?
* En la vista de datos **[nombre de vista de datos]**, pruebe esta hipótesis: **[declare su hipótesis]**. Analice **[metric]** para **[date range]** y muestre las dimensiones o segmentos que lo admiten o no.

## Uso de datos de Adobe Analytics para el análisis de causas raíz

Sus compañeros pueden investigar por qué ha cambiado una métrica en un grupo de informes de Adobe Analytics. Utiliza la habilidad `aa-root-cause-analysis` para analizar un cambio que especifique e identificar las dimensiones y segmentos que contribuyeron a él.

### Requisitos previos

Antes de empezar:

1. **Tener acceso al chat de compañeros y conectar con Adobe Analytics.** En Compañero de trabajo, vaya a **Personalizaciones > Integraciones** y confirme que la integración de `aa-mcp` está en la lista y conectada. Si no está disponible, pídale al administrador que compruebe la configuración de su organización. Consulte [Introducción al análisis de datos con Coworker Chat](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat) para obtener instrucciones de configuración.
1. **Tenga acceso de visualización al grupo de informes de Adobe Analytics que desee analizar.** El compañero hereda los permisos de Adobe Analytics y solo puede utilizar los grupos de informes y los componentes disponibles en Analysis Workspace.
1. **Elija el grupo de informes que contiene los datos relevantes.** Si puede acceder a varios grupos de informes, asigne un nombre al grupo de informes que desee que utilice su compañero.
1. **Identifique el cambio que desea que se investigue.** Especifique la métrica y el período de tiempo. Para un análisis más centrado, incluya un periodo de comparación, dimensiones o segmentos relevantes y cualquier hipótesis que desee que pruebe su compañero.

### Ejemplos de peticiones de datos para Adobe Analytics

Reemplace el texto entre corchetes con nombres de componentes y períodos de tiempo del grupo de informes.

* En el grupo de informes **[nombre del grupo de informes]**, ¿por qué cambió la **[métrica]** durante el **[intervalo de fechas]** en comparación con el **[intervalo de fechas de comparación]**? Desglose el cambio por **[dimensión]** y muestre los segmentos que más contribuyeron.
* En el grupo de informes **[nombre del grupo de informes]**, ¿contribuyó **[dimensión o segmento]** a la disminución de **[métrica]** desde el **[intervalo de fechas A]** hasta el **[intervalo de fechas B]**? Compare los valores de ambos periodos y explique los cambios.
* En el grupo de informes **[nombre del grupo de informes]**, compare **[métrica]** para **[segmento A]** y **[segmento B]** durante **[intervalo de fechas]**. ¿Qué dimensiones contribuyeron más a la diferencia?

## Recursos relacionados

* [Analizar datos con Adobe CX Enterprise Coworker Chat](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-overview)
* [Introducción al análisis de datos con Coworker Chat](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat)
