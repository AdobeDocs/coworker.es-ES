---
title: Conector externo Jira / Atlassian Rovo
description: Aprenda a configurar el conector externo Jira / Atlassian Rovo en CX Enterprise Coworker e inicie sesión con Atlassian para leer y buscar elementos de trabajo de Jira.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 92e7715a5eb7ab4f8feb7348384c94fabc1b78cf
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%
---

# Conector externo Jira / Atlassian Rovo {#jira-atlassian-rovo}

Utilice el conector externo [!DNL Jira] / [!DNL Atlassian Rovo] para leer y buscar los elementos de trabajo [!DNL Jira] en Adobe CX Enterprise Coworker. Después de configurar el conector, pida a sus compañeros que busquen elementos de trabajo, lean sus detalles y busquen con el lenguaje de consulta Jira (JQL). El conector es un servidor de Protocolo de contexto de modelo (MCP) alojado por [!DNL Atlassian].

>[!AVAILABILITY]
>
>El conector externo [!DNL Jira] / [!DNL Atlassian Rovo] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene tres partes independientes:

* **[!DNL Atlassian]preparación:** Un administrador de organización de [!DNL Atlassian] permite al dominio de URL de redireccionamiento de Coworker y revisa las directivas de acceso de MCP.
* **Configuración de la organización:** Un administrador de Coworker configura el conector una vez para toda la organización. El administrador elige las herramientas de sólo lectura que pueden utilizar los miembros.
* **Inicio de sesión de miembro:** Cada miembro inicia sesión con su propia cuenta de [!DNL Atlassian]. Los miembros solo pueden obtener acceso a los datos de [!DNL Jira] para los que su cuenta tiene permiso de visualización.

Al guardar la configuración de la organización, no se inicia sesión en ningún miembro ni se conceden permisos de [!DNL Jira]. Cada miembro debe iniciar sesión por separado.

El conector no tiene una cuenta de servicio compartida ni una opción de token de API. El colaborador registra la aplicación OAuth con [!DNL Atlassian] automáticamente, por lo que no se introduce un ID de cliente ni un secreto de cliente.

