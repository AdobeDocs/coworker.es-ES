---
title: Planifique su implementación de Customer Journey Analytics o medios de streaming con su compañero
description: Descubra cómo las habilidades de la guía de implementación de Coworker convierten una conversación de descubrimiento en un plan de implementación personalizado y ordenado con listas de comprobación exportables.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 1%
---

# Planifique su implementación con Coworker

Adobe CX Enterprise Coworker incluye cinco habilidades de guía de implementación, una para cada superficie de producto: Customer Journey Analytics, una actualización de Adobe Analytics a Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) y medios de streaming. Cada aptitud convierte una breve conversación de contacto en un plan de implementación personalizado y con reconocimiento de dependencia, con una lista de comprobación interactiva y exportaciones listas para usar, todo ello dentro de una única conversación de chat con el compañero.

Si está de pie o migrando a cualquiera de estos productos, puede utilizar estas habilidades para obtener un plan ordenado paso a paso, sin investigar manualmente los requisitos de implementación de Adobe ni crear un plan de proyecto desde cero.

>[!NOTE]
>
>Tenga en cuenta lo siguiente:
>
>* Estas habilidades para la guía de implementación forman parte de un flujo de trabajo opcional más grande: pasos de implementación o actualización personalizados (estas guías), implementación (consulte [Generación de una lista de comprobación de implementación con proyectos de compañeros](./intelligent-checklist.md)) y validación (por ejemplo, [Validación de la actualización de Adobe Analytics a Customer Journey Analytics](./data-validation-aa-cja.md) o [Validación de la implementación de medios de streaming](./streaming-media-validation.md)). No es necesario utilizar las tres fases. Por ejemplo, puede validar los datos sin generar un plan o una lista de comprobación.
>* Estas habilidades no acceden a sus sistemas de Adobe ni realizan ningún cambio. Le ayudan a planificar su implementación. No lo realizan ni lo verifican con un inquilino activo.

Utilice estas aptitudes para:

* Obtenga un plan personalizado y ordenado para defender Customer Journey Analytics desde cero, incluidos los propietarios, las estimaciones de esfuerzo y las dependencias para cada paso.

* Obtenga un plan de migración para la actualización de Adobe Analytics a Customer Journey Analytics, que incluya la asignación de paridad de características de Adobe Analytics, la secuenciación del relleno histórico y una puerta de validación antes de eliminar Adobe Analytics.

* Obtenga un plan guiado para implementar Content Analytics (ACA), que incluye licencias, ámbitos de privacidad y PII y el asistente de configuración guiada.

* Obtenga un plan de incorporación para Marketing Campaign Analytics (MCA) que se adapte a su ruta de ingesta, ya sea que utilice conectores de origen de Adobe, su propio conjunto de datos o un enfoque híbrido.

* Obtenga un plan de implementación para la recopilación de medios de streaming en Edge, incluida la configuración del flujo de datos, la implementación de SDK/API por plataforma y el modelo de eventos de medios.

## Antes de empezar

<!-- FLAG: Best guess, not confirmed by source docs. Requirements doc doesn't state explicit prerequisites for starting a discovery conversation — verify with skills-overview.md or SME before publishing. -->

### Información necesaria

Para iniciar una conversación sobre la guía de implementación, necesita lo siguiente:

* Cuál de las cinco rutas de implementación se aplica a usted: Customer Journey Analytics (nuevo), una actualización de Adobe Analytics a Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) o medios de streaming.

* Detalles básicos sobre su entorno actual, como si tiene una implementación de Adobe Analytics existente, el estado de las licencias o la ruta de ingesta de datos planeada. La conversación de contacto le pide estos detalles, pero tenerlos listos acelera el proceso.

### Limitaciones

Antes de utilizar estas habilidades, tenga en cuenta las siguientes limitaciones:

* **Solo planificación**: estas habilidades no tienen acceso a los sistemas de Adobe ni realizan cambios. No realizan la implementación ni la verifican con un inquilino activo.
* **Una superficie de producto por aptitud**: Cada aptitud cubre una sola ruta de implementación. Si la solicitud se aplica a una superficie de producto diferente, la aptitud le dirige a la correcta en lugar de responder directamente.
* **No es una experiencia de seguimiento de proyectos por sí sola**: estas habilidades generan un plan y exportaciones, pero no realizan un seguimiento del estado, la colaboración o las aprobaciones en curso por sí mismas. Para realizar un seguimiento del plan a lo largo del tiempo, transforme el plan en un proyecto de compañeros mediante un manual predefinido. Consulte [Generar una lista de comprobación de implementación con proyectos de compañeros](./intelligent-checklist.md).

## Iniciar una sesión de planificación de implementación

1. Inicie sesión en Coworker.

1. Seleccione [!UICONTROL **Nuevo chat**].

1. En el campo de texto, describa la implementación o migración que desee planificar. Por ejemplo:

   **Mensaje**

   > Ayúdeme a planificar la implementación de Customer Journey Analytics.

   La solicitud se dirige a la aptitud de la guía de implementación correspondiente, que inicia una conversación interactiva de descubrimiento.

