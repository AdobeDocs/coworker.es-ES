---
title: Detección de anomalías de Experience Platform con compañeros de trabajo
description: Aprenda a detectar anomalías en Adobe Experience Platform con el chat de Coworker. Explore las solicitudes de métricas de ingesta, segmentación y activación de destino.
feature: AI Tools
role: User
level: Intermediate
doc-type: Tutorial
jira: PLAT-313965
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 1%
---

# Detección de anomalías de Experience Platform

Use el chat de [!DNL Adobe CX Enterprise Coworker] para identificar picos y caídas en métricas de Adobe Experience Platform admitidas. Pregunte por los flujos de datos y las audiencias para encontrar desviaciones con respecto a una línea de base.

Comience con una pregunta amplia y, a continuación, céntrese en un flujo o audiencia que necesite atención. Revise la métrica notificada y su línea de base antes de decidir qué investigar.

>[!AVAILABILITY]
>
>La detección de anomalías está en disponibilidad limitada. La disponibilidad general está planificada para el primer trimestre de 2027.

>[!NOTE]
>
>La detección de anomalías proporciona información sin cambiar los datos ni la configuración.

## Aptitudes diagnósticas disponibles

Utilice el complemento `baseline-anomalies` para detectar anomalías, comparar tendencias y revisar el estado del flujo o los errores de los trabajos actuales. El complemento está configurado de manera predeterminada con la oferta de Experience Platform y aplicaciones en [!DNL Coworker].

Elija el tipo de pregunta en función de la información que necesite.

| Habilidad | Objetivo |
| --- | --- |
| [!UICONTROL Anomalías de línea de base Anomalías de flujo de búsqueda] | Detecte picos o caídas en el volumen de registros y registros fallidos en las fases de ingesta, segmentación, exportación y destino. |
| [!UICONTROL Anomalías de línea de base Buscar anomalías de audiencia] | Detecta picos o caídas en los recuentos realizados de perfiles de audiencia y picos en los recuentos de perfiles abandonados. |
| [!UICONTROL Anomalías de línea de base resumen la tendencia de flujo] | Compare el rendimiento de flujo reciente y típico sin un veredicto de anomalía. |
| [!UICONTROL Anomalías de línea de base resumen la tendencia de audiencia] | Compare recuentos de perfiles cualificados y salientes recientes y típicos para la segmentación por lotes, sin un veredicto de anomalía o un intervalo esperado. |
| [!UICONTROL Anomalías de línea de base inspeccionan el estado del flujo] | Revise los recuentos de ejecución duplicados y fallidos, además de los totales de registros fallidos por actividad o flujo. |
| [!UICONTROL Anomalías de línea de base: trabajos con error de búsqueda] | Revisar los trabajos con errores actuales y sus motivos, excluyendo los errores recuperados y los detalles de los registros individuales. |

Los resúmenes de tendencias describen los cambios, pero no determinan si son anomalías. Utilice preguntas sobre anomalías cuando necesite una evaluación de pico o caída.

## Antes de empezar

El complemento está configurado de forma predeterminada. Para comprobar su estado antes de realizar preguntas de diagnóstico, siga estos pasos.

1. Vaya a **[!UICONTROL Personalizaciones]**.

1. Seleccione **[!UICONTROL Complementos]**.

1. Abra **[!UICONTROL baseline-anomalies]** y confirme que su estado es **[!UICONTROL Active]**.

Identifique la zona protegida y el área que desea comprobar. Para un recurso específico, tenga preparados su nombre o identificador de flujo, segmento o destino.

Para obtener instrucciones generales de chat, consulte [Introducción al chat](/help/chat/ui-guide.md).

## Preguntar por anomalías

Describa el área o recurso que desea comprobar y el período de tiempo que desea examinar.

Utilice las siguientes indicaciones de ejemplo como punto de partida. Reemplace nombres de ejemplo con nombres de su organización.

| Objetivo | Mensaje de ejemplo |
| --- | --- |
| Comprobación en todas las áreas compatibles | ¿Ha habido alguna anomalía en las últimas 24 horas? |
| Comprobar ingesta | ¿Hay alguna anomalía con mi ingesta en las últimas 24 horas? |
| Comprobar un flujo específico | ¿Ha habido alguna anomalía en el flujo de ingesta de CustomerImport en las últimas 24 horas? |
| Comprobar segmentación | ¿Ha habido alguna anomalía en la segmentación en las últimas 24 horas? |
| Compruebe un segmento específico | ¿Ha habido alguna anomalía en los miembros de fidelidad del segmento en las últimas 24 horas? |
| Comprobar activación de destino | ¿Hay alguna anomalía en la activación de mi destino en las últimas 24 horas? |
| Comprobar picos de perfil realizados | ¿Alguna audiencia está viendo un pico en los perfiles realizados hoy? |
| Comprobación de anomalías de registro fallidas | ¿Los registros fallidos son anormalmente altos en la importación del cliente de flujo? |

