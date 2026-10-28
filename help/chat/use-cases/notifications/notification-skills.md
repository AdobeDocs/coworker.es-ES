---
title: Aptitudes de notificación
description: Obtenga información sobre cómo revisar y administrar las notificaciones con Adobe CX Enterprise Coworker. Busque elementos de acción, establezca recordatorios y elija cómo desea recibir las notificaciones.
role: Admin,User,Developer,Leader
level: Beginner
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 1%
---

# Aptitudes de notificación {#notification-skills}

Use Habilidades de notificación en Adobe CX Enterprise Coworker para revisar las notificaciones, identificar elementos de acción y administrar las preferencias de notificación a través de la conversación. Trabaje con las notificaciones que ya recibe en el panel de notificaciones de las aplicaciones de Adobe CX Enterprise.

Resumir notificaciones, buscar elementos específicos y agrupar notificaciones repetidas en problemas distintos. Abra una notificación en su aplicación, márquela como leída o no leída, o establezca un recordatorio.

>[!AVAILABILITY]
>
>Las habilidades de notificación están disponibles para todos los clientes con acceso a Adobe CX Enterprise Coworker. No se requiere ninguna configuración adicional para utilizar las aptitudes.
>
>Para recibir notificaciones en [!DNL Slack], su organización debe tener un área de trabajo de [!DNL Slack] conectado.

## Antes de empezar {#before-you-begin}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* Acceso a Adobe CX Enterprise Coworker.
* Acceso a una o más aplicaciones de Adobe CX Enterprise que le envían notificaciones.
* Un área de trabajo [!DNL Slack] conectado para su organización, si desea recibir notificaciones en [!DNL Slack].

## Revisar notificaciones y actuar en consecuencia {#review-and-act}

Comience con un resumen y, a continuación, perfeccione la solicitud y actúe en función de una notificación específica.

1. Abra Chat del compañero. Para obtener instrucciones, consulte [Introducción al chat con compañeros](/help/chat/ui-guide.md).
1. Escriba una solicitud en el cuadro **[!UICONTROL Preguntar al compañero]** y, a continuación, seleccione **[!UICONTROL Enviar]**. Por ejemplo:

   *&quot;¿Qué necesita mi atención hoy?&quot;*

1. Revise las notificaciones que requieren acción y las proporcionadas para la sensibilización.

   ![El chat de compañeros enumera las notificaciones que necesitan acción en respuesta a una solicitud sobre lo que necesita atención hoy.](./assets/review-needs-action.png)

1. Escriba una pregunta de seguimiento para reducir los resultados. Por ejemplo:

   *&quot;De esas notificaciones, ¿hay algún error en Experience Platform que deba conocer?&quot;*

   ![Coworker Chat mejora los resultados de notificación en respuesta a una pregunta sobre errores en Experience Platform.](./assets/refine-platform-failures.png)

1. Pida detalles sobre una notificación o ábrala en su aplicación para investigarla.
1. Solicite marcar una notificación como leída o configure un recordatorio. Por ejemplo:

   *&quot;Recordarme mañana acerca de la alerta de tasa de eventos entrantes de alta prioridad.&quot;*

   ![Chat del compañero confirma un recordatorio para mañana después de especificar qué alerta de tasa de eventos entrantes usar.](./assets/reminder-confirmation.png)

Continuar la conversación sin repetir el contexto de solicitudes anteriores. Si su solicitud se puede aplicar a varias notificaciones, aplicaciones o configuraciones, responda a la pregunta aclaratoria antes de continuar.

Recibirá una solicitud de confirmación antes de un cambio que se extienda más allá de la solicitud.

## Casos de uso admitidos {#supported-use-cases}

Use Aptitudes de notificación para revisar las notificaciones que se le envían, actuar en consecuencia y administrar cómo las recibe.

>[!NOTE]
>
>Las habilidades de notificación no envían, comparten ni eliminan notificaciones.

### Identificar elementos de acción {#identify-action-items}

Pregunte qué notificaciones requieren su atención en las aplicaciones de Adobe CX Enterprise.

Ejemplos de peticiones de datos:

* &quot;¿Qué necesita mi atención hoy?&quot;
* &quot;Ponme al día.&quot;
* &quot;¿Algo pendiente para mí?&quot;

