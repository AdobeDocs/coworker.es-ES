---
title: Conector Externo De Google Ads
description: Obtenga información sobre cómo configurar el conector externo de Google Ads en CX Enterprise Coworker para su organización e iniciar sesión con Google para utilizar los datos de Google Ads en el chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 33bbe0ce723fcad4e25353749039c6b81b0dbdf9
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 1%
---

# Conector externo de Google Ads {#google-ads}

Use el conector externo [!DNL Google Ads] para trabajar con los datos [!DNL Google Ads] en Adobe CX Enterprise Coworker. Después de configurar el conector, pregunte a su compañero a qué cuentas de publicidad puede acceder, qué campos y métricas están disponibles y cómo funcionan sus campañas. El conector es un servidor de Protocolo de contexto de modelo (MCP).

>[!AVAILABILITY]
>
>El conector externo [!DNL Google Ads] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene dos partes independientes:

* **Configuración de la organización:** Un administrador configura el conector una vez para toda la organización y selecciona las herramientas que los miembros pueden utilizar. Adobe proporciona la aplicación OAuth, por lo que no hay credenciales de aplicación que introducir.
* **Inicio de sesión de miembro:** Cada miembro inicia sesión con su propia cuenta de [!DNL Google]. Los miembros solo pueden tener acceso a las cuentas de [!DNL Google Ads] a las que puede tener acceso su cuenta de [!DNL Google].

Al guardar la configuración de la organización, no se inicia sesión en ningún miembro ni se concede acceso a las cuentas de [!DNL Google Ads]. Cada miembro debe iniciar sesión por separado.

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Para la configuración de la organización:** Cuenta con permiso para administrar conectores de organización en Coworker.
* **Para el inicio de sesión de miembros:** Una cuenta de [!DNL Google] con acceso a las cuentas de [!DNL Google Ads] que planea usar.

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL Google Ads] a disposición de todos los miembros de la organización. Los cambios en la página de organización se aplican a todos los usuarios de la organización.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Google Ads]**, seleccione **[!UICONTROL Configurar]**.

1. En el cuadro de diálogo **[!UICONTROL Configuración de Google Ads para su organización]**, confirme que la **[!UICONTROL aplicación OAuth]** es **[!UICONTROL aplicación OAuth administrada por Adobe]**. Adobe proporciona la aplicación [!DNL Google Ads], por lo que no es necesario que escriba las credenciales de la aplicación. En **[!UICONTROL Herramientas disponibles para los usuarios]**, seleccione las herramientas que necesita su organización. Para obtener más información, consulte [Herramientas disponibles](#available-tools). Revise el aviso **[!UICONTROL Cada persona inicia sesión por separado]** y, a continuación, seleccione **[!UICONTROL Guardar conexión]**.

   ![Cuadro de diálogo Configuración de Google Ads para su organización con la aplicación OAuth administrada por Adobe, las tres herramientas seleccionadas y el aviso Cada persona inicia sesión por separado.](./assets/google-ads/org-configure.png){width="500" zoomable="yes"}

1. Revise los detalles guardados del conector **[!UICONTROL google-ads]**.

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Source]** | La URL del servidor MCP para su entorno. |
   | **[!UICONTROL Autenticación]** | El método de autenticación `google-ads_login`. |
   | **[!UICONTROL Directiva de herramientas]** | Los nombres de herramienta o patrones permitidos. |
   | **[!UICONTROL Conexión]** | Su propio estado de inicio de sesión. |

   ![Se guardaron los detalles del conector google-ads que muestran el origen, el método de autenticación, la directiva de herramientas con tres herramientas permitidas y un objeto Firmado en conexión con los botones Cerrar sesión y Actualizar.](./assets/google-ads/org-details.png){width="700" zoomable="yes"}

