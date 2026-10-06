---
description: Conecte su cuenta de HubSpot a Campañas de compañeros mediante una clave de servicio para sincronizar las listas de contactos y, a continuación, administre o desconecte la integración en cualquier momento.
title: Conectar con HubSpot
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%
---
# Conectar con HubSpot {#hubspot}

Adobe Coworker Campaigns permite conectar su cuenta de HubSpot para extraer listas de contactos.

>[!PREREQUISITES]
>
>Para utilizar este conector, primero debe tener:
>
>* Una cuenta activa de HubSpot
>* Se ha creado una clave de servicio [1&rbrace; con los siguientes ámbitos agregados: `crm.objects.contacts.read`, `crm.objects.leads.read`, `crm.schemas.contacts.read`, `crm.lists.read`, `crm.export`](https://developers.hubspot.com/docs/apps/developer-platform/build-apps/authentication/account-service-keys#create-a-service-key)

## Cómo conectar

1. En la página principal de [Campañas de colaboración](https://coworker-campaigns.experience.adobe.com/), haga clic en **Personalizar** y seleccione **Conectores**.

   ![Menú personalizado expandido en la barra lateral con los conectores seleccionados](./assets/hubspot-1.png)

1. Haga clic en **Agregar integración**.

   ![Botón Agregar integración en la pantalla Conectores](./assets/hubspot-2.png)

   >[!NOTE]
   >
   >Si esta no es su primera integración, el botón dirá &quot;Agregar conector&quot;.

1. En la fila HubSpot, haz clic en **Conectar**.

   ![Mosaico HubSpot con el botón Conectar resaltado](./assets/hubspot-3.png)

1. Aparece un modal que muestra los permisos necesarios (enumerados en Requisitos previos en la parte superior de este artículo). Haga clic en **Continuar**.

1. Introduce tu clave de servicio **HubSpot** y haz clic en **Conectar**.

   ![Cuadro de diálogo Conectar HubSpot con el campo Clave de servicio y el botón Conectar](./assets/hubspot-4.png)

Después de la conexión, HubSpot aparece en la lista de Conectores y se puede seleccionar al vincular una lista de contactos para sincronizar desde HubSpot.

**Para desconectar:**

1. En la pantalla Conectores, busque el mosaico HubSpot y haga clic en **Administrar**.

   ![Pantalla de conectores que muestra HubSpot conectado con el botón Administrar resaltado](./assets/hubspot-5.png)

1. Haga clic en **Desconectar** (no es necesario que vuelva a escribir la clave de servicio en este momento).

   ![Cuadro de diálogo Administrar concentrador con el botón Desconectar resaltado](./assets/hubspot-6.png)

1. Vuelva a hacer clic en **Desconectar** para confirmar.

   ![Cuadro de diálogo de confirmación de desconexión con el botón Desconectar resaltado](./assets/hubspot-7.png)
