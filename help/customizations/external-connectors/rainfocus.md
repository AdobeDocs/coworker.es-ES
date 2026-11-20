---
title: Conector externo de RainFocus
description: Aprenda a configurar el conector externo de RainFocus en CX Enterprise Coworker para su organización e inicie sesión con RainFocus para utilizar las herramientas de datos de evento en el chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: e65f811f1e9c27de372ce924301b68f20ab9c1a6
workflow-type: tm+mt
source-wordcount: '2116'
ht-degree: 0%
---

# Conector externo RainFocus {#rainfocus}

Use el conector externo [!DNL RainFocus] para trabajar con los datos de evento [!DNL RainFocus] en Adobe CX Enterprise Coworker. Después de configurar el conector, pregunte a su compañero acerca de las sesiones, los asistentes y los atributos personalizados a los que puede tener acceso su cuenta de [!DNL RainFocus]. El conector usa un perfil MCP [!DNL RainFocus], un servidor de Protocolo de contexto de modelo (MCP) alojado por [!DNL RainFocus].

>[!AVAILABILITY]
>
>El conector externo [!DNL RainFocus] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene tres partes independientes:

* **[!DNL RainFocus]preparación:** Un administrador de [!DNL RainFocus] aprovisiona un perfil de MCP, habilita sus herramientas y proporciona la dirección URL del perfil. Cada miembro necesita una cuenta de [!DNL RainFocus] con la función correcta.
* **Configuración de la organización:** Un administrador de Coworker guarda la dirección URL del perfil de MCP una vez para toda la organización. El conector habilita una lista fija de herramientas de lectura.
* **Inicio de sesión de miembro:** Cada miembro inicia sesión con su propia cuenta de [!DNL RainFocus]. Los miembros solo pueden tener acceso a los datos que permiten su función [!DNL RainFocus] y el perfil.

