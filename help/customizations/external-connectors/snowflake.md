---
title: Conector externo de Snowflake Cortex AI
description: Obtenga información sobre cómo configurar el conector externo de Snowflake Cortex AI en CX Enterprise Coworker con una cuenta de servicio o inicio de sesión por persona para consultar los datos de Snowflake.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 942f76a48eabbc9ac795d9e53aad1faceff31393
workflow-type: tm+mt
source-wordcount: '2057'
ht-degree: 0%
---

# Conector externo de Snowflake Cortex AI {#snowflake}

Utilice el conector externo [!DNL Snowflake Cortex AI] para hacer preguntas acerca de sus datos de [!DNL Snowflake] en lenguaje sencillo en Adobe CX Enterprise Coworker. El conector vincula al compañero con un servidor de Protocolo de contexto de modelo (MCP) administrado por [!DNL Snowflake] en su cuenta de [!DNL Snowflake]. Los compañeros de trabajo pueden utilizar las herramientas que expone el servidor, como [!DNL Cortex Analyst], [!DNL Cortex Search] y las herramientas SQL.

>[!AVAILABILITY]
>
>El conector externo [!DNL Snowflake Cortex AI] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene dos partes independientes:

* **Configuración de la organización:** Un administrador conecta a un colaborador con un servidor MCP [!DNL Snowflake] existente, elige cómo inician sesión las personas y selecciona las herramientas que pueden utilizar los miembros.
* **Acceso de miembro:** Los miembros utilizan la conexión con una identidad de organización compartida o con su propia identidad [!DNL Snowflake], según la opción de inicio de sesión.

El administrador elige una de las siguientes opciones de inicio de sesión:

| Opción | Lo que proporciona el administrador | Cómo funciona el acceso |
| --- | --- | --- |
| **[!UICONTROL Cuenta de servicio de organización]** | Un token de acceso programático (PAT) de [!DNL Snowflake] para una cuenta de servicio. | Todos los miembros utilizan los permisos de la cuenta de servicio. La caducidad o revocación del token afecta a todos los miembros. |
| **[!UICONTROL Cada persona inicia sesión]** | El ID de cliente y el secreto de cliente de una integración de OAuth [!DNL Snowflake], y un rol de [!DNL Snowflake] opcional. | Cada miembro inicia sesión con su propia identidad [!DNL Snowflake] y el acceso sigue sus permisos [!DNL Snowflake]. |

Ninguna opción otorga a [!DNL Snowflake] privilegios que la identidad seleccionada aún no tiene. [!DNL Snowflake] exige permisos en cada solicitud.

## Requisitos previos {#prerequisites}

El compañero se conecta a un servidor MCP [!DNL Snowflake] existente. No crea el servidor ni sus herramientas. Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Para la configuración de la organización:** Cuenta con permiso para administrar conectores de organización en Coworker.
* **Para el servidor MCP [!DNL Snowflake]:** La dirección URL HTTPS completa del servidor, incluida su base de datos, esquema y nombre de servidor.
* **Para la opción de cuenta de servicio:** Una ruta de acceso para una cuenta de servicio dedicada. La función de cuenta de servicio solo debe tener los privilegios necesarios para el servidor MCP y sus herramientas.
* **Para la opción de inicio de sesión por persona:** Una integración de OAuth [!DNL Snowflake] con su ID de cliente y secreto de cliente. También necesita un administrador de [!DNL Snowflake] que pueda registrar la URL de redireccionamiento de Coworker y configurar la integración.

>[!IMPORTANT]
>
>Nunca comparta las rutas de acceso, los secretos del cliente de OAuth u otras credenciales en capturas de pantalla, chats ni tickets de asistencia. Use los secretos de la organización y una identidad [!DNL Snowflake] con menos privilegios.

### Configuración del servidor MCP de Snowflake {#configure-snowflake-mcp-server}

Un administrador de [!DNL Snowflake] debe completar las siguientes tareas en [!DNL Snowflake] antes de configurar el conector:

1. Cree el servidor MCP y defina las herramientas que expone.
1. Conceder acceso a las funciones necesarias al servidor MCP, sus herramientas y los objetos subyacentes.

   El acceso al servidor MCP no concede automáticamente acceso a cada herramienta u objeto.

1. Configure la autenticación para la opción de inicio de sesión que planea utilizar:

   * Para la opción de cuenta de servicio, cree una ruta de acceso para la cuenta de servicio.
   * Para la opción de inicio de sesión por persona, cree una integración de OAuth que emita tokens de actualización.

Para obtener instrucciones, consulte la siguiente documentación de [!DNL Snowflake]:

