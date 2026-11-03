---
title: Conector externo de Microsoft Work IQ
description: Aprenda a configurar el conector externo de Microsoft Work IQ en CX Enterprise Coworker con la aplicación Entra e inicie sesión para utilizar los datos de Microsoft 365 en el chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: f87c1b3ac9c344a07cdc8d0861593c34c97cfc3e
workflow-type: tm+mt
source-wordcount: '1648'
ht-degree: 1%
---

# Conector externo de Microsoft Work IQ {#microsoft-work-iq}

Use el conector externo [!DNL Microsoft Work IQ] para trabajar con los datos [!DNL Microsoft 365] en Adobe CX Enterprise Coworker. Después de configurar el conector, pídale a su Compañero que busque en su correo electrónico, archivos, reuniones y [!DNL Microsoft Teams] mensajes, revise eventos de calendario y más. El conector es un servidor de Protocolo de contexto de modelo (MCP) alojado por [!DNL Microsoft].

>[!AVAILABILITY]
>
>El conector externo [!DNL Microsoft Work IQ] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene dos partes independientes:

* **Configuración de la organización:** Un administrador configura el conector una vez para toda la organización. El administrador conecta una aplicación de [!DNL Microsoft Entra] y selecciona las herramientas que los miembros pueden utilizar.
* **Inicio de sesión de miembro:** Cada miembro inicia sesión con su propia cuenta de trabajo [!DNL Microsoft]. Los miembros solo pueden acceder a los datos a los que puede acceder su cuenta.

Al guardar la configuración de la organización, no se inicia sesión en ningún miembro ni se conceden permisos adicionales de [!DNL Microsoft 365]. Cada miembro debe iniciar sesión por separado.

La tarjeta **[!UICONTROL Microsoft Work IQ]** menciona una aplicación OAuth compartida, que solo está disponible cuando la implementación configura una. No dé por hecho que ya se ha proporcionado una aplicación. Esta página describe cómo conectar su propia aplicación [!DNL Microsoft Entra].

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Para la configuración de la organización:** Cuenta con permiso para administrar conectores de organización en Coworker.
* **Para la aplicación [!DNL Microsoft Entra]:** Un administrador de [!DNL Microsoft Entra] que puede registrar una aplicación web y conceder consentimiento de administrador.
* **Para su inquilino [!DNL Microsoft]:** [!DNL Work IQ] habilitado para el inquilino.
* **Para el inicio de sesión de un miembro:** Cuenta de trabajo de [!DNL Microsoft] que cumple los requisitos y tiene acceso a los datos que planea usar.

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL Microsoft Work IQ] a disposición de todos los miembros de la organización. Los cambios en la página de organización se aplican a todos los usuarios de la organización.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Microsoft Work IQ]**, seleccione **[!UICONTROL Configurar]**.

1. En el cuadro de diálogo **[!UICONTROL Configurar Microsoft Work IQ para su organización]**, revise la **[!UICONTROL URL del servidor]**, `https://workiq.svc.cloud.microsoft/mcp`. A continuación, prepare su aplicación [!DNL Microsoft Entra]. Para los requisitos de [!DNL Microsoft], seleccione **[!UICONTROL instrucciones de configuración de Microsoft]** en el cuadro de diálogo.

   1. Registre una aplicación web en [!DNL Microsoft Entra] o use una existente.
   1. Copie la **[!UICONTROL URL de redireccionamiento]** del cuadro de diálogo y registre este valor exacto como URI de redireccionamiento web en la aplicación. La dirección URL de redireccionamiento difiere entre entornos, por lo que siempre debe copiarla del cuadro de diálogo.
   1. Cree un secreto de cliente o confirme que el secreto de cliente existente sigue siendo válido. Necesita el valor secreto, no el ID secreto.
   1. Conceda consentimiento de administrador para el permiso delegado `WorkIQAgent.Ask` y confirme que [!DNL Work IQ] está habilitado para su inquilino.

   En **[!UICONTROL ID de inquilino de Microsoft Entra]**, ingrese su ID de inquilino. En [!DNL Microsoft Entra], encuentre este valor en **[!UICONTROL Información general]** > **[!UICONTROL Id. de directorio (inquilino)]**.

   ![El cuadro de diálogo Configurar Microsoft Work IQ para su organización muestra la dirección URL del servidor, los requisitos Antes de guardar, la dirección URL de redireccionamiento, el campo ID de inquilino de Microsoft Entra y los campos de nueva credencial.](./assets/microsoft-work-iq/org-configure.png){width="500" zoomable="yes"}

