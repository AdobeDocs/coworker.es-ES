---
title: Conector externo de Google Cloud Storage
description: Obtenga información sobre cómo configurar el conector externo de Google Cloud Storage en CX Enterprise Coworker con la aplicación Google OAuth e iniciar sesión para leer datos agrupados en el chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Este conector está en versión beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 70782269f48e3ff87ca95a1341ee74b02da1d7f4
workflow-type: tm+mt
source-wordcount: '2408'
ht-degree: 1%
---

# Conector externo de Google Cloud Storage {#google-cloud-storage}

Utilice el conector externo [!DNL Google Cloud Storage] para leer los datos de [!DNL Cloud Storage] en Adobe CX Enterprise Coworker. Después de configurar el conector, pídale a su compañero que muestre los bloques de un proyecto conocido, que muestre los objetos por prefijo, que inspeccione los metadatos de los bloques y los objetos y que lea los archivos aprobados. El conector es un servidor de Protocolo de contexto de modelo (MCP) alojado por [!DNL Google].

>[!AVAILABILITY]
>
>El conector externo [!DNL Google Cloud Storage] está en versión beta. La documentación y las funcionalidades están sujetas a cambios.

## Configuración del conector {#connector-configuration}

El proceso de configuración del conector tiene tres partes independientes:

* **[!DNL Google Cloud]preparación:** Un administrador de [!DNL Google Cloud] prepara la facturación, la API de [!DNL Cloud Storage] y los roles de Administración de identidad y acceso (IAM) para los miembros. El administrador también prepara un cliente de OAuth que posee su organización.
* **Configuración de la organización:** Un administrador de Coworker configura el conector una vez para toda la organización. El administrador registra la URL de redireccionamiento de Coworker, introduce las credenciales del cliente de OAuth y selecciona las herramientas que los miembros pueden utilizar.
* **Inicio de sesión de miembro:** Cada miembro inicia sesión con su propia cuenta de [!DNL Google]. Los miembros solo pueden acceder a los contenedores y objetos que [!DNL Google Cloud] IAM permite para su cuenta.

El conector es de solo lectura. Solicita el ámbito `https://www.googleapis.com/auth/devstorage.read_only` y solo ofrece herramientas de lectura. Su organización proporciona su propia aplicación OAuth [!DNL Google]. No hay ninguna aplicación OAuth administrada por Adobe para este conector.

Al guardar la configuración de la organización, no se inicia sesión en ningún miembro ni se conceden permisos de [!DNL Cloud Storage]. Cada miembro ya debe tener el acceso IAM requerido y debe iniciar sesión por separado.

## Requisitos previos {#prerequisites}

Antes de empezar, asegúrese de que dispone de lo siguiente:

* **Para la preparación de [!DNL Google Cloud]:** Un proyecto con la facturación y la API de [!DNL Cloud Storage] habilitada, bloques que contienen datos aprobados, concesiones de IAM para miembros y un cliente de OAuth [!DNL Google] del tipo **[!UICONTROL aplicación web]**.
* **Para la configuración de la organización:** Cuenta con permiso para administrar conectores de organización en Coworker. También necesita el ID de cliente de OAuth y el secreto de cliente, o los secretos de organización existentes que los contengan.
* **Para el inicio de sesión de miembros:** Una cuenta de [!DNL Google] que la audiencia de la aplicación OAuth y [!DNL Google Cloud] IAM permiten.

Conocer el ID del proyecto y los contenedores que los miembros planean leer. El conector no tiene ninguna herramienta para enumerar proyectos. El cliente OAuth puede pertenecer a un proyecto diferente a los contenedores.

## Preparar Google Cloud {#prepare-google-cloud}

Antes de configurar el conector en Coworker, prepare su proyecto [!DNL Google Cloud] y el acceso de los miembros. Un inicio de sesión correcto de [!DNL Google] no concede permisos de almacenamiento.

### Preparar el proyecto y el IAM {#prepare-project-iam}

