---
description: Una guía paso a paso para generar una campaña de correo electrónico en Adobe CX Enterprise Coworker para equipos, desde escribir preguntas hasta revisar y exportar la campaña.
title: Creación de una campaña de correo electrónico
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: bf3751af83dd8d40021fb2459743aec66c53209c
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%
---
# Creación de una campaña de correo electrónico {#create-an-email-campaign}

Obtenga información sobre cómo generar y revisar campañas de correo electrónico completas en minutos.

## Antes de comenzar

Asegúrese de que dispone de:

* Una cuenta activa de Adobe CX Enterprise Coworker para equipos ([regístrese aquí](https://coworker-campaigns.experience.adobe.com/){target="_blank"} si aún no lo ha hecho).

* Su marca se agregó en **Contexto** > **Marcas**.

* (Opcional, pero recomendada) Una plantilla de correo electrónico de HTML cargada en **Contexto** > **Plantillas de correo electrónico**.

* Un CSV de audiencia listo para cargar.

* Una idea clara del objetivo de la campaña (por ejemplo, &quot;recuperar clientes caducados&quot; o &quot;invitar a usuarios de prueba a un seminario web&quot;).

## Paso 1: Iniciar un nuevo chat

Desde la página de inicio, tiene tres formas de empezar:

**Opción uno**: escriba un mensaje en la barra de mensajes central.

_Cuándo se debe usar: cuando se sabe exactamente lo que se desea._

**Opción dos**: elige una plantilla lista para usar de la sección **Plantillas de campaña** debajo de la barra de mensajes.

_Cuándo usar: cuando no está seguro de lo que desea._

**Opción tres**: use la opción &quot;Ayudarme a preguntar&quot; de la lista desplegable de la barra de mensajes para que Coworker para equipos le guíe a través de la escritura del mensaje.

_Cuándo usar: cuando tengas una idea de lo que deseas, pero quieras un poco de ayuda (o, usa &quot;Sorpréndeme&quot; para sorprenderte)._

![Pantalla de inicio que muestra las tres opciones para comenzar](./assets/create-an-email-campaign-1.png){width="800" zoomable="yes"}

## Paso 2: Crear el mensaje

Un fuerte mensaje de Compañero de trabajo para equipos incluye:

* El objetivo de la campaña (lo que está intentando lograr).
* La audiencia (para quién es o de dónde provienen los datos de audiencia).
* Formato y estructura (número de correos electrónicos, cadencia, tono).
* Señales de marca o contexto (referencias a su marca, producto o campaña).

Ejemplo:

`"Create a single-touch win-back email campaign for customers who bought last year but haven't returned. Use the CSV I am uploading. Make sure the content feels seasonal."`

>[!TIP]
>
>Para ver más ejemplos, consulte el artículo _Casos de uso_.

>[!NOTE]
>
>Si ya tiene un resumen de campaña, cárguelo junto con el mensaje como contexto adicional para el plan que generará para usted.

![Escribiendo en su propia solicitud](./assets/create-an-email-campaign-2.png)

Cuando tenga la solicitud lista, haga clic en **Generar campaña**. El compañero de trabajo de los equipos:

* Genere una estrategia de campaña estructurada.
* Pregunte por la audiencia de destino, que también se utilizará para la personalización de contenido.
* Borrador de contenido de correo electrónico personalizado para cada paso.
* Construye dinámicamente el recorrido a lo largo del camino.
* Montarlo todo en un solo tablero de campaña.

## Paso 3: Actualización de la audiencia

Las audiencias se cargan mediante CSV. Todas las audiencias son específicas para sus respectivas campañas (no se almacenan en ningún otro lugar del entorno en este momento).

1. Después de enviar el mensaje, el colaborador de los equipos (normalmente) genera una audiencia de muestra para usted. Si no es así, le solicita que importe una audiencia.

1. Importe su propia audiencia cargando un archivo CSV o trayendo datos de un conector disponible.

   >[!NOTE]
   >
   >Aunque Coworker para equipos le permite continuar creando su campaña con una audiencia de muestra, debe agregar una audiencia real para iniciar la campaña.

1. Importe el archivo CSV.

   >[!IMPORTANT]
   >
   >Excluya los contactos que no desee enviar por correo electrónico (usuarios sin suscribir, direcciones internas, cuentas de prueba) antes de cargarlos. Aunque habilitaremos progresivamente la funcionalidad para excluir usuarios específicos o añadir atributos durante el transcurso de la prueba, no está disponible inmediatamente a partir de la fecha de lanzamiento.

## Paso 4: Revisar y perfeccionar Campaign Assets

Para realizar cambios en el correo electrónico, desplácese hacia la derecha. En _Campaign Assets_, haga clic en **Abrir editor**.

![](./assets/create-an-email-campaign-4.png)

Existen dos formas de actualizar el contenido.

* Realice manualmente los cambios deseados seleccionando varias secciones del correo electrónico (por ejemplo: reemplazar la línea de asunto, actualizar una imagen, etc.).

-o-

* Utilice la interfaz conversacional para realizar cambios hablando directamente con el compañero de trabajo de los equipos. Algunos ejemplos son:

  * &quot;Haga que la línea de asunto sea más urgente&quot;.
  * &quot;Acorta la copia del cuerpo&quot;.
  * &quot;Haga que call to action sea más fuerte&quot;.

También puede utilizar los botones de IA para refinar el Asunto o el Preencabezado.

![](./assets/create-an-email-campaign-5.png)

>[!TIP]
>
>Pulse la tecla escape siempre que esté en un cuadro de diálogo o en el editor de Coworker de Campaign (campañas, recorrido, etc.) para salir rápidamente.

## Paso 5: Enviar un correo electrónico de prueba

Antes de iniciar, envíese la campaña para que pueda revisarla en una bandeja de entrada real. Utilice esta opción para asegurarse de que el correo electrónico se procesa del modo deseado, de que los vínculos funcionan, de que cualquier personalización es precisa, etc.

>[!NOTE]
>
>En este momento, solo puede enviarse un correo electrónico de prueba, y solo uno a la vez.

![](./assets/create-an-email-campaign-6.png)

## Paso 6: Inicio de la campaña

Ya está listo para [iniciar su campaña](/help/coworker-for-teams/launch-manage-campaign.md#launch-a-campaign).

## Preguntas frecuentes

**¿Por qué tarda tanto la primera respuesta?**

Genera una campaña completa, incluida la estrategia, la audiencia que necesita, el flujo de trabajo, etc. El tiempo promedio de la primera respuesta con el contenido generado suele ser de alrededor de un minuto.

**¿Qué puedo hacer si el resultado de Colaborador para equipos no es correcto?**

Haga clic en el icono de comentarios en el encabezado y háganoslo saber para que podamos mejorar la plataforma.

**¿Puedo editar correos electrónicos directamente o solo mediante chat?**

Puedes hacer ambas cosas.

**¿Cómo puedo guardar una campaña sin iniciarla?**

Todas las campañas se guardan automáticamente. Si necesitas acceso a conversaciones recientes, están disponibles en la ventana de la izquierda (debajo de **Chats** si no has creado tu campaña, debajo de **Campañas** si es que lo has hecho).

**¿Hay un límite en el tamaño de mi archivo para la carga de CSV?**

Sí, el límite de tamaño es de 8 MB.

**¿Qué sucede si el CSV de mi audiencia devuelve errores?**

Asegúrese de que el archivo CSV no contenga caracteres ocultos &quot;enriquecidos&quot;.

**¿Cómo comparto un borrador de campaña con un compañero de equipo para que lo revise?**

No hay ningún botón &quot;Compartir&quot; en este momento. Sin embargo, puede descargar el contenido como HTML o exportarlo como un documento de PDF o Word.
