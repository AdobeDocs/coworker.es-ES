---
title: Migración de proyectos de Adobe Analytics a Customer Journey Analytics
description: Utilice a sus colaboradores para validar, asignar y migrar proyectos de Adobe Analytics Workspace y sus componentes a Customer Journey Analytics y, a continuación, compruebe el estado de la migración.
feature: AI Tools
role: Admin
level: Intermediate
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '1785'
ht-degree: 1%
---

# Migración de proyectos de Adobe Analytics a Customer Journey Analytics con Coworker

<!-- FLAG: Confidence: High for the conversation flow, which is sourced from screenshots of the Coworker UI (October 2026) and the aa-mcp tool descriptions. The component migration tools run through the aa-mcp integration; there's no dedicated skill yet. Medium for statements that Coworker shares mappings and migration rules with migrations in the Adobe Analytics user interface; the user believes this is likely. Confirm with engineering. -->

Utilice Adobe CX Enterprise Coworker para migrar proyectos de Adobe Analytics y sus componentes asociados a Customer Journey Analytics en una sola conversación.

El compañero comprueba que las dimensiones y métricas del proyecto están asignadas a la vista de datos de Customer Journey Analytics, le ayuda a asignar cualquier dimensión que no esté disponible y, a continuación, vuelve a crear el proyecto en Customer Journey Analytics.

<!-- FLAG: Add the planned general availability date when it's confirmed. -->

>[!AVAILABILITY]
>
>La funcionalidad descrita en este artículo se encuentra en la fase de prueba limitada de la versión y es posible que aún no esté disponible en su entorno. Esta nota se eliminará cuando la funcionalidad esté disponible de forma general.

>[!IMPORTANT]
>
>Antes de migrar cualquier proyecto, lea [Prepararse para migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration) en la documentación de Adobe Analytics. Explica cómo prepararse para una migración, qué se incluye, qué elementos causan errores y cómo afectan las asignaciones a toda la organización. Esta información se aplica a las migraciones en Coworker.

## Diferencias con la migración en la interfaz de usuario de Adobe Analytics

<!-- FLAG: Add rows as differences are confirmed. Who can migrate and How you migrate: SME Scott Tomko (October 2026); Coworker matches the Analytics 2.0 Component Migration APIs, and functionally both methods do much the same thing. Project owner: Coworker behavior is from a test conversation (October 2026); the Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. Mapping dimensions and metrics: Confidence Medium for the Coworker column, which is based on the aa-mcp tool descriptions and a test conversation, not on an observed failed validation. Confirm that Coworker suggests and updates mappings, and whether it asks for confirmation before it updates a mapping. The Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. -->

La migración de proyectos con Coworker difiere de la migración en la interfaz de usuario de Adobe Analytics de las siguientes maneras:

