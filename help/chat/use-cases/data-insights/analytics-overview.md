---
title: Analizar datos de Customer Journey Analytics con el chat de compañeros
description: Aprenda a utilizar el chat de Adobe CX Enterprise Coworker para analizar los datos de Customer Journey Analytics, crear canales y encontrar dónde abandonan los clientes en el recorrido.
product_v2:
  internal-label: CX Enterprise Coworker
feature_v2:
  internal-label: CX Enterprise Coworker
source-git-commit: f914f4a123216985ae9b562413f26e7b8c29eb0f
workflow-type: tm+mt
source-wordcount: '1281'
ht-degree: 1%
---

# Analizar datos con el chat de compañeros

La información de esta página proporciona información general sobre Adobe CX Enterprise Coworker Chat y cómo puede ayudarle a analizar los datos de su organización.

Coworker Chat permite a los equipos automatizar las tareas de productos de Adobe utilizando un lenguaje natural, convirtiendo rápidamente las ideas en acciones con una planificación flexible, habilidades personalizables y ejecución inteligente. Para obtener más información general sobre el Compañero de trabajo, consulte [Información general de CX Enterprise Coworker](/help/home.md).

## Funcionamiento del análisis de datos

El chat de compañeros puede realizar análisis de datos avanzados que anteriormente solo eran posibles en Analysis Workspace. El chat de compañeros accede a los datos de sus vistas de datos de Customer Journey Analytics o grupos de informes de Adobe Analytics, lo que le permite explorar los datos y obtener respuestas con preguntas en lenguaje natural.

El chat de compañeros hereda los permisos de Customer Journey Analytics o Adobe Analytics. Solo puede acceder a las vistas de datos, los grupos de informes, las dimensiones, las métricas y los segmentos disponibles en Analysis Workspace.

Cuando crea una visualización en el chat de Coworker, puede abrirla en Analysis Workspace en cualquier momento para tener un mayor control manual.

## Respuestas rápidas y trabajo profundo

Puede utilizar el chat de Coworker de dos formas, en función del análisis que necesite:

* **Respuestas rápidas** - Haga una pregunta directa en un lenguaje sencillo y obtenga una respuesta inmediata. Los usuarios empresariales suelen utilizar el chat de Coworker de esta manera, y los analistas también lo utilizan cuando necesitan una respuesta rápida para una parte interesada.
* **Trabajo meticuloso**: mantenga una conversación prolongada y de varias vueltas con Coworker Chat para investigar un problema empresarial, descartar causas y llegar a una recomendación. Los analistas suelen utilizar este método para explorar los datos en profundidad antes de realizar una recomendación.

## Empezar a analizar en el chat de Coworker

Empiece describiendo lo que desea saber en un lenguaje sencillo. El chat de compañeros planifica el análisis, consulta las vistas de datos o los grupos de informes y crea visualizaciones y resúmenes.

Los siguientes casos de uso se agrupan por dominio de análisis. Cada dominio tiene su propia página con casos de uso, indicadores de muestra, requisitos previos y las habilidades que utiliza.

| Dominio | Lo que puede hacer | Mejor para |
| --- | --- | --- |
| [Gobernanza y validación de datos](/help/chat/use-cases/data-insights/data-governance-and-validation.md) | Configure, migre y administre su implementación, y asegúrese de poder confiar en los datos detrás de cada respuesta. | Administración |
| [análisis de Recorrido](/help/chat/use-cases/data-insights/journey-analysis.md) | Descubra dónde abandonan los clientes el recorrido para convertirse y por qué en distintos canales, dispositivos y segmentos. | Analista, usuario empresarial |
| [Análisis de audiencias y segmentos](/help/chat/use-cases/data-insights/audience-and-segment-analysis.md) | Comprenda qué grupos de clientes se comportan de forma diferente y cómo, para que pueda centrarse en los que más importan. | Analista, usuario empresarial |
| [Rendimiento empresarial](/help/chat/use-cases/data-insights/business-performance.md) | Comprenda cómo está funcionando el negocio, por qué se movió una métrica, hacia dónde se dirige y qué hacer a continuación. | Analista, usuario empresarial |
| [Rendimiento del contenido](/help/chat/use-cases/data-insights/content-performance.md) | Comprenda qué contenido gana y por qué, según los atributos de cada recurso, para que pueda invertir en lo que funciona. | Usuario empresarial |
| [Medición y atribución de marketing](/help/chat/use-cases/data-insights/marketing-measurement-and-attribution.md) | Comprenda el impacto incremental de cada canal y campaña de marketing para poder asignar el gasto a la optimización del retorno de la inversión. | Analista, usuario empresarial |

## Aptitudes y limitaciones

Las siguientes habilidades están disponibles para analizar datos de Customer Journey Analytics o Adobe Analytics.