1. (Condicional) Si la aptitud no puede determinar qué ruta de implementación se le aplica, responda la pregunta aclaratoria que le haga y continúe.

## Elija la ruta de implementación

Cada aptitud para la guía de implementación cubre una superficie de producto.

### Customer Journey Analytics

Obtenga un plan de implementación personalizado y ordenado para hacer frente a Customer Journey Analytics desde cero, sin una implementación de Adobe Analytics existente para migrar. El plan incluye propietarios, estimaciones de esfuerzo y dependencias para cada paso.

Ejemplos de peticiones de datos:

* Ayúdeme a planificar la implementación de Customer Journey Analytics.
* Estoy levantando Customer Journey Analytics desde cero. Construye un plan de implementación.

### Actualización de Adobe Analytics a Customer Journey Analytics

Obtenga un plan de migración que asigne la paridad de las funciones de Adobe Analytics a Customer Journey Analytics, secuencie el relleno histórico e incluya una puerta de validación y de ejecución paralela antes de retirar el Adobe Analytics.

Ejemplos de peticiones de datos:

* Ayúdeme a planificar la actualización de Adobe Analytics a Customer Journey Analytics.
* Genere un plan de migración de Adobe Analytics a Customer Journey Analytics.

### Content Analytics (ACA)

Obtenga un plan guiado para implementar Content Analytics (ACA), que incluye licencias, ámbitos de privacidad y PII y el asistente de configuración guiada. Debido a que ACA no tiene cobertura DULE, CMK o HIPAA, su plan incluye pasos de acceso de privacidad.

Ejemplos de peticiones de datos:

* Ayúdeme a planificar la implementación de Content Analytics.
* Compile un plan de implementación de ACA.

### Marketing Campaign Analytics (MCA)

Obtenga un plan de incorporación para Marketing Campaign Analytics (MCA) Essentials que se adapte a su ruta de ingesta, ya sea que utilice conectores de origen de Adobe, su propio conjunto de datos o un enfoque híbrido, de modo que los pasos de asignación y alineación de datos de funnel coincidan con su entorno.

Ejemplos de peticiones de datos:

* Ayúdeme a planificar la implementación de Marketing Campaign Analytics.
* Construir un plan de incorporación de MCA usando mi propio conjunto de datos.

### Medios de streaming

Obtenga un plan de implementación para la recopilación de medios de streaming en Edge que cubra la configuración del flujo de datos, la implementación de SDK/API por plataforma y el modelo de eventos de medios, de modo que instrumente correctamente las sesiones, los pings y las finalizaciones para los informes de Customer Journey Analytics o Adobe Analytics.

Ejemplos de peticiones de datos:

* Ayúdeme a planificar mi implementación de medios de streaming.
* Construye un plan para instrumentar Streaming Media en Edge.

## Revisar los resultados

El compañero le devuelve su plan de implementación como una lista de comprobación interactiva y un resumen en la misma conversación.

**Lista de comprobación interactiva**

Lista de comprobación de HTML que agrupa los pasos de la implementación en fases e hitos. Para cada paso, la lista de comprobación incluye:

* Una estimación del esfuerzo
* Un propietario principal y cualquier propietario secundario
* Dependencias fijas de otros pasos
* Si el paso se puede omitir
* Un vínculo a la documentación de Experience League o developer.adobe.com pertinente

**Exportaciones**

Descargue el plan en el formato que mejor se adapte a su flujo de trabajo:

| Exportar | Qué incluye |
| --- | --- |
| CSV | Una lista sencilla de pasos |
| Jira-import CSV | Pasos con formato de puntos de historia, prioridad y etiquetas para importar en Jira |
| CSV de Workfront | Pasos formateados con duraciones y predecesores para su importación en Workfront |
| Markdown | Una lista de comprobación que puede pegar en la documentación o en las wikis |

**Resumen en el chat**

Junto con la lista de comprobación, Coworker proporciona un resumen de tres partes directamente en la conversación:

1. Una visión general de su plan
1. La tabla de pasos completa
1. Vínculos de descarga para cada exportación

## Cómo se crea el plan

Cada aptitud para la guía de implementación sigue el mismo proceso de cuatro fases:

* **Descubrimiento**: una conversación por fases le hace de 5 a 9 conjuntos de preguntas, específicas de su ruta de implementación, para conocer su entorno y sus objetivos.
* **Calcular**: un LLM determina qué pasos condicionales y anulaciones de dependencia se aplican a sus respuestas. No escribe el plan en sí.
* **Montar y procesar**: un proceso determinista resuelve las dependencias entre pasos, los ordena, calcula la ruta crítica (la cadena más larga de pasos dependientes) y genera la lista de comprobación y las exportaciones.
* **Entrega**: El compañero proporciona vínculos de descarga y un resumen en el chat de tu plan.

Esta combinación de descubrimiento guiado y ensamblado determinístico significa que su plan se genera consistentemente a partir de sus respuestas, en lugar de escribirse a mano alzada.
