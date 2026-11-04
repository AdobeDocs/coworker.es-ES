---
title: Adobe CX Enterprise Coworker para plataformas de IA
description: Obtenga información acerca de Adobe CX Enterprise Coworker para plataformas de IA. Explore las plataformas compatibles, las instrucciones de configuración y las indicaciones de ejemplo para obtener perspectivas de marketing.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: b9c3e1915b1f3f182cc91452e60eea13b05f12fa
workflow-type: tm+mt
source-wordcount: '2104'
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

<!-- Confirmed by PM (Siddhartha Srivastava) on 2026-09-02 for Microsoft 365 Copilot, Claude, and ChatGPT. Validate this permissions model for each additional platform before adding its setup section. -->

## Casos de uso clave {#key-use-cases}

Utilice Coworker en plataformas de IA para acelerar los flujos de trabajo de marketing comunes sin salir de las herramientas diarias.

| Ejemplo de uso | Descripción |
| --- | --- |
| Planificar y revisar campañas | Planifique campañas, incluidas las revisiones de campañas de socios y la previsión de audiencias. Compare el rendimiento de la campaña con el tiempo e identifique qué puntos de contacto impulsan las conversiones. |
| Monitorización de recorridos y preparación de campañas | Revise y supervise las campañas activas, analice los recorridos de los clientes y evalúe la preparación de la campaña. Realice un seguimiento del rendimiento del recorrido y las bajas para identificar oportunidades de optimización. |
| Recuperación de perspectivas operativas | Identifique qué audiencias son más grandes o más comprometidas, de modo que pueda priorizar dónde centrar sus esfuerzos y realizar un seguimiento del crecimiento o la reducción de sus segmentos con el paso del tiempo. |
| Optimización de flujos de trabajo y contenido | Optimice los flujos de trabajo e identifique las necesidades de recursos y contenido para las campañas de CX. Generar informes visuales sobre el rendimiento de la campaña sin crear manualmente consultas o paneles. |
| Colabore y decida más rápido | Utilice mensajes sugeridos para explorar audiencias, campañas y tráfico web. Comparta perspectivas con su equipo durante las reuniones de planificación y responda preguntas ad hoc en tiempo real mientras revisa los planes o las cubiertas. |

<!-- Use cases approved by PM Siddhartha Srivastava on 2026-08-31 and confirmed for Microsoft 365 Copilot, Claude, and ChatGPT on 2026-09-02. Validate applicability for each additional platform before adding its setup section. -->

## Configuración de compañeros {#set-up-coworker}

