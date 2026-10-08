---
title: Generación de una lista de comprobación de implementación en proyectos de compañeros
description: Descubra cómo Proyectos de compañeros genera una lista de comprobación de implementación previamente rellenada a partir de su plan de guías de implementación, con pasos que puede asignar y rastrear.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---

# Generación de una lista de comprobación de implementación con Proyectos de compañeros

Adobe CX Enterprise Coworker puede generar un proyecto de lista de comprobación de implementación en Proyectos de compañeros, previamente completado con los pasos ordenados del plan de guía de implementación para Customer Journey Analytics, una actualización de Adobe Analytics a Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) o medios de streaming. El compañero automatiza o asiste con tantos pasos como sea técnicamente posible, de modo que usted y su equipo tengan un único lugar al que se pueda realizar el seguimiento para trabajar durante la implementación.

Si lidera una implementación, ejecuta pasos técnicos o solo necesita visibilidad del progreso, puede utilizar esta lista de comprobación para asignar el trabajo, rastrear el estado y colaborar con su equipo, sin salir de Compañero de trabajo.

>[!NOTE]
>
>Tenga en cuenta lo siguiente:
>
>* Esta característica forma parte de un flujo de trabajo opcional más grande: pasos de implementación o actualización personalizados (consulte [Planifique su implementación con el compañero](./implementation-guide.md)), implementación (esta lista de comprobación) y validación (por ejemplo, [Valide su actualización de Adobe Analytics a Customer Journey Analytics](./data-validation-aa-cja.md) o [Valide su implementación de Streaming Media](./streaming-media-validation.md)). No es necesario utilizar las tres fases, pero la generación de esta lista de comprobación requiere un plan de guía de implementación completado.
>* Los pasos que ejecuta o ayuda el colaborador incluyen automáticamente una señal de confianza o verificación. Revise estos pasos antes de marcarlos como completados: el compañero no presenta los resultados automatizados como un hecho verificado.

Utilice esta lista de comprobación para:

* Inicie una implementación o migración con un conjunto de pasos ordenados y rellenados previamente para la ruta del producto, en lugar de ensamblar un plan manualmente.

* Comprobar el estado a mitad de la implementación, incluidos los bloqueados y los siguientes, sin preguntar directamente al posible cliente de la implementación.

* Planifique una implementación de varias plataformas o regiones, donde los pasos se ejecuten en paralelo o por fases en lugar de una sola línea recta.

* Permita que sus compañeros ejecuten los pasos directamente siempre que sea posible, como ejecutar una comprobación de validación entre las configuraciones de Adobe Analytics y Customer Journey Analytics.

* Introduzca puertas de aprobación para los pasos que necesiten desactivación antes de que su equipo avance.


## Antes de empezar

<!-- FLAG: Open question — release note confirms a "predefined playbook" transforms the guide plan into a Coworker Project, but it's unconfirmed whether Coworker runs that playbook automatically or the user has to trigger/follow it manually. Written below as if Coworker does it automatically; verify before publishing. Exact UI mechanics also unconfirmed since Coworker Projects platform documentation doesn't exist yet. -->

### Información necesaria

Para generar una lista de comprobación de implementación, necesita lo siguiente:

* Una conversación completa sobre la guía de implementación de la ruta del producto. Ver [Planifique su implementación con Coworker](./implementation-guide.md). Coworker transforma automáticamente este plan en un proyecto de Coworker, utilizando un manual predefinido; no es necesario que exporte nada usted mismo.

* Acceso a los proyectos de compañeros de su organización.

### Limitaciones

Antes de utilizar esta función, tenga en cuenta lo siguiente:

* **No posee el contenido de la guía**: esta característica consume los planes de las habilidades de la guía de implementación. No crea ni mantiene ese contenido subyacente.
* **El comportamiento de sincronización aún no está completamente definido**: La lista de comprobación está pensada para estar sincronizada con las actualizaciones de su plan de guía de implementación, pero aún se está definiendo el mecanismo de sincronización exacto. Consulte manualmente las actualizaciones del plan de guía si la implementación abarca un periodo de tiempo largo.
* **Requiere proyectos de compañeros**: esta característica depende de que la plataforma Proyectos de compañeros esté disponible en su organización.

## Generación de una lista de comprobación

<!-- FLAG: Best guess, not confirmed by source docs. Coworker Projects UI isn't documented in this repo yet — verify exact navigation and UI labels once available. -->

1. Inicie sesión en Coworker.

1. Seleccione [!UICONTROL **Proyectos**] en el carril de navegación.

1. Seleccione [!UICONTROL **Nuevo proyecto**] y, a continuación, seleccione el manual predefinido que coincida con su plan de guía de implementación.

   El compañero transforma su plan en un proyecto previamente completado con los pasos ordenados para su ruta.

## Revisar los resultados

Los compañeros generan su lista de comprobación de implementación como un proyecto de compañeros desde el que usted y su equipo pueden trabajar.

**Vista de proyecto**

El proyecto agrupa los pasos de implementación ordenados a partir del plan. Para cada paso, puede:

* Asignar un propietario
* Actualizar estado, como en curso o completo
* Marque un paso como no aplicable u omítalo si no se aplica a su implementación
* Añada comentarios y colabore con su equipo
* Requerir aprobación antes de que se considere que un paso está completo, para los pasos que necesitan desactivación

**Pasos automatizados y asistidos**

Cuando es técnicamente factible, el colaborador ejecuta o ayuda con un paso directamente, como la aparición de datos de configuración o estado de Adobe Analytics o Customer Journey Analytics. Estos pasos incluyen una señal de confianza o verificación, tal como se ha descrito anteriormente.

**Exportaciones**

Exporte la lista de comprobación o su progreso a nivel de resumen a Jira, Workfront o Excel para poder plegarla en el flujo de trabajo de administración de proyectos existente.

**Múltiples listas de comprobación**

Si administra varias implementaciones simultáneas, como varios grupos de informes, regiones o marcas, puede mantener varios proyectos de lista de comprobación de implementación en lugar de estar limitado a uno.