La pregunta general comprueba tanto los flujos de datos como las audiencias. Confirme la zona protegida y el período de tiempo identificados en la respuesta.

<!-- Author review: Confirm exact supported time windows, defaults, time zone handling, and data freshness. -->

## Revisión de resultados de anomalías

Compare el valor del informe con su línea de base para el recurso y el período de tiempo afectados. Utilice la diferencia para identificar lo que necesita una investigación adicional, en lugar de tratar una anomalía como una causa confirmada.

Por ejemplo, una disminución en los registros de entrada de ingesta identifica un cambio de volumen. Ese cambio por sí solo no explica por qué llegaron menos registros.

Los resultados pueden aparecer como tablas o como un resumen escrito. Las tablas pueden agrupar anomalías en [!UICONTROL Alto riesgo] y [!UICONTROL Riesgo de Medium].

![Los resultados de anomalías agrupan la ingesta y los picos y caídas de volumen de destino por riesgo alto y medio, con los nombres y valores de los recursos censurados.](assets/anomaly-detection/anomaly-detection-results.png){width="900" zoomable="yes"}

Este ejemplo agrupa las anomalías de flujo por riesgo y sugiere investigar los recuentos de ejecución o el historial de tendencias. Se censuran los nombres y valores de los recursos.

| Detalles del resultado | Qué desea revisar |
| --- | --- |
| [!UICONTROL Cuándo (UTC)] | La hora o ventana de tiempo del evento en Hora Universal Coordinada. |
| [!UICONTROL Fase] | La fase de procesamiento afectada, como la ingesta o el destino. |
| [!UICONTROL Flujo] | El flujo afectado, identificado por el nombre o el identificador. |
| [!UICONTROL Qué sucedió] | El cambio detectado, como un pico o una caída de volumen. |
| [!UICONTROL Real frente a esperado] | El valor observado comparado con el valor basal o el rango esperado. |

Revise la explicación junto con la agrupación de riesgo. Para las anomalías de audiencia, Alto indica una gran desviación de la normalidad. Medium indica una salida clara pero moderada. Solo se devuelven las anomalías Alta y Medium.

Los resultados de audiencia excluyen las anomalías de Medium cuando el historial de línea de base es muy variable. Por lo tanto, cualquier anomalía devuelta con un historial muy variable tiene un nivel de alto riesgo.

Utilice niveles de riesgo para priorizar la investigación, no para establecer una causa raíz.

Por ejemplo, una respuesta identifica 10 registros de entrada en un intervalo esperado de uno a cuatro como pico de riesgo medio. El nivel habitual es de aproximadamente un registro, por lo que la desviación es grande en relación con la línea de base. El volumen absoluto sigue siendo pequeño.

Compruebe los tiempos de eventos antes de tratar una anomalía histórica como un problema actual. Un evento fuera de las últimas 24 horas no establece si la condición subyacente se recuperó.

<!-- Author review: Confirm flow risk tier definitions and whether persistence is reported. -->

### Líneas bases e intervalos esperados

Las comparaciones de anomalías horarias utilizan la misma hora durante los 14 días anteriores. Esto explica los patrones típicos por hora, pero no tiene en cuenta la estacionalidad más amplia.

Para las anomalías de audiencia, el intervalo esperado se centra en la mediana y se amplía según la variación en los recuentos históricos. Si el límite inferior calculado es negativo, el intervalo utiliza el recuento histórico más bajo en su lugar. Por lo tanto, el rango puede extenderse más por encima de la mediana que por debajo de ella.

Los recuentos de perfiles realizados por encima del intervalo esperado son picos. Los recuentos por debajo del rango son caídas. Un recuento de cero cuando los perfiles están presentes normalmente es una caída de alto riesgo.

Los recuentos de perfiles salientes solo producen veredictos de pico. Menos salidas se tratan como normales, no como anomalías de colocación.

### No se han devuelto anomalías

Una respuesta puede informar de que no se devolvieron anomalías de Alta o Medium para la audiencia y el período solicitados.

![Un resumen de anomalías de audiencia no informa de anomalías altas o de Medium durante 168 horas e incluye una advertencia sobre el historial excluido.](assets/anomaly-detection/anomaly-detection-no-anomalies.png){width="900" zoomable="yes"}

Este ejemplo incluye una advertencia sobre un historial insuficiente o, en su mayoría, cero. No confirma que cada hora se haya evaluado o que se haya excluido esta audiencia. Se redactan el nombre y el identificador de la audiencia.

### Historial basal insuficiente

El historial de línea de base afecta a si una audiencia puede evaluarse en busca de anomalías.

La detección de anomalías de audiencia no evalúa filas con menos de cinco días de historial o un historial que contenga principalmente ceros.

>[!IMPORTANT]
>
>La ausencia de anomalías notificadas no significa que se hayan evaluado todos los recursos. Es posible que la respuesta no confirme si se evaluó o se omitió una audiencia.

<!-- Author review: Confirm flow minimum history requirements and whether audience evaluation status or excluded resources can be retrieved. -->

## Refine la pregunta