Seleccione una plataforma disponible para las instrucciones de configuración. Después de la instalación, pruebe con [mensajes de ejemplo](#example-prompts).

* [Microsoft 365 Copilot](#microsoft-365-copilot)
* [ChatGPT](#chatgpt)
* [Claude](#claude)
* [Gemini Enterprise](#gemini-enterprise)
* [Amazon Quick](#amazon-quick)
* [IBM watsonx Orchestrate](#ibm-watsonx-orchestrate)
* [Databricks](#databricks)

### [!DNL Microsoft 365 Copilot] {#microsoft-365-copilot}

Use [!DNL Adobe CX Enterprise Coworker for Copilot] para obtener información de marketing en [!DNL Microsoft 365 Copilot].

Antes de comenzar, confirme que tiene acceso a [!DNL Microsoft 365 Copilot].

#### Configuración del acceso a la organización {#copilot-organization-setup}

Un administrador debe completar estos pasos antes de que los usuarios finales puedan obtener acceso a Colaborador en [!DNL Microsoft 365 Copilot].

1. En [!DNL Microsoft 365 admin center], confirme que la configuración del inquilino permite las aplicaciones y los agentes creados por editores externos.
1. Aprobar **[!UICONTROL Adobe CX Enterprise Coworker]** tanto en [!DNL Microsoft 365 admin center] como en [!DNL Teams admin center]. Normalmente, puede encontrar el agente a través de [!DNL Microsoft Commercial Marketplace] o de la lista de **[!UICONTROL aplicaciones integradas]** de su organización.
1. Despliegue del agente para los usuarios finales. Puede implementarlo en usuarios o grupos específicos o en toda la organización. El número de usuarios que habilite no afectará a la configuración ni al coste.

>[!NOTE]
>
>Si [!DNL Microsoft] publica una actualización para el Compañero de trabajo que requiere nuevos permisos, el administrador debe aprobar la actualización en [!DNL Agent Registry] antes de que se implemente a los usuarios.

#### Acceder a Compañero {#copilot-access}

Una vez que el administrador habilite el colaborador, podrá obtener acceso a él en [!DNL Microsoft 365 Copilot] superficies, incluidas [!DNL Teams], [!DNL Word], [!DNL Excel], [!DNL PowerPoint] y el chat web.

En [!DNL Microsoft 365 Copilot], seleccione **[!UICONTROL Agentes]** y después seleccione **[!UICONTROL Más agentes]**.

![Copiloto de Microsoft 365 con el menú Agentes abierto y más agentes resaltados.](./assets/ai-platforms/copilot/copilot-agents.png)

A continuación, seleccione **[!UICONTROL Adobe CX Enterprise Coworker]** en el catálogo del agente.

![Catálogo del agente Copilot de Microsoft 365 con el listado de Adobe CX Enterprise Coworker resaltado.](./assets/ai-platforms/copilot/copilot-select-agent.png)

Finalmente, seleccione **[!UICONTROL Agregar]** para agregar Compañero de trabajo a sus agentes.

![Detalles de Adobe CX Enterprise Coworker en el copiloto de Microsoft 365 con el botón Agregar resaltado.](./assets/ai-platforms/copilot/copilot-add-coworker.png)

### [!DNL ChatGPT] {#chatgpt}

Use [!DNL Adobe CX Enterprise Coworker for ChatGPT] para obtener información de marketing en [!DNL ChatGPT].

Antes de comenzar, confirme que tiene acceso a [!DNL ChatGPT].

#### Configuración del acceso a la organización {#chatgpt-organization-setup}

El administrador debe aprobar el trabajo con los compañeros antes de añadirlo.

* Pida al administrador de [!DNL ChatGPT] que apruebe **[!UICONTROL Adobe CX Enterprise Coworker]** para los usuarios seleccionados o toda la organización.

#### Acceder a Compañero {#chatgpt-access}

En [!DNL ChatGPT], seleccione **[!UICONTROL Complementos]**.

Navegación ![ChatGPT con complementos resaltados.](./assets/ai-platforms/chatgpt/gpt-plugins.png)

A continuación, busque y seleccione **[!UICONTROL Adobe CX Enterprise Coworker]** en el catálogo de complementos.

![Catálogo del complemento ChatGPT con el listado de Adobe CX Enterprise Coworker resaltado entre los resultados de búsqueda de Adobe.](./assets/ai-platforms/chatgpt/gpt-select-plugins.png)

Finalmente, seleccione **[!UICONTROL Instalar complemento]** para agregar Colaborador a [!DNL ChatGPT].

![Detalles de Adobe CX Enterprise Coworker en ChatGPT con el botón Instalar complemento resaltado.](./assets/ai-platforms/chatgpt/gpt-install-coworker.png)

### [!DNL Claude] {#claude}

Use Colaborador para obtener información de marketing en [!DNL Claude].

Antes de comenzar, confirme que tiene acceso a [!DNL Claude].

#### Configuración del acceso a la organización {#claude-organization-setup}

El administrador debe aprobar el trabajo con los compañeros antes de añadirlo.

* Pida al administrador de [!DNL Claude] que apruebe **[!UICONTROL Adobe CX Enterprise Coworker]** para los usuarios seleccionados o toda la organización.

#### Acceder a Compañero {#claude-access}

1. En [!DNL Claude], seleccione **[!UICONTROL Personalizar]**.

   ![Claude la navegación con la opción Personalizar resaltada.](./assets/ai-platforms/claude/claude-customize.png)

1. Seleccione **[!UICONTROL Conectores]**, luego **[!UICONTROL Discover]** y use **[!UICONTROL Buscar]** para encontrar Adobe CX Enterprise Coworker.

   ![Claude Personaliza la página con la ficha Conectores resaltada y el catálogo de Discover abierto.](./assets/ai-platforms/claude/claude-connectors.png)

1. Seleccione **[!UICONTROL Adobe CX Enterprise Coworker]** y, a continuación, seleccione **[!UICONTROL Conectarse a Claude]**.

   ![Detalles del conector Adobe CX Enterprise Coworker en Claude con la opción Conectarse a Claude resaltada.](./assets/ai-platforms/claude/claude-connect-coworker.png)

1. Inicie sesión con sus credenciales de Adobe para conectar a su compañero de trabajo con [!DNL Claude].

### [!DNL Gemini Enterprise] {#gemini-enterprise}

Use Colaborador para obtener información de marketing en [!DNL Gemini Enterprise].

Antes de comenzar, confirme que tiene acceso a [!DNL Gemini Enterprise].

#### Configuración del acceso a la organización {#gemini-organization-setup}

Como administrador de [!DNL Gemini Enterprise], complete estos pasos para que Coworker esté disponible para su organización.

1. Vaya al [mercado de agentes de IA empresariales de Gemini](https://console.cloud.google.com/marketplace/browse?filter=solution-type:ai-agent-service).
1. Busque Adobe CX Enterprise Coworker y, a continuación, seleccione la tarjeta del agente **[!UICONTROL Adobe CX Enterprise Coworker]**.
1. En la tarjeta del agente, seleccione **[!UICONTROL Contactar con ventas]**.

   ![Listado de agentes de Gemini Enterprise Marketplace con el botón Contactar con ventas.](./assets/ai-platforms/gemini-enterprise/gemini-contact-sales.png){width="700"}

1. Complete el formulario para enviar la solicitud a Adobe.

   ![Envíe un correo electrónico al formulario de Adobe Inc con campos de contacto y proyecto, una casilla de verificación de consentimiento y el botón Enviar correo electrónico.](./assets/ai-platforms/gemini-enterprise/gemini-contact-adobe.png){width="600"}

   Adobe crea una oferta privada sin coste alguno y le envía un vínculo por correo electrónico.

1. Abra el vínculo enviado por correo electrónico y apruebe la oferta privada.

   Después de aprobar la oferta, Adobe habilita el agente para su cuenta de [!DNL Gemini Enterprise].

1. Publique el agente en usuarios seleccionados o en todos los usuarios de empresa de su organización.

#### Acceder a Compañero {#gemini-access}

Una vez que el administrador le publique el Colaborador, ábralo en [!DNL Gemini Enterprise] para empezar a hacer preguntas.

1. En [!DNL Gemini Enterprise], vaya al catálogo **[!UICONTROL Agentes]**.
1. Busque Adobe CX Enterprise Coworker.
1. Seleccione **[!UICONTROL Adobe CX Enterprise Coworker]** e introduzca un mensaje para comenzar.

Para obtener ideas, explore los [casos de uso clave](#key-use-cases) y [indicaciones de ejemplo](#example-prompts).

### [!DNL Amazon Quick] {#amazon-quick}

Use Colaborador para obtener información de marketing en [!DNL Amazon Quick].

Antes de comenzar, confirme que tiene acceso a [!DNL Amazon Quick] y a su cuenta de Adobe.

#### Conectar Compañero {#amazon-quick-connection}

Conectar a un compañero de trabajo en [!DNL Amazon Quick] mediante el protocolo de contexto de modelo (MCP). Adobe ya ha aprobado [!DNL Amazon Quick] para esta conexión.

1. En [!DNL Amazon Quick], vaya a **[!UICONTROL Conectores]**.
1. Busque MCP y abra la configuración del conector.
1. Escriba `https://mcp.coworker.experience.adobe.io` como URL del servidor MCP.

   Espere unos minutos para que se complete la conexión y regístrese.

1. Siga las indicaciones de configuración e inicie sesión con sus credenciales de Adobe.
1. Confirme que la conexión se ha realizado correctamente antes de empezar a hacer preguntas.

#### Acceder a Compañero {#amazon-quick-access}

Después de conectar a Coworker, utilícelo en [!DNL Amazon Quick] para hacer preguntas acerca de sus datos de Adobe.

Para obtener ideas, explore los [casos de uso clave](#key-use-cases) y [indicaciones de ejemplo](#example-prompts).

### [!DNL IBM watsonx Orchestrate] {#ibm-watsonx-orchestrate}

Use Colaborador para obtener información de marketing en [!DNL IBM watsonx Orchestrate].

Antes de comenzar, confirme que tiene acceso a [!DNL IBM watsonx Orchestrate] y a su cuenta de Adobe.

También necesita permiso para administrar conexiones, registrar servidores MCP y editar un agente. Confirme la configuración de cliente de OAuth con su representante de Adobe antes de configurarlo.

#### Cree su conexión de compañero de trabajo {#ibm-connection}

Conecte a un compañero mediante OAuth y, a continuación, autentique con su cuenta de Adobe. Los siguientes pasos preparan la conexión para probarla en el entorno de borrador.

1. En [!DNL IBM watsonx Orchestrate], vaya a **[!UICONTROL Conexiones]** y, a continuación, seleccione **[!UICONTROL Agregar conexión]**.
1. Escriba **[!UICONTROL ID de conexión]**, **[!UICONTROL nombre para mostrar]** y **[!UICONTROL descripción de conexión]** opcional y, a continuación, seleccione **[!UICONTROL Guardar y continuar]**.
1. En **[!UICONTROL Configurar el entorno de borrador]**, seleccione **[!UICONTROL Código de autorización de OAuth2]** como **[!UICONTROL Tipo de autenticación]**.
1. Introduzca la configuración de conexión.

   | Campo | Valor |
   | --- | --- |
   | [!UICONTROL URL del servidor] | `https://mcp.coworker.experience.adobe.io` |
   | [!UICONTROL URL de token] | Punto final de token confirmado para su cliente de OAuth. |
   | [!UICONTROL URL de autorización] | Punto final de autorización confirmado para su cliente OAuth. |
   | [!UICONTROL ID de cliente] | Su ID de cliente de OAuth aprobado. |
   | [!UICONTROL Secreto de cliente] | Secreto de cliente de OAuth aprobado. |

   ![Configuración de conexión de IBM watsonx Orchestrate con autenticación de código de autorización de OAuth2 y la dirección del servidor de Coworker.](./assets/ai-platforms/ibm/ibm-add-connection.png){width="700"}

1. Seleccione **[!UICONTROL PKCE]** y **[!UICONTROL Credenciales de miembro]**, y después seleccione **[!UICONTROL Siguiente]**.
1. Complete **[!UICONTROL Configurar el entorno en vivo]** y luego seleccione **[!UICONTROL Finalizar]** para guardar la conexión.

<!-- Confirm the customer process for obtaining OAuth settings before publication. -->

#### Iniciar sesión con Adobe {#ibm-sign-in}

Agregue sus credenciales de miembro para autenticar la conexión con su identidad de Adobe.

1. Vaya a **[!UICONTROL Configuración]** > **[!UICONTROL Credenciales de miembro]** y, a continuación, seleccione **[!UICONTROL Agregar credencial de miembro]**.
1. Seleccione su conexión de compañero y continúe con **[!UICONTROL Establecer credencial]**.
1. Seleccione **[!UICONTROL Conectar y guardar]** y luego inicie sesión con sus credenciales de Adobe cuando se le solicite.
1. Vuelva a [!DNL IBM watsonx Orchestrate] y confirme que su credencial se agregó correctamente.

#### Registrar el servidor MCP {#ibm-register-server}

Registre a un compañero a través del Protocolo de contexto de modelo (MCP) para importar sus herramientas en [!DNL IBM watsonx Orchestrate].

1. Vaya a **[!UICONTROL AI GATEWAY]** > **[!UICONTROL servidores MCP]** y, a continuación, seleccione **[!UICONTROL Registrar servidor]**.
1. Introduzca la configuración del servidor.

   | Campo | Valor |
   | --- | --- |
   | [!UICONTROL Nombre de servidor] | Un nombre descriptivo, como `cx-coworker`. |
   | [!UICONTROL Tipo de transporte] | [!UICONTROL HTTP transmisible] |
   | [!UICONTROL URL del servidor MCP] | `https://mcp.coworker.experience.adobe.io` |
   | [!UICONTROL Conexión] | La conexión de Compañero de trabajo que ha autenticado. |

1. Seleccione **[!UICONTROL Registrar]** y espere a que finalice el registro del servidor y la importación de la herramienta.

   ![IBM watsonx Orchestrate está registrando el servidor Coworker con transporte HTTP reproducible y la conexión autenticada.](./assets/ai-platforms/ibm/ibm-register-mcp.png){width="700"}

#### Agregar herramientas al agente {#ibm-agent-tools}

Añada las herramientas importadas al agente y pruebe la conexión antes de desplegar el agente.

1. Vaya a **[!UICONTROL Inventario activo]** > **[!UICONTROL Agentes]** y abra el agente que desea configurar.
1. En **[!UICONTROL Generar]**, seleccione **[!UICONTROL Herramientas]** y, a continuación, **[!UICONTROL Agregar herramienta]**.
1. Seleccione **[!UICONTROL servidor MCP]** y busque las herramientas de su servidor Coworker registrado.
1. Seleccione las herramientas de Coworker que necesita y luego seleccione **[!UICONTROL Agregar al agente]**.
1. Escriba un mensaje en **[!UICONTROL Vista previa de borrador]** y revise la respuesta para confirmar que la conexión funciona.

Para obtener ideas, explore los [casos de uso clave](#key-use-cases) y [indicaciones de ejemplo](#example-prompts).

### [!DNL Databricks] {#databricks}

Use Colaborador para obtener información de marketing en [!DNL Databricks Genie One].

Antes de comenzar, confirme que tiene acceso a [!DNL Databricks Genie One] y a su cuenta de Adobe. También necesita permiso para instalar un servicio MCP en el catálogo y esquema [!DNL Unity Catalog] que haya elegido.

Confirme la configuración de cliente de OAuth con su representante de Adobe antes de configurarlo.

#### Instalar compañero {#databricks-install}

Instale el servicio MCP de Coworker desde [!DNL Databricks Marketplace].

1. En [!DNL Databricks], vaya a **[!UICONTROL Marketplace]** y busque Adobe Coworker.
1. Seleccione **[!UICONTROL Adobe CX Enterprise Coworker]** y, a continuación, seleccione **[!UICONTROL Instalar]**.
1. Seleccione un **[!UICONTROL catálogo]** y un **[!UICONTROL esquema]** y, a continuación, escriba un **[!UICONTROL nombre de servicio MCP]**.
1. Mantenga la configuración de conexión proporcionada por la lista, incluidos los siguientes valores.

   | Campo | Valor |
   | --- | --- |
   | [!UICONTROL Host] | `https://mcp.coworker.experience.adobe.io` |
   | [!UICONTROL Ruta básica] | `/mcp` |
   | [!UICONTROL Tipo de credencial] | [!UICONTROL OAuth U2M] |

   ![Cuadro de diálogo de instalación de Databricks Marketplace para Adobe CX Enterprise Coworker con campos de catálogo, esquema, conexión y credenciales.](./assets/ai-platforms/databricks/databricks-install.png){width="700"}

1. Escriba su **[!UICONTROL ID de cliente]** y **[!UICONTROL secreto de cliente]**.
1. Revise y acepte los términos y, a continuación, seleccione **[!UICONTROL Instalar]**.

<!-- Confirm the customer process for obtaining OAuth settings before publication. -->

#### Conecte su cuenta de Adobe {#databricks-adobe-connection}

Cada usuario inicia sesión con su cuenta de Adobe. Las solicitudes de compañeros de trabajo utilizan los permisos de Adobe de ese usuario.

1. En **[!UICONTROL Catálogo]**, abra el servicio Compañero de trabajo instalado en el catálogo y esquema seleccionados.
1. Complete el inicio de sesión en Adobe cuando se le solicite.
1. Confirme que el servicio **[!UICONTROL Status]** está **[!UICONTROL Activo]** y que sus herramientas están en la lista.
1. En **[!UICONTROL Comenzar]**, selecciona **[!UICONTROL Genie]**, luego **[!UICONTROL Genie One]** y selecciona **[!UICONTROL Agregar a Genie One]**.

#### Acceder a Compañero {#databricks-access}

Confirme que el conector está disponible antes de hacer preguntas en [!DNL Genie One].

1. En [!DNL Genie One], vaya a **[!UICONTROL Personalizaciones]** > **[!UICONTROL Conectores]** y abra el conector de Compañero de trabajo.
1. Confirme que el conector muestra **[!UICONTROL Conectado]**. Revise la configuración de aprobación de la herramienta según las políticas de su organización.

   ![Conector Coworker en Databricks Genie One que muestra el estado Conectado, las herramientas disponibles y la configuración de aprobación de herramientas.](./assets/ai-platforms/databricks/databricks-connectors.png){width="700"}

1. Seleccione **[!UICONTROL Nuevo chat]** e introduzca un mensaje, como &quot;Usando Adobe Coworker, enumere las audiencias publicadas&quot;.

Para obtener ideas, explore los [casos de uso clave](#key-use-cases) y [indicaciones de ejemplo](#example-prompts).

<!-- Setup steps for Microsoft 365 Copilot, ChatGPT, and Claude reflect the real customer-facing flow confirmed by PM (Siddhartha Srivastava) on 2026-09-02: an org admin approves the connector or plugin, then end users find and add it in their platform's catalog and sign in. The previous version of this file described a manual MCP-connector setup for ChatGPT (Settings > Connectors > paste server URL) -- PM clarified that flow is for internal testing only, not the customer path, so it was removed here. -->

<!-- Amazon Quick setup follows PM guidance from the October 28, 2026 email, "Coworker in AI Platforms screenshots - Gemini / Amazon Quick." End users connect through MCP and sign in with Adobe credentials. -->

## Ejemplos de peticiones {#example-prompts}

Después de configurar Coworker en una plataforma compatible, intente estas indicaciones o escriba las suyas propias en lenguaje natural.

* Muestre sus cinco audiencias principales.
* Mostrar una métrica del último mes.
* Muestre sus proyectos activos de Workfront.
* Mostrar recorridos con audiencias de fidelización.

## Limitaciones conocidas {#known-limitations}

El colaborador en plataformas de IA no admite todas las funciones disponibles en la interfaz del colaborador.

* No puede conectar a un compañero a un mazo agéntico personalizado fuera de las plataformas de IA admitidas que se enumeran en este documento. Para solicitar soporte para plataformas de IA adicionales o mazos agénticos a través de MCP, póngase en contacto con su representante de Adobe.
* La aptitud para la generación de imágenes de Firefly no está disponible cuando se accede a Colaborador a través de Claude. La aptitud permanece disponible en la interfaz de Coworker y en otras plataformas de IA admitidas descritas en este documento. Para utilizar la aptitud de Firefly Image Generation, acceda a Coworker a través de la interfaz de Coworker u otra plataforma de IA compatible.

## Solución de problemas de compañeros en plataformas de IA {#troubleshoot}

Pruebe estos pasos si encuentra problemas con Coworker en una plataforma de IA.

* Si ve un error, cierre la sesión y vuelva a iniciarla con sus credenciales de Adobe. La reautenticación resuelve la mayoría de los problemas.
* Si no puede acceder a Compañero de trabajo o a datos específicos, póngase en contacto con el administrador de Adobe para confirmar el acceso y los permisos del producto.

<!--
Editorial maintenance, 2026-10-27:
Only approved platforms with validated setup guidance belong in the platform sections.
Databricks setup follows the supplied "Adobe Coworker in Genie One.mp4" walkthrough. Confirm marketplace availability and customer OAuth provisioning before publication.

To add an approved platform:
* Confirm approval and obtain access to the customer flow.
* Validate prerequisites, organization approval, catalog discovery, listing name, installation, and Adobe sign-in.
* Confirm the shared licensing, permissions, use cases, prompts, limitations, and troubleshooting guidance applies.
* Add an H3 platform section with an explicit anchor under Set up Coworker and add it to the linked platform list.
* Follow the existing order: introduction, platform prerequisites, setup tasks, and user access. Use H4 task headings with unique anchors.
* Document any platform-specific requirements or exceptions within that section.
* Preview the section and verify its links and image references.
Keep the article introduction, metadata, and shared prerequisites free of platform lists so adding a section does not require duplicate updates.

Gemini Enterprise follow-up:
Administrator setup and end user access steps are documented. Confirm applicability of the shared guidance before expanding the section.
-->
