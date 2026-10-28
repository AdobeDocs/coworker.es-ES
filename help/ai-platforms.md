---
title: Adobe CX Enterprise Coworker para plataformas de IA
description: Obtenga información acerca de Adobe CX Enterprise Coworker para plataformas de IA. Explore las plataformas compatibles, las instrucciones de configuración y las indicaciones de ejemplo para obtener perspectivas de marketing.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 1%
---

# Adobe CX Enterprise Coworker para plataformas de IA

Utilice Adobe CX Enterprise Coworker para plataformas de IA para obtener perspectivas de marketing en las herramientas de IA que ya utiliza. Haga preguntas en lenguaje natural sin cambiar de herramienta. Busque el producto que aparece como Adobe CX Enterprise Coworker en cada plataforma.

Encuentre las plataformas disponibles y sus instrucciones de configuración en [Configurar compañero](#set-up-coworker).

El uso de Coworker en plataformas de IA no supone ningún coste adicional. Se incluye en la licencia de CX Enterprise Coworker y el uso se basa en los mismos créditos de IA que otras funciones de Coworker. Para obtener más información, consulte [Trabajos de agente de Adobe Experience Platform y consumo de créditos de IA](https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/overview/ai-credit-consumption){target="_blank"}.

<!-- TODO: architecture diagram pending from engineering. KT page notes "to be provided on 8/28"; still outstanding as of 8/31. Insert here once received. -->

## Requisitos previos {#prerequisites}

Antes de poder usar Coworker en una plataforma de IA, confirme que dispone de lo siguiente.

* Adobe CX Enterprise Coworker proporcionado para su organización y su propio acceso a él en Adobe.
* Adobe Experience Platform y al menos uno de Adobe Real-Time CDP, Adobe Journey Optimizer o Adobe Customer Journey Analytics.
* Acceso a una plataforma de IA enumerada en [Configurar compañero](#set-up-coworker).

## Acceso a datos y permisos {#data-access-and-permissions}

Los compañeros de trabajo en plataformas de IA reflejan los mismos datos y el mismo nivel de acceso vinculado a su identidad de Adobe. Lo que puede consultar y ver coincide con lo que ya tiene derecho a ver en Experience Platform y sus soluciones asociadas. El compañero hereda esos permisos, por lo que no se requiere una configuración de permisos independiente para la integración de la plataforma de IA. El compañero devuelve perspectivas de solo lectura y no modifica los datos del cliente. Revise los resúmenes y análisis generados antes de utilizarlos para tomar decisiones comerciales.

<!-- Confirmed by PM (Siddhartha Srivastava) on 2026-09-02 for Microsoft 365 Copilot, Claude, and ChatGPT. Validate this permissions model for each additional platform before adding its setup tab. -->

## Casos de uso clave {#key-use-cases}

Utilice Coworker en plataformas de IA para acelerar los flujos de trabajo de marketing comunes sin salir de las herramientas diarias.

| Ejemplo de uso | Descripción |
| --- | --- |
| Planificar y revisar campañas | Planifique campañas, incluidas las revisiones de campañas de socios y la previsión de audiencias. Compare el rendimiento de la campaña con el tiempo e identifique qué puntos de contacto impulsan las conversiones. |
| Monitorización de recorridos y preparación de campañas | Revise y supervise las campañas activas, analice los recorridos de los clientes y evalúe la preparación de la campaña. Realice un seguimiento del rendimiento del recorrido y las bajas para identificar oportunidades de optimización. |
| Recuperación de perspectivas operativas | Identifique qué audiencias son más grandes o más comprometidas, de modo que pueda priorizar dónde centrar sus esfuerzos y realizar un seguimiento del crecimiento o la reducción de sus segmentos con el paso del tiempo. |
| Optimización de flujos de trabajo y contenido | Optimice los flujos de trabajo e identifique las necesidades de recursos y contenido para las campañas de CX. Generar informes visuales sobre el rendimiento de la campaña sin crear manualmente consultas o paneles. |
| Colabore y decida más rápido | Utilice mensajes sugeridos para explorar audiencias, campañas y tráfico web. Comparta perspectivas con su equipo durante las reuniones de planificación y responda preguntas ad hoc en tiempo real mientras revisa los planes o las cubiertas. |

<!-- Use cases approved by PM Siddhartha Srivastava on 2026-08-31 and confirmed for Microsoft 365 Copilot, Claude, and ChatGPT on 2026-09-02. Validate applicability for each additional platform before adding its setup tab. -->

## Configuración de compañeros {#set-up-coworker}

Seleccione una plataforma disponible para las instrucciones de configuración. Después de la instalación, pruebe con [mensajes de ejemplo](#example-prompts).

>[!BEGINTABS]

>[!TAB Copiloto de Microsoft 365]

Use [!DNL Adobe CX Enterprise Coworker for Copilot] para obtener información de marketing en [!DNL Microsoft 365 Copilot].

Antes de comenzar, confirme que tiene acceso a [!DNL Microsoft 365 Copilot].

**Configurar compañeros de trabajo para su organización**

Un administrador debe completar estos pasos antes de que los usuarios finales puedan obtener acceso a Colaborador en [!DNL Microsoft 365 Copilot].

1. En [!DNL Microsoft 365 admin center], confirme que la configuración del inquilino permite las aplicaciones y los agentes creados por editores externos.
1. Aprobar **[!UICONTROL Adobe CX Enterprise Coworker]** tanto en [!DNL Microsoft 365 admin center] como en [!DNL Teams admin center]. Normalmente, puede encontrar el agente a través de [!DNL Microsoft Commercial Marketplace] o de la lista de **[!UICONTROL aplicaciones integradas]** de su organización.
1. Despliegue del agente para los usuarios finales. Puede implementarlo en usuarios o grupos específicos o en toda la organización. El número de usuarios que habilite no afectará a la configuración ni al coste.

>[!NOTE]
>
>Si [!DNL Microsoft] publica una actualización para el Compañero de trabajo que requiere nuevos permisos, el administrador debe aprobar la actualización en [!DNL Agent Registry] antes de que se implemente a los usuarios.

**Acceder a compañero de trabajo en[!DNL Copilot]**

Una vez que el administrador habilite el colaborador, podrá obtener acceso a él en [!DNL Microsoft 365 Copilot] superficies, incluidas [!DNL Teams], [!DNL Word], [!DNL Excel], [!DNL PowerPoint] y el chat web.

En [!DNL Microsoft 365 Copilot], seleccione **[!UICONTROL Agentes]** y después seleccione **[!UICONTROL Más agentes]**.

![Copiloto de Microsoft 365 con el menú Agentes abierto y más agentes resaltados.](./assets/ai-platforms/copilot/copilot-agents.png)

A continuación, seleccione **[!UICONTROL Adobe CX Enterprise Coworker]** en el catálogo del agente.

![Catálogo del agente Copilot de Microsoft 365 con el listado de Adobe CX Enterprise Coworker resaltado.](./assets/ai-platforms/copilot/copilot-select-agent.png)

Finalmente, seleccione **[!UICONTROL Agregar]** para agregar Compañero de trabajo a sus agentes.

![Detalles de Adobe CX Enterprise Coworker en el copiloto de Microsoft 365 con el botón Agregar resaltado.](./assets/ai-platforms/copilot/copilot-add-coworker.png)

>[!TAB ChatGPT]

Use [!DNL Adobe CX Enterprise Coworker for ChatGPT] para obtener información de marketing en [!DNL ChatGPT].

Antes de comenzar, confirme que tiene acceso a [!DNL ChatGPT].

**Configurar compañeros de trabajo para su organización**

* Pida al administrador de [!DNL ChatGPT] que apruebe **[!UICONTROL Adobe CX Enterprise Coworker]** para los usuarios seleccionados o toda la organización.

**Acceder a compañero de trabajo en[!DNL ChatGPT]**

En [!DNL ChatGPT], seleccione **[!UICONTROL Complementos]**.

Navegación ![ChatGPT con complementos resaltados.](./assets/ai-platforms/chatgpt/gpt-plugins.png)

A continuación, busque y seleccione **[!UICONTROL Adobe CX Enterprise Coworker]** en el catálogo de complementos.

![Catálogo del complemento ChatGPT con el listado de Adobe CX Enterprise Coworker resaltado entre los resultados de búsqueda de Adobe.](./assets/ai-platforms/chatgpt/gpt-select-plugins.png)

Finalmente, seleccione **[!UICONTROL Instalar complemento]** para agregar Colaborador a [!DNL ChatGPT].

![Detalles de Adobe CX Enterprise Coworker en ChatGPT con el botón Instalar complemento resaltado.](./assets/ai-platforms/chatgpt/gpt-install-coworker.png)

>[!TAB Claude]

Use Colaborador para obtener información de marketing en [!DNL Claude].

Antes de comenzar, confirme que tiene acceso a [!DNL Claude].

**Configurar compañeros de trabajo para su organización**

* Pida al administrador de [!DNL Claude] que apruebe **[!UICONTROL Adobe CX Enterprise Coworker]** para los usuarios seleccionados o toda la organización.

**Acceder a compañero de trabajo en[!DNL Claude]**

1. En [!DNL Claude], seleccione **[!UICONTROL Personalizar]**.

   ![Claude la navegación con la opción Personalizar resaltada.](./assets/ai-platforms/claude/claude-customize.png)

1. Seleccione **[!UICONTROL Conectores]**, luego **[!UICONTROL Discover]** y use **[!UICONTROL Buscar]** para encontrar Adobe CX Enterprise Coworker.

   ![Claude Personaliza la página con la ficha Conectores resaltada y el catálogo de Discover abierto.](./assets/ai-platforms/claude/claude-connectors.png)

1. Seleccione **[!UICONTROL Adobe CX Enterprise Coworker]** y, a continuación, seleccione **[!UICONTROL Conectarse a Claude]**.

   ![Detalles del conector Adobe CX Enterprise Coworker en Claude con la opción Conectarse a Claude resaltada.](./assets/ai-platforms/claude/claude-connect-coworker.png)

1. Inicie sesión con sus credenciales de Adobe para conectar a su compañero de trabajo con [!DNL Claude].

>[!ENDTABS]

<!-- Setup steps above reflect the real customer-facing flow confirmed by PM (Siddhartha Srivastava) on 2026-09-02: an org admin approves the connector or plugin, then end users find and add it in their platform's catalog and sign in. The previous version of this file described a manual MCP-connector setup for ChatGPT (Settings > Connectors > paste server URL) -- PM clarified that flow is for internal testing only, not the customer path, so it was removed here. -->

## Ejemplos de peticiones {#example-prompts}

Después de configurar Coworker en una plataforma compatible, intente estas indicaciones o escriba las suyas propias en lenguaje natural.

* Muestre sus cinco audiencias principales.
* Mostrar una métrica del último mes.
* Muestre sus proyectos activos de Workfront.
* Mostrar recorridos con audiencias de fidelización.

## Limitaciones conocidas {#known-limitations}

El compañero en las plataformas de IA no admite todos los patrones de integración.

* No puede conectar a su compañero a su propio arnés magnético usando MCP.

## Solución de problemas de compañeros en plataformas de IA {#troubleshoot}

Pruebe estos pasos si encuentra problemas con Coworker en una plataforma de IA.

* Si ve un error, cierre la sesión y vuelva a iniciarla con sus credenciales de Adobe. La reautenticación resuelve la mayoría de los problemas.
* Si no puede acceder a Compañero de trabajo o a datos específicos, póngase en contacto con el administrador de Adobe para confirmar el acceso y los permisos del producto.

<!--
Editorial maintenance, 2026-10-27:
Only approved platforms with validated setup guidance belong in the rendered tab set.
Remaining platforms to add: Gemini, Amazon Quick, IBM, and Databricks.

To add an approved platform:
* Confirm approval and obtain access to the customer flow.
* Validate prerequisites, organization approval, catalog discovery, listing name, installation, and Adobe sign-in.
* Confirm the shared licensing, permissions, use cases, prompts, limitations, and troubleshooting guidance applies.
* Add one tab before ENDTABS, following the existing order: introduction, platform prerequisites, organization setup, and user access.
* Document any platform-specific requirements or exceptions within that tab.
* Preview the tab and verify its links and image references.
Keep the introduction, metadata, and shared prerequisites free of platform lists so adding a tab does not require duplicate updates.

Gemini draft scope:
No setup steps are confirmed. Validate the complete customer flow and all shared guidance before adding the tab.
Do not infer the flow from another platform.
-->