Centra tu siguiente pregunta en el recurso afectado. Por ejemplo, después de una comprobación de ingesta amplia, pregunte sobre las anomalías de un flujo con nombre.

Después de preguntar sobre las últimas 24 horas, amplíe el período con este seguimiento:

```text
What about in the past two weeks?
```

La respuesta puede identificar anomalías históricas incluso cuando no aparecen en las últimas 24 horas.

Para una investigación más detallada, pregunte sobre los recuentos de ejecución de flujo, las tendencias de flujo, las tendencias de audiencia o los trabajos con errores actuales. También puede preguntar sobre trabajos individuales a medida que investiga.

Elija su siguiente pregunta en función de la información que necesite. Los resúmenes de tendencias y estado no proporcionan veredictos de anomalías.

| Objetivo | Mensaje de ejemplo | Qué esperar |
| --- | --- | --- |
| Revisar tendencias de audiencia | ¿Cómo han cambiado mis audiencias en la última semana? | Recuentos de perfiles cualificados y abandonados recientes y típicos para la segmentación por lotes, sin un intervalo esperado. |
| Revisar tendencias de flujo | ¿Cómo ha cambiado el volumen de ingesta durante la última semana? | Rendimiento reciente comparado con el rendimiento típico, sin un veredicto de anomalía. |
| Revisar estado de flujo | ¿Cuántas ejecuciones han tenido éxito o han fallado en los flujos de ingesta en las últimas 24 horas? | Recuentos de ejecución deduplicados y totales de registros con errores acumulados, sin motivos de error. |
| Investigación de trabajos fallidos | ¿Qué trabajos de exportación han fallado en las últimas 24 horas y por qué? | Trabajos cuyo estado más reciente ha fallado dentro del ámbito solicitado, con motivos de error del trabajo. |
| Investigación de un fallo de flujo | ¿Cuál es el error en el flujo de importación del cliente? | Motivos del error para los trabajos actualmente fallidos asociados al flujo, sin detalles para registros individuales. |

El historial de tendencias de audiencia se conserva durante aproximadamente dos semanas o 336 horas. El valor típico es la mediana de esa hora durante los 14 días anteriores.

Para los trabajos con errores actuales, un resultado vacío significa que no hay ningún trabajo con errores actualmente en el ámbito solicitado. No significa que no se hayan producido errores durante el período solicitado. Se excluyen los trabajos que fallaron y luego se realizaron correctamente.

Continúe investigando con habilidades de comprobación de estado o utilice habilidades de alerta para habilitar una alerta para un recurso admitido. Estas acciones utilizan habilidades independientes, no la propia detección de anomalías.

Para ver los flujos de trabajo de alertas relacionados, consulte [Aptitudes sobre alertas de clientes](/help/chat/use-cases/customer-alerts/customer-alerts.md).

<!-- Author review: Validate a complete public example response and the supported alert assets and setup before adding an alert procedure. -->

## Referencia de métrica

La versión limitada incluye las siete métricas siguientes en cuanto a ingesta, segmentación y activación de destino. Utilice esta referencia para identificar los recuentos asociados a cada área.

| Área | Identificador de métrica | Recuento medido |
| --- | --- | --- |
| Ingesta | `input_record_count` | Recuento de registros de entrada para un flujo de ingesta. |
| Ingesta | `failed_record_count` | Recuento de registros fallidos para un flujo de ingesta. |
| Segmentación | `__segment_{segment_id}__realized_profiles` | Recuento de perfiles aptos para un segmento. |
| Segmentación | `__segment_{segment_id}__exited_profiles` | Recuento de perfiles que salen de un segmento. |
| Activación del destino | `{destination}_input_record_count` | Recuento de registros de entrada para un destino. |
| Activación del destino | `{destination}_skipped_record_count` | Recuento de registros omitidos para un destino. |
| Activación del destino | `{destination}_output_record_count` | Recuento de registros de salida para un destino. |

<!-- Author review: Confirm metric aggregation intervals and identifier visibility. -->

## Alcance y limitaciones

Utilice la detección de anomalías para identificar desviaciones, no para confirmar una causa raíz ni reparar un recurso.

Puede preguntar sobre flujos, segmentos y destinos por nombre o identificador. La detección de anomalías de flujo cubre las fases de ingesta, segmentación, exportación y destino.

Utilice la aptitud de trabajo con errores para los trabajos con errores actuales y sus motivos de error. Se excluyen los errores recuperados. Los diagnósticos de trabajo no incluyen detalles para registros individuales o veredictos de anomalías.

El estado de flujo proporciona recuentos agregados, no motivos de error. Los resúmenes de tendencias describen valores recientes y típicos, no veredictos de anomalías. Los resúmenes de tendencias de audiencia abarcan solo la segmentación por lotes.

La detección de anomalías no cambia los datos ni la configuración. Utilice aptitudes independientes para acciones de alerta admitidas e investigaciones de estado más profundas.

<!-- Author review: Confirm job identifier support and any recommendation capabilities before adding examples. -->
