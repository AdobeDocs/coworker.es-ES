---
description: La descripción se incluye aquí.
title: Subdominio
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: d36bbe844cff08b2c820418121dea794a7a347c2
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 4%
---
# Adición de un subdominio y remitentes {#subdomain-senders}

Un subdominio es una división de su dominio que se puede utilizar para aislar sus marcas o varios tipos de tráfico (por ejemplo, comunicaciones de marketing).

Usemos el dominio &quot;mybrand.com&quot;, que se usa para enviar comunicaciones de marketing. En este caso, puede configurar un subdominio específico:

* Subdominio &quot;marketing.mybrand.com&quot; para correos electrónicos de prospección.

Al hacerlo, ayudará a preservar la reputación de su dominio y otros subdominios. Por ejemplo: si el subdominio &quot;marketing.mybrand.com&quot; termina agregándose a la lista de bloqueados de un proveedor de servicio de Internet debido a malas prácticas de entrega, esto impediría que se agregue todo el dominio &quot;mybrand.com&quot; y cualquier otro subdominio que haya creado.

>[!IMPORTANT]
>
>Como parte de la prueba gratuita, se permiten un máximo de dos subdominios.

## Cómo añadir un subdominio

1. En la parte inferior de la navegación izquierda, haga clic en su nombre.

   CAPTURA DE PANTALLA

1. Haga clic en **Configuración**.

   CAPTURA DE PANTALLA

1. En _Workspace_, seleccione **dominios y remitentes**.

   CAPTURA DE PANTALLA

1. Haga clic en **Agregar subdominio**.

   CAPTURA DE PANTALLA

1. Escriba su subdominio y haga clic en **Siguiente**.

   CAPTURA DE PANTALLA

1. Haga clic en el icono de copia PIC junto a los valores aplicables que debe agregar a su proveedor DNS.

   CAPTURA DE PANTALLA

   >[!NOTE]
   >
   >Si su proveedor DNS le permite cargar los campos en lotes, puede hacer clic en **Exportar CSV** para exportar todos los campos.

1. Cuando termine de escribir la información en su proveedor de DNS, haga clic en **He agregado estos registros** en Campañas de compañeros para continuar.

   CAPTURA DE PANTALLA

   >[!NOTE]
   >
   >Los cambios de DNS pueden tardar hasta 30 minutos en propagarse. Si ve una X roja en lugar de una verificación verde en cualquiera de las filas, las campañas de compañeros se comprobarán cada dos minutos hasta que se completen.

1. Cuando se validan todos los registros, aparece una tabla _Registro de validación_ en la parte inferior de la ventana. Desplácese hacia abajo, copie todos los valores enumerados y agréguelos a su proveedor DNS.

   CAPTURA DE PANTALLA

1. Cuando termine, haga clic en **He agregado este registro** (o **estos registros** si hay varios) en Campañas de compañeros para continuar.

   CAPTURA DE PANTALLA

1. Escriba su nombre de remitente, prefijo de correo electrónico, nombre de respuesta y correo electrónico de respuesta, y haga clic en **Finalizar y configurar**.

   CAPTURA DE PANTALLA

1. El nuevo subdominio aparecerá en la lista. Su estado es _En curso_, ya que el proceso puede tardar entre unos minutos y dos horas en completarse.

   CAPTURA DE PANTALLA

1. Una vez completado el proceso, el estado cambia a _Verificado_.

   CAPTURA DE PANTALLA

## Cómo añadir un remitente

Texto

