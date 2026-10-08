---
title: Validación de datos de Adobe Analytics a Customer Journey Analytics
description: Descubra cómo los administradores de Analytics utilizan la habilidad de validación de datos de CX Enterprise Coworker para comparar los datos de Adobe Analytics y Customer Journey Analytics durante la actualización.
feature: AI Tools
role: User
level: Intermediate
doc-type: Feature Video
duration:
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22083
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1530'
ht-degree: 0%
---
# Validar datos con su compañero de trabajo al actualizar de Adobe Analytics a Customer Journey Analytics

>[!NOTE]
> 
>Siga los pasos de esta página solo después de completar todos los pasos de actualización anteriores. Puede seguir los pasos de actualización recomendados (recomendados para la mayoría de las organizaciones) o puede seguir los pasos generados dinámicamente para su organización con la Guía de actualización de Customer Journey Analytics. <ul><li>**Pasos de actualización recomendados** (recomendado para la mayoría de las organizaciones)<p>Un conjunto de pasos que conducen a una implementación de Customer Journey Analytics ideal.</p><p>Para obtener información detallada, consulte [Actualizar de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations).</p></li><li>**Guía de actualización de Customer Journey Analytics** (Pasos personalizados adaptados a las necesidades específicas de su organización)<p>Hay disponible una nueva guía de actualización que genera dinámicamente pasos de actualización adaptados a su organización y a sus circunstancias únicas.</p><p>Para acceder a la guía desde Customer Journey Analytics, selecciona la pestaña **[!UICONTROL Workspace]** y, a continuación, selecciona **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo. Siga las instrucciones que aparecen en pantalla.</p></li></ul>

Adobe CX Enterprise Coworker incluye una aptitud de validación que le permite validar datos al actualizar de Adobe Analytics a Customer Journey Analytics. La validación de datos se completa en una sola conversación.

Esta aptitud compara automáticamente:

* Cada dimensión, métrica y tendencia individualmente en las implementaciones.

* Todos los grupos de informes de Adobe Analytics con todas las vistas de datos de Customer Journey Analytics.

Después de realizar estas comparaciones, la aptitud genera perspectivas y recomendaciones impulsadas por IA que puede implementar para facilitar la actualización a Customer Journey Analytics.

## Antes de empezar

Para validar los datos como parte de la actualización, necesita lo siguiente:

* El grupo de informes de Adobe Analytics que desea validar.

* La vista de datos de Customer Journey Analytics que contiene los mismos datos.

No necesita saber cómo se ha diseñado la implementación. La aptitud detecta automáticamente si la implementación de Customer Journey Analytics utiliza el conector de Source de Analytics o una nueva implementación de Experience Platform Web SDK.

