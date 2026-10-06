---
title: Validación de la implementación de Streaming Media con Coworker
description: Descubra cómo la aptitud de validación de medios de streaming de su compañero comprueba su configuración, sesiones y registros para confirmar que la implementación realiza un seguimiento correcto.
hold: true
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '1301'
ht-degree: 0%
---

# Valide la implementación de medios de streaming con su compañero

Sus compañeros de trabajo incluyen una aptitud de validación de medios de streaming que comprueba la implementación de Adobe Streaming Media (Video and Audio Analytics) en Edge Network y alimenta a Customer Journey Analytics o Adobe Analytics. En lugar de hacer referencias cruzadas manuales de Assurance, la configuración de conjuntos de datos, los grupos de campos de esquema XDM, la configuración de vistas de datos de Customer Journey Analytics y los registros de red sin procesar, se obtiene un solo informe de validación.

Si va a implementar o solucionar problemas con el seguimiento de medios de streaming, puede utilizar esta habilidad para confirmar que la implementación esté configurada correctamente, recopilar los datos según lo esperado y capturar lo que pretendía rastrear, todo ello dentro de una sola conversación de chat con compañeros.

>[!NOTE]
>
>Tenga en cuenta lo siguiente:
>
>* Esta aptitud forma parte de un flujo de trabajo opcional más grande: pasos de implementación o actualización personalizados (consulte [Planifique su implementación con el compañero](./implementation-guide.md)), implementación (consulte [Generar una lista de comprobación de implementación con los proyectos del compañero](./intelligent-checklist.md)) y validación (esta aptitud). No es necesario utilizar las tres fases. Por ejemplo, puede validar la implementación de medios de streaming sin generar un plan o una lista de comprobación.
>* Esta aptitud valida y diagnostica problemas. No corrige su configuración ni sus datos. Utilice sus conclusiones para guiar sus propias correcciones.

Utilice esta aptitud para:

* Ejecute una auditoría de configuración en la secuencia de datos, el esquema XDM, el conjunto de datos y la vista de datos de Customer Journey Analytics, con el primer punto de comprobación roto marcado como la causa probable.

  Actualmente, esta función se encuentra en disponibilidad limitada.

* Valide un ID de sesión de vídeo específico y vea exactamente qué salto, ingesta de conjuntos de datos o asignación de Customer Journey Analytics se produjo una discrepancia en.

* Valide una sesión desde un registro Charles o HAR cargado, o una lista de URL más sencilla, sin necesidad de una sesión de Assurance en directo.

  Actualmente, esta función se encuentra en disponibilidad limitada.

* Obtenga una comprobación de estado general con un único mensaje, sin necesidad de ID de sesión ni registro, que resuma la configuración y una muestra de las sesiones recientes.

## Antes de empezar

<!-- FLAG: General access prerequisite is inferred, not stated explicitly in source docs. Per-mode inputs (session ID, log file) are directly sourced from Functional Requirements. -->

### Información necesaria

Para validar la implementación de los medios de streaming, necesita lo siguiente:

* Acceda a Coworker con los datos de Adobe Experience Platform y Customer Journey Analytics de su organización conectados.

* Para una validación de ID de sesión, seleccione el ID de sesión de vídeo que desee comprobar.

* Para una validación basada en registros, un archivo de registro Charles o HAR o una lista de URL más sencilla en formato .txt, .md o .json.

No se requiere ninguna entrada específica para una auditoría de configuración o una comprobación de estado general. El compañero lee la configuración existente y toma muestras de las sesiones recientes automáticamente.

### Limitaciones

Antes de utilizar esta aptitud, tenga en cuenta lo siguiente:

* **Solo diagnóstico**: esta aptitud no corrige la configuración ni los datos. Identifica los problemas; usted realiza el cambio.
* **Solo medios de transmisión**: Esta aptitud cubre las implementaciones de medios de transmisión en Edge Network. Los conjuntos de datos que no son multimedia y las implementaciones estándar de análisis de aplicaciones o web están cubiertas por otras habilidades de validación de Coworker.
* **Solo bajo demanda**: Esta aptitud no proporciona supervisión continua o en tiempo real. Ejecútela cuando desee una comprobación, en lugar de como una alerta continua.
* **Sin rastreador integrado**: esta aptitud no rastrea el sitio o la aplicación por usted. Si desea validar la cobertura como rastreada, proporcione una salida de rastreador o de explorador sin encabezado como prueba.
* **Solo implementaciones de Edge Network**: No se admiten las rutas de implementación heredadas de Media SDK y solo Analytics.
* **Aún no se incluyen funciones más amplias**: para las versiones posteriores se han planificado la validación del flujo de eventos en directo y del flujo de trabajo, la validación del escenario o el manual del cliente, un resumen del tablero histórico de varias plataformas y la validación de activación de Real-Time CDP o Adobe Journey Optimizer de flujo descendente.

## Iniciar una sesión de validación

1. Inicie sesión en Coworker.

1. Seleccione [!UICONTROL **Nuevo chat**].

1. En el campo de texto, describa lo que desea validar. Por ejemplo:

   **Mensaje**

   > Validar #123 de ID de sesión de vídeo.

   La solicitud se redirigirá a la aptitud de validación de medios de streaming, que ejecutará el modo de validación correspondiente.

1. (Condicional) Si la aptitud necesita más información, como un ID de sesión o un archivo de registro, indíquela cuando se le solicite.