Aunque el nombre del conector incluye [!DNL Atlassian Rovo], el conector solicita [!DNL Jira] solo acceso de lectura y búsqueda. No solicita acceso destructivo, de escritura o específico de [!DNL Confluence], [!DNL Rovo]. Otras capacidades de MCP [!DNL Atlassian] no están necesariamente disponibles a través de este conector.

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Para la configuración de la organización:** Cuenta con permiso para administrar conectores de organización en Coworker, en una organización donde el conector [!DNL Jira] / [!DNL Atlassian Rovo] está disponible.
* **Para la preparación de [!DNL Atlassian]:** Un administrador de organización de [!DNL Atlassian] que puede aprobar el acceso a MCP y el dominio de redirección de URL de Coworker.
* **Para el inicio de sesión de miembros:** [!DNL Atlassian] cuentas con acceso a los [!DNL Jira] sitios, proyectos y elementos de trabajo deseados.
* **Para acceso a la red:** [!DNL Atlassian] listas de permitidos IP y directivas de aplicación que permiten la conexión. Un inicio de sesión correcto no confirma que se permitan las solicitudes de herramientas.
* **[!DNL Rovo]habilitado:** [!DNL Rovo] habilitado para su organización [!DNL Atlassian] y los sitios [!DNL Jira] deseados antes de que los miembros usen el conector. Para obtener más información, consulte [Cómo habilitar Rovo](https://www.atlassian.com/software/rovo/guides/admin-guide/rovo-activation) en la documentación de [!DNL Atlassian].

## Preparar acceso de [!DNL Atlassian] {#prepare-atlassian}

Antes de que los miembros inicien sesión, un administrador de organización de [!DNL Atlassian] prepara el acceso en [!DNL Atlassian Administration]:

1. Abra [!DNL Atlassian Administration] y seleccione la organización deseada.

1. Seleccione **[!UICONTROL Conectores]** > **[!UICONTROL Servidor MCP de Atlassian]** > **[!UICONTROL Agregar dominio]**.

1. Agregue el dominio de la **[!UICONTROL URL de redireccionamiento]** que se muestra en el cuadro de diálogo de configuración de Coworker. Para ver el cuadro de diálogo, consulte [Configurar el conector para su organización](#configure-organization).

   Siga las reglas de formato de dominio [!DNL Atlassian] en lugar de pegar la dirección URL completa. Para obtener más información, consulte [Dominios de servidor MCP de Atlassian disponibles](https://support.atlassian.com/security-and-access-policies/docs/available-atlassian-mcp-server-domains/) en la documentación de [!DNL Atlassian].

1. Revise los grupos de permisos MCP, las directivas de aplicación y las listas de permitidos IP con el administrador [!DNL Atlassian]. Para obtener más información, consulte la siguiente documentación de [!DNL Atlassian]:

   * [Herramientas MCP de Atlassian compatibles](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/), para los grupos de permisos y ámbitos que requiere cada herramienta
   * [Controlar la configuración del servidor MCP de Atlassian](https://support.atlassian.com/security-and-access-policies/docs/control-atlassian-mcp-server-settings/) para la autenticación y la inclusión en la lista de permitidos de IP

Utilice siempre la URL de redireccionamiento que se muestra en el cuadro de diálogo Compañero de trabajo para el entorno que está configurando. No copie una URL de redireccionamiento de otro entorno.

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL Jira] / [!DNL Atlassian Rovo] a disposición de todos los miembros de la organización. Los cambios en la página de organización se aplican a todos los usuarios de la organización.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Jira / Atlassian Rovo]**, seleccione **[!UICONTROL Configurar]**. Los miembros no pueden configurar ni quitar esta conexión.

1. En el cuadro de diálogo **[!UICONTROL Conectar Jira / Atlassian Rovo]**, revise la **[!UICONTROL URL del servidor]**, `https://mcp.atlassian.com/v2/mcp`, corregida.

   Revise la **[!UICONTROL URL de redireccionamiento]** y asegúrese de que un administrador de [!DNL Atlassian] apruebe su dominio, tal como se describe en [Preparar acceso de Atlassian](#prepare-atlassian). No introduzca ninguna credencial de OAuth.

1. En **[!UICONTROL Herramientas disponibles para los usuarios]**, elija las herramientas que pueden utilizar los miembros. Para obtener más información, consulte [Herramientas disponibles](#available-tools).

   La herramienta de detección de sitios `getAccessibleAtlassianResources` es necesaria y permanece habilitada. Las otras cinco herramientas son opcionales. Para bloquear una herramienta opcional para todos los miembros de su organización, elimínela. Para recuperar las herramientas que quitó, seleccione **[!UICONTROL Restaurar todas las herramientas]**. Puede guardar la configuración con sólo la detección de sitios habilitada, pero los integrantes no podrán leer ni buscar elementos de trabajo.

   ![Conecte el cuadro de diálogo Jira / Atlassian Rovo que muestra la URL del servidor, una URL de redireccionamiento censurada y seis herramientas disponibles para los usuarios, con la herramienta getAccessibleAtlassianResources necesaria y cinco herramientas opcionales.](./assets/jira-atlassian-rovo/org-configure.png){width="500" zoomable="yes"}

1. Seleccione **[!UICONTROL Guardar conexión]** y revise los detalles de la conexión.

   El conector solicita los siguientes ámbitos de OAuth cuando cada miembro inicia sesión:

   | Ámbito | Objetivo |
   | --- | --- |
   | `read:me`, `read:account` | Autorización de soporte técnico con la cuenta [!DNL Atlassian] del miembro. |
   | `read:jira:agent-interface` | Leer datos de [!DNL Jira]. |
   | `search:jira:agent-interface` | Buscar datos de [!DNL Jira]. |
   | `offline_access` | Actualice el token de inicio de sesión. |

   El tiempo de espera de la herramienta es de 60 segundos. La primera conexión y la detección de herramientas pueden tardar más.

### Herramientas disponibles {#available-tools}

El conector [!DNL Jira] / [!DNL Atlassian Rovo] proporciona las siguientes herramientas de solo lectura:

| Herramienta | Descripción | Control de administrador |
| --- | --- | --- |
| `getAccessibleAtlassianResources` | Busque los [!DNL Atlassian] sitios e ID de nube a los que puede acceder. Las herramientas de [!DNL Jira] necesitan esta herramienta. | Requerido |
| `atlassianUserInfo` | Obtenga la información de cuenta del usuario que ha iniciado sesión. | Opcional |
| `getJiraIssue` | Obtener un elemento de trabajo [!DNL Jira] por identificador o clave. | Opcional |
| `searchJiraIssuesUsingJql` | Buscar [!DNL Jira] elementos de trabajo con JQL. | Opcional |
| `discover` | Busque operaciones de herramienta adicionales y sus esquemas de entrada. | Opcional |
| `executeRead` | Ejecute las operaciones de lectura que se encuentran a través de `discover`, como la lectura de comentarios, registros de cambios, proyectos, tableros y sprints. | Opcional |

>[!IMPORTANT]
>
>Las herramientas `discover` y `executeRead` proporcionan a los miembros acceso a operaciones de lectura permitidas adicionales como grupo. No puede desactivar operaciones individuales. Si su organización no acepta este acceso, elimine ambas herramientas. El conector no incluye operaciones de escritura (`executeWrite`) u operaciones destructivas (`executeDestructive`).

La eliminación de herramientas opcionales limita su disponibilidad en Coworker. No reduce los ámbitos de OAuth que el conector solicita al iniciar sesión.

Cada herramienta necesita [!DNL Atlassian] grupos y ámbitos de permisos específicos. Para obtener más información, consulte [Herramientas MCP de Atlassian compatibles](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/) en la documentación de [!DNL Atlassian].

## Iniciar sesión como miembro {#sign-in-as-a-member}

Cuando un administrador configura el conector, cada miembro inicia sesión con su propia cuenta de [!DNL Atlassian]. No necesita un ID de cliente, un secreto de cliente o un token de acceso para iniciar sesión.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Usuario]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**.

1. Encuentra la tarjeta **[!UICONTROL Jira / Atlassian Rovo]**. Si la tarjeta muestra **[!UICONTROL No configurado]** y **[!UICONTROL Aún no está disponible. El administrador debe configurar esto.]**, pídale al administrador que [configure el conector](#configure-organization). Los miembros no pueden configurar el conector.

1. Seleccione **[!UICONTROL Iniciar sesión]** y use la cuenta de [!DNL Atlassian] que tiene acceso al sitio [!DNL Jira] al que va dirigido. Complete cualquier inicio de sesión único (SSO), autenticación multifactor (MFA) y mensajes de consentimiento necesarios. Revise el acceso de lectura y búsqueda solicitado antes de dar su consentimiento.

   >[!IMPORTANT]
   >
   >Continúe solo si reconoce la aplicación y si su organización aprueba el acceso solicitado.

1. Vuelva a Compañero de trabajo y abra los detalles del conector. La conexión es de sólo lectura para los miembros y puede ver las herramientas habilitadas por el administrador. Seleccione **[!UICONTROL Probar conexión]** para confirmar la conexión.

1. De manera opcional, ejecute una pequeña comprobación de solo lectura, tal como se describe en [Compruebe su acceso a Jira](#check-access).

Una prueba que se realice correctamente no confirma que se puede obtener acceso a cada sitio, proyecto o elemento de trabajo de [!DNL Jira].

## Compruebe su acceso de [!DNL Jira] {#check-access}

Para confirmar que el conector puede leer los datos, inicie una conversación e introduzca un mensaje de solo lectura.

Mensaje de ejemplo:

* &quot;Busca en Jira hasta cinco elementos de trabajo asignados a mí, ordenados según la última actualización. Incluya sus claves y vínculos. No modifique nada&quot;.

Para que esta solicitud funcione, el administrador debe habilitar una herramienta de búsqueda y la cuenta de [!DNL Jira] debe tener permiso para ver los elementos de trabajo.

## Solucionar problemas de acceso {#troubleshoot-access}

Si falla el inicio de sesión o el acceso, consulte lo siguiente con su administrador:

| Problema | Qué comprobar |
| --- | --- |
| El inicio de sesión está bloqueado para el cliente o dominio | Confirme que el dominio de URL de redireccionamiento de su entorno se aprobó en [!DNL Atlassian Administration], en la configuración de **[!UICONTROL servidor MCP de Atlassian]**. |
| El consentimiento se realiza correctamente, pero se deniegan las llamadas a la herramienta | Compruebe sus permisos de [!DNL Jira], los grupos de permisos de MCP [!DNL Atlassian], las directivas de aplicación y las listas de permitidos de IP. Para ver los grupos de permisos que requiere cada herramienta, consulte [Herramientas MCP de Atlassian compatibles](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/). |
| La búsqueda de JQL falla, pero otras lecturas funcionan | Confirme que el administrador habilitó `searchJiraIssuesUsingJql` y que la conexión solicita el ámbito `search:jira:agent-interface`. |
| El consentimiento devuelve `invalid_request` | Pida al administrador que confirme que la conexión solicita `read:me` y `read:account` además de los ámbitos de [!DNL Jira]. |
| Después de un cambio, aún se ven ámbitos más antiguos | Una invalidación de proveedor de autenticación `jira_login` de nivel de usuario obsoleta puede tener prioridad sobre la conexión de la organización. Pida a un administrador que actualice o elimine únicamente esa anulación obsoleta y vuelva a iniciar sesión. |
| Falta una herramienta | Solicite al administrador que compruebe la selección de la herramienta. Las operaciones de lectura adicionales necesitan `discover` y `executeRead`, los ámbitos necesarios y los permisos adecuados. |
| **[!UICONTROL Comprobar conexión]** es lenta o se agota el tiempo de espera | La detección de herramientas puede tardar más tiempo que el tiempo de espera de la herramienta de 60 segundos. Compruebe si el problema es una detección lenta o un error de inicio de sesión antes de cambiar las credenciales. |

Cuando pida ayuda, no comparta contraseñas, tokens, códigos de autorización ni direcciones URL de consentimiento. No los incluya en capturas de pantalla ni en tickets de asistencia.
