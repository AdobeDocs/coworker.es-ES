---
title: Conector externo de Slack
description: Aprenda a configurar el conector externo de Slack en CX Enterprise Coworker con su propia aplicación de Slack e inicie sesión para usar las conversaciones de Slack en el chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 877954880bf6fda5151dcb343af92888db21cef4
workflow-type: tm+mt
source-wordcount: '2268'
ht-degree: 0%
---

# Conector externo de Slack {#slack}

Use el conector externo [!DNL Slack] para trabajar con las conversaciones de [!DNL Slack] en Adobe CX Enterprise Coworker. Después de configurar el conector, pídale a su compañero que busque mensajes y archivos, lea canales e hilos y busque personas. También puede enviar mensajes y respuestas si el administrador activa estas herramientas. El conector usa el servidor MCP (Protocolo de contexto de modelo remoto) oficial hospedado por [!DNL Slack].

>[!AVAILABILITY]
>
>El conector externo [!DNL Slack] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene tres partes independientes:

* **[!DNL Slack]preparación de la aplicación:** El propietario de una aplicación de [!DNL Slack] prepara una aplicación elegible, registra la URL de redireccionamiento de compañeros y establece los ámbitos del usuario. Adobe no proporciona una aplicación [!DNL Slack] administrada.
* **Configuración de la organización:** Un administrador de Coworker configura el conector una vez para toda la organización. El administrador introduce las credenciales de la aplicación y elige los ámbitos de OAuth del usuario y las herramientas que los miembros pueden utilizar.
* **Inicio de sesión de miembro:** Cada miembro inicia sesión con su propia cuenta de [!DNL Slack]. Los miembros solo pueden tener acceso al contenido al que puede tener acceso su cuenta de [!DNL Slack].

El conector no utiliza un bot compartido ni una identidad [!DNL Slack] compartida. El compañero envía mensajes y respuestas como el miembro que ha iniciado sesión. Al guardar la configuración de la organización, no se inicia sesión en ningún miembro ni se concede acceso adicional a [!DNL Slack]. Cada miembro debe iniciar sesión por separado.

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Acceso de compañero:** Cuenta con permiso para administrar conectores de organización en una organización donde el conector [!DNL Slack] está disponible.
* **Aplicación [!DNL Slack]:** Aplicación interna o aplicación [!DNL Slack Marketplace] aprobada para el área de trabajo. También necesita un propietario de la aplicación que pueda confirmar los ámbitos del usuario aprobado y editar la configuración de la aplicación.
* **Credenciales de la aplicación:** El ID de cliente y el secreto de cliente de la aplicación, compartidos a través del proceso aprobado para administrar credenciales.
* **Herramienta y decisión de ámbito:** Las herramientas de lectura, mensajería y borrador que su organización planea habilitar, y los ámbitos de OAuth que el usuario planea solicitar.
* **Un área de trabajo o canal de prueba:** Un lugar para comprobar la conexión con los miembros que acepten probarla. No envíe mensajes de prueba en canales de cliente o de producción.

>[!IMPORTANT]
>
>Nunca comparta secretos de clientes, tokens de acceso u otras credenciales en capturas de pantalla, chats ni tickets de asistencia. Introduzca las credenciales solo en los campos seguros del cuadro de diálogo de configuración.

## Prepare su aplicación de Slack {#prepare-slack-app}