1. En **[!UICONTROL De donde provienen las credenciales]**, seleccione una de las siguientes opciones:

   * **[!UICONTROL Escriba nuevo]:** En **[!UICONTROL ID de cliente de aplicación de OAuth]**, escriba el ID de aplicación (cliente) de su aplicación [!DNL Microsoft Entra]. En **[!UICONTROL secreto de cliente de aplicación OAuth]**, escriba el valor secreto. El compañero almacena el valor secreto como un secreto de organización.
   * **[!UICONTROL Use un secreto existente]:** En **[!UICONTROL Secreto que contiene el ID de cliente]** y **[!UICONTROL Secreto que contiene el secreto de cliente]**, seleccione los secretos de organización guardados para su aplicación. Si los secretos correctos no están disponibles, selecciona **[!UICONTROL Introducir nuevo]** en su lugar. Sigue introduciendo el ID de inquilino por separado.

   El ID de inquilino, el ID de cliente y el secreto de cliente deben pertenecer a la misma aplicación y al mismo inquilino. Si vuelve a utilizar secretos guardados, confirme que el secreto de cliente no ha caducado. Estas credenciales de la aplicación son independientes de las [!DNL Microsoft] contraseñas que los miembros utilizan para iniciar sesión.

   ![Use una opción de secreto existente seleccionada, con secretos de organización elegidos para el ID de cliente y el secreto de cliente.](./assets/microsoft-work-iq/org-existing-secret.png){width="500" zoomable="yes"}

