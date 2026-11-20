---
title: Conector Externo De Amazon Ads
description: Obtenga información sobre cómo configurar el conector externo de Amazon Ads en CX Enterprise Coworker para su organización e iniciar sesión con Amazon para utilizar las herramientas de Amazon Ads en el chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 80dda0b442d6c7fe560c965b985f58173b73fe13
workflow-type: tm+mt
source-wordcount: '3078'
ht-degree: 1%
---

# Conector externo de Amazon Ads {#amazon-ads}

Use el conector externo [!DNL Amazon Ads] para trabajar con los datos [!DNL Amazon Ads] en Adobe CX Enterprise Coworker. Una vez configurado el conector, pregunte a su compañero a qué cuentas de publicidad puede acceder y revise campañas, informes, facturación y otra información de la cuenta. El conector es un servidor de Protocolo de contexto de modelo (MCP) alojado por [!DNL Amazon].

>[!AVAILABILITY]
>
>El conector externo [!DNL Amazon Ads] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene tres partes independientes:

* **[!DNL Amazon]preparación:** Un administrador de cuentas de [!DNL Amazon Ads] proporciona a cada miembro acceso a las cuentas publicitarias que necesitan. Si su organización utiliza su propia aplicación OAuth, el propietario de la aplicación confirma su aprobación y registra la URL de redireccionamiento de Coworker.
* **Configuración de la organización:** Un administrador de Coworker configura el conector una vez para toda la organización. El administrador elige una región, una aplicación de OAuth y las herramientas que pueden utilizar los miembros.
* **Inicio de sesión de miembro:** Cada miembro inicia sesión con su propia cuenta de [!DNL Amazon]. Los miembros solo pueden tener acceso a las cuentas publicitarias para las que su cuenta de [!DNL Amazon] tiene permiso de uso.