| | Coworker | Interfaz de usuario de Adobe Analytics |
| --- | --- | --- |
| **Quién puede migrar proyectos** | Administradores de Adobe Analytics y usuarios con el permiso [!UICONTROL **Migración de componentes**] | Solo administradores de Adobe Analytics |
| **Propietario del proyecto** | El usuario que realiza la migración | El usuario que especifique en el campo [!UICONTROL **Propietario del proyecto**] |
| **Dimensiones y métricas de asignación** | El compañero valida el proyecto y enumera cómo se asigna cada dimensión y métrica. Para los que no se pueden asignar automáticamente, el colaborador sugiere una dimensión o métrica en la vista de datos y actualiza la asignación. | En la sección [!UICONTROL **Asignar esquema**], seleccione cada dimensión o métrica con un estado [!UICONTROL **No asignado**] y asígnela manualmente. |
| **Cómo migras** | Describa lo que desea en un mensaje. El compañero hace el trabajo, haciendo algunas preguntas en el camino. Por ejemplo, un compañero puede crear un proyecto con los componentes que usted nombre y luego migrarlo. Ver [Comenzar desde componentes específicos](#start-from-specific-components). | Cree un proyecto en Analysis Workspace, añada los componentes que desea migrar y guarde el proyecto. A continuación, en [!UICONTROL **Migración de componentes**], seleccione el proyecto, especifique un propietario de proyecto, asigne el esquema para cada grupo de informes y seleccione [!UICONTROL **Migrar**]. |

## Requisitos previos

<!-- FLAG: Confidence: High for the Adobe Analytics MCP and permission bullets, which come from the release announcement and SME Scott Tomko (October 2026): like the Analytics 2.0 Component Migration APIs, Coworker lets non-admins with the Component Migration permission migrate projects, while the Adobe Analytics UI is admin-only. Open question: Coworker makes the user who runs the migration the owner of the new project, but the aa-mcp tool description says the owner "should be an admin" and the Adobe Analytics component migration docs say the owner must be a Customer Journey Analytics administrator. Confirm whether a non-admin who runs a migration needs Customer Journey Analytics admin rights, or whether Coworker assigns a different owner. -->

Para migrar proyectos con Coworker, necesita:

* Acceso al MCP de Adobe Analytics. Las herramientas de migración de componentes se habilitan automáticamente para los clientes que tienen acceso a MCP de Adobe Analytics. Para confirmar que [!UICONTROL **aa-mcp**] está conectado, consulte [Introducción al análisis de datos con el chat de compañeros](/help/chat/use-cases/data-insights/analytics-chat.md).

* Derechos de administrador de Adobe Analytics o el permiso [!UICONTROL **Migración de componentes**] en Admin Console. No es necesario que sea un administrador.

* Los [requisitos previos](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#prerequisites) para la migración de componentes en la documentación de Adobe Analytics.

* Proyecto que utiliza grupos de informes base. No se pueden migrar los grupos de informes virtuales.<!-- FLAG: Sourced from Coworker's response in the UI. The Adobe Analytics component migration docs don't mention virtual report suites. Confirm, and consider adding it to those docs. -->

## Revise las asignaciones de grupos de informes antes de migrar

<!-- FLAG: Confidence: Medium. The recommendation to review mappings before the first migration from a report suite is inferred from the Adobe Analytics guidance to decide mappings as an organization; Coworker also validates mappings during each migration. Confirm with Scott. -->

Considere la posibilidad de revisar cómo se asignan las dimensiones y métricas de un grupo de informes antes de la primera migración desde ese grupo de informes. Las asignaciones se aplican a todos los proyectos que migra su organización, por lo que la configuración en primer lugar ayuda a los proyectos posteriores a aprobar la validación. Para obtener instrucciones sobre cómo elegir asignaciones, consulte [Decida como organización cómo asignará los componentes](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#decide-as-an-organization-how-you-will-map-components) en la documentación de Adobe Analytics.

Para revisar las asignaciones, seleccione [!UICONTROL **Revisar asignaciones solamente**] en la ficha [!UICONTROL **Ámbito**] o pregunte directamente al Compañero de trabajo:

**Indicadores**

* &quot;Mostrarme cómo se asignan las dimensiones y métricas del grupo de informes a mi vista de datos&quot;
* &quot;¿Qué dimensiones y métricas del grupo de informes no están asignadas a mi vista de datos?&quot;

También puede pedir al compañero que actualice las asignaciones.

Si omite esta revisión, Coworker sigue [comprobando las asignaciones de cada proyecto que migra](#review-the-validation-results-and-mappings).

## Iniciar una migración

<!-- FLAG: Confidence: High that migration works at the project level and that components migrate with their project (component-migration.md in the Adobe Analytics docs), and that components that already exist in Customer Journey Analytics aren't re-created (prepare-component-migration.md). Medium-low for when to use each method and for combining them; this guidance is inferred and isn't in the Adobe Analytics docs. Confirm with Scott. Also confirm whether Coworker creates a project automatically when you ask it to migrate only components (for example, "Migrate my Spring sale segments to CJA"), or whether you must ask it to create the project. -->

El compañero siempre migra un proyecto y sus componentes asociados. Para migrar componentes específicos, pídale a sus compañeros que los añadan a un proyecto nuevo y, a continuación, migre ese proyecto.

Los componentes que ya existen en Customer Journey Analytics no se vuelven a crear, por lo que puede utilizar ambos métodos. Por ejemplo, migre primero los proyectos más importantes y, a continuación, migre los componentes restantes. Elija por dónde empezar en función de lo que desee en Customer Journey Analytics:

* **Migrar un proyecto** cuando desee mantener los paneles y las visualizaciones del proyecto en Customer Journey Analytics. Ver [Iniciar desde un proyecto](#start-from-a-project).
* **Migre componentes específicos** cuando quiera componentes como segmentos, métricas calculadas o intervalos de fechas en Customer Journey Analytics, pero no necesite ninguno de los proyectos que los usen. Por ejemplo, puede planificar la creación de nuevos proyectos en Customer Journey Analytics que los incluyan. Ver [Comenzar desde componentes específicos](#start-from-specific-components).

### Empezar desde un proyecto

Para migrar un proyecto y sus componentes asociados:

1. Inicie sesión en Coworker.

1. Seleccione **[!UICONTROL Nuevo chat]**.

1. En el campo de texto, pida a sus compañeros que migren el proyecto. Por ejemplo:

   **Mensaje**

   > Quiero migrar componentes de Adobe Analytics a Customer Journey Analytics.

   El compañero describe lo que puede migrar e inicia un cuestionario.

1. En la ficha [!UICONTROL **Ámbito**], seleccione una de las siguientes opciones y, a continuación, seleccione [!UICONTROL **Siguiente**]:

   <!-- FLAG: Confidence: Medium for the "Plan a full upgrade" description. It likely hands off to the implementation guide skill and leaves the migration flow. Confirm with engineering. Also confirm what the Source & target tab asks; it was skipped in the screenshots. The Next and Submit buttons on the first questionnaire's Source & target and Review tabs are assumed to work like the second questionnaire. -->

   | Opción | Descripción |
   | --- | --- |
   | [!UICONTROL **Un proyecto AA específico**] | Migre un proyecto al que le asigne un nombre. Siga los pasos restantes de esta sección. |
   | [!UICONTROL **Revisar asignaciones solamente**] | Compruebe cómo se asignan las métricas y dimensiones de un grupo de informes a una vista de datos sin migrar nada. Consulte [Revisar las asignaciones de los grupos de informes antes de migrar](#review-report-suite-mappings-before-you-migrate). |
   | [!UICONTROL **Planificar una actualización completa**] | Obtenga un plan completo para pasar de Adobe Analytics a Customer Journey Analytics. Ver [Planifique su implementación con Coworker](/help/chat/use-cases/data-insights/implementation-guide.md). |

1. (Opcional) Responda las preguntas de la ficha [!UICONTROL **Source y Target**] y, a continuación, seleccione [!UICONTROL **Siguiente**].

1. En la ficha [!UICONTROL **Revisar**], confirme sus respuestas y, a continuación, seleccione [!UICONTROL **Enviar**].

   El compañero comprueba a qué empresas de Adobe Analytics tiene acceso y cuántos grupos de informes base tiene cada una; a continuación, comienza un segundo cuestionario.

1. Responda las siguientes preguntas, seleccionando [!UICONTROL **Siguiente**] después de cada una:

   | Tabulación | Pregunta | Contexto adicional |
   | --- | --- | --- |
   | [!UICONTROL **Proyecto**] | ¿Cuál es el nombre del proyecto AA que desea migrar? | Un nombre parcial está bien. |
   | [!UICONTROL **Grupo de informes**] | ¿Qué grupo de informes utiliza el proyecto? | Seleccione un grupo de informes de la lista o escriba el nombre de otro. |
   | [!UICONTROL **Vista de datos**] | ¿A qué vista de datos de CJA debe migrar? | (Opcional) Escriba el nombre de una vista de datos o déjela en blanco, y el Compañero de trabajo sugerirá vistas de datos coincidentes. |

1. En la ficha [!UICONTROL **Revisar**], confirme sus respuestas y, a continuación, seleccione [!UICONTROL **Enviar**].

   Para omitir el cuestionario en cualquier paso, selecciona [!UICONTROL **Omitir cuestionario**] y describe lo que deseas en el chat en su lugar.

1. Continúe con [Revise los resultados de validación y las asignaciones](#review-the-validation-results-and-mappings).

### Empezar desde componentes específicos

<!-- FLAG: Sourced from a prompt that SME Scott Tomko ran in Coworker (October 2026). The example is generalized; the original prompt named a customer. Coworker may ask a few questions along the way. Confirm what happens to the project that Coworker creates in Adobe Analytics, and to its migrated copy in Customer Journey Analytics, if you only wanted the components. -->

Para migrar componentes específicos:

1. Pida a sus compañeros que creen un proyecto con esos componentes y luego lo migren. Por ejemplo:

   **Mensaje**

   > Quiero migrar todos mis segmentos de Analytics con &quot;Rebajas de primavera&quot; en el nombre a CJA. Cree un nuevo proyecto de Workspace con todos estos segmentos añadidos y, a continuación, migre ese proyecto a CJA.

   Su compañero crea el proyecto en Adobe Analytics.

1. Continúe con la siguiente sección: [Revise los resultados de validación y las asignaciones](#review-the-validation-results-and-mappings).

## Revise los resultados de validación y las asignaciones

<!-- FLAG: Confidence: Medium for the steps that fix a failed validation. They're based on the aa-mcp tool descriptions and on a test conversation where validation passed only after the project's panel was switched to a base report suite. Confirm how Coworker presents a failed validation, and whether it asks for confirmation before it updates a mapping. -->

El compañero valida el proyecto con la vista de datos seleccionada y, a continuación, informa de si el proyecto se puede migrar. Los resultados enumeran cada dimensión y métrica del proyecto y la dimensión o métrica de Customer Journey Analytics a la que está asignada. Por ejemplo:

* **Métrica:** Ocurrencias se convierte en eventos
* **Dimension:** La hora permanece Hora

Para ver los componentes y elementos de proyecto que se migran, consulte [Comprender lo que se incluye en una migración](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-what-is-included-in-a-migration) en la documentación de Adobe Analytics.

Si la validación no pasa:

* **Dimensiones o métricas que no se pueden asignar automáticamente:** El compañero sugiere una dimensión o métrica en la vista de datos para asignar cada una de ellas a, actualiza la asignación y, a continuación, valida de nuevo el proyecto. También puede indicarle a su Compañero de trabajo a qué dimensión o métrica asignarla, por ejemplo, &quot;Asignar vistas de página a web.webPageDetails.pageViews.value&quot;.

* **Elementos no compatibles:** Quite cualquier elemento no compatible del proyecto en Adobe Analytics. Por ejemplo, asegúrese de que cada panel utilice un grupo de informes base en lugar de un grupo de informes virtuales. A continuación, pida a sus compañeros que comprueben de nuevo el proyecto. Para obtener la lista de elementos no compatibles, consulte [Comprender los elementos no compatibles que causan errores](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-unsupported-elements-that-cause-errors) en la documentación de Adobe Analytics.

Para comprobar las asignaciones de todo un grupo de informes antes de migrar, consulte [Revisar las asignaciones de los grupos de informes antes de migrar](#review-report-suite-mappings-before-you-migrate).

## Migración del proyecto

1. Cuando la validación se aprueba, el colaborador pregunta si desea crear la versión de Customer Journey Analytics del proyecto en la vista de datos seleccionada. Seleccione [!UICONTROL **Sí, migrar**] y luego seleccione [!UICONTROL **Enviar**].

   Para detenerse sin migrar, seleccione [!UICONTROL **No, deténgase aquí**].

   El colaborador vuelve a crear el proyecto en Customer Journey Analytics, con usted como propietario del proyecto. El proyecto original de Adobe Analytics no cambia.

1. Continúe con la sección siguiente, [Comprobar el estado de la migración](#check-the-migration-status).

## Comprobación del estado de la migración

Las migraciones se ejecutan en segundo plano, por lo que es posible que el nuevo proyecto no esté listo de inmediato.

1. Solicitar a los compañeros que comprueben el estado de la migración:

   **Mensaje**

   > Comprobar estado

   <!-- FLAG: The Failed row links to Retry a failed migration in the Adobe Analytics docs, but those steps use the Component migration page in the Adobe Analytics UI, which is admin-only. A non-admin with the Component Migration permission can't follow them. Confirm with Scott whether Coworker can retry a failed migration (for example, "Retry the migration"). If so, replace the link with a prompt. -->

   El compañero informa de uno de los siguientes estados:

   | Estado | Lo que significa |
   | --- | --- |
   | En cola | La migración está esperando para iniciarse. |
   | Iniciado | La migración está en curso. |
   | Completado | La migración ha finalizado. El compañero proporciona un resumen de lo que se ha migrado, incluido el nombre del proyecto y la vista de datos. |
   | Error | Error en la migración. Puede volver a intentar la migración. Consulte [Reintentar una migración fallida](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/component-migration#retry-a-failed-migration) en la documentación de Adobe Analytics. |

1. Cuando finalice la migración, abra el nuevo proyecto desde la lista de proyectos en Customer Journey Analytics Workspace.

1. (Opcional) Transfiera la propiedad del proyecto a cualquier usuario de Customer Journey Analytics. Para obtener más información, consulte [Transferir recursos](https://experienceleague.adobe.com/es/docs/analytics-platform/using/tools/asset-transfer/transfer-assets).

Una vez finalizada la migración, los compañeros pueden sugerir otro proyecto para migrar.

## Sugerencias para obtener mejores resultados

* Deje la vista de datos en blanco en el cuestionario si no está seguro de cuál usar. Sus compañeros sugieren vistas de datos que coinciden con el grupo de informes.
* Después de la migración, compare los datos de Adobe Analytics y Customer Journey Analytics para confirmar que los informes coinciden. Ver [Validar datos con el compañero al actualizar de Adobe Analytics a Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).

## Próximos pasos

* Para migrar proyectos en la interfaz de usuario de Adobe Analytics, consulte [Migrar componentes y proyectos de Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics/admin/admin-tools/component-migration/component-migration) en la documentación de Adobe Analytics.
* Para los demás casos de uso de implementación y administración, consulte [Descripción general de la implementación y administración inteligentes](/help/chat/use-cases/data-insights/data-governance-and-validation.md).