El estado de **[!UICONTROL Connection]** en los detalles del conector hace referencia a su propia conexión, no a la organización. Todos los miembros tienen que iniciar sesión con su propia cuenta. Una vez que los miembros inicien sesión, podrán seleccionar **[!UICONTROL Test]** para probar la detección de herramientas. Para usar el conector, sigue los pasos indicados en [Iniciar sesión como miembro](#sign-in-as-a-member).

Para dejar de ofrecer el conector a tu organización, selecciona **[!UICONTROL Quitar]** en la página de detalles del conector.

### Herramientas disponibles {#available-tools}

El conector [!DNL Google Ads] proporciona las siguientes herramientas:

| Herramienta | Descripción |
| --- | --- |
| `customers_list_accessible_customers` | Enumere los ID de cliente a los que puede acceder directamente su cuenta de [!DNL Google] con sesión iniciada. |
| `metadata_get_resource_metadata` | Busque los campos, métricas y segmentos que puede usar para un recurso de [!DNL Google Ads], como una campaña o un grupo de anuncios. |
| `search_search` | Recuperar la configuración de [!DNL Google Ads] o los datos de informes. |

## Iniciar sesión como miembro {#sign-in-as-a-member}

Cuando un administrador configura el conector, cada miembro inicia sesión con su propia cuenta de [!DNL Google].

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Usuario]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Google Ads]**, seleccione **[!UICONTROL Iniciar sesión]**.

   Si la tarjeta muestra **[!UICONTROL No configurado]** o el conector no está disponible, pídale al administrador que [configure el conector](#configure-organization).

1. En la pantalla [!DNL Google] **[!UICONTROL Elija una cuenta]**, seleccione la cuenta con acceso a sus cuentas de [!DNL Google Ads] o seleccione **[!UICONTROL Usar otra cuenta]**. A continuación, complete los pasos de inicio de sesión que su organización requiera, como inicio de sesión único (SSO), autenticación multifactor (MFA) o verificación de identidad.

   Los pasos y su orden dependen de la organización y de las directivas de la cuenta.

   ![Google Elija una pantalla de cuenta para Adobe Experience Platform, que enumera dos cuentas censuradas y la opción Usar otra cuenta.](./assets/google-ads/member-choose-account.png){width="500" zoomable="yes"}

1. Revisa la cuenta seleccionada y la aplicación que estás autorizando y, a continuación, selecciona **[!UICONTROL Continuar]**.

   [!DNL Google] muestra el nombre de la aplicación como [!DNL Adobe Experience Platform]. Si ya ha usado la aplicación, [!DNL Google] muestra que está iniciando sesión de nuevo. Los usuarios nuevos pueden ver diferentes indicadores.

   ![Pantalla de Google que indica que está iniciando sesión de nuevo en Adobe Experience Platform, con una cuenta censurada y los botones Cancelar y Continuar.](./assets/google-ads/member-continue.png){width="500" zoomable="yes"}

1. Revise la solicitud de acceso y, a continuación, seleccione **[!UICONTROL Continuar]**.

   ![Pantalla de Google que indica que Adobe Experience Platform desea acceder a su cuenta de Google, con una cuenta censurada, un aviso de que la aplicación ya tiene acceso y los botones Cancelar y Continuar.](./assets/google-ads/member-consent.png){width="500" zoomable="yes"}

   >[!IMPORTANT]
   >
   >Continúe solo si reconoce la aplicación y si su organización aprueba el acceso solicitado.

1. Después de que [!DNL Google] le devuelva a Coworker, abra los detalles del conector **[!UICONTROL google-ads]**. Confirme que el conector muestra **[!UICONTROL Conectado]** y **[!UICONTROL iniciado sesión]**.

   Mantenga **[!UICONTROL Resource identifier]** en su valor predeterminado a menos que su administrador le indique lo contrario. Este campo establece la audiencia de token que se envía al iniciar sesión. Para volver al valor predeterminado, borre el campo y seleccione **[!UICONTROL Guardar identificador de recurso]**.

   ![detalles del conector google-ads que muestran un estado Conectado, un estado Firmado en conexión con los botones Cerrar sesión y Actualizar y el campo Identificador de recurso](./assets/google-ads/member-connected.png){width="700" zoomable="yes"}.

1. Seleccione **[!UICONTROL Test]** para comprobar que el compañero puede descubrir las herramientas del conector. A continuación, revisa **[!UICONTROL Herramientas habilitadas por tu administrador]** para ver las herramientas que puedes usar.

   **[!UICONTROL Prueba]** está disponible después de que inicies sesión.

   ![Herramientas habilitadas por su sección de administración que enumeran las tres herramientas de Google Ads y sus descripciones.](./assets/google-ads/member-tools.png){width="700" zoomable="yes"}

Para desconectar tu cuenta de [!DNL Google] del conector, selecciona **[!UICONTROL Cerrar sesión]**. Los detalles del conector también muestran la configuración **[!UICONTROL Tiempo de espera de herramienta]** y un control **[!UICONTROL Actualizar]**.

El estado **[!UICONTROL Conectado]** no confirma el acceso a una cuenta de publicidad específica o que cada informe se ejecute correctamente. Para confirmar tu acceso, [comprueba el acceso a tu cuenta de publicidad](#check-ad-account-access).

## Compruebe el acceso a su cuenta de publicidad {#check-ad-account-access}

Para confirmar qué cuentas de [!DNL Google Ads] puede utilizar, inicie una conversación y escriba un mensaje.

Mensaje de ejemplo:

* &quot;¿A qué cuentas de Google Ads puedo acceder?&quot;

El compañero de trabajo usa la herramienta `customers_list_accessible_customers` para enumerar los ID de cliente a los que su cuenta de [!DNL Google] puede acceder directamente. Se trata de una comprobación de acceso a la cuenta, no de un informe de rendimiento. Si utiliza una cuenta de administrador, la lista no incluye todas las cuentas incluidas en ella.

Antes de solicitar un informe, haga lo siguiente:

* Elija una cuenta de la lista.
* Especifique un intervalo de fechas con una fecha de inicio y otra de finalización.
* Pida a sus compañeros que busquen los campos y las métricas disponibles para el informe.

## Solucionar problemas de acceso {#troubleshoot-access}

Si no puede obtener acceso a los datos de [!DNL Google Ads], consulte lo siguiente con el administrador:

| Área | Qué comprobar |
| --- | --- |
| Cuenta de [!DNL Google] | Ha iniciado sesión con la cuenta [!DNL Google] que tiene acceso a la cuenta [!DNL Google Ads]. |
| Permisos de cuenta | Su cuenta de [!DNL Google] tiene permisos para las cuentas de [!DNL Google Ads] que desea usar. |
| Cuentas del responsable | Si accede a una cuenta a través de una cuenta de responsable, el administrador confirma la configuración necesaria de la cuenta de responsable. |
| Selección de herramientas | El administrador habilitó las herramientas que necesita en **[!UICONTROL Herramientas disponibles para los usuarios]**. |
| Identificador de recurso | El **[!UICONTROL identificador de recurso]** utiliza el valor predeterminado, a menos que el administrador le indique lo contrario. |