Al guardar la configuración de la organización, no se inicia sesión en ningún miembro ni se conceden permisos de [!DNL Amazon Ads]. Cada miembro ya debe tener el acceso requerido en [!DNL Amazon Ads] y debe iniciar sesión por separado.

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Acceso de compañero:** Cuenta con permiso para administrar conectores de organización en una organización donde el conector [!DNL Amazon Ads] está disponible.
* **Cuentas de Advertising:** Las cuentas publicitarias que planea usar y su región [!DNL Amazon Ads], así como los miembros con los permisos necesarios para dichas cuentas. Para obtener más información, consulte [Conceder acceso a la cuenta publicitaria](#grant-member-access).
* **Una decisión de aplicación de OAuth:** Elija entre las siguientes opciones:
  * **Aplicación OAuth administrada por Adobe:** Adobe administra el registro de la aplicación y sus credenciales. La aplicación administrada debe estar disponible en su entorno.
  * **Su propia aplicación OAuth:** Una aplicación [!DNL Login with Amazon] ha aprobado la API [!DNL Amazon Ads], su ID de cliente OAuth y secreto de cliente, y un administrador que puede editar su perfil de seguridad. Un perfil de seguridad registrado por sí solo no concede la aprobación de la API [!DNL Amazon Ads].

La configuración guiada admite una conexión [!DNL Amazon Ads] y una región por organización. Cada miembro inicia sesión con su propia cuenta de [!DNL Amazon]. La aplicación administrada por Adobe es un registro de aplicación compartida, no una cuenta compartida de [!DNL Amazon].

## Preparación del acceso a Amazon {#prepare-amazon}

Antes de configurar el conector en Coworker, prepare la aplicación y el acceso a la cuenta en [!DNL Amazon]. El acceso a la configuración de la aplicación y el acceso a los datos publicitarios son independientes. Los miembros que utilizan el conector no necesitan permiso para editar la aplicación.

### Confirmar aprobación de aplicación {#confirm-app-approval}

Si usa su propia aplicación OAuth, pídale al propietario de la aplicación que confirme el perfil de seguridad [!DNL Login with Amazon] correcto y su aprobación de API [!DNL Amazon Ads]. La creación de un perfil de seguridad o la visualización de la aplicación en la consola para desarrolladores de [!DNL Amazon] no reemplaza la aprobación de la API de [!DNL Amazon Ads]. Para obtener más información, consulte [Introducción al MCP de Amazon Ads](https://advertising.amazon.com/API/docs/en-us/mcp/get-started) y [Conexión al servidor MCP de Ads mediante OAuth](https://advertising.amazon.com/API/docs/en-us/mcp/oauth) en la documentación de [!DNL Amazon Ads].

Para su propia aplicación, Coworker aplica la siguiente configuración automáticamente. Estos valores no se introducen en el cuadro de diálogo de configuración.

| Configuración | Valor |
| --- | --- |
| URL de autorización | `https://lwa.amazon.com/ap/oa` |
| URL de token | `https://api.amazon.com/auth/o2/token` |
| Ámbito solicitado | `advertising::campaign_management` |
| Clave de revisión para intercambio de código (PKCE) | Habilitado |
| Autenticación de cliente de extremo de token | `client_secret_post`, como cliente confidencial |
| Registro dinámico de clientes | No compatible |
| Tiempo de espera de herramienta y transporte | HTTP transmisible, 60 segundos |

Si utiliza la aplicación OAuth administrada por Adobe, Adobe administra el registro de la aplicación y sus credenciales. No es necesario que complete este paso ni que introduzca las credenciales de la aplicación.

### Registrar la URL de redireccionamiento {#register-redirect-url}

Si usa su propia aplicación de OAuth, registre la URL de redireccionamiento de Coworker en la aplicación [!DNL Login with Amazon]:

1. En Colaborador, abre el cuadro de diálogo **[!UICONTROL Configuración de Amazon Ads para tu organización]**, tal como se describe en [Configuración del conector para tu organización](#configure-organization). Seleccione **[!UICONTROL Usar mi propia aplicación OAuth]** para mostrar la **[!UICONTROL URL de redireccionamiento]** y, a continuación, copie el valor completo.
1. En [Iniciar sesión con la consola de Amazon](https://developer.amazon.com/loginwithamazon/console/site/lwa/overview.html), busque el perfil de seguridad de su aplicación. Seleccione **[!UICONTROL Administrar]** > **[!UICONTROL Configuración web]** y, a continuación, seleccione **[!UICONTROL Editar]**.
1. Agregue la URL de redireccionamiento completa en **[!UICONTROL URL de retorno permitidas]** y, a continuación, guarde los cambios. Si otros equipos comparten la aplicación, mantenga las direcciones URL existentes y obtenga la aprobación del propietario de la aplicación antes de cambiar la configuración.
1. Tenga en cuenta el ID de cliente de OAuth y el secreto de cliente del mismo perfil de seguridad. Los escribes al [configurar el conector](#configure-organization).

Copie siempre la dirección URL de redireccionamiento del cuadro de diálogo Compañero de trabajo en el entorno que está configurando. No cree la dirección URL usted mismo, utilice la dirección URL de la página Compañero de trabajo en su explorador ni reutilice una dirección URL de redireccionamiento desde otro entorno o cliente de MCP. Para obtener más información, consulte [Registrarse para iniciar sesión con Amazon](https://developer.amazon.com/docs/login-with-amazon/register-web.html) en la documentación de [!DNL Amazon].

>[!NOTE]
>
>Si la **[!UICONTROL URL de redireccionamiento]** muestra solamente la ruta de acceso `/connectors/oauth/callback`, su entorno aún no admite el inicio de sesión para este conector. No registre una ruta de acceso parcial ni adivine el nombre de host. Póngase en contacto con su representante de Adobe.

### Conceder acceso a la cuenta publicitaria {#grant-member-access}

Un administrador de cuentas de [!DNL Amazon Ads] invita a cada miembro a las cuentas publicitarias que necesita:

1. Abra la consola [Amazon Ads](https://advertising.amazon.com/) y, a continuación, seleccione **[!UICONTROL Cambiar cuenta]** para elegir la cuenta del anunciante o del administrador.
1. Seleccione **[!UICONTROL Administración]** > **[!UICONTROL Acceso y configuración de la cuenta]** > **[!UICONTROL Usuarios]** > **[!UICONTROL Invitar usuarios]**. Las opciones exactas dependen del tipo de cuenta. Invite a la cuenta [!DNL Amazon] del miembro, con los permisos mínimos para las tareas que planea realizar.
1. Para una cuenta de administrador, compruebe si el acceso cubre toda la cuenta de administrador o solo los anunciantes vinculados seleccionados. Pida al miembro que acepte la invitación con la misma cuenta de [!DNL Amazon] que utiliza para el Compañero de trabajo.
1. Confirme que el miembro puede seleccionar el anunciante en [!DNL Amazon Ads]. Tenga en cuenta el nombre de cuenta, la región y el ID del anunciante esperados en un registro interno aprobado para que pueda confirmar el acceso más adelante en Compañero de trabajo.

Elija la función con menos privilegios que admita las tareas que planea. No conceda acceso de administrador solo para que una comprobación de acceso se realice correctamente. El acceso a una instancia de [!DNL Amazon Marketing Cloud] es independiente del acceso a las campañas del anunciante. Para obtener más información, consulte la siguiente documentación de [!DNL Amazon Ads]:

* [Administrar usuarios en una cuenta de responsable](https://advertising.amazon.com/help/G4M4JGKGV2VAY9JC)
* [Agregar o quitar usuarios de su cuenta](https://advertising.amazon.com/help/GDQVHVQMY9F88PCA)
* [Comprender los permisos de cuenta](https://advertising.amazon.com/help/GM4EFDQQPG9LGL3F)
* [Permisos de API de Amazon Ads](https://advertising.amazon.com/API/docs/en-us/guides/account-management/permissions)

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL Amazon Ads] a disposición de todos los miembros de la organización. Los cambios en la página de organización se aplican a todos los usuarios de la organización. Los miembros no pueden configurar la conexión de organización desde el ámbito **[!UICONTROL Usuario]**.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Amazon Ads]**, seleccione **[!UICONTROL Configurar]**.

   Se abre el cuadro de diálogo **[!UICONTROL Configuración de Amazon Ads para su organización]**, con las secciones **[!UICONTROL Detalles de conexión]**, **[!UICONTROL Herramientas disponibles para los usuarios]** y **[!UICONTROL Acceso y permisos]**. Después de guardar la configuración, la tarjeta muestra **[!UICONTROL Configuración guardada]** y **[!UICONTROL Configurar]** cambios en **[!UICONTROL Ver configuración]**.

1. En **[!UICONTROL Región de Amazon Ads]**, seleccione la región que coincida con sus cuentas publicitarias. Compañero de trabajo muestra la URL del servidor MCP para la región debajo de la selección.

   | Región | URL del servidor MCP |
   | --- | --- |
   | [!UICONTROL Norteamérica] (predeterminado) | `https://advertising-ai.amazon.com/mcp` |
   | [!UICONTROL Europa] | `https://advertising-ai-eu.amazon.com/mcp` |
   | [!UICONTROL Lejano Oriente] | `https://advertising-ai-fe.amazon.com/mcp` |

   La configuración guiada guarda una región. Para cambiar de región más adelante, quite la conexión y configúrela de nuevo. A continuación, todos los miembros deben volver a iniciar sesión, por lo que deberá planificar el cambio antes de interrumpir la conexión de trabajo.

1. Seleccione una **[!UICONTROL aplicación de OAuth]**:

   * **[!UICONTROL Aplicación OAuth administrada por Adobe]:** Adobe proporciona la aplicación [!DNL Amazon Ads], por lo que no es necesario que especifique las credenciales de la aplicación. Cada miembro inicia sesión con su propia cuenta de [!DNL Amazon] y autoriza la aplicación de Adobe.

     ![Cuadro de diálogo Configuración de Amazon Ads para su organización con la región de Norteamérica, la aplicación OAuth administrada por Adobe seleccionada y los grupos de herramientas contraídos.](./assets/amazon-ads/org-configure.png){width="500" zoomable="yes"}

   * **[!UICONTROL Usar mi propia aplicación OAuth]:** Cada miembro autoriza la aplicación de su organización con su propia cuenta de [!DNL Amazon]. En **[!UICONTROL Su aplicación de Amazon]**, complete los siguientes pasos:

     1. Asegúrese de que la **[!UICONTROL URL de redireccionamiento]** esté registrada en la aplicación. Para obtener más información, consulte [Registrar la dirección URL de redireccionamiento](#register-redirect-url).
     1. Escriba **[!UICONTROL el id. de aplicación de Amazon]** y **[!UICONTROL el secreto de aplicación de Amazon]**. El campo **[!UICONTROL ID de aplicación de Amazon]** toma el ID de cliente de OAuth, no un ID de anunciante, un ID de cuenta de administrador o el ID de aplicación [!DNL Amazon]. El compañero almacena los valores que se introducen como secretos de la organización.
     1. Para reutilizar las credenciales guardadas, seleccione **[!UICONTROL Usar un secreto existente]**. A continuación, seleccione el **[!UICONTROL Secreto que contiene el ID de la aplicación]** y el **[!UICONTROL Secreto que contiene el secreto de la aplicación]**. Si su organización aún no tiene secretos, agréguelos en **[!UICONTROL Configuración]** > **[!UICONTROL Secretos]**.

     Ambas credenciales son obligatorias. Introduzca valores de credencial solo en los campos seguros. No introduzca una referencia secreta en un campo de valor sin formato.

1. En **[!UICONTROL Herramientas disponibles para los usuarios]**, expanda cada grupo de herramientas y seleccione las herramientas que su organización necesita. De manera predeterminada, solo se seleccionan las herramientas `ads_accounts-list_ads_accounts` y `ads_accounts-get_ads_account`. Para cambiar todas las herramientas a la vez, usa **[!UICONTROL Seleccionar todo]** o **[!UICONTROL Borrar todo]**. Debe seleccionar al menos una herramienta.

   Comience con las dos herramientas de la cuenta para realizar una primera comprobación de acceso. Seleccione las herramientas de campaña e informes solo cuando su organización las necesite y las apruebe. Para obtener más información, consulte [Grupos de herramientas](#tool-groups).

1. Seleccione **[!UICONTROL Guardar conexión]** y, a continuación, revise los detalles guardados del conector **[!UICONTROL amazon-ads]**.

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Source]** | La URL del servidor MCP para la región seleccionada. |
   | **[!UICONTROL Autenticación]** | El método de autenticación `amazon-ads_login`. |
   | **[!UICONTROL Tiempo de espera de herramienta]** | El tiempo que el Compañero de trabajo espera una respuesta de la herramienta. |
   | **[!UICONTROL Conexión]** | La aplicación OAuth en uso y su propio estado de inicio de sesión. |
   | **[!UICONTROL Herramientas]** | Las herramientas seleccionadas para los miembros, con los controles **[!UICONTROL Seleccionar todo]** y **[!UICONTROL Borrar]** y un recuento de las herramientas seleccionadas. |

   ![Se guardaron los detalles del conector amazon-ads que muestran el origen de Norteamérica, el método de autenticación, un objeto Firmado en conexión con los botones Cerrar sesión y Actualizar, y dos de las 47 herramientas seleccionadas.](./assets/amazon-ads/org-details.png){width="700" zoomable="yes"}

Al guardar no se inicia sesión en usted ni en ningún miembro de [!DNL Amazon]. El estado de **[!UICONTROL Connection]** en los detalles del conector hace referencia a su propia conexión, no a la organización. Para comprobar la conexión, selecciona **[!UICONTROL Iniciar sesión]** en la página de detalles del conector para iniciar sesión con tu propia cuenta de [!DNL Amazon] y luego selecciona **[!UICONTROL Probar]**. El resultado muestra **[!UICONTROL Conexión correcta]** o **[!UICONTROL Conexión fallida]**, con las herramientas o errores devueltos. Un resultado correcto no confirma el acceso a una operación de anunciante específica.

Para cambiar las herramientas disponibles para los miembros más adelante, actualice la selección en **[!UICONTROL Herramientas disponibles]** con **[!UICONTROL Seleccionar todo]** o **[!UICONTROL Borrar]** y, a continuación, seleccione **[!UICONTROL Guardar selección de herramientas]**. Debe permanecer seleccionada al menos una herramienta. Los miembros no pueden cambiar la selección de herramientas.

Para dejar de ofrecer el conector a tu organización, selecciona **[!UICONTROL Quitar]** en la página de detalles del conector.

### Grupos de herramientas {#tool-groups}

El conector [!DNL Amazon Ads] organiza sus herramientas en los siguientes grupos:

| Grupo de herramientas | Herramientas | Qué hacen las herramientas |
| --- | --- | --- |
| [!UICONTROL Administración y direccionamiento de campañas] | 7 | Consulte campañas, grupos de anuncios, anuncios, destinatarios, portafolios y sus asociaciones, y compruebe la idoneidad del producto. |
| [!UICONTROL Cuentas y organización] | 6 | Enumerar y obtener cuentas publicitarias, y consultar vínculos de anunciantes y cuentas, cuentas de administrador y cuentas de prueba. |
| [!UICONTROL Acceso y seguridad de usuario] | 5 | Enumere los usuarios, las funciones, los permisos y las invitaciones, y obtenga una invitación. |
| [!UICONTROL Creación de informes y análisis] | 1 | Recupere un informe. No se incluye la creación de informes. |
| [!UICONTROL Amazon Marketing Cloud] | 6 | Lea los flujos de trabajo y las fuentes de datos, y el estado y las direcciones URL de descarga de las ejecuciones existentes. No se incluye la ejecución del flujo de trabajo. |
| [!UICONTROL Resúmenes de facturación y financieros] | 4 | Leer facturas, resúmenes de facturas, uso del perfil de facturación y notificaciones de facturación. |
| [!UICONTROL Amazon Live] | 12 | Leer información de canal, difusión, emisión en directo, medios, carrusel y código de promoción. |
| [!UICONTROL Elegibilidad y ofertas] | 6 | Lea la idoneidad del programa y el producto, las ofertas y recompensas de promoción y los términos de la información del token. |

Las herramientas de cada grupo pueden cambiar a medida que [!DNL Amazon] actualiza el conector. La configuración guiada guarda la lista exacta de herramientas que seleccione, incluso cuando seleccione cada herramienta. Las herramientas que deja sin seleccionar y las que el servidor agrega posteriormente no estarán disponibles para los miembros hasta que las seleccione.

>[!IMPORTANT]
>
>La lista de herramientas de configuración está depurada para leer datos, pero el conector en su conjunto no es de solo lectura. Los miembros autorizan el ámbito `advertising::campaign_management`, que es más amplio que la lista de configuración. Al probar la conexión, la lista de herramientas también puede incluir las herramientas devueltas por el servidor. Revise cada definición de herramienta y los permisos de [!DNL Amazon Ads] de sus miembros antes de seleccionar más herramientas.

## Iniciar sesión como miembro {#sign-in-as-a-member}

Cuando un administrador configura el conector, cada miembro inicia sesión con su propia cuenta de [!DNL Amazon]. No necesita un secreto de aplicación o un token de acceso para iniciar sesión.

>[!NOTE]
>
>Si el conector indica que el inicio de sesión y **[!UICONTROL Test]** aún no están disponibles en su entorno, deténgase aquí. La configuración de la organización por sí sola no hace que el inicio de sesión de miembros esté disponible. Póngase en contacto con su representante de Adobe.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Usuario]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**. Encuentra la tarjeta **[!UICONTROL Amazon Ads]**.

1. Si la tarjeta muestra **[!UICONTROL No configurado]**, pídale al administrador que [configure el conector](#configure-organization). Los miembros no pueden configurar el conector.

1. Cuando la tarjeta muestre **[!UICONTROL Sin sesión iniciada]**, selecciona **[!UICONTROL Iniciar sesión]**. Habilite la ventana emergente de inicio de sesión y, a continuación, inicie sesión con la cuenta de [!DNL Amazon] que tiene acceso a sus cuentas publicitarias.

1. Complete las [!DNL Amazon] solicitudes de autenticación, como la autenticación multifactor (MFA) y la solicitud de consentimiento. Revise el nombre de la aplicación y el acceso solicitado antes de aprobarla.

   Con la aplicación administrada por Adobe, puede autorizar la aplicación de Adobe. Con la aplicación de su propia organización, autoriza esa aplicación en su lugar.

   >[!IMPORTANT]
   >
   >Continúe solo si reconoce la aplicación y si su organización aprueba el acceso solicitado.

1. Vuelva a Compañero de trabajo y confirme que la tarjeta muestra **[!UICONTROL Sesión iniciada]**. Seleccione **[!UICONTROL Ver detalles]** y, a continuación, revise **[!UICONTROL las herramientas habilitadas por el administrador]**. Los miembros pueden ver las herramientas, pero no pueden cambiarlas ni quitar la conexión de la organización.

1. Seleccione **[!UICONTROL Prueba]** para comprobar la detección de la herramienta y el estado de la conexión.

Una ventana emergente cerrada por sí sola no confirma que el inicio de sesión se haya realizado correctamente. Una prueba realizada correctamente no confirma el acceso a todos los anunciantes, campañas, informes o instancias de [!DNL Amazon Marketing Cloud]. Cuando un administrador inicia sesión, los demás miembros no inician sesión.

Para desconectar tu cuenta de [!DNL Amazon] del conector, selecciona **[!UICONTROL Cerrar sesión]**.

## Compruebe el acceso a su cuenta publicitaria {#check-account-access}

Para confirmar qué cuentas publicitarias puede utilizar, ejecute una comprobación de solo lectura. Use una cuenta de prueba aprobada y asegúrese de que el administrador habilitó las herramientas `ads_accounts-list_ads_accounts` y `ads_accounts-get_ads_account`. A continuación, inicie una conversación e introduzca un mensaje.

Mensaje de ejemplo:

* &quot;Con Amazon Ads, enumere hasta cinco cuentas publicitarias a las que pueda acceder en la región configurada. Si se devuelven esos campos, se muestra únicamente el nombre de cuenta, el ID de cuenta y la región. No cree, actualice, elimine, inicie, ejecute flujos de trabajo, genere informes ni cambie permisos. Si no se admite un límite de listado, resuma solo cinco resultados y no solicite páginas adicionales.&quot;

Confirme que el resultado incluye la cuenta que espera. Para ver más detalles, pídale al compañero que obtenga los detalles de esa cuenta, usando el ID de cuenta del resultado. No adivine los ID de cuenta y no solicite campañas solo para probar el inicio de sesión.

Una lista de cuentas vacía no siempre significa que el conector no funcione. Compruebe la cuenta de [!DNL Amazon] con la que inició sesión, las invitaciones aceptadas, los anunciantes vinculados que cubre una cuenta de administrador y la región configurada. Una cuenta de prueba sin campañas también puede devolver una lista de campañas vacía. Si una herramienta que necesita no está habilitada, pregunte al administrador. No utilice una herramienta que cambie datos como sustituto.

## Solucionar problemas de acceso {#troubleshoot-access}

Si no puede obtener acceso a los datos de [!DNL Amazon Ads], consulte lo siguiente con el administrador:

| Problema | Qué comprobar |
| --- | --- |
| Falta la tarjeta **[!UICONTROL Amazon Ads]** o **[!UICONTROL Configure]** | Confirme que el conector está disponible para su organización y que tiene permiso para administrar conectores de organización. Los miembros deben esperar la configuración de la organización. |
| La configuración administrada por Adobe guarda los archivos, pero el inicio de sesión falla | Póngase en contacto con su representante de Adobe para confirmar que la aplicación administrada por Adobe está disponible en su entorno. Una operación de guardado correcta no confirma esto. |
| La URL de redireccionamiento no coincide | Comparar la **[!UICONTROL URL de redireccionamiento]** completa del cuadro de diálogo Compañero de trabajo con las **[!UICONTROL URL de retorno permitidas]** en [!DNL Login with Amazon], incluidos el esquema, el host y la ruta. No utilice una URL de redireccionamiento de otro cliente, región o entorno de MCP, ni la URL de la página Compañero de trabajo en su explorador. |
| La **[!UICONTROL URL de redireccionamiento]** solo muestra `/connectors/oauth/callback` | Su entorno aún no muestra la dirección URL de redireccionamiento completa ni admite el inicio de sesión y **[!UICONTROL Prueba]**. No registre una ruta de acceso parcial ni adivine el nombre de host. Póngase en contacto con su representante de Adobe. |
| No puede guardar su propia configuración de la aplicación OAuth | Introduzca el ID de cliente de OAuth y el secreto de cliente y mantenga al menos una herramienta seleccionada. Asegúrese de que el **[!UICONTROL ID de aplicación de Amazon]** sea el ID de cliente de OAuth, no un ID de anunciante ni el ID de aplicación [!DNL Amazon]. |
| Error de consentimiento o autorización de aplicación | Compruebe la aprobación de la API [!DNL Amazon Ads], el perfil de seguridad, el ID de cliente y el emparejamiento secreto, el registro de URL de redireccionamiento y la aplicación que se muestran en la pantalla de consentimiento. No comparta la dirección URL de consentimiento, el código de autorización ni los tokens cuando pida ayuda. |
| Ha iniciado sesión, pero las cuentas o herramientas se han denegado o están vacías | Compruebe la cuenta de [!DNL Amazon] con la que inició sesión, la invitación aceptada, los anunciantes vinculados que cubre una cuenta de administrador, la región configurada y los permisos que requiere la tarea. El acceso a la aplicación o a las herramientas de socios no confirma el acceso del anunciante. El acceso de [!DNL Amazon Marketing Cloud] es independiente. |
| [!DNL Amazon Ads] indica que la cuenta actual no puede tener acceso a una página | Seleccione **[!UICONTROL Cambiar cuenta]** y elija la cuenta de administrador o anunciante. Si falta la cuenta, pídale al administrador que compruebe que ha aceptado la invitación y que se le ha asignado la cuenta. Si la cuenta está presente pero la administración de usuarios no está disponible, pida al administrador que compruebe su función. |
| Falta una herramienta o no está disponible | Compruebe la selección de herramientas de su organización, las herramientas que devuelve el servidor y los permisos de [!DNL Amazon Ads]. Las herramientas que el servidor agrega posteriormente no se seleccionan automáticamente. De forma predeterminada, solo están habilitadas las dos herramientas de cuenta. |
| **[!UICONTROL Test]** informa de un conector personal con el mismo nombre | Un conector personal con el mismo nombre puede tener prioridad sobre el conector de organización. Siga las directrices que se muestran para eliminar o cambiar el nombre sólo del conector personal en conflicto, con la aprobación de su propietario. |
| La ventana emergente de inicio de sesión está bloqueada, no termina o el estado no se actualiza | Permita la ventana emergente y, a continuación, vuelva a Compañero de trabajo para comprobar el estado y los detalles del error. No dé por hecho que la ventana emergente ha cerrado o mostrado una página de aterrizaje. |
| Se agota el tiempo de espera de una herramienta o debe iniciar sesión repetidamente | Compruebe el tiempo de espera de **[!UICONTROL herramienta]** de 60 segundos, los detalles del error, la disponibilidad de la red y [!DNL Amazon], y la configuración de la aplicación. |
| Su compañero dice que la configuración no está habilitada o que se sigue configurando un nuevo secreto | Consulte el estado con su representante de Adobe. No vuelva a crear las credenciales repetidamente y no considere que un guardado fallido se ha realizado correctamente. |

Cuando contacte con el servicio de asistencia técnica de, incluya solo el texto de error, la hora del error, el entorno, la región seleccionada y la opción de aplicación OAuth. No comparta secretos de aplicaciones, tokens de acceso, códigos de autorización, el encabezado de autorización, parámetros de consulta de consentimiento o redirección o datos de cuenta de cliente.
