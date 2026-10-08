---
title: Herramientas de Journey Optimizer en CX Coworker Gateway
description: Descubra qué herramientas de Adobe Journey Optimizer están disponibles a través de CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 2%
---
# Herramientas de Adobe Journey Optimizer en CX Coworker Gateway {#ajo-mcp}

Utilice las herramientas de producto de Adobe Journey Optimizer para inspeccionar campañas, recorridos y configuraciones de canal desde un cliente compatible con MCP. Estas herramientas están disponibles a través de la [puerta de enlace de CX Coworker](overview.md) cuando su organización está habilitada y su cuenta de usuario tiene los permisos de Journey Optimizer requeridos.

Para obtener más información, consulte [Trabajar con clientes MCP](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/combine/ajo-mcp){target="_blank"} en la documentación de Adobe Journey Optimizer.

Si desea una experiencia conversacional y auténtica para crear, analizar y simular recorridos, consulte [Journey Agent](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/agents/ajo-agent) en su lugar.

>[!AVAILABILITY]
>
>Las herramientas de producto de Journey Optimizer se encuentran en Beta. El acceso se realiza únicamente por invitación y requiere la habilitación de la organización de Adobe. Consulte [Acceder a las herramientas de CX Coworker Gateway](access.md).

## Funcionalidades clave {#mcp-capabilities}

Las herramientas de Journey Optimizer proporcionan una superficie de solo lectura para la revisión de la configuración de campañas, recorridos y canales. Puede:

- Enumere las campañas de Journey Optimizer y filtre por estado.
- Recupere detalles de la campaña, incluidos los metadatos de segmentación, programación, canal y configuración de contenido.
- Enumere e inspeccione los recorridos de la zona protegida, incluidas las ramas, las condiciones y las acciones.
- Enumere las configuraciones de canal para los canales de correo electrónico, SMS, push y WhatsApp.
- Enumerar las acciones de marketing disponibles para la aplicación de políticas de gobernanza de datos.
- Revise la configuración de la campaña, el recorrido y el canal en lenguaje natural sin navegar por las pantallas de producto.

>[!IMPORTANT]
>
>Todas las herramientas de Journey Optimizer de la Beta actual son de solo lectura. No se puede crear, actualizar, eliminar, iniciar, detener o publicar campañas o recorridos.

## Herramientas disponibles {#mcp-tools}

| Herramienta | Descripción |
| --- | --- |
| `ajo_campaign_list` | Examine las campañas de marketing de Journey Optimizer. Admite el filtrado por estado, como `DRAFT`, `LIVE`, `STOPPED` y `COMPLETED`. |
| `ajo_campaign_get` | Obtenga detalles y configuración de una campaña específica por ID, incluidos metadatos de segmentación de audiencia, programación, canal y configuración de contenido. |
| `ajo_journey_list` | Examine todos los recorridos de la zona protegida de Journey Optimizer. |
| `ajo_journey_get` | Obtenga detalles completos para un recorrido específico por ID, incluidas su ramificación, condiciones y acciones. |
| visualización de recorrido | Procesar la estructura y el flujo de un recorrido para una exploración visual e interactiva. |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | Vea los ajustes preestablecidos de superficie y la configuración de marca para los canales de correo electrónico, SMS, push o [!DNL WhatsApp]. |
| `ajo_channel_configuration_resource_list`, `ajo_channel_configuration_resource_get` | Enumere y recupere los recursos de configuración de compatibilidad a los que hacen referencia las configuraciones de canal, como credenciales push, subdominios de correo electrónico, grupos de IP, credenciales de SMS y credenciales de [!DNL WhatsApp]. |
| `ajo_marketing_action_list` | Enumerar las acciones de marketing disponibles para la aplicación de políticas de gobernanza de datos. |

## Ejemplos de peticiones {#mcp-use-cases}

| Objetivo | Mensaje de ejemplo |
| --- | --- |
| Información general de Campaign | &quot;Mostrarme todas mis campañas de Journey Optimizer&quot;. |
| Auditoría de estado | &quot;¿Qué campañas están activas actualmente?&quot; |
| Detalles de la campaña | &quot;Obtener todos los detalles de la campaña `[campaign ID]`&quot;. |
| Información general del recorrido | &quot;Mostrarme todos mis recorridos de Journey Optimizer&quot;. |
| detalles del recorrido | &quot;Obtenga todos los detalles del recorrido `[journey ID]`, incluidas las ramas y las condiciones&quot;. |
| Audiencia y segmentación | &quot;¿A qué audiencia se dirige la campaña `[campaign ID]`?&quot; |
| Programación y calendario | &quot;¿Cuándo está programado que se ejecute la campaña `[campaign ID]`?&quot; |
| Resolución de problemas | &quot;Revise la configuración de la campaña `[campaign ID]` y marque los posibles problemas&quot;. |
| Configuración de canal | &quot;¿Qué configuraciones de canal de correo electrónico están disponibles?&quot; |
| Auditoría de canales | &quot;¿Qué configuraciones de canal faltan o están incompletas?&quot; |
| Gobernanza | &quot;¿Qué acciones de marketing están disponibles en mi zona protegida?&quot; |