| Habilidad | Úselo para lo siguiente | Permisos necesarios | Fuera de ámbito |
| --- | --- | --- | --- |
| `cja`, `aa` | Consulte vistas de datos de Customer Journey Analytics (`cja`) o grupos de informes de Adobe Analytics (`aa`) en tiempo real:<ul><li>Métricas de extracción, dimensiones, segmentos, vistas de datos y grupos de informes</li><li>Comparar canales, periodos de tiempo o segmentos en paralelo</li><li>Ejecución del análisis de visitas en el orden previsto y funnel de varios pasos</li><li>Métricas de previsión basadas en tendencias históricas</li></ul> | Ver el acceso a la vista de datos o al grupo de informes que desea consultar | <ul><li>Creación o edición de componentes de vista de datos o de grupo de informes</li><li>Datos fuera de las vistas de datos o los grupos de informes a los que tiene acceso</li><li>Modelado predictivo más allá de la previsión de métricas</li></ul> |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Investigue por qué ha cambiado una métrica en lugar de informar solamente de que ha cambiado:<ul><li>Investigar un cambio en una métrica conocida durante un período conocido</li><li>Aparecen las dimensiones y segmentos que contribuyeron al cambio</li></ul> | Ver el acceso a la vista de datos o al grupo de informes que se analiza | <ul><li>Detección de anomalías que no le ha preguntado (sin alertas automatizadas o en tiempo real)</li><li>Análisis de la causa raíz de las métricas fuera de una vista de datos o un grupo de informes al que tenga acceso</li></ul> |
| `cja-executive-summary` | Produzca resúmenes de sus datos preparados para las partes interesadas:<ul><li>Resumir el rendimiento durante un periodo especificado</li><li>Generar recomendaciones prescriptivas basadas en los datos</li><li>Descripción del contenido de una presentación de diapositivas o lectura de la parte interesada</li></ul> | Ver el acceso a las vistas de datos o a los grupos de informes incluidos en el resumen | <ul><li>Generación de la presentación final o del archivo de presentación</li><li>Resúmenes que abarcan vistas de datos o grupos de informes a los que no tiene acceso</li></ul> |
| `aa-cja-validation` | Comparar, auditar y reconciliar datos entre [!DNL Adobe Analytics] y Customer Journey Analytics:<ul><li>Comparar valores de métricas entre un grupo de informes y una vista de datos</li><li>Marcar discrepancias entre las dos fuentes de datos</li></ul> | Ver el acceso al grupo de informes [!DNL Adobe Analytics] y a la vista de datos de Customer Journey Analytics que se compara | <ul><li>Solución de la causa subyacente de una discrepancia de datos</li><li>Validando orígenes de datos distintos de [!DNL Adobe Analytics] y Customer Journey Analytics</li></ul> |
| `cja-skill-creator` | Convierta un análisis que ya ha ejecutado en una aptitud reutilizable:<ul><li>Conversión de un análisis completado en una aptitud reutilizable con nombre</li><li>Hacer que una aptitud guardada esté disponible en las futuras sesiones de chat</li></ul> | Administrar aptitudes | <ul><li>Compartir automáticamente una aptitud guardada con otros usuarios (las bibliotecas de aptitudes de nivel de organización requieren la configuración del administrador)</li><li>Edición de los componentes de vista de datos o de grupo de informes a los que hace referencia una aptitud</li></ul> |

## Prácticas recomendadas al analizar datos con Coworker Chat

### Prácticas recomendadas a nivel de organización

* Nombrar a un analista de su organización como Coworker champion.

* Cree una biblioteca de preguntas y habilidades evaluadas que se correlacionen con los datos y los componentes disponibles para los usuarios.

* Cree una o más habilidades que dirijan el chat de compañeros para utilizar solo los componentes que desee utilizar en los análisis. Esto ayuda a Coworker Chat a proporcionar a los usuarios de su organización los datos más relevantes.

* Informe a los usuarios sobre cuándo preguntar a Coworker Chat una respuesta rápida en comparación con cuándo usarla para un trabajo profundo.

### Prácticas recomendadas a nivel de usuario

* Utilice el modo de plan.

  Este modo es especialmente útil para tareas complejas, pero también puede arrojar mejores resultados para tareas simples porque permite a los compañeros hacer preguntas de seguimiento antes de actuar. Para obtener más información, consulte [Modo de planificación](/help/chat/ui-guide.md#plan-mode).

* Cuando cree una solicitud, sea lo más específico posible:

  * Asigne un nombre a las dimensiones, métricas e intervalos de fechas que desee analizar.
  * Hacer referencia a los componentes por su nombre exacto.
  * Especifique los segmentos, audiencias, canales o dispositivos que quiera incluir, excluir o comparar.
  * Indique si desea un tipo de visualización específico, como una funnel, una tendencia o una tabla de cohorte.
  * Pida los siguientes pasos recomendados si desea que Coworker Chat le sugiera preguntas de seguimiento.
  * Solicite un horizonte de previsión, como &quot;próximos 30 días&quot;, al proyectar métricas.
  * Mencione cualquier hipótesis que ya tenga, de modo que Coworker Chat pueda validarla o descartarla.
  * Pregunte por las dimensiones de contribución si desea un desglose de un cambio de métrica.
  * Especifique la audiencia para un resumen, como el liderazgo o el equipo de marketing, y solicite una descripción del paquete de diapositivas si planea presentar los resultados.
  * Asigne un nombre al grupo de informes y a la vista de datos específicos que desea comparar al validar los datos.
  * Complete primero un análisis y, a continuación, pida a Chat del compañero que lo guarde como una habilidad, poniéndole un nombre claro y descriptivo y anotando la frecuencia con la que planea reutilizarlo.

* Añade direcciones estándar a la memoria de Coworker Chat. Por ejemplo, si siempre utiliza datos de las mismas vistas de datos o grupos de informes, agréguelos a la memoria. Para obtener más información, consulte [Agregar una vista de datos o una preferencia de grupo de informes en Memoria](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory) en Introducción al análisis de datos con Chat del compañero.

## Próximos pasos

* Para configurar el chat de compañeros y ver un ejemplo que funcione, consulta [Análisis de datos con el chat de compañeros](/help/chat/use-cases/data-insights/analytics-chat.md).
* Para ver todos los flujos de trabajo de chat de compañeros y las habilidades subyacentes, consulte [Flujos de trabajo de chat de compañeros](/help/chat/use-cases/workflows.md).


