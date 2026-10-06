---
title: Aptitudes de alerta al cliente
description: Aprenda a utilizar las habilidades de alerta del cliente en CX Coworker para revisar, analizar y priorizar la actividad de alerta a través de conversaciones en lenguaje natural.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 4%
---

# Aptitudes de alerta al cliente

>[!AVAILABILITY]
>
> Las habilidades de alerta al cliente están disponibles para todos los clientes con acceso a Adobe CX Enterprise Coworker.
>
> Para utilizar las habilidades de alerta del cliente, debe tener acceso a las alertas de Adobe Experience Platform y a los recursos asociados a ellas.

Use las habilidades de alerta del cliente en CX Coworker para convertir la actividad de alerta en una sesión informativa operativa personalizada. Revise las alertas recientes, identifique los problemas de alta prioridad, comprenda qué recursos se ven afectados y centre los esfuerzos de investigación a través de conversaciones en lenguaje natural.

Las habilidades de alerta del cliente le ayudan a pasar de las señales de alerta a perspectivas procesables sin revisar manualmente las vistas de alerta ni correlacionar la información en varias interfaces. Comience con una pregunta amplia acerca de la actividad de alertas recientes y, a continuación, utilice preguntas de seguimiento para identificar patrones de alerta recurrentes, analizar los objetos afectados y centrarse en las alertas que posee.

