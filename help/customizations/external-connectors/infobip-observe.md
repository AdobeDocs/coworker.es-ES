---
title: Conector Externo De Infobip Observe
description: Aprenda a configurar el conector externo de Infobip Observe en CX Enterprise Coworker para su organización e inicie sesión con Infobip para utilizar las herramientas de Observe.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 382a5f6fd629b8b10468c0cfe4d41f050a7f3725
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 1%
---

# Conector externo de Infobip Observe {#infobip-observe}

Use el conector externo [!DNL Infobip Observe] para revisar el tráfico y los costos de [!DNL Infobip] en Adobe CX Enterprise Coworker. Una vez configurado el conector, pregunte al compañero acerca de las métricas de tráfico, el uso de la facturación, los registros de mensajes y el estado y los códigos de error. El conector es el servidor de Protocolo de contexto de modelo (MCP) [!DNL Observe] alojado por [!DNL Infobip].

>[!AVAILABILITY]
>
>El conector externo [!DNL Infobip Observe] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene dos partes independientes:

* **Configuración de la organización:** Un administrador configura el conector una vez para toda la organización y aprueba las herramientas que los miembros pueden utilizar.
* **Inicio de sesión de miembro:** Cada miembro inicia sesión con su propia cuenta de [!DNL Infobip]. Los miembros solo pueden tener acceso a los datos para los que su cuenta de [!DNL Infobip] tiene permiso de uso.

El conector no tiene inicio de sesión en una organización compartida. Cada miembro que utiliza el conector inicia sesión por separado. Al guardar la configuración de la organización, no se inicia sesión en ningún miembro ni se conceden permisos adicionales de [!DNL Infobip].

## Requisitos previos {#prerequisites}

El conector solo funciona con el servidor MCP [!DNL Infobip] [!DNL Observe]. No se conecta a los servidores MCP de mensajería, aprovisionamiento o administración de cuentas de [!DNL Infobip].

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Acceso de compañero:** Cuenta con permiso para administrar conectores de organización en una organización donde el conector [!DNL Infobip Observe] está disponible.
* Cuenta de **[!DNL Infobip]:** Una cuenta de [!DNL Infobip] aprobada con acceso a [!DNL Observe] en el centro de datos previsto. [!DNL Infobip] ofrece [!DNL Observe] MCP como característica de acceso anticipado. Confirme su derecho y la idoneidad de la cuenta con [!DNL Infobip].
* **Identidades de miembros:** miembros con sus propias cuentas de [!DNL Infobip] y permiso para acceder a los datos deseados.
* **Ámbito aprobado para pruebas:** Ámbito de prueba aprobado y datos no confidenciales antes de consultar los registros de facturación, tráfico o mensajes.

Para probar el conector, puede registrarse para obtener una cuenta de prueba gratuita de [!DNL Infobip]. Una cuenta de prueba no garantiza el aislamiento de los datos ni el coste cero. Para obtener más información, consulte [Uso de servidores MCP de Infobip](https://www.infobip.com/docs/mcp/using-mcp){target="_blank"} y [Observe MCP](https://www.infobip.com/docs/mcp/observe-mcp){target="_blank"} en la documentación de [!DNL Infobip].

>[!IMPORTANT]
>
>Nunca comparta contraseñas, claves API, tokens, códigos de autorización o URL de consentimiento y devolución de llamada en capturas de pantalla, chats o tickets de asistencia.

## Modelo de conexión e inicio de sesión {#connection-model}

El compañero aplica la siguiente configuración automáticamente. No cree una aplicación OAuth ni introduzca las credenciales de la aplicación.

| Configuración | Valor |
| --- | --- |
| URL del servidor | `https://mcp.infobip.com/observe` |
| Transporte | HTTP reproducible |
| Detección del servidor de autorización | `https://mcp.infobip.com/observe/.well-known/oauth-authorization-server` |
| Iniciar sesión | Cada miembro inicia sesión con OAuth mediante el registro dinámico de clientes |
| Configuración de OAuth | Detectado automáticamente. Los administradores no especifican un ID de cliente, secreto de cliente, ámbitos o extremos de OAuth. |
| Selección de herramientas | Cuatro herramientas aprobadas. Los administradores pueden limitar la selección. |

La detección de [!DNL Infobip] y el consentimiento de cada miembro determinan el acceso que recibe el colaborador. [!DNL Infobip] documenta los ámbitos `billing:usage:view`, `metrics:manage`, `messages-api:manage` y `error-codes:read` para el MCP [!DNL Observe]. Revise el acceso solicitado en la pantalla de consentimiento antes de aprobarlo.

[!DNL Infobip] también admite la autenticación de claves de API para el MCP [!DNL Observe] en otros clientes MCP. El compañero no utiliza claves API para este conector. Los miembros solo inician sesión con OAuth.

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL Infobip Observe] a disposición de todos los miembros de la organización. Los cambios en la página de organización se aplican a todos los usuarios de la organización. Los miembros no pueden configurar la conexión de la organización.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**.