Un administrador de [!DNL Google Cloud] completa los siguientes pasos:

1. Seleccione o cree un proyecto en [Google Cloud Console](https://console.cloud.google.com/).
1. Vincule una cuenta de facturación en cada proyecto que contenga bloques.

   El acceso de solo lectura no es gratuito. Pueden seguir aplicándose cargos por almacenamiento, operación, recuperación y red. Para obtener más información, consulte [Precios de almacenamiento en la nube](https://cloud.google.com/storage/pricing).

1. Habilite la **[!UICONTROL API de almacenamiento en la nube]** en cada proyecto relevante. Si el cliente de OAuth pertenece a un proyecto independiente, habilite también la API en ese proyecto.
1. Conceda a los miembros los roles con menos privilegios en la siguiente tabla. Prefiera un grupo administrado sobre cuentas individuales.

| Función | Dónde se puede conceder | Objetivo |
| --- | --- | --- |
| [!UICONTROL Usuario de herramienta MCP] (`roles/mcp.toolUser`) | El proyecto utilizado para las llamadas de MCP | Realizar llamadas a la herramienta MCP (`mcp.tools.call`). |
| [!UICONTROL Visor del contenedor de almacenamiento] (`roles/storage.bucketViewer`) o un rol de solo lectura personalizado | El proyecto que contiene los contenedores | Enumerar contenedores y leer metadatos de contenedores (`storage.buckets.list` y `storage.buckets.get`). |
| [!UICONTROL Visor de objetos de almacenamiento] (`roles/storage.objectViewer`) | Cada bloque autorizado o el proyecto, si los miembros pueden leer todos sus bloques | Enumerar objetos, leer metadatos de objetos y leer contenido de objetos (`storage.objects.list` y `storage.objects.get`). |

No conceder a [!UICONTROL Administrador de almacenamiento] solo a los bloques de la lista. Los miembros sin permiso para enumerar contenedores aún pueden leer un contenedor autorizado cuando proporcionan su nombre. Para obtener más información, consulte [Funciones IAM de almacenamiento en la nube](https://docs.cloud.google.com/storage/docs/access-control/iam-roles) en la documentación de [!DNL Google Cloud].

[!DNL Google] también ofrece una directiva de denegación IAM opcional que bloquea las herramientas MCP de lectura-escritura para otros clientes MCP. El conector Coworker ya utiliza una selección de herramientas de solo lectura y un ámbito de solo lectura. Revise los efectos en todo el proyecto con el administrador de [!DNL Google Cloud] antes de aplicar la directiva. Para obtener más información, consulte [Impedir el uso de la herramienta MCP de lectura-escritura](https://docs.cloud.google.com/mcp/prevent-read-write-tool-use).

### Configuración de conexión {#connection-settings}

El compañero utiliza la siguiente configuración de conexión. Estos valores no se introducen en el cuadro de diálogo de configuración.

| Configuración | Valor |
| --- | --- |
| URL del servidor MCP | `https://storage.googleapis.com/storage/mcp` (solo extremo global) |
| Transporte | HTTP reproducible |
| Servidor de autorización | `https://accounts.google.com/` |
| Ámbito solicitado | `https://www.googleapis.com/auth/devstorage.read_only` |

Para obtener más información, consulte [Usar el servidor MCP remoto de Cloud Storage](https://docs.cloud.google.com/storage/docs/use-cloud-storage-mcp) y [Autenticar con servidores MCP de Google](https://docs.cloud.google.com/mcp/authenticate-mcp) en la documentación de [!DNL Google Cloud].

## Configure el conector para su organización {#configure-organization}

Los administradores ponen el conector [!DNL Google Cloud Storage] a disposición de todos los miembros de la organización. Los cambios realizados en la página de la organización se aplican a todos los miembros de la organización.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Organización]** y luego seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Google Cloud Storage]**, seleccione **[!UICONTROL Configurar]**.

   Si el conector ya está configurado, abra su configuración guardada en su lugar.

1. En el cuadro de diálogo **[!UICONTROL Configuración del almacenamiento en la nube de Google para su organización]**, en **[!UICONTROL Su aplicación de Google]**, copie la **[!UICONTROL URL de redireccionamiento]** completa.

   La dirección URL de redireccionamiento difiere según el entorno y la región. Copie siempre el valor exacto del cuadro de diálogo. No utilice la dirección URL de la página Compañero de trabajo en el explorador, la dirección URL del servidor MCP o una dirección URL de redireccionamiento de otro entorno.

1. Prepare el cliente de OAuth para su organización en [Google Auth Platform](https://console.cloud.google.com/auth/overview):

   1. Configure **[!UICONTROL Marca]** y **[!UICONTROL Audiencia]** para su organización. Para una aplicación externa en pruebas, añada los miembros deseados como usuarios de prueba. Complete los requisitos de publicación y verificación de [!DNL Google] que se aplican antes de un uso más amplio.
   1. En **[!UICONTROL Acceso a datos]**, incluya el ámbito `https://www.googleapis.com/auth/devstorage.read_only`. El conector no necesita ámbitos de lectura-escritura o de control total.
   1. En **[!UICONTROL Clientes]**, cree o seleccione un cliente OAuth con **[!UICONTROL Tipo de aplicación]** establecido en **[!UICONTROL Aplicación web]**.
   1. Agregue la URL de redireccionamiento que copió a **[!UICONTROL URI de redireccionamiento autorizados]**. Si un cliente sirve varios entornos, registre la URL de redireccionamiento de cada entorno.
   1. Obtenga el **[!UICONTROL ID de cliente]** y el **[!UICONTROL secreto de cliente]** a través del proceso de administración de secretos aprobado de su organización.

   Los miembros autorizan esta aplicación de OAuth que posee su organización. Mantenga las credenciales fuera de las conversaciones, los tickets y la documentación.

1. En **[!UICONTROL De donde provienen las credenciales]**, seleccione una de las siguientes opciones:

   * **[!UICONTROL Escriba nuevo]:** Escriba el **[!UICONTROL ID de cliente OAuth de Google]** y el **[!UICONTROL secreto de cliente OAuth de Google]**. El compañero almacena los valores que se introducen como secretos de la organización.
   * **[!UICONTROL Usar un secreto existente]:** Seleccione los secretos de organización guardados que contienen el ID de cliente y el secreto de cliente.

   No utilice secretos personales para un conector de organización.

   ![Configure Google Cloud Storage para el cuadro de diálogo de su organización que muestra una URL de redireccionamiento censurada, las opciones Introducir nuevo y Usar un secreto existente, los campos ID de cliente de OAuth de Google y secreto de cliente, y el aviso Antes de que los usuarios puedan iniciar sesión.](./assets/google-cloud-storage/org-configure.png){width="500" zoomable="yes"}

1. Expandir **[!UICONTROL Examinar y leer (5 de 5)]**. Mantenga las cinco herramientas seleccionadas o seleccione sólo las herramientas que necesiten los miembros. Debe seleccionar al menos una herramienta. Para obtener más información, consulte [Herramientas disponibles](#available-tools).

   En **[!UICONTROL Acceso y permisos]**, revise los avisos de **[!UICONTROL Acceso de solo lectura]** y **[!UICONTROL Cada persona inicia sesión por separado]**. Luego selecciona **[!UICONTROL Guardar conexión]**.

   ![Sección de herramientas disponibles para los usuarios con las cinco herramientas de exploración y lectura seleccionadas, seguida del acceso de solo lectura y Cada persona inicia sesión con avisos por separado.](./assets/google-cloud-storage/org-tools.png){width="500" zoomable="yes"}

1. Revise los detalles guardados del conector **[!UICONTROL google-cloud-storage]**.

   | Configuración | Descripción |
   | --- | --- |
   | **[!UICONTROL Source]** | URL del servidor MCP `https://storage.googleapis.com/storage/mcp`. |
   | **[!UICONTROL Autenticación]** | El método de autenticación `google-cloud-storage_login`. |
   | **[!UICONTROL Conexión]** | Su propio estado de inicio de sesión. |
   | **[!UICONTROL Herramientas]** | Las herramientas seleccionadas para los miembros, con los controles **[!UICONTROL Seleccionar todo]** y **[!UICONTROL Borrar]** y un recuento de las herramientas seleccionadas. |

   ![Se guardaron los detalles del conector google-cloud-storage que mostraban el origen, el método de autenticación, una conexión no firmada con un botón Iniciar sesión y cinco de las cinco herramientas seleccionadas.](./assets/google-cloud-storage/org-details.png){width="700" zoomable="yes"}

El estado **[!UICONTROL Sin sesión iniciada]** en los detalles del conector hace referencia a su propia conexión, no a la organización. Al guardar la configuración de la organización, no se inicia sesión ni en usted ni en ningún miembro y no se confirma el acceso a un bloque. Para usar el conector, sigue los pasos indicados en [Iniciar sesión como miembro](#sign-in-as-a-member).

Para cambiar las herramientas disponibles para los miembros más adelante, actualice la selección en la página de detalles del conector y, a continuación, seleccione **[!UICONTROL Guardar selección de herramientas]**. Los miembros no pueden cambiar la selección de herramientas.

Para dejar de ofrecer el conector a tu organización, selecciona **[!UICONTROL Quitar]** en la página de detalles del conector.

### Herramientas disponibles {#available-tools}

El conector [!DNL Google Cloud Storage] proporciona las siguientes herramientas de solo lectura en el grupo **[!UICONTROL Examinar y leer]**:

| Herramienta | Descripción | Permiso requerido |
| --- | --- | --- |
| `list_buckets` | Enumerar los contenedores de un proyecto [!DNL Google Cloud] conocido, con filtrado de prefijo y paginación. | `storage.buckets.list` en el proyecto |
| `list_objects` | Enumerar objetos y prefijos en un bloque autorizado. La lista no es recursiva de forma predeterminada. | `storage.objects.list` en el contenedor |
| `get_bucket_metadata` | Leer la configuración del contenedor, como la ubicación, la clase de almacenamiento, la retención y el control de versiones. | `storage.buckets.get` |
| `get_object_metadata` | Tamaño de objeto de lectura, tipo de contenido, marcas de tiempo, generación y metadatos personalizados. | `storage.objects.get` |
| `read_object` | Texto de lectura o contenido binario admitido, hasta 8 MiB por objeto. | `storage.objects.get` |

Cada llamada a la herramienta también requiere el permiso `mcp.tools.call`, normalmente a través del rol [!UICONTROL Usuario de herramienta MCP] en el proyecto correspondiente.

El conector no ofrece la herramienta obsoleta `read_text` ni las herramientas `write_text`, `create_bucket`, `delete_object` y `delete_bucket`. No hay ninguna opción para activar las herramientas de escritura. Las herramientas que [!DNL Google] agrega al servidor más adelante no estarán disponibles automáticamente, ni siquiera cuando seleccione las cinco herramientas.

## Iniciar sesión como miembro {#sign-in-as-a-member}

Cuando un administrador configura el conector, cada miembro inicia sesión con su propia cuenta de [!DNL Google]. No necesita el secreto de cliente de OAuth para iniciar sesión.

1. Abra **[!UICONTROL Personalizaciones]**, seleccione **[!UICONTROL Usuario]** y, a continuación, seleccione **[!UICONTROL Conectores externos]**. En la tarjeta **[!UICONTROL Google Cloud Storage]**, seleccione **[!UICONTROL Iniciar sesión]**.

   Antes de iniciar sesión, la tarjeta muestra **[!UICONTROL Sin sesión]**. Si la tarjeta muestra **[!UICONTROL No configurado]**, pídale al administrador que [configure el conector](#configure-organization).

1. En la pantalla [!DNL Google] **[!UICONTROL Elegir una cuenta]**, seleccione la cuenta que tenga el acceso IAM requerido o seleccione **[!UICONTROL Usar otra cuenta]**. Complete los pasos de inicio de sesión que su organización requiera, como el inicio de sesión único (SSO) o la autenticación multifactor (MFA).

   Esta cuenta puede diferir de la cuenta que utiliza para el Compañero de trabajo.

   ![Google Elija una pantalla de cuenta con cuentas censuradas y la opción Usar otra cuenta.](./assets/google-cloud-storage/member-choose-account.png){width="500" zoomable="yes"}

1. Si [!DNL Google] muestra **[!UICONTROL Google no ha verificado esta aplicación]**, confirme la aplicación y su propietario con el administrador.

   Si su organización aprueba el uso de esta aplicación, seleccione **[!UICONTROL Continuar]**. De lo contrario, selecciona **[!UICONTROL Volver a la seguridad]** y pídele al propietario de la aplicación que resuelva los requisitos de audiencia, publicación o verificación.

   ![Pantalla de Google que indica que Google no ha comprobado esta aplicación porque se está probando, con las opciones Continuar y Volver a seguridad.](./assets/google-cloud-storage/member-unverified-app.png){width="500" zoomable="yes"}

   Revise el nombre de la aplicación y el acceso solicitado en la pantalla de consentimiento y, a continuación, seleccione **[!UICONTROL Continuar]**. El conector solicita **[!UICONTROL Ver los datos en Google Cloud Storage]**, que coincide con el ámbito de solo lectura.

   En las capturas de pantalla, la aplicación se llama adobe.io. La aplicación de su organización muestra su propio nombre. Este nombre no significa que Adobe proporcione la aplicación OAuth.

   >[!IMPORTANT]
   >
   >Continúe solo si reconoce la aplicación y si su organización aprueba el acceso solicitado.

   ![Pantalla de consentimiento de Google donde una aplicación de ejemplo llamada adobe.io solicita acceso para ver sus datos en Google Cloud Storage, con una cuenta censurada y los botones Cancelar y Continuar.](./assets/google-cloud-storage/member-consent.png){width="500" zoomable="yes"}

1. Vuelva a Compañero de trabajo y confirme que el inicio de sesión se ha completado. Revise **[!UICONTROL Herramientas habilitadas por su administrador]** en los detalles del conector. Solo puede utilizar las herramientas que haya activado el administrador.

Si la conexión termina o la sesión caduca, vuelva a iniciar sesión. Cuando un administrador inicia sesión, los demás miembros no inician sesión.

## Compruebe el acceso al cubo {#check-bucket-access}

Un inicio de sesión o una lista de herramientas correctos no confirman que pueda acceder a un bloque específico. [!DNL Google] no requiere autenticación para enumerar las herramientas del servidor. Para confirmar el acceso, inicie una nueva conversación e introduzca un mensaje de solo lectura. Reemplace los marcadores de posición por recursos aprobados.

Ejemplos de peticiones de datos:

* &quot;Enumerar los contenedores en el proyecto `YOUR_PROJECT_ID`.&quot;
* &quot;Enumerar hasta 25 objetos bajo `reports/` en el bloque `YOUR_BUCKET`. Compruebe el tamaño y el tipo de contenido de `reports/example.txt`, luego lea sus primeros 4096 bytes y revíselos&quot;.

Confirme que el resultado incluye el bloque u objeto que espera. Para enumerar objetos en prefijos anidados, pida una lista recursiva de forma explícita. Compruebe los metadatos del objeto antes de leer un objeto.

## Límites y gestión de datos {#limits-data-handling}

Tenga en cuenta los siguientes límites y consideraciones sobre la administración de datos al utilizar el conector:

* **ID de proyecto:** Proporcione un ID de proyecto en su solicitud. El conector no puede enumerar proyectos.
* **Prefijos:** Los prefijos de objeto son nombres literales, no carpetas reales. Los listados no son recursivos de forma predeterminada y devuelven los resultados en páginas.
* **Tamaño de página:** Una página de lista puede contener hasta 1.000 elementos. Utilice un tamaño de página pequeño, como 25 a 100, y un prefijo estrecho.
* **Tamaño de objeto:** El tamaño máximo de objeto para una lectura es de 8 MiB. La lectura de sólo parte de un objeto mayor no supera este límite. La compatibilidad con archivos binarios depende del modelo y del cliente.
* **Costos y cuotas:** Se pueden aplicar cargos de almacenamiento, solicitud, recuperación y red. [!DNL Google] también aplica cuotas al servidor MCP. Para obtener más información, consulte [Cuotas MCP de almacenamiento en la nube](https://docs.cloud.google.com/storage/quotas#gcs-mcp).
* **Tratamiento de datos:** El contenido de los objetos, los nombres y los metadatos personalizados entran en su conversación con el compañero. Usar solo los datos aprobados.
* **Registros de auditoría:** [!DNL Cloud Storage] lecturas aparecen en [!DNL Cloud Audit Logs] solo cuando los registros de acceso a datos aplicables están habilitados.

El conector no puede cargar, sobrescribir, crear ni eliminar archivos o contenedores. Tampoco puede guardar resúmenes en [!DNL Cloud Storage].

## Solucionar problemas de acceso {#troubleshoot-access}

Si falla el inicio de sesión o el acceso, consulte lo siguiente con su administrador:

| Problema | Qué comprobar |
| --- | --- |
| La tarjeta muestra **[!UICONTROL No configurado]** | Guarde la conexión de la organización para la organización activa. |
| `redirect_uri_mismatch` | Registre la **[!UICONTROL URL de redireccionamiento]** exacta desde el cuadro de diálogo Compañero de trabajo en el cliente OAuth de la **[!UICONTROL aplicación web]**. |
| `invalid_client` | Compruebe el tipo de cliente, el ID de cliente y el secreto de cliente, así como los secretos de organización seleccionados. |
| `access_denied` o una advertencia de aplicación no verificada | Compruebe la audiencia de la aplicación, la idoneidad del usuario de prueba y el estado de verificación con el propietario de la aplicación. No apruebe una aplicación desconocida. |
| HTTP 401 o la sesión ha finalizado | Inicie sesión de nuevo. |
| `mcp.tools.call` se ha denegado | Compruebe el rol [!UICONTROL Usuario de herramienta MCP] y cualquier directiva de denegación de IAM que se aplique. |
| Se ha denegado la lista de compartimentos, pero se puede leer un compartimento conocido | Compruebe el permiso de `storage.buckets.list` en el proyecto. Los permisos de objeto por sí solos no permiten enumerar bloques en un proyecto. |
| Metadatos de bloque denegados | Compruebe el permiso de `storage.buckets.get`. |
| Lista de objetos o lectura denegada | Compruebe el rol [!UICONTROL Visor de objetos de almacenamiento] en el contenedor y la cuenta [!DNL Google] con la que inició sesión. |
| `SERVICE_DISABLED` | Habilite la API [!DNL Cloud Storage] en el proyecto mencionado en el error. |
| HTTP 403 que requiere facturación | Compruebe la facturación en el proyecto que contiene los bloques, incluido el proyecto en su solicitud `list_buckets`. |
| `OutOfRange` en una lectura | El objeto supera el límite de 8 MiB. Utilice una alternativa aprobada fuera de este conector. |
| Falta una herramienta | Compruebe la selección de herramientas que guardó el administrador. Las herramientas de escritura y obsoletas no están disponibles. |
| Error en una solicitud para cargar, sobrescribir, crear o eliminar | El conector es de solo lectura y no admite estas acciones. |