Para obtener información acerca de las alertas de cliente, consulte la [descripción general de las alertas de cliente](https://experienceleague.adobe.com/es/docs/experience-platform/observability/alerts/overview).

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

- Acceso a Adobe Experience Platform.
- Permiso para ver alertas relevantes para su organización.
- El complemento CXO de Adobe instalado en CX Coworker.

Para obtener instrucciones sobre la instalación de complementos, consulte la [guía de la interfaz de usuario de Coworker](../../ui-guide.md).

## Uso de habilidades de alerta del cliente {#use-customer-alert-skills}

Interactúe con las aptitudes de alerta del cliente mediante CX Coworker mediante solicitudes en lenguaje natural. Haga preguntas sobre la actividad de alerta, las suscripciones, las tendencias de alerta o los objetos afectados. Continúe la conversación con preguntas de seguimiento para refinar los resultados y enfocar el análisis.

Para utilizar las aptitudes de alerta del cliente:

1. Vaya a **[!UICONTROL CX Coworker]**.

1. Escriba una pregunta o solicitud acerca de sus alertas. Por ejemplo:

   *&quot;¿Enumerar todas las alertas activadas en las últimas 24 horas?&quot;*

   ![La primera pregunta hecha en CX Coworker](./assets/alerts/initial-question.png)

1. Revise los resultados devueltos por las aptitudes de alerta del cliente.

   ![La tabla de resultados devolvió la pregunta inicial.](./assets/alerts/results-table.png)

1. Refine los resultados con preguntas de seguimiento. Por ejemplo:

   *&quot;Mostrarme los tres tipos principales de alertas activadas en las últimas 24 horas.&quot;*

   ![Resultados refinados que muestran los tres tipos de alertas principales.](./assets/alerts/alert-types.png)

1. Continúe restringiendo el ámbito hasta que identifique las alertas, patrones u objetos afectados que requieren atención. Por ejemplo:

   *&quot;Enumerar los 5 objetos principales afectados por alertas de gravedad alta&quot;*

   ![Resultados refinados que muestran los cinco objetos principales afectados.](./assets/alerts/objects-impacted.png)

Las habilidades de alerta al cliente mantienen el contexto conversacional, lo que le permite avanzar de una actividad de alerta a una investigación centrada sin repetir solicitudes anteriores.

## Casos de uso admitidos {#supported-use-cases}

Utilice las habilidades de alerta del cliente para monitorizar la actividad operativa, investigar problemas y centrarse en las alertas más relevantes para su función.

### Revisar actividad de alerta

Revise el estado de alerta actual o investigue la actividad de alerta histórica en un período de tiempo específico.

Por ejemplo:

- &quot;¿Qué alertas se han activado en las últimas 24 horas?&quot;
- &quot;Mostrar alertas activas de los últimos siete días&quot;.

### Identificación de patrones de alerta recurrentes

Revise el historial de alertas para identificar los tipos de alertas que se producen con más frecuencia en su organización. En lugar de revisar una gran cantidad de eventos de alerta individuales, utilice Aptitudes de alerta del cliente para resumir patrones recurrentes y resaltar áreas que puedan requerir atención.

Por ejemplo:

- &quot;Mostrarme los 3 tipos de alertas activadas principales&quot;.
- &quot;¿Qué tipos de alerta se produjeron con mayor frecuencia este mes?&quot;

### Centrarse en cuestiones de alta prioridad

Limite los resultados a un nivel de gravedad específico para priorizar los esfuerzos de investigación.

Por ejemplo:

- &quot;Mostrar solo alertas de alta gravedad&quot;.
- &quot;¿Qué alertas críticas se han activado esta semana?&quot;

### Comprender el radio de impacto de las alertas

Identificar qué objetos se ven afectados con mayor frecuencia y comprender dónde debe comenzar la investigación.

Las habilidades de alerta del cliente analizan la actividad de alerta y los objetos asociados con alertas recurrentes o de alta gravedad, lo que le ayuda a centrarse en las áreas con mayor impacto operativo.

Por ejemplo:

- &quot;¿Cuáles son los 5 objetos más afectados?&quot;
- &quot;¿Qué objetos están asociados con las alertas de gravedad más alta?&quot;

### Conexión de tipos de alerta a objetos afectados

Descubra cómo la actividad de alerta afecta a recursos específicos.

Las aptitudes de alerta del cliente conectan los objetos afectados a los tipos de alerta que los activaron, lo que le ayuda a identificar patrones y determinar el origen probable de los problemas operativos.

Por ejemplo:

- &quot;¿Qué tipos de alerta afectaron a este conjunto de datos con mayor frecuencia?&quot;
- &quot;Mostrar la relación entre los tipos de alerta y los objetos afectados&quot;.
- &quot;¿Qué tipo de alerta afectó al objeto afectado con mayor frecuencia?&quot;

### Centrarse en Mis alertas

Analice las alertas a las que se suscribe y que son responsables de la monitorización.

Utilice la experiencia [!DNL My Alerts] para revisar la actividad reciente, priorizar los problemas de alta gravedad y enfocar el análisis operativo en las alertas más relevantes para su rol.

Por ejemplo:

- &quot;Mostrarme las alertas de alta gravedad a las que me suscribo&quot;.
- &quot;¿Qué alertas de [!DNL My Alerts] se activaron esta semana?&quot;
- &quot;¿Alguna de mis alertas suscritas requiere atención?&quot;

### Administrar suscripciones de alerta

Revise y administre suscripciones de alerta a través de conversaciones en lenguaje natural.

Por ejemplo:

- &quot;¿A qué alertas estoy suscrito?&quot;
- &quot;Suscríbeme a esta alerta.&quot;
- &quot;Quitar mi suscripción a esta alerta.&quot;

## Ejemplos de peticiones {#example-prompts}

Utilice las siguientes indicaciones como ejemplos al interactuar con las habilidades de alerta del cliente.

### Indicadores de actividad de alerta

- &quot;¿Qué ha pasado en las últimas 24 horas?&quot;
- &quot;¿Qué alertas se han activado en las últimas 24 horas?&quot;
- &quot;Mostrar todas las alertas activadas esta semana&quot;.
- &quot;¿Tengo alertas activas?&quot;

### Indicadores de tendencia de alerta

- &quot;Mostrarme los 3 tipos de alertas activadas principales&quot;.
- &quot;¿Qué tipos de alerta se produjeron con mayor frecuencia este mes?&quot;
- &quot;¿Qué patrones de alerta ves en los últimos siete días?&quot;

### Mensajes de análisis de gravedad

- &quot;Mostrar solo alertas de alta gravedad&quot;.
- &quot;Mostrar alertas críticas de los últimos 30 días&quot;.
- &quot;¿Qué alertas de alta gravedad se produjeron con mayor frecuencia?&quot;

### Indicadores de análisis de impacto

- &quot;¿Cuáles son los 5 objetos más afectados?&quot;
- &quot;¿Qué objetos están asociados con la mayor cantidad de alertas?&quot;
- &quot;Mostrar la relación entre los tipos de alerta y los objetos afectados&quot;.
- &quot;¿Qué tipo de alerta afectó al objeto afectado con mayor frecuencia?&quot;

### Mis avisos de alertas

- &quot;Mostrarme las alertas de alta gravedad a las que me suscribo&quot;.
- &quot;¿Qué alertas de [!DNL My Alerts] se activaron esta semana?&quot;
- &quot;¿Alguna de mis alertas suscritas está activa actualmente?&quot;
- &quot;¿Alguna de mis alertas suscritas requiere atención?&quot;

### Mensajes de administración de suscripciones

- &quot;¿A qué alertas estoy suscrito?&quot;
- &quot;Suscríbeme a esta alerta.&quot;
- &quot;Quitar mi suscripción a esta alerta.&quot;

## Próximos pasos {#next-steps}

Después de leer esta guía, debería saber cómo utilizar las habilidades de alerta del cliente en CX Coworker para revisar la actividad de las alertas, analizar las tendencias de las alertas, administrar las suscripciones a alertas e investigar los problemas operativos a través de conversaciones en lenguaje natural.

Para obtener más información acerca de las alertas, consulte la [Descripción general de las alertas de cliente](https://experienceleague.adobe.com/es/docs/experience-platform/observability/alerts/overview).