1. En **[!UICONTROL Herramientas disponibles para los usuarios]**, seleccione las herramientas que necesita su organización. Para obtener más información, consulte [Herramientas disponibles](#available-tools). Revise **[!UICONTROL Acceso y permisos]**, que confirma que cada persona inicia sesión por separado, y luego seleccione **[!UICONTROL Guardar configuración]**.

   ![Cuadro de diálogo Configuración completa de Microsoft Work IQ para su organización, con las herramientas de solo lectura seleccionadas en Herramientas disponibles para los usuarios, la herramienta Tareas y las herramientas de cambio de datos borradas y el aviso Cada persona inicia sesión por separado en Acceso y permisos.](./assets/microsoft-work-iq/org-tools.png){zoomable="yes"}

1. Revise los detalles guardados del conector **[!UICONTROL workiq]**. De forma opcional, seleccione **[!UICONTROL Test]** para comprobar que el Compañero de trabajo puede descubrir las herramientas del conector. Para cambiar las herramientas después de guardar, vea [Cambiar la selección de herramientas](#change-tool-selection).

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Source]** | El servidor MCP [!DNL Work IQ], `https://workiq.svc.cloud.microsoft/mcp`. |
   | **[!UICONTROL Autenticación]** | El método de autenticación `workiq_login`. |
   | **[!UICONTROL Tiempo de espera de herramienta]** | Tiempo de espera de la herramienta para el conector. |
   | **[!UICONTROL Conexión]** | Su propio estado de inicio de sesión. |

   ![Se guardaron los detalles del conector de workiq que muestran el origen, el método de autenticación, el tiempo de espera de la herramienta, el estado No conectado y las herramientas seleccionadas.](./assets/microsoft-work-iq/org-details.png){width="500" zoomable="yes"}

El estado **[!UICONTROL Sin sesión iniciada]** en los detalles del conector hace referencia a su propia conexión, no a la organización. Para usar el conector, selecciona **[!UICONTROL Iniciar sesión]** y sigue los pasos indicados en [Iniciar sesión como miembro](#sign-in-as-a-member).

Para dejar de ofrecer el conector a tu organización, selecciona **[!UICONTROL Quitar]** en la página de detalles del conector.

### Herramientas disponibles {#available-tools}

El conector [!DNL Microsoft Work IQ] proporciona las siguientes herramientas:

| Herramienta | Descripción |
| --- | --- |
| `search_paths` | Encuentre qué capacidades de [!DNL Microsoft 365] están disponibles y cómo solucionarlas. |
| `get_schema` | Consulte qué campos acepta o devuelve una solicitud compatible. |
| `list_agents` | Ver los [!DNL Microsoft 365 Copilot] agentes disponibles en su cuenta, sin ejecutarlos. |
| `fetch` | Lee [!DNL Microsoft 365] elementos a los que tu cuenta puede acceder, como mensajes, eventos, archivos y personas. No cambia los datos. |
| `call_function` | Calcule los resultados a partir de datos a los que puede acceder su cuenta, como una vista de calendario o cambios recientes. No cambia los datos. |
| `retrieve` | Busque correo electrónico, archivos, reuniones, [!DNL Microsoft Teams] mensajes, personas y orígenes conectados, con vínculos a cada origen. |
| `fetch_blob` | Descargue un archivo, como un documento, una imagen o una fotografía de perfil, de hasta 4 MB. No cambia los datos. |
| `ask` | Pregunte a [!DNL Microsoft 365 Copilot], o a uno de sus agentes, acerca de su correo electrónico, reuniones, archivos y otros datos de [!DNL Microsoft 365]. |
| `delete_entity` | Eliminar un elemento de [!DNL Microsoft 365], como un mensaje o un evento. Cambia los datos. |
| `do_action` | Ejecute una acción [!DNL Microsoft 365], como enviar correo o mover un elemento. Cambia los datos. |
| `create_entity` | Crear un elemento [!DNL Microsoft 365], como un evento o un borrador de mensaje. Cambia los datos. |
| `update_entity` | Cambiar un elemento [!DNL Microsoft 365] existente, como un evento o un contacto. Cambia los datos. |

>[!IMPORTANT]
>
>Las herramientas `delete_entity`, `do_action`, `create_entity` y `update_entity` cambian los datos en [!DNL Microsoft 365]. Revise detenidamente estas herramientas y seleccione únicamente las herramientas que su organización desea que utilicen los miembros.

Las herramientas que el servidor agrega posteriormente permanecen desactivadas hasta que las selecciona.

### Cambiar la selección de herramientas {#change-tool-selection}

Para cambiar las herramientas disponibles para los miembros después de guardar, utilice la sección **[!UICONTROL Herramientas]** de la página de detalles del conector.

1. Seleccione o borre herramientas individuales, o use **[!UICONTROL Seleccionar todo]** o **[!UICONTROL Borrar]**.

1. Seleccione **[!UICONTROL Guardar selección de herramientas]**.

>[!CAUTION]
>
>Si se selecciona **[!UICONTROL Mostrar todas las herramientas]**, se borrará la selección actual. Los miembros pueden utilizar todas las herramientas que no excluya la directiva, hasta que guarde una nueva selección. No seleccione **[!UICONTROL Mostrar todas las herramientas]** solo para ver la lista de herramientas.

## Iniciar sesión como miembro {#sign-in-as-a-member}

Una vez que un administrador configura el conector, cada miembro inicia sesión con su propia cuenta de trabajo [!DNL Microsoft]. No necesita el secreto del cliente de la aplicación para iniciar sesión.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Usuario]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**.

1. En la tarjeta **[!UICONTROL Microsoft Work IQ]**, seleccione **[!UICONTROL Iniciar sesión]**.

   Si la tarjeta muestra **[!UICONTROL No configurado]** o el conector no está disponible, pídale al administrador que [configure el conector](#configure-organization).

1. En la pantalla [!DNL Microsoft] **[!UICONTROL Elegir una cuenta]**, seleccione la cuenta de trabajo de su organización o seleccione **[!UICONTROL Usar otra cuenta]**.

   Es posible que el explorador recuerde varias cuentas, incluidas las de otros inquilinos. La cuenta con la que ya se ha iniciado sesión no siempre es la correcta. Elija la cuenta con el acceso de [!DNL Microsoft 365] que necesita.

   ![Microsoft Elija una pantalla de cuenta que enumere dos cuentas con nombres y direcciones de correo electrónico borrosos, y la opción Usar otra cuenta.](./assets/microsoft-work-iq/member-pick-account.png){width="400" zoomable="yes"}

1. Complete los pasos de inicio de sesión para su cuenta, como una contraseña, inicio de sesión único (SSO), inicio de sesión sin contraseña, autenticación multifactor (MFA) u otra verificación.

   Escriba sus credenciales de [!DNL Microsoft] solamente en el flujo de inicio de sesión que apruebe su organización. Nunca los introduzca en los campos de la aplicación OAuth del conector.

   ![Pantalla de introducción de contraseña de Microsoft para una cuenta de trabajo con una dirección de correo electrónico borrosa y el botón de inicio de sesión.](./assets/microsoft-work-iq/member-password.png){width="400" zoomable="yes"}

1. Si [!DNL Microsoft] solicita consentimiento, revise la solicitud.

   >[!IMPORTANT]
   >
   >Continúe solo si reconoce la aplicación y si su organización aprueba el acceso solicitado.

1. Después de que [!DNL Microsoft] le devuelva a Coworker, abra los detalles del conector **[!UICONTROL workiq]**. Confirme que el conector muestra **[!UICONTROL Conectado]** y **[!UICONTROL iniciado sesión]**.

   ![detalles del conector workiq que muestran un estado Conectado, una conexión Firmada y las herramientas habilitadas por el administrador.](./assets/microsoft-work-iq/member-connected.png){width="700" zoomable="yes"}

1. Revise **[!UICONTROL Herramientas habilitadas por el administrador]** para ver las herramientas que puede usar.

Desde los detalles del conector, también puede hacer lo siguiente:

* **[!UICONTROL Prueba]:** Comprueba que el Compañero de trabajo puede descubrir las herramientas del conector.
* **[!UICONTROL Cerrar sesión]:** Desconecta tu cuenta de [!DNL Microsoft] del conector.

Los detalles del conector también muestran la configuración **[!UICONTROL Tiempo de espera de herramienta]** y un control **[!UICONTROL Actualizar]**.

El estado **[!UICONTROL Conectado]** no confirma que se pueda tener acceso a todos los recursos de [!DNL Microsoft 365] o que todas las herramientas se ejecuten correctamente. Para confirmar tu acceso, [comprueba tu acceso a Microsoft 365](#check-access).

## Compruebe su acceso a Microsoft 365 {#check-access}

Para confirmar que el conector puede leer los datos, inicie una conversación e introduzca un mensaje de solo lectura.

Mensaje de ejemplo:

* &quot;Encuentre mis reuniones para mañana e incluya enlaces a las fuentes. No cree, actualice, envíe ni elimine nada&quot;.

Para que esta solicitud funcione, el administrador debe habilitar una herramienta que pueda leer datos del calendario y su cuenta debe tener acceso a los datos.

## Solucionar problemas de acceso {#troubleshoot-access}

Si falla el inicio de sesión o el acceso, consulte lo siguiente con su administrador:

| Área | Qué comprobar |
| --- | --- |
| Cuenta de [!DNL Microsoft] | Ha iniciado sesión con la cuenta de trabajo correcta para el inquilino deseado. |
| Disponibilidad de [!DNL Work IQ] | [!DNL Work IQ] está habilitado para su inquilino [!DNL Microsoft]. |
| URI de redirección | La aplicación [!DNL Microsoft Entra] tiene la dirección URL de redireccionamiento exacta desde el cuadro de diálogo registrado como URI de redireccionamiento web. |
| Consentimiento del administrador | Un administrador concedió consentimiento de administrador para el permiso delegado `WorkIQAgent.Ask`. |
| Secreto del cliente | El secreto de cliente no ha caducado y el conector utiliza el valor secreto, no el ID secreto. |
| Secretos guardados | Ambos secretos de organización seleccionados pertenecen a la aplicación [!DNL Microsoft Entra] deseada. |
| Selección de herramientas | Si solo falla una herramienta, el administrador ha habilitado esa herramienta. |
| [!DNL Microsoft 365] permisos | Su cuenta tiene permiso para acceder a los datos solicitados. |
