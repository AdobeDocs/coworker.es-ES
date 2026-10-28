---
description: Aprenda a conectar a los compañeros de trabajo de los equipos a su cuenta de Salesforce para acceder a los posibles clientes y contactos.
title: Conectar con Salesforce
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: bd7454ee46cb1ee4ca8b7ae6ab07348a23854979
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%
---
# Conectar con Salesforce {#salesforce}

Coworker para equipos le permite conectar su cuenta de Salesforce para acceder a sus posibles clientes y contactos.

>[!PREREQUISITES]
>
>Para utilizar este conector, primero debe tener:
>
>* Una cuenta activa de Salesforce
>* Los siguientes permisos en Salesforce: `api`, `sobjects.Contact.read`, `sobjects.Campaign.read`, `sobjects.CampaignMember.read`
>* Su URL de instancia de Salesforce, [ID de cliente y secreto de cliente](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&type=5#:~:text=DESCRIPTION-,client_id,-The%20consumer%20key){target="_blank"} son útiles

## Cómo conectar

1. En la página principal de [Colaborador para equipos](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, haga clic en **Contexto** y seleccione **Conectores**.

   ![Compañero de trabajo para equipos abandonaron la navegación con Contexto expandido y Conectores resaltados](./assets/salesforce-1.png)

1. Haga clic en **Agregar integración**.

   ![Botón Agregar integración en la pantalla Conectores](./assets/salesforce-2.png)

   >[!NOTE]
   >
   >Si esta no es su primera integración, el botón dirá &quot;Agregar conector&quot;.

1. En la fila Salesforce, haga clic en **Conectar**.

   ![Mosaico del conector Salesforce con el botón Conectar](./assets/salesforce-3.png)

1. Escriba su **URL de instancia**, **ID de cliente** y **secreto de cliente** de Salesforce. Haga clic en **Conectar**.

   >[!NOTE]
   >
   >* En Salesforce, ID del cliente = Clave de consumidor y Secreto del cliente = Secreto del consumidor.
   >
   >* En la cuenta de Salesforce, puedes encontrar la URL de la instancia en la barra de direcciones del explorador o en **Configuración** > **Configuración de la empresa** > **Mi dominio**.

   ![Conectar el cuadro de diálogo de Salesforce con campos como URL de instancia, ID de cliente y Secreto de cliente](./assets/salesforce-4.png)

Después de la conexión, Salesforce aparece en la lista Conectores y se puede seleccionar al vincular un posible cliente o una lista de contactos para sincronizar desde Salesforce.

**Para desconectar:**

1. En la pantalla Conectores, busque el mosaico Salesforce y haga clic en **Administrar**.

   ![Pantalla de conectores que muestra Salesforce conectado con el botón Administrar resaltado](./assets/salesforce-5.png)

1. Haga clic en **Desconectar** (no es necesario volver a escribir el secreto de cliente en este momento).

   ![Cuadro de diálogo Administrar Salesforce con el botón Desconectar resaltado](./assets/salesforce-6.png)

1. Vuelva a hacer clic en **Desconectar** para confirmar.

   ![Cuadro de diálogo de confirmación de desconexión con el botón Desconectar resaltado](./assets/salesforce-7.png)
