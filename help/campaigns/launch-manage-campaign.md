---
description: Obtenga información sobre cómo iniciar una campaña, programar cuándo se emite y con qué frecuencia y detener de forma permanente una campaña en directo que se envía de forma activa.
title: Inicio y administración de una campaña
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%
---
# Inicio y administración de una campaña {#launch-campaign}

Una vez creada la campaña, aprenda a iniciarla, programarla cuando se publique y detenerla si es necesario.

>[!AVAILABILITY]
>
>Actualmente, la campaña de Launch solo está disponible para usuarios de regiones de América del Norte.

## Lanzamiento de una campaña

1. En la campaña completada, haga clic en **Revisar e iniciar**.

   >[!NOTE]
   >
   >Si falta algo, aparece un cuadro de diálogo con lo que debe completar. Realice las correcciones y vuelva a seleccionar **Revisar e iniciar**.

1. Una vez que la campaña pasa la comprobación de preparación, se abre el cuadro de diálogo de inicio con una previsualización del correo electrónico y la audiencia.

1. Revise la programación que se muestra en el cuadro de diálogo. Para cambiarlo, usa las opciones de horario descritas en [Programar cuando se inicie una campaña](#schedule-when-a-campaign-launches) y luego haz clic en **Guardar**.

1. Haga clic en **Iniciar campaña** cuando haya terminado.

>[!NOTE]
>
>- Una campaña no se puede iniciar con una audiencia de muestra (no real), con borradores de correo electrónico que no se hayan revisado o con una configuración de envío no configurada.
>
>- Si programa una campaña, aún puede editarla antes de su lanzamiento. No es necesario cambiar al modo de borrador.

## Programar cuando se inicie una campaña {#schedule-when-a-campaign-launches}

Al lanzar una campaña, puede elegir exactamente cuándo sale: inmediatamente, en una fecha y hora futuras específicas o en una programación recurrente. También puede volver más tarde y cambiar la programación de una campaña que ya se ha iniciado o programado.

### Requisitos previos

La campaña debe estar lista para iniciarse (se ha completado toda la configuración necesaria).

### Programar una campaña al inicio

1. En la campaña, haga clic en **Revisar e iniciar**.

1. En el cuadro de diálogo de lanzamiento, elija una opción de programación:
   - **Ahora**: la campaña comienza a enviarse inmediatamente después del lanzamiento.
   - **Programar una vez**: elija un futuro **Fecha de inicio** (fecha y hora juntas).
   - **Recurrente**: elija una **Frecuencia** (Diaria, Semanal o Mensual) y una hora de inicio, luego establezca el patrón de periodicidad (vea los campos a continuación).

1. Si se selecciona Recurrente, elija si la campaña finaliza **Nunca** o **En una fecha**, y elija una fecha de finalización si corresponde.

1. Confirme para iniciar la campaña con la programación seleccionada.

### Editar una programación existente

1. Abra la campaña y vaya a su configuración.

1. Busque la sección de programación y seleccione el resumen de programación actual.

1. Actualice la programación utilizando las mismas opciones descritas anteriormente.

1. Guarde el cambio.

### Campos de entrada

| Campo | Descripción | ¿Requerido? |
| --- | --- | --- |
| Modo de horario | Opción de ahora, programar una vez o recurrente | Sí |
| Fecha de inicio | Fecha y hora de inicio de la campaña (modo Schedule once) | Sí, para Programar una vez |
| Frecuencia | Diario, Semanal o Mensual (modo recurrente) | Sí, para recurrente |
| Hora de inicio | Hora del día en que la campaña recurrente envía | Sí, para recurrente |
| Días de la semana | Qué día(s) de la campaña se repite | Sí, para frecuencia semanal |
| Día del mes | En qué día del mes se repite la campaña | Sí, para la frecuencia mensual |
| Finalizar campaña | Nunca, o en una fecha de finalización específica | Sí, para recurrente |

### Cosas que debe tener en cuenta

- Las campañas recurrentes se pueden configurar para que se ejecuten indefinidamente o hasta una fecha final específica. Las campañas únicas e inmediatas no tienen una opción de fecha de finalización, ya que se ejecutan una vez.
- La programación no admite intervalos de repetición personalizados, como &quot;cada 2 semanas&quot; o &quot;cada 3 días&quot;. Tampoco admite una periodicidad mensual relativa, como &quot;el segundo lunes del mes&quot;.

## Detener una campaña {#stop-campaign}

Puede detener una campaña que esté enviando activamente (una campaña &quot;en directo&quot;) directamente desde la página de detalles de la campaña.

>[!CAUTION]
>
>Detener una campaña es permanente. Los destinatarios dejan de avanzar por la campaña inmediatamente y la campaña no se puede reanudar ni reiniciar más tarde. Para volver a enviar, debe crear una nueva campaña e iniciarla.

<!--

### Prerequisites

- [NEEDS INPUT - to confirm with engineer: does stopping a campaign require a specific role or permission, or can any user with campaign access do this?]

-->

### Cómo detener una campaña

1. Abra una campaña que esté activa actualmente.

1. En el encabezado de detalles de la campaña, haga clic en **Detener campaña**.

1. Haga clic en **Detener** para confirmar.
