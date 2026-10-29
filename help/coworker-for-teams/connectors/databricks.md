---
description: Coworker para equipos le permite conectarse y consultar tablas del catálogo Unity en su espacio de trabajo de Databricks para crear y activar audiencias de campaña.
title: Conectar con Databricks
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%
---
# Conectar con Databricks {#databricks}

Coworker para equipos le permite conectarse y consultar tablas del catálogo Unity en su espacio de trabajo de Databricks para crear y activar audiencias de campaña.

>[!PREREQUISITES]
>
>Para utilizar este conector, primero debe tener:
>
>* Una cuenta activa de Databricks
>* Su host de Workspace de Databricks, [ruta de acceso al almacén SQL](https://docs.databricks.com/aws/en/compute/sql-warehouse/create){target="_blank"}, [token de acceso personal](https://learn.microsoft.com/en-us/azure/databricks/dev-tools/auth/pat){target="_blank"} y [catálogos Unity](https://learn.microsoft.com/en-us/azure/databricks/discover/database-objects){target="_blank"} son útiles.

## Cómo conectar

1. En la página principal de [Colaborador para equipos](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, haga clic en **Contexto** y seleccione **Conectores**.

   ![Compañero de trabajo para equipos abandonaron la navegación con Contexto expandido y Conectores resaltados](./assets/databricks-1.png)

1. Haga clic en **Agregar integración**.

   ![Botón Agregar integración en la pantalla Conectores](./assets/databricks-2.png)

   >[!NOTE]
   >
   >Si esta no es su primera integración, el botón dirá &quot;Agregar conector&quot;.

1. En la fila Databricks, haga clic en **Conectar**.

   ![Mosaico del conector Databricks con el botón Conectar](./assets/databricks-3.png)

1. Escriba sus catálogos Databricks **Workspace host**, **ruta de acceso al almacén SQL**, **token de acceso personal** y **Unity**. Haga clic en **Conectar**.

   >[!NOTE]
   >
   >En la página de inicio de Databricks, el host de Workspace se puede encontrar directamente en la barra de direcciones del explorador. Para localizar todas las demás credenciales, consulte los vínculos de **Requisitos previos** que aparecen en la parte superior de este artículo.

   ![Cuadro de diálogo Conectar marcadores de datos con campos para host de Workspace, ruta de acceso de almacén de SQL, token de acceso personal y catálogos Unity](./assets/databricks-4.png)

Después de la conexión, Databricks aparece en la lista Conectores.

**Para desconectar:**

1. En la pantalla Conectores, busque el mosaico de Databricks y haga clic en **Administrar**.

1. Haga clic en **Desconectar** (no es necesario volver a introducir el token de acceso personal en este momento).

1. Vuelva a hacer clic en **Desconectar** para confirmar.