Antes de configurar el conector en Coworker, el propietario de la aplicación prepara la aplicación [!DNL Slack]. Es posible que un administrador de aplicaciones de espacio de trabajo u organización también tenga que aprobarla. Para los requisitos de [!DNL Slack], consulte [Slack MCP server](https://docs.slack.dev/ai/slack-mcp-server/) en la documentación para desarrolladores de [!DNL Slack].

### Elija una aplicación apta {#choose-eligible-app}

[!DNL Slack] solo admite su servidor MCP para aplicaciones personalizadas internas y aplicaciones publicadas en [!DNL Slack Marketplace]. Las aplicaciones no incluidas en la lista que se distribuyen fuera de su organización no pueden utilizar el servidor MCP [!DNL Slack]. Activar la distribución pública por sí solo no hace que una aplicación sea elegible.

1. Elija el espacio de trabajo u organización que posee la aplicación y el propietario de la aplicación.
1. En [Administración de aplicaciones de Slack](https://api.slack.com/apps), cree una nueva aplicación en ese espacio de trabajo. Para reutilizar una aplicación apta existente, obtenga primero la aprobación de su propietario.
1. En la configuración de la aplicación, seleccione **[!UICONTROL Información básica]** > **[!UICONTROL Credenciales de la aplicación]**. Observe **[!UICONTROL ID de cliente]** y **[!UICONTROL Secreto de cliente]**.

   Introduzca solo estos dos valores en Compañero de trabajo. No utilice el ID de la aplicación, el secreto de firma, un token de bot ni un token de nivel de aplicación.

### Registrar la URL de redireccionamiento {#register-redirect-url}

Registre la URL de redireccionamiento de compañeros en la aplicación [!DNL Slack]:

1. En Colaborador, abre el cuadro de diálogo **[!UICONTROL Conectar Slack]**, tal como se describe en [Configurar el conector para tu organización](#configure-organization). Copie el valor completo de **[!UICONTROL Redirect URL]**.

   Puede abrir el cuadro de diálogo para copiar la URL antes de completar o guardar la configuración.

1. En la configuración de la aplicación [!DNL Slack], seleccione **[!UICONTROL OAuth y permisos]**. En **[!UICONTROL URL de redireccionamiento]**, agregue la URL de redireccionamiento completa y, a continuación, guarde.

Copie siempre la dirección URL de redireccionamiento del cuadro de diálogo Compañero de trabajo en el entorno que está configurando. Registre el esquema, el nombre de host, el puerto, si hay uno presente, y la ruta exactos. No cree la URL usted mismo ni reutilice una URL de redireccionamiento desde otro entorno. Si utiliza más de un entorno, registre cada URL de redireccionamiento por separado.

### Establecer los ámbitos del usuario {#set-user-scopes}

El conector utiliza ámbitos OAuth del usuario, que autorizan la cuenta de cada miembro. No utiliza ámbitos de bots.

1. En la configuración de la aplicación [!DNL Slack], seleccione **[!UICONTROL OAuth y permisos]** > **[!UICONTROL Ámbitos]** > **[!UICONTROL Ámbitos de token de usuario]**.
1. Agregue los ámbitos de usuario que apruebe su organización. Compárelos con los [ámbitos predeterminados](#review-scopes) en Coworker y agregue solamente los ámbitos que planea solicitar.

   Los ámbitos predeterminados son el conjunto de capacidades predeterminado de Coworker, no un mínimo que requiere [!DNL Slack]. Use los ámbitos granulares `search:read.*`, no el ámbito `search:read` más antiguo. En un manifiesto de aplicación, los ámbitos de usuario pertenecen a `oauth_config.scopes.user`, no a `oauth_config.scopes.bot`.

El ámbito de usuario `chat:write` permite que el colaborador envíe mensajes como el miembro que ha iniciado sesión. Si su organización no planea enviar mensajes, déjela fuera.

Es posible que el área de trabajo o la organización empresarial [!DNL Slack] necesiten la aprobación de la aplicación y la revisión del ámbito. La aprobación de la aplicación no reemplaza el consentimiento de cada miembro. Una directiva que permite solamente [!DNL Slack Marketplace] aplicaciones puede bloquear una aplicación interna. Para obtener más información, consulte [Administrar la aprobación de la aplicación en el espacio de trabajo](https://slack.com/help/articles/222386767-Manage-app-approval-for-your-workspace).

Si su aplicación usa restricciones de direcciones IP permitidas, [!DNL Slack] también las aplica a solicitudes de MCP. Póngase en contacto con su representante de Adobe para confirmar las direcciones que desea permitir. No adivine los intervalos de direcciones IP. Algunas funcionalidades, como la búsqueda semántica, pueden depender del plan [!DNL Slack].

### Revisar configuración irreversible de la aplicación {#review-irreversible-settings}

El compañero se conecta como cliente OAuth confidencial con el ID de cliente y el secreto de cliente. No se puede revertir alguna configuración de la aplicación [!DNL Slack], así que revise lo siguiente antes de cambiarla:

* **Clave de revisión para intercambio de código (PKCE):** No active la configuración PKCE [!DNL Slack] para este conector sin confirmación. [!DNL Slack] documenta que esta configuración cambia la aplicación a un cliente público y solamente la compatibilidad con [!DNL Slack] puede revertirla. Para obtener más información, vea [Utilizar PKCE](https://docs.slack.dev/authentication/using-pkce/).
* **Rotación de tokens:** La rotación de tokens de [!DNL Slack] no se puede desactivar después de activarla. Póngase en contacto con su representante de Adobe antes de activarlo para esta aplicación. Para obtener más información, vea [Usar la rotación de tokens](https://docs.slack.dev/authentication/using-token-rotation/).

### Funciones de bots no requeridas {#bot-features-not-required}

El conector no necesita funciones de bots. No necesita ámbitos de token de bots, una dirección URL de solicitud [!DNL Events API], una dirección URL de solicitud de interactividad, webhooks entrantes, comandos de barra diagonal, [!DNL Socket Mode] ni tokens de nivel de aplicación. Si una aplicación existente utiliza estas funciones para otro fin, manténgalas.

El servidor MCP [!DNL Slack] no admite el registro dinámico de clientes ni eventos enviados por el servidor (SSE). El compañero utiliza su aplicación registrada y el transporte HTTP Streamable.

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL Slack] a disposición de todos los miembros de la organización. Los cambios en la página de organización se aplican a todos los usuarios de la organización. Complete [Preparar su aplicación de Slack](#prepare-slack-app) antes de que los miembros inicien sesión.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Slack]**, seleccione **[!UICONTROL Configurar]**.

   Se abre el cuadro de diálogo **[!UICONTROL Conectar Slack]**. El conector usa la URL fija del servidor MCP [!DNL Slack], `https://mcp.slack.com/mcp`. Utilice el ámbito de organización para esta configuración, no una conexión personal.

1. Asegúrese de que la **[!UICONTROL URL de redireccionamiento]** en la **[!UICONTROL aplicación Slack]** esté registrada en su aplicación, tal como se describe en [Registrar la URL de redireccionamiento](#register-redirect-url). A continuación, ingrese **[!UICONTROL ID de cliente]** y **[!UICONTROL secreto de cliente]** de su aplicación. Ambos campos son obligatorios.

   No introduzca el ID de aplicación, el secreto de firma ni un token de bot. El compañero almacena las credenciales como secretos, no como configuración de conector de texto sin formato.

   ![Conecte el cuadro de diálogo de Slack que muestra la sección de la aplicación de Slack con una URL de redireccionamiento censurada, campos vacíos de ID de cliente y secreto de cliente, los ámbitos predeterminados de OAuth de usuario y las primeras herramientas disponibles para los usuarios.](./assets/slack/org-configure.png){width="500" zoomable="yes"}

1. Revise los **[!UICONTROL ámbitos de OAuth del usuario]**. Para obtener más información, vea [Revisar los ámbitos de OAuth del usuario](#review-scopes).

1. En **[!UICONTROL Herramientas disponibles para los usuarios]**, quite las herramientas que los miembros no deben usar. Debe quedar al menos una herramienta. Para obtener más información, consulte [Herramientas disponibles](#available-tools).

1. Revise **[!UICONTROL Acceso y permisos]** y, a continuación, seleccione **[!UICONTROL Guardar conexión]**. La tarjeta **[!UICONTROL Slack]** muestra **[!UICONTROL Configuración guardada]**.

   El cuadro de diálogo también muestra el método **[!UICONTROL Authentication]**, el tipo **[!UICONTROL Connection]** y el tiempo de espera de **[!UICONTROL Tool]**. El compañero no guarda la configuración cuando un campo de credenciales o la lista de ámbitos están vacíos.

   Vuelva a cargar la página, seleccione **[!UICONTROL Ver configuración]** y confirme que la configuración y la selección de la herramienta se hayan guardado antes de que los miembros inicien sesión.

   ![Cuadro de diálogo Conectar Slack que muestra los ámbitos de OAuth del usuario, las 16 herramientas disponibles para los usuarios, el aviso de acceso y permisos, la autenticación OAuth, la conexión HTTP y la configuración de tiempo de espera de la herramienta de 60 segundos.](./assets/slack/org-scopes-tools.png){width="500" zoomable="yes"}

Al guardar no se inicia sesión en usted ni en ningún miembro de [!DNL Slack]. Para comprobar la conexión, inicie sesión como usted mismo, tal como se describe en [Iniciar sesión como miembro](#sign-in-as-a-member).

### Revisar los ámbitos de OAuth del usuario {#review-scopes}

El campo **[!UICONTROL ámbitos de OAuth del usuario]** es obligatorio. Separe los ámbitos con espacios o comas y haga coincidir los ámbitos de usuario aprobados para la aplicación. De forma predeterminada, el campo contiene los 22 ámbitos siguientes:

```text
search:read.public search:read.private search:read.im search:read.mpim search:read.files search:read.users channels:history groups:history im:history mpim:history channels:read groups:read im:read mpim:read users:read users:read.email files:read canvases:read lists:read emoji:read reactions:read chat:write
```

Es posible que el espacio de trabajo no apruebe todos los ámbitos predeterminados. Revise los ámbitos solicitados con el propietario de la aplicación.

>[!IMPORTANT]
>
>Los ámbitos predeterminados incluyen contenido privado, como canales privados, mensajes de grupo y mensajes directos. También incluyen `chat:write`, que permite al compañero enviar mensajes y respuestas como el miembro que ha iniciado sesión. Decida explícitamente si su organización habilita las herramientas de envío de mensajes. Al quitar una herramienta no se quitan sus ámbitos de OAuth. Si no desea que los miembros envíen mensajes, quite la herramienta `slack_send_message` y el ámbito `chat:write`.

La selección de herramientas y los ámbitos de OAuth son independientes. Cuando restrinja el acceso, revise la lista de herramientas y el campo de ámbito. Una herramienta habilitada no concede a un miembro más acceso de [!DNL Slack] que el que tiene su cuenta.

### Herramientas disponibles {#available-tools}

El conector [!DNL Slack] proporciona las 16 herramientas siguientes. De forma predeterminada, todos están disponibles para los miembros.

| Capacidad | Herramienta |
| --- | --- |
| Buscar | `slack_search_public` |
| Buscar | `slack_search_public_and_private` |
| Buscar | `slack_search_channels` |
| Buscar | `slack_search_users` |
| Leer conversaciones | `slack_read_channel` |
| Leer conversaciones | `slack_read_thread` |
| Leer conversaciones | `slack_list_channel_members` |
| Leer conversaciones | `slack_list_user_channels` |
| Leer contenido y perfiles | `slack_read_canvas` |
| Leer contenido y perfiles | `slack_read_user_profile` |
| Leer contenido y perfiles | `slack_read_file` |
| Leer contenido y perfiles | `slack_read_list` |
| Emoji y reacciones | `slack_search_emojis` |
| Emoji y reacciones | `slack_get_reactions` |
| Mensajes y borradores | `slack_send_message` |
| Mensajes y borradores | `slack_send_message_draft` |

El conector no es de solo lectura. Los miembros pueden enviar mensajes y respuestas a menos que quite la herramienta `slack_send_message`. La creación de canales, los mensajes programados, las cargas de archivos, la adición de reacciones y los cambios en el lienzo o la lista no están incluidos.

## Iniciar sesión como miembro {#sign-in-as-a-member}

Cuando un administrador configura el conector, cada miembro inicia sesión con su propia cuenta de [!DNL Slack]. No necesita el secreto de cliente para iniciar sesión.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Usuario]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**.

1. Buscar la tarjeta **[!UICONTROL Slack]**. Si la tarjeta muestra **[!UICONTROL No configurado]** y **[!UICONTROL Aún no está disponible. El administrador debe configurar esto.]**, pídale al administrador que [configure el conector](#configure-organization).

   No pida ni copie el secreto de cliente de la organización.

1. Una vez que el administrador haya configurado el conector, la tarjeta **[!UICONTROL Slack]** mostrará **[!UICONTROL Se requiere el inicio de sesión]**. Seleccione **[!UICONTROL Iniciar sesión]** en la tarjeta.

   También puede abrir los detalles del conector **[!UICONTROL Slack]**. Antes de iniciar sesión, la sección **[!UICONTROL Conexión]** muestra **[!UICONTROL No se ha iniciado sesión]**, con un botón **[!UICONTROL Iniciar sesión]**.

   ![Detalles del conector de Slack para un miembro, que muestran el estado Requiere inicio de sesión, el botón Probar conexión, la dirección URL del servidor, Cada usuario inicia sesión, un botón No iniciado sesión con un botón Inicio de sesión y las herramientas habilitadas por el administrador.](./assets/slack/member-details.png){width="700" zoomable="yes"}

1. Complete la autorización de [!DNL Slack] con la cuenta y el área de trabajo de [!DNL Slack] que planea usar. Revise los permisos solicitados y los requisitos de aprobación del espacio de trabajo.

   >[!IMPORTANT]
   >
   >Continúe solo si reconoce la aplicación y si su organización aprueba el acceso solicitado.

1. Vuelva a Compañero de trabajo y revise el estado de la conexión. Seleccione **[!UICONTROL Probar la conexión]** y, a continuación, [compruebe su acceso a Slack](#check-access) antes de confiar en la conexión.

1. Revise atentamente las acciones de mensajería. El compañero envía mensajes y respuestas como su cuenta de [!DNL Slack].

Como miembro, puede probar la conexión o cerrar la sesión, pero no puede cambiar la configuración de la organización. Solo puede tener acceso al contenido que [!DNL Slack] y los ámbitos concedidos permiten. Este contenido incluye conversaciones privadas solamente cuando su propia cuenta de [!DNL Slack] puede acceder a ellas.

Para desconectar tu cuenta de [!DNL Slack] del conector, selecciona **[!UICONTROL Cerrar sesión]**.

## Compruebe el acceso a Slack {#check-access}

Para confirmar que el conector puede leer el contenido de [!DNL Slack], inicie una conversación y escriba un mensaje de sólo lectura. Asegúrese de que el administrador habilitó la herramienta `slack_list_user_channels`.

Mensaje de ejemplo:

* &quot;Con Slack, enumere hasta cinco canales a los que pertenezco. Mostrar solo los nombres de canal. No envíe mensajes, cree borradores ni cambie nada&quot;.

Si su organización habilita las herramientas de mensajería, pruebe el envío solo en un canal que esté reservado para pruebas y con aprobación. Pida a un segundo miembro que inicie sesión por separado y confirme que cada miembro solo ve su propio contenido de [!DNL Slack].

## Solucionar problemas de acceso {#troubleshoot-access}

Si se produce un error en la configuración, el inicio de sesión o el acceso, consulte lo siguiente con el administrador:

| Problema | Qué comprobar |
| --- | --- |
| No se puede guardar la configuración | Introduzca el ID de cliente y el secreto de cliente, mantenga al menos un ámbito de OAuth de usuario y mantenga al menos una herramienta. No introduzca un ID de aplicación, un secreto de firma o un token de bot. |
| Falta la dirección URL de redireccionamiento **[!UICONTROL 1&rbrace; o [!DNL Slack] informa de que la redirección no coincide]** | Compare la URL de redireccionamiento completa del cuadro de diálogo Compañero de trabajo, incluidos el esquema, el host, el puerto y la ruta, con las **[!UICONTROL URL de redireccionamiento]** guardadas en la aplicación [!DNL Slack]. Si falta la dirección URL o los valores difieren, póngase en contacto con el representante de Adobe. |
| [!DNL Slack] inicio de sesión o error en las solicitudes | Compruebe la aprobación de la aplicación, los ámbitos del usuario concedido, la cuenta de [!DNL Slack] y el espacio de trabajo con el que inició sesión, así como las restricciones de direcciones IP de la aplicación. Si las solicitudes siguen fallando, cierre la sesión y vuelva a iniciarla. |
| Una acción de lectura o envío no está disponible | Compruebe la selección de herramientas de su organización, los ámbitos solicitados y concedidos, y los permisos de [!DNL Slack] del miembro. Esta configuración es independiente. |
| Un miembro no puede cambiar la configuración de la aplicación | Este comportamiento se espera para una conexión que administra la organización. Pregunte al administrador. Los miembros nunca introducen el secreto de cliente de la organización. |
