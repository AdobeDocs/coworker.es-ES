---
description: Obtenga información sobre cómo conectar su cuenta de Marketo Engage a Coworker para equipos, de modo que pueda sincronizar listas estáticas e inteligentes de Marketo.
title: Conectar con Marketo Engage
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%
---
# Conectar con Marketo Engage {#marketo}

Coworker para equipos le permite conectar su cuenta de Marketo Engage para extraer listas inteligentes y estáticas.

>[!PREREQUISITES]
>
>Para utilizar este conector, primero debe tener:
>
>* Una cuenta activa de Marketo Engage
>* Su **URL de instancia** de Marketo
>* Se ha creado un [servicio personalizado](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#custom-services-1){target="_blank"} para los equipos de Marketo con su [ID de cliente y secreto de cliente](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/authentication#creating-an-access-token){target="_blank"} a mano.

## Cómo conectar

1. En la página principal de [Colaborador para equipos](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, haga clic en **Contexto** y seleccione **Conectores**.

   ![Compañero de trabajo para equipos abandonaron la navegación con Contexto expandido y Conectores resaltados](./assets/marketo-1.png)

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