1. Busque **[!UICONTROL Observador de Infobip]** y luego seleccione **[!UICONTROL Configurar]**.

1. En el cuadro de diálogo **[!UICONTROL Conectar Infobip Observe]**, revise la **[!UICONTROL URL del servidor]**, `https://mcp.infobip.com/observe`, corregida.

   No es necesario que introduzca un ID de cliente de OAuth, un secreto de cliente o ámbitos.

1. En **[!UICONTROL Herramientas disponibles para los usuarios]**, revise las cuatro herramientas seleccionadas inicialmente. Elimine cualquier herramienta que los miembros de su organización no deban utilizar. Debe quedar al menos una herramienta.

   Para obtener más información, consulte [Herramientas disponibles](#available-tools).

   ![Conecte el cuadro de diálogo Observar de Infobip que muestra la dirección URL del servidor, las cuatro herramientas disponibles para los usuarios, el aviso de acceso y permisos, la autenticación OAuth, la conexión HTTP y la configuración de tiempo de espera de la herramienta de 60 segundos.](./assets/infobip-observe/org-configure.png){width="500" zoomable="yes"}

1. Seleccione **[!UICONTROL Guardar conexión]**. A continuación, vuelva a abrir la configuración para comprobar que la selección de herramientas persiste.

Al guardar no se inicia sesión en usted ni en ningún miembro de [!DNL Infobip]. Para comprobar la conexión usted mismo, inicie sesión como se describe en [Iniciar sesión como miembro](#sign-in-as-a-member).

Para que las cuatro herramientas vuelvan a estar disponibles después de quitarlas, seleccione **[!UICONTROL Restaurar todas las herramientas]**. Esta opción restaura únicamente las cuatro herramientas aprobadas. El compañero no habilita las herramientas que [!DNL Infobip] agrega posteriormente. No puede guardar la configuración sin ninguna herramienta seleccionada.

### Herramientas disponibles {#available-tools}

El conector [!DNL Infobip Observe] proporciona las siguientes herramientas. [!DNL Infobip] puede cambiar los límites de cada herramienta, así que compruebe la documentación de [!DNL Infobip] antes de confiar en ellos.

| Herramienta | Objetivo | Límites |
| --- | --- | --- |
| `get_traffic_performance_metrics` | Métricas de tráfico, envío y participación agregadas. | Hasta 366 días de datos. Las ventanas por hora cubren hasta 14 días y las ventanas diarias, hasta 93 días. Devuelve los datos de la cuenta con sesión iniciada de forma predeterminada. Incluya subcuentas explícitamente. |
| `get_billing_usage_costs` | Uso y costes que coinciden con las facturas. | Los dos meses naturales actuales y anteriores. Incluye la jerarquía de cuentas completa de forma predeterminada. Los datos de un mes son provisionales hasta el quinto día del mes siguiente. |
| `get_message_logs` | Registros para mensajes individuales. | Las últimas 48 horas. Los registros pueden incluir identificadores de destinatarios, información personal y contenido de mensajes. |
| `look_up_status_and_error_codes` | Descripciones de estados conocidos y nombres de códigos de error. | Hasta 50 nombres por solicitud. [!DNL Infobip] puede omitir nombres desconocidos en los resultados. |

Los resultados están limitados a un centro de datos [!DNL Infobip]. La selección de herramientas controla qué herramientas pueden utilizar los miembros en Coworker. No limita el acceso de [!DNL Infobip] que los miembros conceden al iniciar sesión, la jerarquía de cuentas o los permisos que [!DNL Infobip] aplica.

>[!IMPORTANT]
>
>Los registros de mensajes pueden contener datos personales, como identificadores de destinatario y contenido de mensajes. La información de facturación es confidencial y cubre la jerarquía de cuentas completa de forma predeterminada. Habilite estas herramientas solo cuando su organización apruebe su uso. Utilice filtros de cuenta explícitos y aprobados y consultas limitadas.

## Iniciar sesión como miembro {#sign-in-as-a-member}

Cuando un administrador configura el conector, cada miembro inicia sesión con su propia cuenta de [!DNL Infobip]. Su inicio de sesión solo le pertenece a usted. Otros miembros no usan sus credenciales.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Usuario]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**. Buscar **[!UICONTROL Observador De Infobip]**.

   Si la tarjeta muestra **[!UICONTROL No configurado]** y **[!UICONTROL Aún no está disponible. El administrador debe configurar esto.]**, pídale al administrador que [configure el conector](#configure-organization).

1. Seleccione **[!UICONTROL Iniciar sesión]** y use la cuenta [!DNL Infobip] deseada. Complete el inicio de sesión único (SSO), la autenticación de varios factores (MFA) y las indicaciones de consentimiento. Antes de realizar la aprobación, revise el acceso solicitado, la cuenta y el centro de datos.

1. Vuelva a Compañero de trabajo y abra los detalles del conector. Revise las herramientas que ha activado el administrador.

   Los miembros pueden ver las herramientas, pero no pueden cambiar la configuración de la organización.

1. Seleccione **[!UICONTROL Probar conexión]**.

   Una prueba correcta confirma que el compañero puede conectarse y enumerar las herramientas. No confirma que todas las herramientas se ejecuten correctamente.

1. Si está autorizado y el administrador habilitó la herramienta `look_up_status_and_error_codes`, ejecute la búsqueda en [Compruebe su conexión](#check-connection).

1. Para desconectar tu cuenta de [!DNL Infobip] del conector, selecciona **[!UICONTROL Cerrar sesión]**.

   Cerrar sesión no necesariamente revoca el acceso que concedió en [!DNL Infobip].

## Compruebe su conexión {#check-connection}

Para confirmar que el conector funciona con su cuenta, ejecute una búsqueda de solo lectura. Asegúrese de que el administrador habilitó la herramienta `look_up_status_and_error_codes`. A continuación, inicie una conversación e introduzca un mensaje.

Mensaje de ejemplo:

* &quot;Utilizando Infobip Observe, busque el código de estado NO_ERROR y describa lo que significa. No consulte las métricas de tráfico, la facturación ni los registros de mensajes&quot;.

Confirme que el resultado incluye una descripción de `NO_ERROR` sin un mensaje de error. Una búsqueda correcta no confirma que las herramientas de tráfico, facturación o registro de mensajes funcionen para la cuenta. No consulte los registros de facturación o de mensajes solo para probar la conexión.

## Solucionar problemas de acceso {#troubleshoot-access}

Si no puede obtener acceso a los datos de [!DNL Infobip], consulte lo siguiente con el administrador:

| Problema | Qué comprobar |
| --- | --- |
| Falta el conector **[!UICONTROL Infobip Observe]** | Confirme que el conector está disponible para su organización y que tiene permiso para administrar conectores de organización. Póngase en contacto con su representante de Adobe si es necesario. |
| Error de consentimiento o inicio de sesión | Compruebe la cuenta de [!DNL Infobip] que utilizó, sus derechos de [!DNL Observe] y el centro de datos. No comparta la dirección URL de consentimiento, la URL de devolución de llamada o los códigos de autorización cuando pida ayuda. |
| El inicio de sesión se realiza correctamente, pero falla una herramienta | Compruebe los permisos efectivos de [!DNL Infobip], la cuenta y el centro de datos con el que inició sesión y el error que devuelve [!DNL Infobip]. Un inicio de sesión correcto no confirma que una herramienta se ejecute correctamente. |
| Una herramienta no está disponible | Compruebe las herramientas que ha activado el administrador. El compañero no habilita automáticamente las nuevas herramientas de [!DNL Infobip]. |
| No puede guardar la configuración | Mantenga al menos una herramienta seleccionada. Para dejar de ofrecer el conector, elimínelo en su lugar. |
| Los resultados de facturación incluyen cuentas inesperadas | Los resultados de facturación incluyen la jerarquía de cuentas completa de forma predeterminada. Deténgase y, a continuación, revise los filtros y permisos de la cuenta aprobada. |
| Los registros de mensajes muestran datos confidenciales | Detenga la consulta y limite las consultas posteriores a datos aprobados no confidenciales. No pegue registros sin procesar en chats ni tickets de asistencia. |
| La búsqueda del código de estado se realiza correctamente, pero falla otra solicitud | Investigue la solicitud fallida por separado. Una búsqueda correcta no confirma que todas las herramientas o cuentas funcionen. |
