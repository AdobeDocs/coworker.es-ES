---
description: descripción.
title: Comprender el editor de correo electrónico
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%
---
# Comprender el editor de correo electrónico {#email-editor}

El editor de correo electrónico permite refinar un correo electrónico generado por IA directamente en el tablero de campaña. Edite la línea de asunto y el preencabezado, dé formato al texto y a las imágenes en línea o cambie a una plantilla diferente.

Al seleccionar una tarjeta de correo electrónico en el tablero de campañas, se abre el editor de correo electrónico como un panel lateral. Desde allí, el usuario puede editar el asunto y el preencabezado (con alternativas sugeridas por IA), hacer clic en el cuerpo del correo electrónico para seleccionar y dar formato al texto o las imágenes, cambiar entre variantes generadas por IA, intercambiar la plantilla de HTML, comprobar la compatibilidad entre el cliente y el correo electrónico y enviar un correo electrónico de prueba a su propia bandeja de entrada. Los cambios se guardan automáticamente y las versiones anteriores se pueden revisar y restaurar.

## Cómo acceder a

1. Abra la campaña deseada y haga clic en Open editor en la tarjeta de correo electrónico.

CAPTURA DE PANTALLA

1. Edite directamente los campos **Subject** y **Preheader**, o haga clic en **Sugerencias inteligentes** junto a para buscar alternativas generadas por IA.
1. Haga clic en el cuerpo del correo electrónico para seleccionar un bloque de texto o una imagen y, a continuación, utilice la barra de herramientas flotante que aparece para dar formato al texto o administrar la imagen.
1. Use **Cambiar plantilla de HTML** para reemplazar el cuerpo del correo electrónico por una plantilla diferente.
1. Use **Enviar correo electrónico de prueba**, ingrese una dirección de destinatario y haga clic en **Enviar** para enviar por correo electrónico una vista previa activa a esa dirección.
1. Utilice el icono del historial de versiones para obtener una vista previa y restaurar una versión guardada anteriormente.
1. Los cambios se guardan automáticamente: no es necesario guardarlos manualmente.

### Comportamientos clave

- Las cargas de imágenes tienen un límite de 10 MB; las imágenes de más de 3 MB se comprimen automáticamente, con una nota de calidad que recomienda imágenes de menos de 3 MB.
- Los campos Subject y Preheader tienen la opción de usar alternativas generadas por IA a través de este ICONO.
- Utilice Ctrl+z (CMD+z para Mac) para &#39;Deshacer&#39; e invertir la última acción. Utilice CTRL+Y (CMD+y para Mac) para &#39;Rehacer&#39; e invertir la última operación de Deshacer. KEITH CHECK STANDARD
- Las versiones guardadas anteriores se pueden previsualizar y restaurar desde un panel del historial de versiones a través de este ICONO.
- De forma predeterminada, generamos dos variantes por correo electrónico; puede seleccionar la variante deseada a través de sus miniaturas a la derecha.

## Qué no hace esta función

- No es un generador de bloques de arrastrar y soltar: no hay ninguna biblioteca de bloques y los bloques de contenido no se pueden añadir, eliminar ni reordenar; la edición se realiza directamente en el HTML de correo electrónico existente.
- Actualmente no admite la inserción de etiquetas de personalización/combinación.
- No proporciona un campo de texto alternativo para las imágenes.
- No aplica una línea de asunto, un encabezado previo u otras comprobaciones de nivel de contenido antes de que un correo electrónico se considere &quot;listo&quot;: las únicas comprobaciones previas al inicio son de nivel de campaña (configuración del envío, envío de un correo electrónico de prueba, audiencia real), no comprobaciones del contenido del correo electrónico en sí.
- El alternado de previsualización de escritorio/móvil no está disponible en la vista de edición de correo electrónico de campaña estándar. [SE NECESITA ENTRADA para confirmar el ámbito]
- [NECESITA ENTRADA — para confirmar con el ingeniero: si el editor se convierte en de solo lectura (no solo en el campo del remitente) una vez que se ha activado/iniciado una campaña.]
