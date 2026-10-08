---
title: Acceder a las herramientas de CX Coworker Gateway
description: Confirme la disponibilidad del producto, la habilitación de la organización y los permisos antes de utilizar las herramientas de Adobe CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 4%
---
# Acceder a las herramientas de CX Coworker Gateway {#mcp-access}

Adobe CX Enterprise expone las herramientas de producto a través de un único MCP. El acceso se evalúa mediante herramientas de producto: la organización de Adobe debe estar habilitada para las herramientas de producto relevantes y la cuenta de usuario debe tener los permisos de producto necesarios para ver o cambiar los datos de producto que exponen esas herramientas.

>[!IMPORTANT]
>
>Debe habilitarse la organización de Adobe para poder usar las herramientas de puerta de enlace de CX Coworker. Si su organización aún no tiene acceso, póngase en contacto con el equipo de cuenta de Adobe para solicitar la habilitación de su organización.

## Requisitos de acceso {#mcp-requirements}


| Herramientas de producto | Disponibilidad | Requisitos de acceso |
| --- | --- | --- |
| Real-Time CDP | Beta | Licencia de Real-Time CDP activa, habilitación de Beta para su organización de Adobe y permisos para ver las audiencias, los destinos, los orígenes, la identidad y los recursos de activación que consulta. |
| Experience Platform | Beta | Licencia de Experience Platform activa, habilitación de Beta para su organización de Adobe y permisos para ver los esquemas, conjuntos de datos, gobernanza, servicio de consultas, auditoría y recursos de zona protegida que consulta. |
| Journey Optimizer | Beta | Licencia de Journey Optimizer activa, habilitación de Beta para su organización de Adobe y permisos para ver campañas, recorridos y configuraciones de canal. |
| Customer Journey Analytics | Disponible | Licencia de Customer Journey Analytics activa y un perfil de producto que incluye el elemento de permiso **Acceso a MCP** en Adobe Admin Console. Los permisos del producto siguen controlando a qué vistas de datos, componentes, informes, proyectos y audiencias puede acceder o modificar. |
| Adobe Analytics | Disponible | Licencia de Adobe Analytics activa y un perfil de producto que incluye el elemento de permiso **Acceso a MCP** en Adobe Admin Console. Los permisos de producto siguen controlando a qué grupos de informes, componentes, informes, segmentos, intervalos de fechas y proyectos puede acceder o modificar. |
| Workfront | Vista previa | Licencia de Workfront activa y habilitación de MCP de Workfront. Consulte la [documentación de MCP de Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview). |
| Target | Beta | Licencia de Target activa con una organización de Adobe Experience Platform. Consulte la [documentación de MCP de Target](https://experienceleague.adobe.com/en/docs/target/using/mcp/target-mcp-get-started). |



>[!NOTE]
>
>El MCP solo muestra las herramientas que su organización y sus credenciales pueden utilizar. Si falta una herramienta de producto tras iniciar sesión, confirme las licencias de productos, la habilitación de la organización y los permisos de usuario.

## Solicitar acceso {#mcp-request}

Para herramientas de producto de Beta o de versión limitada, póngase en contacto con el representante de su cuenta de Adobe y especifique qué herramientas de producto de Adobe para CX Coworker Gateway desea utilizar. Su representante puede coordinar la activación del producto y confirmar cuando su organización de Adobe esté lista.

Para las herramientas de producto disponibles de forma general que utilizan el elemento de permiso **Acceso a MCP**, pídale a un administrador de sistema o de producto que agregue su cuenta a un perfil de producto que incluya acceso a MCP.

## Habilitación en el producto {#mcp-product-enablement}

Algunos productos requieren la habilitación del producto o permisos específicos del producto, además del acceso a MCP. Por ejemplo:

- Adobe Analytics y Customer Journey Analytics requieren el elemento de permiso **Acceso a MCP** en Adobe Admin Console.
- Las herramientas de MCP de Workfront están habilitadas desde la configuración de Workfront.
- Las herramientas de producto de Beta requieren la habilitación de la organización de Adobe para que sus herramientas aparezcan a través del MCP.

Consulte la página del producto de la herramienta que planea utilizar para obtener permisos, requisitos de contexto y limitaciones específicos del producto.

## Antes de realizar la instalación {#mcp-prerequisites}

Antes de conectar su cliente MCP, confirme lo siguiente:

- Su organización de Adobe está habilitada para las herramientas de producto que necesita.
- Su cuenta de usuario tiene los permisos de producto necesarios para los datos y las operaciones que planea utilizar.
- Tiene acceso a un cliente MCP admitido como [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] o [!DNL VS Code].
- Para la instalación empresarial, usted o un compañero pueden administrar conectores o aplicaciones personalizadas en la configuración de organización del cliente de MCP.

Siguiente: [Instalar Adobe CX Coworker Gateway](install.md).