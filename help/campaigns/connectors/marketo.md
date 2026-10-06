---
description: Aprenda a conectar su cuenta de Marketo Engage a Campañas de compañeros para poder sincronizar listas inteligentes y estáticas de Marketo.
title: Conectar con Marketo Engage
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# Conectar con Marketo Engage {#marketo}

Adobe Coworker Campaigns permite conectar su cuenta de Marketo Engage para extraer listas inteligentes y estáticas.

>[!PREREQUISITES]
>
>Para utilizar este conector, primero debe tener:
>
>* Una cuenta activa de Marketo Engage
>* Su **URL de instancia** de Marketo
>* Se ha creado un [servicio personalizado](https://experienceleague.adobe.com/es/docs/marketo-developer/marketo/rest/custom-services#custom-services-1) para las campañas de compañeros en Marketo, con su [ID de cliente y secreto de cliente](https://experienceleague.adobe.com/es/docs/marketo-developer/marketo/rest/authentication#creating-an-access-token) a mano

## Cómo conectar

1. En la página principal de [Campañas de colaboración](https://coworker-campaigns.experience.adobe.com/), haga clic en **Personalizar** y seleccione **Conectores**.

   ![Campañas de compañeros dejaron la navegación con Personalizar expandida y Conectores resaltados](./assets/marketo-1.png)

1. Haga clic en **Agregar integración**.

   ![Botón Agregar integración en la pantalla Conectores](./assets/marketo-2.png)

   >[!NOTE]
   >
   >Si esta no es su primera integración, el botón dirá &quot;Agregar conector&quot;.

1. En la fila Marketo, haga clic en **Conectar**.

   ![Mosaico del conector Marketo con el botón Conectar](./assets/marketo-3.png)

1. Escriba su **URL de instancia**, **ID de cliente** y **secreto de cliente** de Marketo. Haga clic en **Conectar**.

   >[!NOTE]
   >
   >Puede encontrar la URL de la instancia de Marketo en la barra de direcciones del explorador al ver la página de Mi Marketo.

   ![Conectar el cuadro de diálogo de Marketo con campos como URL de instancia, ID de cliente y Secreto de cliente](./assets/marketo-4.png)

Después de la conexión, Marketo aparece en la lista Conectores y se puede seleccionar al vincular una lista de contactos para sincronizar desde Marketo.

**Para desconectar:**

1. En la pantalla Conectores, busque el mosaico Marketo y haga clic en **Administrar**.

   ![Pantalla de conectores con el mosaico de Marketo que muestra el estado Conectado y el botón Administrar](./assets/marketo-5.png)

1. Haga clic en **Desconectar** (no es necesario volver a escribir el secreto de cliente en este momento).

   ![Cuadro de diálogo Administrar Marketo con los campos URL de instancia e ID de cliente y un botón Desconectar](./assets/marketo-6.png)

   >[!NOTE]
   >
   >Una vez agregada la dirección URL de instancia por primera vez, su valor predeterminado es la dirección URL del extremo REST, que termina en `*.mktorest.com`.

1. Vuelva a hacer clic en **Desconectar** para confirmar.

   ![Desconectar cuadro de diálogo de confirmación de conexión](./assets/marketo-7.png)
