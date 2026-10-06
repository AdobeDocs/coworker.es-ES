---
title: Habilidades de agencia de herramientas para espacios aislados
description: Aprenda a utilizar las habilidades de agente de herramientas de espacio aislado para replicar metadatos de objetos en entornos de espacio aislado.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%
---

# Aptitudes agénticas de herramientas de zona protegida

>[!AVAILABILITY]
>
>Las habilidades de agente de herramientas de zona protegida están disponibles para todos los clientes con acceso a Adobe CX Enterprise Coworker. Para utilizar todas las funciones disponibles, necesita los siguientes permisos:
>
>**Manage-sandbox** o **View-sandbox**: estos permisos le permiten utilizar habilidades de agente de herramientas de espacio aislado para ver espacios aislados directamente en Coworker.
>
>**Administrar paquete**: Este permiso le permite usar Habilidades de agente de herramientas de espacio aislado para crear paquetes directamente en Compañero de trabajo.

>[!NOTE]
>
>Actualmente, puede utilizar las habilidades de agente de herramientas de zona protegida para descubrir, empaquetar y migrar objetos de esquema y audiencia. En futuras versiones se añadirá compatibilidad con tipos de objeto adicionales.

Utilice las habilidades de agente de herramientas de espacio aislado para mover metadatos de objetos, incluidos esquemas y audiencias, a entornos de Adobe Experience Platform. Para ello, describa lo que desea lograr en lenguaje natural. Con CX Coworker, puede descubrir los metadatos necesarios, identificar automáticamente las dependencias, crear paquetes de migración y migrar objetos a través de una experiencia conversacional.

>[!VIDEO](https://video.tv.adobe.com/v/3496706?learn=on)

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

- Acceso a Adobe Experience Platform y a la organización y zona protegida adecuadas.
- Acceso a los objetos que desea descubrir o migrar.
- El complemento CXO de Adobe instalado en CX Coworker.

Para obtener instrucciones sobre la instalación de complementos, consulte la [guía de la interfaz de usuario de Coworker](https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Uso de habilidades de agente de herramientas de espacio aislado {#use-sandbox-tooling-agentic-skills}

Interactúe con las habilidades agénticas de las herramientas de espacio aislado a través de CX Coworker usando lenguaje natural. Describa su objetivo con la mayor claridad posible. Las solicitudes específicas producen los mejores resultados, mientras que las solicitudes vagas o demasiado breves pueden devolver resultados de menor calidad o no invocar al agente.

Para utilizar las habilidades de agente de herramientas de espacio aislado:

1. Vaya a **[!UICONTROL CX Coworker]**.
1. Escriba una descripción clara de lo que desea lograr. Por ejemplo:

   *&quot;Mover el miembro Platino de fidelidad de esquema de la zona protegida actual a la zona protegida de demostración de Acme.&quot;*

1. Revise la tabla de resultados, que muestra los entornos limitados de origen y destino. Cuando esté listo para continuar, seleccione **[!UICONTROL Continuar]** y, a continuación, seleccione **[!UICONTROL Enviar]** para confirmar.

   ![Los resultados de la solicitud con la opción Continuar seleccionada, destacando Enviar.](./assets/sandbox-tooling/results-proceed.png)

1. Seleccione uno o varios objetos que desee migrar y, a continuación, seleccione **[!UICONTROL Enviar]**.

   ![Enviar resaltado de página de selección de objetos.](./assets/sandbox-tooling/object-selection.png)

1. Revise los objetos y dependencias que el agente identifica y confirme las acciones de la operación: *Crear nuevo* o *Usar existente*. Cuando esté listo para comenzar la migración, seleccione **[!UICONTROL Continuar]** y, a continuación, seleccione **[!UICONTROL Enviar]** para confirmar. La migración puede tardar varios minutos en completarse.

   ![Confirmar envío de resalte de página de plan de acción.](./assets/sandbox-tooling/action-plan.png)

1. Cuando finaliza la migración, los objetos seleccionados están disponibles en la zona protegida de destino.

   ![Transferir página completa que muestra el estado de la solicitud.](./assets/sandbox-tooling/transfer-complete.png)

Para obtener más información sobre el uso de CX Coworker, consulte la [Guía de la interfaz de usuario de Coworker](https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Casos de uso admitidos {#supported-use-cases}

Explore formas comunes de utilizar las habilidades agénticas de la herramienta de uso de zonas protegidas para simplificar la administración de zonas protegidas y la migración de metadatos.

### Mover metadatos de objeto entre zonas protegidas

Como administrador de zona protegida que administra varios entornos limitados de Adobe Experience Platform, puede migrar los metadatos de los objetos mediante solicitudes en lenguaje natural en lugar de navegar manualmente por la interfaz de usuario.

Con CX Coworker, puede migrar metadatos de objetos, incluidos esquemas, audiencias y recursos de configuración relacionados, de una zona protegida a otra describiendo la migración en lenguaje natural. Las habilidades de agente de herramientas de zona protegida identifican y empaquetan automáticamente las dependencias requeridas, lo que garantiza una migración fiable.

Por ejemplo:

- &quot;Mueva el esquema Platino de los miembros de fidelidad de Luma de la zona protegida actual a la zona protegida de producción&quot;.

### Promocionar audiencias entre zonas protegidas

Como administrador de zona protegida, puede promocionar audiencias entre entornos sin volver a crearlas o configurarlas manualmente.

Por ejemplo:

- &quot;Promocione la audiencia &#39;Nombre de audiencia&#39; a la zona protegida de ensayo.&quot;

Las habilidades de agente de herramientas de zona protegida identifican la audiencia especificada, validan sus dependencias y migran todos los objetos necesarios a la zona protegida de destino.

## Ejemplos de peticiones {#example-prompts}

Utilice las siguientes indicaciones como ejemplos al interactuar con las habilidades de agente de herramientas de zona protegida.

### Mensajes de esquema

Utilice estas indicaciones cuando conozca el nombre del esquema y la zona protegida de destino.

- &quot;Mover el esquema &#39;Nombre del esquema&#39; de la zona protegida actual a la zona protegida de producción.&quot;

### Mensajes de audiencia

Utilice estas indicaciones cuando conozca el nombre de la audiencia.

- &quot;Promocione la audiencia &#39;Nombre de audiencia&#39; a la zona protegida de ensayo.&quot;

## Próximos pasos {#next-steps}

Después de leer esta guía, debe comprender cómo utilizar las habilidades de agente de herramientas de espacio aislado para descubrir, empaquetar y migrar objetos admitidos entre espacios aislados.

Para obtener más información sobre las herramientas de zonas protegidas, consulte la [Guía de herramientas de zonas protegidas](https://experienceleague.adobe.com/es/docs/experience-platform/sandbox/ui/sandbox-tooling).