## Elija el modo de validación

La aptitud de validación de medios de streaming incluye cuatro modos.

### Auditoría de configuración

Actualmente, esta función se encuentra en disponibilidad limitada.

Valide todo el flujo de Adobe Experience Platform desde la secuencia de datos hasta la vista de datos de Customer Journey Analytics, incluido el esquema XDM, el conjunto de datos y cualquier regla de preparación de datos o campo derivado de Customer Journey Analytics. El compañero informa de un cuadro de resultados de aprobado/suspenso por salto y marca el primer punto de comprobación interrumpido como la causa probable.

Ejemplos de peticiones de datos:

* Valide la configuración de medios de streaming para la vista, el conjunto y el flujo de datos.
* Comprobar mi configuración de medios de streaming de extremo a extremo.
* ¿Mi flujo de datos de análisis de medios está configurado correctamente para Customer Journey Analytics?

### Validación de ID de sesión

Compruebe las filas del conjunto de datos de Adobe Experience Platform con la vista de datos de Customer Journey Analytics para una sesión de vídeo específica y determine si un hueco es un problema de ingesta de conjunto de datos o un problema de asignación de Customer Journey Analytics.

Ejemplos de peticiones de datos:

* Validar #123 de ID de sesión de vídeo.
* ¿Por qué la sesión abc-123 no se muestra en Customer Journey Analytics?
* Compare session xyz entre el conjunto de datos y la vista de datos de Customer Journey Analytics.

### Validación basada en registros

Actualmente, esta función se encuentra en disponibilidad limitada.

Valide una sesión desde un registro Charles o HAR que cargue o desde una lista de URL más sencilla, sin necesidad de una sesión de Assurance en directo. El compañero valida los patrones de punto de conexión, los códigos de respuesta, la secuencia de eventos y la cadencia de ping, y los estados que realizan comprobaciones que se ejecutan con plena confianza, reducen la confianza o se omiten.

Ejemplos de peticiones de datos:

* Validar los registros adjuntos de los datos de medios de streaming.
* Consulte este registro de Charles para ver el #456 del ID de sesión.
* Valide esta lista de direcciones URL con los pings de medios esperados.

### Panel de validación

Obtenga una comprobación de estado general con un solo mensaje. Coworker resume la auditoría de configuración y una comprobación de sesión ligera y muestreada en un estado, y afirma explícitamente que las comprobaciones basadas en registros no se ejecutaron si no se proporcionaba ningún registro.

Ejemplos de peticiones de datos:

* Compruebe los datos de medios de streaming.
* Dame un informe sobre mi implementación de medios de streaming.
* ¿En qué medida es saludable mi implementación de medios de streaming en general?

## Revisar los resultados

Cada modo devuelve los resultados en un formato adecuado para la validación.

**Resultados de la auditoría de configuración**

Un cuadro de resultados de aprobado/suspenso por salto que abarca la secuencia de datos, el esquema XDM, el conjunto de datos, la vista de datos de Customer Journey Analytics y la preparación de datos o las reglas de campo derivadas. Coworker identifica el primer salto fallido como la causa raíz probable.

**Resultados de validación de ID de sesión**

Un resumen de informes solo de Customer Journey Analytics que incluye el ID de sesión, los metadatos de contenido, los recuentos de filas por tipo de evento, los valores de métricas clave y una nota de integridad. Si hay un hueco, el compañero identifica si se produjo durante la ingesta de conjuntos de datos o en el paso de asignación de Customer Journey Analytics.

>[!NOTE]
>
>De forma predeterminada, los ID de sesión y los valores de identidad autenticados se excluyen de cualquier resumen exportado o compartido.

**Resultados de validación basados en registros**

Una validación estructural y de secuencia del registro cargado que abarca los patrones de punto de conexión, los códigos de respuesta, el orden de eventos y la cadencia de ping. El compañero indica qué comprobaciones se ejecutaron con plena confianza, qué se ejecutaron con una confianza reducida y cuáles se omitieron, en función de si proporcionó una captura de registro completa o una lista de URL más sencilla.

**Resultados del panel**

Un solo estado consolidado etiquetado como &quot;Configuración + Datos disponibles&quot;, que combina los resultados de la auditoría de configuración con una comprobación de muestra de sesiones recientes. El compañero nombra qué sesiones se muestrearon y afirma explícitamente que las comprobaciones basadas en registros no se ejecutaron porque no se proporcionó ningún registro.

## Funcionamiento de la validación

Cada modo se asigna a un motor específico:

* **Motor de validación de configuración**: lee la configuración de su secuencia de datos, esquema XDM, conjunto de datos y vista de datos de Customer Journey Analytics y la evalúa con un conjunto fijo de puntos de comprobación.
* **Motor de comprobación cruzada de sesión**: dado un ID de sesión, consulta el conjunto de datos y la vista de datos de Customer Journey Analytics, calcula el recuento de filas y el tipo esperados para esa sesión y compara los resultados reales en cada salto.
* **Analizador y validador de registros**: analiza el registro o la lista de direcciones URL cargados, reconstruye la secuencia de solicitudes y el tiempo, y aplica comprobaciones estructurales, de secuencia y de nivel de red.
* **Motor de agregación de tableros**: ejecuta el motor de validación de configuración y una ejecución de muestra del motor de comprobación cruzada de sesión, y los combina en un solo estado cuando no se ha proporcionado un ID de sesión, un registro o un libro de reproducción.