>[!VIDEO](https://video.tv.adobe.com/v/3496851/?captions=spa&learn=on&enablevpops)

## Iniciar una sesión de validación

1. Inicie sesión en Coworker.

1. Seleccione [!UICONTROL **Nuevo chat**].

1. En el campo de texto, solicite al agente que valide la actualización de Adobe Analytics a Customer Journey Analytics:

   **Mensaje**

   > Ayúdeme a validar la actualización de mi empresa de Adobe Analytics a Customer Journey Analytics.

   La solicitud se dirige a la aptitud de validación de datos, que inicia un proceso de configuración interactivo.

1. Para cada pregunta en el proceso de configuración, selecciona una respuesta y luego selecciona [!UICONTROL **Enviar**].

   El proceso de configuración incluye las preguntas de la tabla siguiente.

   >[!NOTE]
   >
   >Puede cambiar cualquiera de estas selecciones más adelante en la misma conversación. Por ejemplo, pídale al agente que cambie el grupo de informes o la vista de datos, y el agente solo repetirá los pasos necesarios para actualizar esa selección, sin reiniciar todo el proceso de instalación.

   | Pregunta | Contexto adicional |
   |---------|----------|
   | [!UICONTROL **Seleccione su empresa de Analytics**] | Esta es su compañía de inicio de sesión de Adobe Analytics. |
   | [!UICONTROL **Seleccione su grupo de informes**] <!--In the UI, recommend change to "Select your Adobe Analytics report suite"--> | Este es el grupo de informes de Adobe Analytics que contiene los datos que desea validar con los datos de Customer Journey Analytics. |
   | [!UICONTROL **Seleccione su vista de datos de Customer Journey Analytics**] | Es la vista de datos de Customer Journey Analytics que contiene los mismos datos que el grupo de informes de Adobe Analytics que ha seleccionado. |

1. Revise el resumen de la configuración para confirmar que está validando los datos correctos antes de continuar.

   El resumen incluye la empresa, el grupo de informes y la vista de datos seleccionados, así como una vista previa de las métricas y dimensiones principales de cada sistema.

1. Continúe con la siguiente sección: [Elija los datos que desea validar](#choose-the-data-to-validate).

## Elija los datos que desea validar

Puede validar métricas o dimensiones individuales, o bien puede validar todas las métricas y dimensiones que se incluyen en el grupo de informes y en la vista de datos.

1. Seleccione entre las siguientes opciones:

   | Opción de validación | Descripción |
   |---------|----------|
   | [!UICONTROL **Comparación de métrica única**] | Comparar la tendencia de una métrica entre Adobe Analytics y Customer Journey Analytics. Utilícelo cuando desee realizar una comprobación rápida de una métrica específica, como vistas de página o visitas. |
   | [!UICONTROL **Comparación de dimensión única**] | Compare el desglose de una sola dimensión entre Adobe Analytics y Customer Journey Analytics. Utilícelo cuando sospeche una diferencia de asignación o clasificación para una dimensión específica. |
   | [!UICONTROL **Auditoría completa de grupos de informes y vistas de datos**] | Compare hasta 40 métricas de Adobe Analytics y 20 dimensiones con sus homólogos de Customer Journey Analytics en una sola ejecución. Utilícelo cuando desee obtener una vista completa del estado general de la actualización. |

1. Continúe con la siguiente sección [Revisar el análisis](#review-the-analysis).

## Revisión del análisis

1. Seleccione la ficha [!UICONTROL **Tasa de coincidencia general**] para ver un porcentaje que indica en qué medida coinciden los datos del grupo de informes de Adobe Analytics con los de la vista de datos de Customer Journey Analytics.

   Esta puntuación siempre aparece primero, antes que cualquier otro resultado. Pesa todas las métricas y dimensiones comparadas por igual para garantizar que las métricas de gran volumen, como las vistas de página, no distorsionen la puntuación.

   Utilice la siguiente escala para interpretar la puntuación:

   | Puntuación | Clasificación | Lo que significa |
   |---------|----------|----------|
   | 97-100% | ![Cuadrado verde](../../assets/data-validation-aa-cja/excellent-square.svg) [!UICONTROL Excelente] | Todas las propiedades están altamente alineadas. No se requiere ninguna acción. |
   | 90-96 % | ![Círculo amarillo](../../assets/data-validation-aa-cja/good-circle.svg) [!UICONTROL Bueno] | Hay brechas menores. Monitorice las tendencias e investigue si disminuyen. |
   | 75-89 % | ![Círculo naranja](../../assets/data-validation-aa-cja/review-circle.svg) [!UICONTROL Revisión] | Existen brechas significativas. Investigue las causas raíz antes de depender de los datos de Customer Journey Analytics. |
   | Menos del 75% | ![Círculo rojo](../../assets/data-validation-aa-cja/critical-circle.svg) [!UICONTROL Pobre] | Desalineación significativa. Realice acciones inmediatas antes de utilizar los datos de Customer Journey Analytics. |

1. Seleccione la ficha [!UICONTROL **Información clave**] para ver de dos a cuatro cuadros de llamada cortos, cada uno de los cuales resume un resultado del análisis en una sola frase.

   Las llamadas están codificadas por gravedad para que pueda identificar primero los hallazgos más importantes.

1. Seleccione la ficha [!UICONTROL **Resumen**] para ver la siguiente información:

   * Totales de Adobe Analytics

   * Totales de Customer Journey Analytics

   * Desviación total

   * Días que pasan

     Refleja cuántos días del intervalo de fechas entran en el estado de variación [!UICONTROL **Aprobado**] que se describe a continuación.

   * Días críticos

     Refleja cuántos días del intervalo de fechas entran en el estado de variación [!UICONTROL **crítica**] que se describe a continuación.

1. (Condicional) Al hacer una comparación de una sola dimensión o de una sola métrica, seleccione la pestaña [!UICONTROL **Tendencia diaria**] para ver una comparación en paralelo de los datos de Adobe Analytics y los datos de Customer Journey Analytics.

   En el caso de las métricas, se trata de un gráfico de líneas que compara la tendencia diaria.

   ![Pestaña de tendencia diaria que muestra un gráfico de líneas](../../assets/data-validation-aa-cja/trend-line.png)

   Para las dimensiones, se trata de un gráfico de barras que compara los valores principales.

   ![Pestaña de tendencia diaria que muestra un gráfico de barras horizontales](../../assets/data-validation-aa-cja/trend-bar.png)

1. (Condicional) Al realizar una comparación de una sola dimensión o una comparación de métrica única, seleccione la pestaña [!UICONTROL **Detalle de fecha**] para ver la siguiente información de cada métrica o valor de dimensión comparado:

   * Fecha

   * Valor de Adobe Analytics

   * Valor de Customer Journey Analytics

   * Porcentaje de varianza

   * Distintivo de estado

   ![Pestaña de detalles de fecha que muestra una tabla de porcentajes de variación e insignias de estado](../../assets/data-validation-aa-cja/date-detail.png)

   Las columnas Variación y Estado utilizan la siguiente escala:

   | Varianza | Estado | Lo que significa |
   |---------|----------|----------|
   | Menos del 3% | ![Marca de verificación verde](../../assets/data-validation-aa-cja/pass-check.svg) [!UICONTROL Aprobado] | Los datos están bien alineados. No se requiere ninguna acción. |
   | 3-10 % | ![Triángulo de advertencia amarillo](../../assets/data-validation-aa-cja/flagged-warning.svg) [!UICONTROL Indicador] | Monitorice la diferencia e investigue si continúa o empeora. |
   | Superior al 10 % | ![Círculo rojo](../../assets/data-validation-aa-cja/critical-circle.svg) [!UICONTROL Crítico] | Investigue inmediatamente. Esto generalmente apunta a un problema de esquema, ingesta o asignación. |

1. (Condicional) Cuando ejecute un grupo de informes completo y una auditoría de vista de datos, seleccione la pestaña [!UICONTROL **informe de valoración**] para ver la siguiente información:

   * Conteos de aprobaciones

   * Recuentos marcados

   * Recuentos críticos

   * Tablas que enumeran las cinco métricas y dimensiones que mejor se ajustan y las cinco que menos se ajustan

1. Desplácese hacia abajo por el análisis para ver los patrones y problemas adicionales descubiertos durante el análisis, las causas probables de dichos patrones y las acciones sugeridas para resolver cualquier discrepancia en los datos.

   >[!NOTE]
   >
   >Se esperan algunas variaciones que no indican ningún problema con la actualización a Customer Journey Analytics.

   Los problemas comunes incluyen:

   * Adobe Analytics cuenta los visitantes basados en el dispositivo, mientras que Customer Journey Analytics cuenta las personas, mediante la vinculación de identidad entre dispositivos.
   * Adobe Analytics procesa los datos en el momento de la recopilación, mientras que Customer Journey Analytics los procesa en el momento del informe.
   * Las definiciones de sesión difieren: las visitas de Adobe Analytics utilizan un tiempo de espera fijo, mientras que las sesiones de Customer Journey Analytics se pueden configurar.
   * Adobe Analytics filtra los bots de forma predeterminada, mientras que el filtrado de bots de Customer Journey Analytics es opcional.
   * Adobe Analytics informa de los valores que faltan como &quot;No especificado&quot; o &quot;Ninguno&quot;, mientras que Customer Journey Analytics informa de ellos como &quot;Sin valor&quot;.
   * Las diferencias de canal de marketing pueden ser el resultado de reglas de procesamiento de Adobe Analytics comparadas con campos derivados de Customer Journey Analytics aplicados de forma retroactiva.
   * Si los valores de Customer Journey Analytics son consistentes con aproximadamente el doble de los valores de Adobe Analytics en todas las métricas, esto generalmente indica datos duplicados en la vista de datos en lugar de un efecto de vinculación de identidad.

1. Compruebe que las acciones sugeridas son válidas y, a continuación, resuelva el problema en Adobe Experience Platform o Adobe Analytics.

1. (Opcional) Continúe con el análisis analizando otra métrica, analizando otra dimensión o ejecutando otro informe de hasta 40 métricas y 20 dimensiones, como se describe en [Elija los datos que desea validar](#choose-the-data-to-validate).

   No es necesario que repita el proceso de configuración para hacerlo; su empresa, grupo de informes y selecciones de vista de datos se transfieren a lo largo de la conversación.

1. Siga los [pasos de actualización recomendados](https://experienceleague.adobe.com/es/docs/analytics-platform/using/compare-aa-cja/upgrade-to-cja/cja-upgrade-recommendations#recommended-upgrade-steps-for-most-organizations) o los pasos de actualización generados dinámicamente en la Guía de actualización de Customer Journey Analytics.

   Para acceder a la Guía de actualización de Customer Journey Analytics desde Customer Journey Analytics, selecciona la pestaña **[!UICONTROL Workspace]** y, a continuación, selecciona **[!UICONTROL Actualizar a Customer Journey Analytics]** en el panel izquierdo. Siga las instrucciones que aparecen en pantalla.

