---
title: Validación de los datos de Experience Platform con compañeros de trabajo
description: Aprenda a utilizar la habilidad de validación de datos de CX Enterprise Coworker para comprobar la calidad de los conjuntos de datos y campos de Adobe Experience Platform a través del chat.
feature: AI Tools
role: User
level: Intermediate
doc-type: Tutorial
last-substantial-update: 2026-08-27T00:00:00.000Z
jira: PLAT-302857
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1058'
ht-degree: 0%
---

# Validación de los datos de Experience Platform con Coworker

Adobe CX Enterprise Coworker incluye la aptitud Validación de datos, que comprueba la calidad de los datos de los conjuntos de datos de Experience Platform. Utilícelo para ejecutar validaciones estadísticas y semánticas en conjuntos de datos, analizar campos de conjuntos de datos e identificar problemas de calidad de datos, todo ello a través de una sola conversación de Coworker Chat.

Los ingenieros de datos, administradores de datos e ingenieros de implementación lo utilizan para realizar comprobaciones de calidad rápidas, sin consultas SQL ni jerarquías de esquema complejas.

Utilice esta aptitud para:

* Valide los campos de identidad y evento clave después de una nueva implementación o una actualización de la implementación.
* Investigue un problema de asignación sospechoso inspeccionando los valores principales y los valores no válidos de un campo.
* Ejecute comprobaciones continuas de administración de datos en conjuntos de datos críticos para detectar regresiones de forma temprana.

<!--TODO: skill display name "Data Validation skill" confirmed via the published KT-22622 video page (validate-dataset-quality-for-cja.md, merged 2026-09-16). Still need the technical skill ID from engineering (Petru Adrian Snep) for the use-cases overview table row. That page didn't add one either.-->

>[!NOTE]
>
>Esta aptitud es de solo lectura. No cambia los datos, esquemas o asignaciones.

## Antes de empezar

Para validar los datos con Coworker, necesita:

* El nombre o ID del conjunto de datos que desea validar.
* (Opcional) El nombre de un campo específico que se va a validar, si no desea que la aptitud seleccione campos automáticamente.

## Iniciar una sesión de validación

1. Inicie sesión en Coworker.

1. Seleccione [!UICONTROL **Nuevo chat**].

1. En el campo de texto, solicite al agente que valide un campo o un conjunto de datos. Por ejemplo:

   **Mensaje**

   > Validar conjunto de datos &quot;Ejemplo Electronics 1000&quot;

   ![Pantalla de inicio de chat de Coworker con el mensaje Validar conjunto de datos Electronics Sample 1000 introducido en el campo de mensaje.](../../assets/data-validation-aep/start-session.png)

   >[!TIP]
   >
   >Anteponga el nombre del conjunto de datos con la palabra &quot;conjunto de datos&quot; para que la aptitud pueda identificarlo correctamente. Por ejemplo, utilice &quot;Validar el conjunto de datos Ejemplo de electrónica 1000&quot; en lugar de &quot;Validar muestra de electrónica 1000&quot;.

   La solicitud se enruta a la aptitud Validación de datos, que analiza una muestra del conjunto de datos y devuelve los resultados en la misma conversación.

## Elija lo que desea validar

Puede validar un solo campo o un conjunto de datos completo.

>[!BEGINTABS]

>[!TAB Validación de campo]

Validar un campo específico en un conjunto de datos. Esta opción proporciona:

* Recuento nulo y recuento de valores distintos.
* Valores distintos principales y sus frecuencias.
* Validación semántica asistida por IA que marca valores que no coinciden con el formato esperado del campo, según los metadatos del campo y sus valores reales.

Ejemplos de peticiones de datos:

* Valide el campo de correo electrónico en el conjunto de datos Customers_2024.
* Valide el estado del campo para el conjunto de datos customer_events_2024.
* Valide el campo person.address.city para el conjunto de datos de datos de cliente.

>[!TAB Validación de conjunto de datos]

Valide hasta cinco campos de un conjunto de datos a la vez. Puede especificar los campos usted mismo o permitir que la aptitud analice el conjunto de datos y seleccione automáticamente los campos más relevantes. Esta opción devuelve la misma información que la validación de campos, en todos los campos que valide.

Ejemplos de peticiones de datos:

* Validar conjunto de datos de datos de cliente 2024.
* Valide los campos de correo electrónico y teléfono para Customers_2024.
* Resuma firstName, lastName, birthDate para los datos del cliente.

>[!ENDTABS]

## Revisar los resultados

Para cada campo validado, los resultados aparecen como una fila en una tabla con las siguientes columnas:

| Columna | Descripción |
| --- | --- |
| [!UICONTROL Nombre de campo] | El nombre del campo. |
| [!UICONTROL Ruta de campo] | Ruta de acceso completa del campo en el esquema. |
| [!UICONTROL Tipo de campo] | El tipo de datos del campo. |
| [!UICONTROL Valores válidos] | Porcentaje de valores de muestra que superan la validación. |
| [!UICONTROL Valores distintos] | El porcentaje de valores muestreados que son distintos. |
| [!UICONTROL Valores nulos] | El porcentaje de valores muestreados que son nulos. |
| [!UICONTROL Cinco valores distintos principales] | Los cinco valores más comunes y sus frecuencias. |
| [!UICONTROL Cinco valores principales no válidos] | Los cinco valores no válidos más comunes, con una explicación para cada uno, por ejemplo &quot;no es un formato de correo electrónico válido&quot;. |
| [!UICONTROL insight adicional] | Una breve nota en lenguaje natural sobre la calidad del campo. |

Debajo de los resultados, el compañero agrega una lista de **Pasos siguientes** que sugiere mensajes de seguimiento, como validar otro campo o volver a ejecutar el conjunto de datos.

Al validar un solo campo, Coworker también devuelve un gráfico:

![Chat del compañero que muestra un gráfico circular y un resumen escrito para el campo Marca, con un informe de 79,5% de valores válidos, 20,5% de valores nulos y sin valores no válidos detectados.](../../assets/data-validation-aep/null-values.png)

Seleccione [!UICONTROL **Gráfico**] o [!UICONTROL **Tabla**] para cambiar entre vistas de los mismos resultados.

Al validar un conjunto de datos, los resultados aparecen en una tabla con una fila por campo. Los campos que asigne aparecerán tal y como los haya especificado:

![Tabla de chat de compañeros de trabajo titulada Ejemplo de electrónica 1000 Validación de campo, que muestra los resultados de validación de los campos Categoría, Marca y Precio que el usuario nombró en el mensaje.](../../assets/data-validation-aep/field-validation.png)

Los campos que selecciona la aptitud aparecen automáticamente del mismo modo:

![Tabla de chat de Coworker que muestra los resultados de validación de cinco campos seleccionados automáticamente en el conjunto de datos de ejemplo 1000 de Electronics: Categoría, Marca, Precio, Inventario y Condición.](../../assets/data-validation-aep/dataset-validation.png)

Seleccione [!UICONTROL **CSV**] para descargar la tabla de resultados completa.

## Comprobaciones realizadas por la validación de datos

La aptitud realiza los siguientes tipos de comprobaciones en cada campo y conjunto de datos:

* **Comprobaciones de integridad**: recuentos y porcentajes nulos y ausentes.
* **Comprobaciones de distribución**: valores distintos principales y sus distribuciones, y detección de alta cardinalidad.
* **Comprobaciones semánticas en el esquema**: utiliza el nombre, el tipo y la descripción del campo XDM para deducir el aspecto de un valor válido y, a continuación, marca las anomalías.
* **Comprobaciones según el tipo de datos**, donde corresponda:
  * Correo electrónico: formato y verosimilitud de dominio.
  * Teléfono: preparación de formato, por ejemplo, E.164.
  * Fechas y marcas de hora: comprobaciones básicas de formato, por ejemplo, ISO-8601.

Estas comprobaciones combinan estadísticas deterministas con una validación semántica asistida por LLM para detectar valores que tienen un aspecto incorrecto incluso cuando coinciden técnicamente con el esquema.

## Limitaciones

Antes de validar los datos, tenga en cuenta las siguientes limitaciones. Estas restricciones equilibran el rendimiento con la funcionalidad y establecen expectativas para el análisis y las perspectivas que puede esperar.

* **Solo muestreo**: la aptitud valida una muestra del conjunto de datos (normalmente las 1000 filas más recientes), no todo el conjunto de datos. Los análisis de conjuntos de datos completos no están disponibles.
* **Límite de recuento de campos**: al validar un conjunto de datos, la aptitud analiza hasta cinco campos por solicitud. Puede especificar estos campos o permitir que la aptitud los seleccione automáticamente.
* **Semántica probabilística**: la detección de valores no válidos se basa en parte en la inferencia basada en LLM, que a veces puede omitir errores sutiles o marcar valores límite.
* **Solo lectura**: la aptitud no cambia los datos ni su esquema. Resalta posibles problemas, pero no realiza correcciones automatizadas.

Si sus necesidades de validación son más exhaustivas o requieren una lógica empresarial compleja, complemente estos resultados con herramientas adicionales como las validaciones del servicio de consulta o de la preparación de datos.

**Información relacionada**

* [Validar datos de Adobe Analytics a Customer Journey Analytics al actualizar](./data-validation-aa-cja.md)
* [Validar datos de Customer Journey Analytics con la aptitud de validación de datos en Coworker](./validate-dataset-quality-for-cja.md)
* [Validación de datos (asistente de IA)](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-validation)
* [Confiar en los informes de Customer Journey Analytics: aptitud de validación de datos en Adobe CX Enterprise Coworker](https://www.youtube.com/watch?v=gCSm_QYSYhk) (vídeo)