## Herramientas de administración de contenido {#mcp-content-management}

Además de las herramientas de producto de solo lectura anteriores, los usuarios de Journey Optimizer pueden detectar y administrar recursos de contenido (plantillas de contenido, fragmentos, páginas de aterrizaje y contenido de mensajes en línea de recorridos o campañas) directamente desde CX Coworker con indicaciones en lenguaje natural. Esta capacidad está equipada con un conjunto independiente de herramientas de MCP con capacidad de lectura y escritura para contenido de Journey Optimizer, y está disponible para todos los clientes que tengan acceso a CX Coworker.

Para obtener más información, consulte [Herramientas de administración de contenido](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/essentials/ajo-coworker-skills#content-management){target="_blank"} en la documentación de Adobe Journey Optimizer.

Las herramientas de gestión de contenido le permiten:

- Examine plantillas de contenido, fragmentos y páginas de aterrizaje y recupere su estructura, metadatos y estado.
- Recupere el contenido del mensaje en línea configurado en un nodo de recorrido o de acción de campaña.
- Cree y actualice plantillas de contenido para cualquier canal.
- Crear, actualizar, clonar y publicar fragmentos.
- Reemplace una variante de canal en el mensaje en línea de un nodo de recorrido o acción de campaña.

>[!IMPORTANT]
>
>A diferencia de las herramientas de producto de solo lectura anteriores, las herramientas de administración de contenido admiten operaciones de escritura. No se admiten las búsquedas de texto completo en plantillas o fragmentos, la validación de plantillas o fragmentos, la creación o publicación de páginas de aterrizaje y la eliminación de plantillas de contenido, fragmentos o páginas de aterrizaje.

## Contexto y permisos del producto {#mcp-context}

La cuenta de usuario debe tener permiso para ver las campañas de Journey Optimizer, los recorridos y las configuraciones de canal que consulte. El MCP no omite los permisos del producto.

Si su organización utiliza varios entornos limitados, especifique el contexto del entorno o la zona protegida en el mensaje cuando necesite resultados de un entorno limitado específico.

## Limitaciones conocidas {#mcp-limitations}

| Limitación | Descripción | Solución alternativa |
| --- | --- | --- |
| Superficie de solo lectura | Las herramientas de Journey Optimizer solo exponen las operaciones de recuperación. No puede crear, actualizar, eliminar, iniciar, detener ni publicar campañas o recorridos. | Utilice la interfaz de usuario o las API de Journey Optimizer para realizar operaciones de escritura. |
| Sin métricas de participación ni de rendimiento | Las herramientas no devuelven datos de informes como impresiones, tasas de pulsaciones, conversiones o estadísticas de envío. | Utilice los informes de Journey Optimizer, las herramientas de Customer Journey Analytics o las herramientas de Adobe Analytics para las métricas de rendimiento. |
| La paginación de la lista de campañas es limitada | La lista de campañas devuelve la primera página de resultados, con un máximo de 50 campañas ordenadas alfabéticamente. Los valores de desplazamiento y límite no se aplican. | Use `Get Campaign` directamente si se conoce el ID de campaña. Utilice la interfaz de usuario de Journey Optimizer para realizar exploraciones y filtros completos. |
| Sin filtrado del lado del servidor por fecha, canal o programación | La lista de campañas admite el filtrado de estado, pero no el filtrado de fecha de publicación, fecha de programación, canal o tipo de campaña. | Utilice la lista de campañas de la IU de Journey Optimizer para el filtrado nativo de fechas y canales. |
| Recuperación de contenido de mensaje no disponible a través de herramientas de producto | Message HTML, las líneas de asunto, los tokens de personalización y el contenido de ofertas no están disponibles a través de las herramientas de producto de solo lectura anteriores. | Utilice las [herramientas de administración de contenido](#mcp-content-management) para recuperar y actualizar el contenido de los mensajes en línea o para verlo directamente en la interfaz de usuario de Journey Optimizer. |