Al guardar la configuración de la organización, no se inicia sesión en ningún miembro, no se conceden permisos de [!DNL RainFocus] ni se ejecuta una herramienta de datos de [!DNL RainFocus]. Cada miembro debe iniciar sesión por separado.

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Acceso de compañero de trabajo:** Una cuenta de administrador de compañero de trabajo con la configuración de la organización activada, en una organización donde el conector [!DNL RainFocus] está disponible.
* **Un perfil MCP:** Un perfil MCP [!DNL RainFocus] aprovisionado y su dirección URL de perfil HTTPS completa proporcionado por el administrador [!DNL RainFocus]. Para obtener más información, consulte [Obtener la dirección URL del perfil MCP](#get-profile-url).
* **Cuentas de miembro:** Para cada miembro, una cuenta de [!DNL RainFocus] con un rol de seguridad que proporciona acceso a los datos que necesitan.

No introduzca un ID de cliente, secreto de cliente ni token de acceso en Coworker. Cada miembro inicia sesión en [!DNL RainFocus] con su propia cuenta.

## Preparar acceso de [!DNL RainFocus] {#prepare-rainfocus}

Antes de configurar el conector en Coworker, prepare el perfil MCP y el acceso de los miembros en [!DNL RainFocus]. [!DNL RainFocus] es propietario del perfil, de las herramientas habilitadas, de los roles de los miembros y de los cargos. El compañero almacena la dirección URL del perfil y la lista de herramientas de su organización, así como el inicio de sesión de cada miembro.

### Obtener la dirección URL del perfil MCP {#get-profile-url}

[!DNL RainFocus] suele configurar perfiles MCP para sus clientes en función de sus requisitos. Si el administrador de [!DNL RainFocus] configura el perfil, el proceso es el siguiente:

1. En [!DNL RainFocus], abra **[!UICONTROL Integration Suite]** > **[!UICONTROL Perfiles activos]** > **[!UICONTROL Perfiles MCP]** y luego cree un perfil.
1. Habilite únicamente las herramientas que necesite su caso de uso y deje las demás herramientas desactivadas.
1. Copie la URL del servidor MCP generado. La dirección URL es específica del perfil.

Proporcione la URL completa al administrador de Coworker que configura el conector. No adivine un nombre de perfil ni cree la dirección URL usted mismo. Para obtener más información, consulte [Anuncio de perfiles MCP de RainFocus](https://www.rainfocus.com/company/news-press/rainfocus-launches-ai-agent-connectivity-for-event-data-with-mcp-profiles/).

### Confirmar acceso de miembro {#confirm-member-access}

Cada miembro inicia sesión con su propia cuenta de [!DNL RainFocus]. La función de seguridad de la cuenta y las herramientas habilitadas en el perfil controlan a qué datos puede acceder un miembro. Pida al administrador de [!DNL RainFocus] que confirme que cada miembro tiene la función con menos privilegios para sus tareas.

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL RainFocus] a disposición de todos los miembros de la organización. Los cambios en la página de organización se aplican a todos los usuarios de la organización. El ámbito **[!UICONTROL Org]** solo aparece para los administradores con la configuración de la organización activada.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**.
1. Busque la tarjeta **[!UICONTROL RainFocus]**, que tiene una etiqueta Beta y muestra **[!UICONTROL No configurado]**. Seleccione **[!UICONTROL Configurar]**.

1. En el cuadro de diálogo **[!UICONTROL Configurar RainFocus]**, escriba la **[!UICONTROL URL del perfil de desarrollo]**. Utilice la dirección URL completa del perfil MCP proporcionada por el administrador [!DNL RainFocus].

   La dirección URL debe comenzar con `https://`. No puede contener espacios, barras invertidas, una cadena de consulta (`?`), un fragmento (`#`), un nombre de usuario o contraseña, un puerto no predeterminado o `.` o `..` segmentos de ruta de acceso. Si la dirección URL no coincide con una regla, el colaborador muestra un mensaje que describe la regla. El compañero solo comprueba el formato de la dirección URL. No comprueba que el perfil existe ni que puede utilizarlo.

1. Revise las secciones **[!UICONTROL Acceso y permisos]** y **[!UICONTROL lista de permitidos fija de la herramienta de lectura]**. El conector habilita las 10 herramientas de lectura y no puede agregarlas, quitarlas ni editarlas en este cuadro de diálogo. Algunas herramientas devuelven datos personales de los asistentes o exportaciones masivas. Para obtener más información, consulte [Herramientas disponibles](#available-tools).

   ![Configure el cuadro de diálogo RainFocus que muestra el campo vacío URL del perfil de desarrollo, la sección Acceso y permisos, la lista de permitidos fija de la herramienta de lectura con 10 herramientas y el botón Guardar conexión.](./assets/rainfocus/org-configure.png){width="500" zoomable="yes"}

1. Seleccione **[!UICONTROL Guardar conexión]**. Mientras el Compañero guarda la conexión, no puede editar ni cancelar el formulario.

Si se produce un error al guardar, el cuadro de diálogo muestra **[!UICONTROL No se pudo guardar la conexión]** y conserva la dirección URL que ha especificado. Es posible que algunas opciones de configuración se guarden aunque se produzca un error al guardarlas. Vuelva a abrir la configuración y compruébela antes de intentarlo de nuevo. Para evitar cambios conflictivos, asegúrese de que solo un administrador configura el conector a la vez.

### Compruebe la configuración guardada {#verify-configuration}

Después de guardar la conexión, compruebe la configuración:

1. Después de guardar, el cuadro de diálogo abre los detalles del conector guardado. Vuelva a la lista **[!UICONTROL Conectores externos]** y confirme que la tarjeta **[!UICONTROL RainFocus]** muestra **[!UICONTROL Configuración guardada]** y **[!UICONTROL Ver configuración]**.
1. Vuelva a cargar la página y seleccione **[!UICONTROL Ver configuración]**.
1. Confirme los siguientes detalles:

   * **[!UICONTROL Source]** muestra la dirección URL del perfil que ingresaste.
   * **[!UICONTROL Autenticación]** está presente.
   * **[!UICONTROL Directiva de herramientas]** > **[!UICONTROL Patrones o nombres de herramientas permitidos]** enumera las mismas 10 herramientas que la sección [Herramientas disponibles](#available-tools).

1. Para comprobar tu propia conexión, selecciona **[!UICONTROL Probar]**. Si tu compañero te pide que inicies sesión, usa tu propia cuenta de [!DNL RainFocus], tal como se describe en [Iniciar sesión como miembro](#sign-in-as-a-member).

   **[!UICONTROL Prueba]** enumera las herramientas del servidor y actualiza el recuento de **[!UICONTROL Herramientas]**. Si el servidor no devuelve ninguna herramienta, los detalles muestran **[!UICONTROL 0 herramientas disponibles]**. Si la prueba falla, los detalles muestran **[!UICONTROL Error de conexión]**.

   ![Detalles guardados del conector de Rainocus que muestran una fuente censurada, el método de autenticación rainfocus_login, un botón No iniciado sesión con un botón de inicio de sesión y los botones Probar y Quitar.](./assets/rainfocus/org-details.png){width="700" zoomable="yes"}

Los controles de **[!UICONTROL Conexión]**, **[!UICONTROL Prueba]** e inicio de sesión de los detalles del conector solo se aplican a su propia conexión. Cuando inicia sesión como administrador, no se inicia la sesión de ningún miembro. Una prueba con éxito solo enumera las herramientas. La prueba no ejecuta una herramienta de datos [!DNL RainFocus] ni confirma que un miembro pueda obtener acceso a datos específicos.

Los detalles del conector no tienen opción de editar la dirección URL del perfil. **[!UICONTROL Quitar]** abre una confirmación y, a continuación, quita la conexión de toda la organización. Trate la eliminación como una decisión deliberada del administrador, no como un paso para solucionar problemas.

### Herramientas disponibles {#available-tools}

El conector [!DNL RainFocus] habilita una lista fija de 10 herramientas de lectura:

| Herramienta | Área de datos |
| --- | --- |
| `get_attendeeInfo` | Asistentes |
| `get_attendee_load` | Asistentes |
| `get_attendee_search` | Asistentes |
| `get_attribute_load` | Atributos personalizados |
| `get_attribute_search` | Atributos personalizados |
| `get_attributevalue_load` | Atributos personalizados |
| `get_entityDataDump_attendee` | Asistentes, exportación masiva |
| `get_entityDataDump_session` | Sesiones, exportación masiva |
| `get_session_load` | Sessions |
| `get_session_search` | Sessions |

Las herramientas que no están en esta lista, incluidas las que [!DNL RainFocus] agrega posteriormente, no se habilitan automáticamente. La lista no reemplaza las funciones de seguridad de [!DNL RainFocus] ni la configuración de herramientas del perfil, que aún controla el acceso a los datos.

>[!IMPORTANT]
>
>Varias herramientas pueden devolver datos personales e información de contacto sobre los asistentes. Dos herramientas exportan datos de forma masiva y sus resultados pueden ser grandes. Las lecturas también pueden conllevar cargos según los términos de [!DNL RainFocus]. Revise estas herramientas con los propietarios de control de datos antes de que los miembros inicien sesión.

## Iniciar sesión como miembro {#sign-in-as-a-member}

Cuando un administrador configura el conector, cada miembro inicia sesión con su propia cuenta de [!DNL RainFocus]. No necesita un ID de cliente, un secreto de cliente o un token de acceso para iniciar sesión.

1. Abra **[!UICONTROL Personalizaciones]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**. Los miembros utilizan el ámbito **[!UICONTROL Usuario]** de forma predeterminada. Encuentra la tarjeta **[!UICONTROL RainFocus]**.
1. Si la tarjeta muestra **[!UICONTROL Aún no está disponible. El administrador debe configurar esto.]**, pídale al administrador que [configure el conector](#configure-organization). Los miembros no pueden introducir su propia URL de perfil.
1. Compruebe el estado en la tarjeta. La tarjeta muestra el estado **[!UICONTROL Se requiere inicio de sesión]**, **[!UICONTROL Conectado]**, **[!UICONTROL Configurado por el administrador]** o **[!UICONTROL Error de conexión]**.

   **[!UICONTROL Configurado por el administrador]** significa que el compañero no puede confirmar el estado de inicio de sesión. Esto no significa que haya iniciado sesión o que haya cerrado la sesión.

1. Seleccione **[!UICONTROL Iniciar sesión]**. También puede abrir los detalles de la tarjeta y seleccionar **[!UICONTROL Iniciar sesión]** en la sección **[!UICONTROL Conexión]**. En la ventana [!DNL RainFocus], complete el inicio de sesión, el inicio de sesión único (SSO), la autenticación multifactor (MFA) y las indicaciones de consentimiento. Revise el acceso que apruebe.

   Si aparece **[!UICONTROL Discover authorization]**, Coworker lee los detalles de inicio de sesión del servidor, no sus herramientas. Si la detección falla, o si el panel solicita un **[!UICONTROL ID de cliente]** o **[!UICONTROL secreto de cliente]**, detenga y póngase en contacto con el administrador. No introduzca ni adivine credenciales.

   ![Detalles del conector RainFocus para un miembro, que muestra el estado de necesidad de iniciar sesión, una URL de servidor censurada, Cada usuario inicia sesión, un estado de no sesión con un botón de autorización de Discover y las 10 herramientas habilitadas por el administrador.](./assets/rainfocus/member-details.png){width="700" zoomable="yes"}

1. Vuelva a Compañero de trabajo y confirme que el estado muestra **[!UICONTROL Conectado]**. Una ventana de inicio de sesión cerrada por sí sola no confirma el éxito. Si cierra la ventana antes de tiempo, no cambia nada y puede volver a intentarlo.
1. Abra los detalles de la tarjeta para revisar la configuración de su administrador. Puede ver la **[!UICONTROL URL del servidor]**, **[!UICONTROL Quién inicia sesión]**, **[!UICONTROL Autenticación]** y **[!UICONTROL Herramientas habilitadas por el administrador]**.
1. Seleccione **[!UICONTROL Probar]** en la tarjeta o **[!UICONTROL Probar conexión]** en los detalles para comprobar la conexión con su cuenta.

   Una prueba que se realizó correctamente muestra que [!DNL RainFocus] respondió con su cuenta, con la cantidad de herramientas disponibles. La prueba solo enumera las herramientas. No ejecuta una herramienta de datos ni confirma el acceso a eventos o registros específicos. Para renovar tu inicio de sesión y volver a enumerar las herramientas, selecciona **[!UICONTROL Actualizar]**. Si el Compañero de trabajo no puede renovar su inicio de sesión, el botón muestra **[!UICONTROL Herramientas de recarga]** en su lugar, que solo vuelve a mostrar las herramientas.

1. Si la prueba falla, el compañero muestra **[!UICONTROL No se pudo conectar con RainFocus]**, con **[!UICONTROL Inténtelo de nuevo]** y **[!UICONTROL detalles técnicos]**. Si ha cerrado la sesión, vuelva a iniciarla. Si el problema persiste, póngase en contacto con el administrador.

Los miembros pueden iniciar sesión, cerrar la sesión, probar, actualizar y ver las herramientas habilitadas. Los miembros no pueden cambiar ni quitar la conexión con la organización, editar la dirección URL del perfil ni cambiar las herramientas. Todos los miembros que abran los detalles podrán ver la dirección URL del perfil. Cuando un administrador inicia sesión, los demás miembros no inician sesión.

Para desconectar tu cuenta de [!DNL RainFocus] del conector, selecciona **[!UICONTROL Cerrar sesión]**. Puede volver a iniciar sesión en cualquier momento.

## Compruebe el acceso a los datos del evento {#check-event-access}

Para confirmar que puede usar datos de [!DNL RainFocus], ejecute una comprobación de solo lectura con una solicitud restringida. Utilice un evento con el que esté aprobado para trabajar y evite herramientas que devuelvan datos de asistentes o exportaciones masivas para esta comprobación. Inicie una conversación e introduzca un mensaje.

Mensaje de ejemplo:

* &quot;Usando RainFocus, encuentro hasta cinco sesiones a las que puedo acceder. Mostrar solo el título y el ID de la sesión si se devuelven esos campos. No exporte datos, devuelva información de los asistentes ni cambie nada&quot;.

Confirme que el resultado incluye las sesiones que espera. Un resultado vacío no siempre significa que el conector no funcione. Compruebe la cuenta de [!DNL RainFocus] con la que inició sesión, el rol de seguridad y las herramientas habilitadas en el perfil. Si un resultado es inesperadamente grande o incluye datos confidenciales, detenga y limite la solicitud.

## Solucionar problemas de acceso {#troubleshoot-access}

Si no puede obtener acceso a los datos de [!DNL RainFocus], consulte lo siguiente con el administrador:

| Problema | Qué comprobar |
| --- | --- |
| Falta la tarjeta **[!UICONTROL RainFocus]** | Confirme con su representante de Adobe que el conector está disponible para su organización. |
| Falta el ámbito **[!UICONTROL Org]** | Confirme que es administrador y que la configuración de la organización está activada para su organización. |
| El compañero rechaza la URL del perfil | Siga la regla del mensaje. Use la dirección URL de perfil completa de su administrador de [!DNL RainFocus] y no adivine un nombre de perfil. |
| **[!UICONTROL No se pudo guardar la conexión]** aparece | Es posible que se guarden algunas configuraciones. Vuelva a abrir la configuración y compruébela antes de intentarlo de nuevo. Asegúrese de que solo un administrador configura el conector a la vez. |
| La tarjeta muestra **[!UICONTROL Aún no está disponible. El administrador debe configurar esto.]** | Falta la configuración de la organización. Pida al administrador que [configure el conector](#configure-organization). |
| El inicio de sesión solicita un **[!UICONTROL ID de cliente]** o **[!UICONTROL secreto de cliente]**, o bien se produce un error en la detección | Detenga y póngase en contacto con el administrador. No introduzca ni adivine credenciales ni registre una aplicación. |
| Error de inicio de sesión después de aprobar el acceso en [!DNL RainFocus] | Compruebe la cuenta de [!DNL RainFocus] y la función de seguridad que utilizó. Pida a su representante de Adobe y a [!DNL RainFocus] que comprueben la configuración de inicio de sesión de su entorno. No comparta la dirección URL de inicio de sesión. |
| **[!UICONTROL Prueba]** correcta, pero las solicitudes de datos fallan | **[!UICONTROL Prueba]** solo enumera las herramientas. Compruebe el rol de seguridad de [!DNL RainFocus], las herramientas habilitadas en el perfil y los filtros que requiere la herramienta. |
| **[!UICONTROL No se pudo conectar con RainFocus]** aparece cuando ha iniciado sesión | Seleccione **[!UICONTROL Inténtelo de nuevo]**. Si el problema persiste, póngase en contacto con el administrador. |
| Un resultado es inesperadamente grande o incluye datos confidenciales | Detenga y limite su solicitud. No pegue datos de evento sin procesar en tickets o chat. |

Cuando contacte con el servicio de asistencia técnica de, incluya solo el texto del error, la hora del error y el entorno. No comparta detalles técnicos, direcciones URL de perfil, capturas de inicio de sesión, contraseñas, tokens ni códigos de autorización.