### Resumir notificaciones {#summarize-notifications}

Solicite un resumen para un periodo de tiempo o una solicitud. Revise los elementos de acción por separado de las notificaciones proporcionadas para el conocimiento. Las notificaciones repetidas se agrupan en problemas distintos en lugar de enumerarse individualmente.

Ejemplos de peticiones de datos:

* &quot;Resumir mis notificaciones de la semana pasada.&quot;
* &quot;Proporcionarme una descripción general de mis notificaciones del último día&quot;.
* &quot;Resumir mis notificaciones de Adobe Journey Optimizer&quot;.

![El chat de compañeros agrupa un resumen de notificación en elementos que necesitan acción y elementos proporcionados para su conocimiento.](./assets/notification-summary.png)

### Buscar notificaciones específicas {#find-specific-notifications}

Filtre las notificaciones por criterios como estado no leído, solicitudes de aprobación, errores o versiones de productos.

Ejemplos de peticiones de datos:

* &quot;Mostrarme solo las notificaciones no leídas&quot;.
* &quot;Mostrarme mis solicitudes de aprobación&quot;.
* &quot;¿Hay alguna alerta de fallo crítico que deba conocer?&quot;
* &quot;Mostrarme las notificaciones de la versión para Experience Platform&quot;.

### Revisar detalles de notificación {#review-notification-details}

Solicite todos los detalles de una notificación tal y como se envió. Si varias notificaciones coinciden con su solicitud, especifique a cuál se refiere.

Ejemplos de peticiones de datos:

* &quot;Cuéntame más sobre la notificación de recorrido&quot;.
* &quot;¿Qué significa esta alerta para mí?&quot;

### Actuar sobre las notificaciones {#act-on-notifications}

Abra una notificación en su aplicación, márquela como leída o no leída, o establezca un recordatorio. Elija un recordatorio para cinco minutos, 15 minutos, una hora o mañana.

Ejemplos de peticiones de datos:

* &quot;Marque esa notificación como leída&quot;.
* &quot;Marcar esa notificación como no leída&quot;.
* &quot;Recordatorio de esta notificación en una hora&quot;.
* &quot;Marcar todas mis notificaciones como leídas&quot;.

### Administrar las preferencias de notificación {#manage-notification-preferences}

Pregunte por la configuración actual antes de cambiar la forma en que recibe las notificaciones. Especifique la aplicación o categoría de notificación que desea actualizar.

| Preferencia | Cambios disponibles |
| --- | --- |
| Canales de envío | Activa o desactiva las notificaciones dentro de la aplicación, las notificaciones por correo electrónico o las notificaciones de [!DNL Slack] de una aplicación o categoría. |
| Frecuencia de correo electrónico | Elija una entrega inmediata por correo electrónico o un resumen diario o semanal. |
| Prioridad de categoría | Elija qué categorías de notificación tienen prioridad alta. |
| Alertas emergentes | Elija las categorías de notificación que deben mostrar las alertas emergentes. |

Ejemplos de peticiones de datos:

* &quot;¿Cuál es mi configuración de notificaciones para Adobe Journey Optimizer?&quot;
* &quot;Deshabilitar [!DNL Slack] notificaciones para Experience Platform&quot;.
* &quot;Cambiar mi resumen diario a semanal&quot;.
* &quot;Silenciar las notificaciones de actualización de versiones&quot;.
* &quot;Enviar solo notificaciones de Adobe Journey Optimizer por correo electrónico&quot;.

Si Chat del compañero le pide detalles de programación, especifique el día, la hora y el huso horario de su resumen semanal.

![El chat de compañeros de trabajo pregunta a qué día debería llegar el resumen semanal, con fichas adicionales para la hora, la zona horaria y la revisión.](./assets/digest-schedule.png)

## Más ayuda sobre este tema {#more-help}

Utilice estas guías para empezar a usar el chat de compañeros o investigar la actividad de alertas de Experience Platform.

* [Introducción al chat con compañeros](/help/chat/ui-guide.md)
* [Aptitudes de alerta al cliente](/help/chat/use-cases/customer-alerts/customer-alerts.md)