* [Servidor MCP administrado por Snowflake](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents-mcp){target="_blank"}
* [Crear servidor MCP](https://docs.snowflake.com/en/sql-reference/sql/create-mcp-server){target="_blank"}
* [Descripción general del control de acceso](https://docs.snowflake.com/en/user-guide/security-access-control-overview){target="_blank"}
* [Configuración de Snowflake OAuth para clientes personalizados](https://docs.snowflake.com/en/user-guide/oauth-custom){target="_blank"}
* [Creación de una integración de seguridad (Snowflake OAuth)](https://docs.snowflake.com/en/sql-reference/sql/create-security-integration-oauth-snowflake){target="_blank"}
* [Uso de tokens de acceso programáticos para la autenticación](https://docs.snowflake.com/en/user-guide/programmatic-access-tokens){target="_blank"}

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL Snowflake Cortex AI] a disposición de todos los miembros de la organización. Los cambios en la página de organización se aplican a todos los usuarios de la organización.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Snowflake Cortex AI]**, seleccione **[!UICONTROL Configurar]**.

1. En el cuadro de diálogo **[!UICONTROL Conectar Snowflake Cortex AI]**, escriba la dirección URL completa del servidor MCP [!DNL Snowflake] en **[!UICONTROL URL del servidor]**. La dirección URL debe utilizar HTTPS y seguir este patrón:

   ```text
   https://<account-host>/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server-name>
   ```

   Utilice la dirección URL exacta para su cuenta de [!DNL Snowflake] y servidor MCP. El nombre de host de la cuenta no debe contener guiones bajos, incluido uno codificado (`%5F`). No incluya credenciales en la dirección URL. El compañero comprueba el esquema, el host y la ruta HTTPS antes de guardar.

1. En **[!UICONTROL ¿Quién inicia sesión?]**, seleccione una opción de inicio de sesión y, a continuación, complete su configuración.

   * **[!UICONTROL Cuenta de servicio de organización]:** Las solicitudes utilizan los permisos de la cuenta de servicio a través de un token de acceso programático (PAT). Utilice esta opción para el acceso administrado centralmente. Utilice una cuenta de servicio dedicada con una función de ámbito limitado, no una cuenta personal.

     ![Cuadro de diálogo Conectar Snowflake con la cuenta de servicio de organización seleccionada, que muestra el campo URL del servidor, las opciones de token de cuenta de servicio, el campo Token de acceso de programación y una advertencia de que todos actúan con los permisos del propietario del token.](./assets/snowflake/org-service-account.png){width="500" zoomable="yes"}

     | Configuración | Descripción |
     | --- | --- |
     | **[!UICONTROL Token de cuenta de servicio]** | Elija de dónde proviene el token. Seleccione **[!UICONTROL Introducir nuevo]** para introducir una ruta de acceso o **[!UICONTROL Usar un secreto existente]** para reutilizar un secreto de organización que ya contenga el token. Un secreto existente debe contener el valor completo del encabezado `Authorization`, no solo el token sin procesar. |
     | **[!UICONTROL Token de acceso mediante programación]** | Requerido cuando selecciona **[!UICONTROL Escriba nuevo]**. Cree el token para una cuenta de servicio [!DNL Snowflake] dedicada con solo los permisos necesarios. Para obtener instrucciones, seleccione **[!UICONTROL Cómo crear un token de acceso de programación]** en el cuadro de diálogo. El compañero almacena el token como un secreto de organización. |

     >[!IMPORTANT]
     >
     >Todas las personas que utilizan esta conexión actúan con los permisos del propietario del token. Si el token caduca o se revoca, la conexión deja de funcionar para todos los miembros.

     La creación y el uso de una PAT pueden estar sujetos a [!DNL Snowflake] directivas de red y autenticación. Si la creación o autenticación de tokens está bloqueada, pídale al administrador de [!DNL Snowflake] que compruebe estas directivas.

   * **[!UICONTROL Cada persona inicia sesión]:** Las solicitudes utilizan los permisos de [!DNL Snowflake] de cada persona. Utilice esta opción para obtener acceso controlado y controlado por el usuario.

     ![Conectar el cuadro de diálogo de Snowflake con Cada persona inicia sesión seleccionada y muestra la URL de redireccionamiento, las opciones de credenciales de integración de OAuth, los campos de ID de cliente de integración de OAuth y secreto de cliente, y el campo opcional de rol de Snowflake.](./assets/snowflake/org-oauth.png){width="500" zoomable="yes"}

     | Configuración | Descripción |
     | --- | --- |
     | **[!UICONTROL URL de redireccionamiento]** | Sólo lectura. Copie esta dirección URL y regístrela como URI de redireccionamiento en la integración de seguridad de OAuth [!DNL Snowflake]. El valor debe coincidir exactamente. Para obtener instrucciones, seleccione **[!UICONTROL Cómo crear una integración de OAuth de Snowflake]** en el cuadro de diálogo. La dirección URL de redireccionamiento difiere entre entornos, por lo que siempre debe copiarla del cuadro de diálogo. |
     | **[!UICONTROL Credenciales de integración de OAuth]** | Elija de dónde provienen las credenciales. Seleccione **[!UICONTROL Introducir nuevo]** para introducir el ID de cliente y el secreto de cliente, o **[!UICONTROL Usar un secreto existente]** para seleccionar los secretos de organización que los contienen. |
     | **[!UICONTROL ID de cliente de integración de OAuth]** | Requerido cuando selecciona **[!UICONTROL Escriba nuevo]**. El ID de cliente de su integración de OAuth [!DNL Snowflake] administrada por el cliente. |
     | **[!UICONTROL secreto de cliente de integración de OAuth]** | Requerido cuando selecciona **[!UICONTROL Escriba nuevo]**. El secreto de cliente de la misma integración de OAuth. Los miembros nunca introducen estas credenciales. |
     | **[!UICONTROL Rol de Snowflake]** | Opcional. La función que utiliza cada sesión, solicitada a través del ámbito de OAuth `session:role:ROLE_NAME`. La función debe otorgarse a sus miembros y tener acceso al servidor MCP. Deje el campo en blanco para utilizar la función predeterminada de cada miembro. |

     El compañero deriva los extremos de OAuth de la dirección URL de la cuenta y solicita un token de actualización. Configure la integración de OAuth para emitir tokens de actualización. El ámbito solicitado por sí solo no anula la configuración de la integración.

     Coworker convierte el nombre de la función a mayúsculas. Las funciones creadas con un nombre entre comillas no se pueden usar. Si la integración de OAuth bloquea la función o si un miembro no la tiene, puede producirse un error en el inicio de sesión o el acceso.

1. En **[!UICONTROL Herramientas disponibles para los usuarios]**, elija las herramientas que pueden utilizar los miembros. Cada servidor MCP de [!DNL Snowflake] define sus propias herramientas, por lo que el cuadro de diálogo no muestra una lista fija. Escriba los nombres de las herramientas tal como se definen en el servidor MCP, no los tipos de herramientas como `CORTEX_ANALYST_MESSAGE`. Para ver los nombres de las herramientas, ejecute `DESCRIBE MCP SERVER` en [!DNL Snowflake].

   ![Cuadro de diálogo Conectar Snowflake que muestra el campo de función Snowflake, la sección Herramientas disponibles para usuarios con los campos Nombres de herramientas permitidos y Nombres de herramientas bloqueados, el aviso Acceso y permisos, y un resumen con autenticación OAuth (integración de clientes), conexión HTTP y un tiempo de espera de herramienta de 300 segundos.](./assets/snowflake/org-tools.png){width="500" zoomable="yes"}

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Nombres de herramientas permitidos]** | Las herramientas que pueden utilizar los miembros. Separe los nombres con comas o espacios. Deje el campo vacío para permitir todas las herramientas que expone el servidor, excepto las herramientas bloqueadas. |
   | **[!UICONTROL Nombres de herramientas bloqueados]** | Las herramientas que los miembros nunca pueden utilizar. Separe los nombres con comas o espacios. Las herramientas bloqueadas no están disponibles aunque también las permita. |

   >[!IMPORTANT]
   >
   >Si deja **[!UICONTROL Nombres de herramientas permitidos]** vacíos, los miembros podrán utilizar todas las herramientas, incluida cualquier herramienta de ejecución de SQL. Las herramientas de ejecución de SQL ejecutan SQL como identidad conectada. Revise las definiciones de herramientas en el servidor y permita solo las herramientas que su organización necesita.

   Las descripciones de herramientas no sustituyen los privilegios de [!DNL Snowflake] ni otros controles de acceso. Para las herramientas [!DNL Cortex Analyst], configure una vista semántica y los permisos necesarios, incluido el rol de base de datos `SNOWFLAKE.CORTEX_USER`. Para las herramientas de [!DNL Cortex Agent], configure las herramientas de solo lectura y desactive la ejecución de código en [!DNL Snowflake]. Los miembros no pueden cambiar la selección de herramientas.

1. Revise **[!UICONTROL Acceso y permisos]** y, a continuación, seleccione **[!UICONTROL Guardar conexión]**. La tarjeta **[!UICONTROL Snowflake Cortex AI]** muestra **[!UICONTROL Configuración guardada]**.

   Seleccione **[!UICONTROL Ver configuración]** para revisar la URL del servidor, el tipo de autenticación y la directiva de herramientas. A continuación, seleccione **[!UICONTROL Probar conexión]** para comprobar el acceso y descubrir las herramientas del servidor.

   Las nuevas conexiones de [!DNL Snowflake] utilizan un tiempo de espera de herramienta de 300 segundos. Una conexión anterior sin un tiempo de espera guardado puede utilizar el valor predeterminado de 60 segundos. Compruebe el tiempo de espera mostrado para una conexión existente.

Una prueba correcta no confirma que cada herramienta o objeto [!DNL Snowflake] esté disponible para todos los miembros.

## Uso del conector como miembro {#use-as-member}

Cuando un administrador haya configurado el conector, ábralo desde su propia vista de **[!UICONTROL personalizaciones]**.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Usuario]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**.

   Si la tarjeta **[!UICONTROL Snowflake Cortex AI]** muestra **[!UICONTROL No configurado]**, pídale al administrador que [configure el conector](#configure-organization).

1. Abra **[!UICONTROL Snowflake Cortex AI]**. Los detalles del conector son de solo lectura para los miembros. No puede cambiar la dirección URL del servidor, las credenciales o la selección de herramientas.

1. Si la conexión utiliza una cuenta de servicio de organización, las solicitudes utilizan la identidad de la organización. No es necesario que inicie sesión. Nunca ingrese ni comparta la ruta.

1. Si la conexión usa el inicio de sesión por persona, inicie el inicio de sesión y realice la autenticación con la cuenta [!DNL Snowflake] deseada. Complete los pasos necesarios de inicio de sesión único (SSO) o autenticación multifactor (MFA). Confirme la organización, la aplicación y la función solicitadas, si aparece alguna.

1. Si es necesario, seleccione **[!UICONTROL Probar conexión]**. Una prueba que se realizó correctamente muestra **[!UICONTROL Conexión correcta]** y la cantidad de herramientas disponibles.

   ![Detalles del conector de Snowflake que muestran un estado Conectado, un mensaje de Conexión correcta con cinco herramientas disponibles, un aviso de que el administrador configuró el conector y la dirección URL del servidor, la opción de inicio de sesión, la autenticación, la conexión y el tiempo de espera de la herramienta.](./assets/snowflake/member-details.png){width="700" zoomable="yes"}

   Antes de que una prueba se realice correctamente, es posible que los detalles muestren solamente los nombres de herramienta que el administrador ha permitido, o que le soliciten que ejecute la prueba. Después de la prueba, cada herramienta aparece con su descripción.

   ![Detalles del conector de Snowflake que muestran el tipo de conexión, el tiempo de espera de la herramienta, el estado de inicio de sesión, los botones Cerrar sesión y Actualizar, y cinco herramientas de ejemplo habilitadas por el administrador.](./assets/snowflake/member-tools.png){width="700" zoomable="yes"}

Las herramientas del ejemplo están definidas por un servidor MCP [!DNL Snowflake]. Las herramientas que ve dependen del servidor y de la selección de herramientas del administrador.

Los detalles de autenticación de la conexión muestran si utiliza una PAT, una OAuth del equipo o una OAuth por persona. Para desconectar tu cuenta de [!DNL Snowflake], selecciona **[!UICONTROL Cerrar sesión]**.

El estado **[!UICONTROL Conectado]** no garantiza el acceso a una herramienta u objeto de datos específico. [!DNL Snowflake] concesiones, directivas y el rol seleccionado aún se aplican.

## Solucionar problemas de acceso {#troubleshoot-access}

Si se produce un error en la configuración, el inicio de sesión o el acceso, consulte lo siguiente con el administrador:

| Problema | Qué comprobar |
| --- | --- |
| Se rechaza la URL del servidor | La dirección URL utiliza HTTPS y la ruta de acceso completa `/api/v2/databases/<database>/schemas/<schema>/mcp-servers/<server-name>`. El nombre de host de la cuenta no tiene guiones bajos y la dirección URL no tiene credenciales. |
| La ruta no se puede crear ni utilizar | Directiva de red, directiva de autenticación, caducidad de token y función de la cuenta de servicio. Si usa un secreto existente, confirme que contiene el valor completo del encabezado `Authorization`. |
| La URL de redireccionamiento de OAuth no coincide | La integración de OAuth [!DNL Snowflake] tiene la dirección URL de redireccionamiento exacta desde el mismo entorno de Coworker. |
| Inicio de sesión correcto, pero las solicitudes fallan | La función se concede al miembro y se permite mediante la integración de OAuth. La integración emite tokens de actualización, y el ID de cliente y el secreto pertenecen a la integración deseada. |
| Falta una herramienta o está denegada | La configuración de **[!UICONTROL Nombres de herramientas permitidos]** y **[!UICONTROL Nombres de herramientas bloqueados]**, la disponibilidad de la herramienta en el servidor MCP y las concesiones de [!DNL Snowflake] en el servidor, la herramienta y los objetos subyacentes. |
| Se agota el tiempo de espera de una llamada de herramienta | **[!UICONTROL Tiempo de espera de herramienta]** en los detalles del conector. Las nuevas conexiones tardan 300 segundos. Las conexiones más antiguas sin un tiempo de espera guardado pueden tardar 60 segundos. |
