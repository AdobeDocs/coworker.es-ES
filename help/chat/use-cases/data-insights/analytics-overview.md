---
title: Analizar datos de Customer Journey Analytics con el chat de compañeros
description: Aprenda a utilizar el chat de Adobe CX Enterprise Coworker para analizar los datos de Customer Journey Analytics, crear canales y encontrar dónde abandonan los clientes en el recorrido.
hold: true
product_v2:
  internal-label: CX Enterprise Coworker
feature_v2:
  internal-label: CX Enterprise Coworker
source-git-commit: 12ee914ed944c82694b9373f611e19cf040e2229
workflow-type: tm+mt
source-wordcount: '2332'
ht-degree: 0%
---

Adobe CX Enterprise Coworker Chat permite a los equipos automatizar las tareas de productos de Adobe utilizando un lenguaje natural, convirtiendo rápidamente las ideas en acciones con una planificación flexible, habilidades personalizables y ejecución inteligente. Para obtener más información general sobre el Compañero de trabajo, consulte [Información general de CX Enterprise Coworker](/help/home.md).

## Análisis de datos con Coworker Chat

El chat de compañeros puede realizar análisis de datos avanzados que anteriormente solo eran posibles en Analysis Workspace. El chat de compañeros accede a los datos de sus vistas de datos de Customer Journey Analytics o grupos de informes de Adobe Analytics, lo que le permite explorar esos datos y obtener respuestas a las preguntas en lenguaje natural.

Puede abrir la visualización creada en Coworker Chat para controlarla manualmente en cualquier momento.

## Empezar a analizar en el chat de Coworker

Empiece describiendo lo que desea saber en un lenguaje sencillo. El chat de compañeros planifica el análisis, consulta las vistas de datos o los grupos de informes y crea visualizaciones y resúmenes.

Los casos de uso siguientes son ejemplos. Puede preguntar por cualquier dato al que tenga permiso para acceder

### Casos de uso clave

<!-- The following cards link to each of the stand-alone articles in this folder -->

<!--
CARDS

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat
  {title = Analyze Customer Journey Analytics and Adobe Analytics data}
  {description = Answers natural-language questions about your data views or report suites, builds funnels and other visualizations, and finds where customers drop off. You can open any visualization in Analysis Workspace for further analysis.}
  {cta = Read}
  {image = ../../assets/coworker-funnel-response-card.png}

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis
  {title = Explore trends and root causes}
  {description = Identifies trends in your Customer Journey Analytics and Adobe Analytics data and the factors that drive changes in performance, without manual queries.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-line-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Analyze Customer Journey Analytics and Adobe Analytics data">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analizar datos de Customer Journey Analytics y Adobe Analytics">
                        <img class="is-bordered-r-small" src="../../assets/coworker-funnel-response-card.png" alt="Analizar datos de Customer Journey Analytics y Adobe Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analizar datos de Customer Journey Analytics y Adobe Analytics">Analizar datos de Customer Journey Analytics y Adobe Analytics</a>
                    </p>
                    <p class="is-size-6">Responde preguntas en lenguaje natural acerca de las vistas de datos o los grupos de informes, crea canales y otras visualizaciones y encuentra dónde abandonan los clientes. Puede abrir cualquier visualización en Analysis Workspace para un análisis más detallado.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Explore trends and root causes">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Explorar tendencias y causas básicas">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-line-card.png" alt="Explorar tendencias y causas básicas"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Explorar tendencias y causas básicas">Explorar tendencias y causas básicas</a>
                    </p>
                    <p class="is-size-6">Identifica las tendencias en los datos de Customer Journey Analytics y Adobe Analytics y los factores que impulsan los cambios en el rendimiento, sin consultas manuales.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide
  {title = Plan your implementation}
  {description = Creates a personalized, step-by-step plan for implementing Customer Journey Analytics, upgrading from Adobe Analytics, or setting up Content Analytics, Marketing Campaign Analytics, or Streaming Media collection on the Edge. Plans include details such as owners, effort estimates, dependencies, and validation steps.}
  {cta = Read}
  {image = ../../assets/ui-guide-6.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist
  {title = Generate an implementation checklist}
  {description = Turns your Customer Journey Analytics implementation plan into a checklist in Coworker Projects, where your team can assign steps, track status, and add approval gates.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/date-detail.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Plan your implementation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" title="Planifique su implementación">
                        <img class="is-bordered-r-small" src="../../assets/ui-guide-6.png" alt="Planifique su implementación"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" title="Planifique su implementación">Planifique su implementación</a>
                    </p>
                    <p class="is-size-6">Crea un plan personalizado paso a paso para implementar Customer Journey Analytics, actualizar desde Adobe Analytics o configurar la recopilación de Content Analytics, Marketing Campaign Analytics o medios de streaming en Edge. Los planes incluyen detalles como propietarios, estimaciones de esfuerzo, dependencias y pasos de validación.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Generate an implementation checklist">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" title="Generación de una lista de comprobación de implementación">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/date-detail.png" alt="Generación de una lista de comprobación de implementación"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" title="Generación de una lista de comprobación de implementación">Generar una lista de comprobación de implementación</a>
                    </p>
                    <p class="is-size-6">Convierte el plan de implementación de Customer Journey Analytics en una lista de comprobación en Proyectos de compañeros, donde su equipo puede asignar pasos, rastrear el estado y agregar puertas de aprobación.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja
  {title = Validate data when upgrading from Adobe Analytics to Customer Journey Analytics}
  {description = Compares dimensions, metrics, and trends between your Adobe Analytics report suites and Customer Journey Analytics data views, then recommends fixes to support your upgrade.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-bar-card.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation
  {title = Validate your Streaming Media implementation}
  {description = Checks your datastream, schema, dataset, data view, and session data to confirm that streaming media tracking is configured and collecting data correctly.}
  {cta = Read}
  {image = ../../assets/ui-guide-8.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data when upgrading from Adobe Analytics to Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Validación de datos al actualizar de Adobe Analytics a Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-bar-card.png" alt="Validación de datos al actualizar de Adobe Analytics a Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Validación de datos al actualizar de Adobe Analytics a Customer Journey Analytics">Validar datos al actualizar de Adobe Analytics a Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Compara dimensiones, métricas y tendencias entre sus grupos de informes de Adobe Analytics y las vistas de datos de Customer Journey Analytics y, a continuación, recomienda correcciones para admitir la actualización.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate your Streaming Media implementation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" title="Validación de la implementación de Streaming Media">
                        <img class="is-bordered-r-small" src="../../assets/ui-guide-8.png" alt="Validación de la implementación de Streaming Media"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" title="Validación de la implementación de Streaming Media">Valide su implementación de medios de streaming</a>
                    </p>
                    <p class="is-size-6">Comprueba la secuencia de datos, el esquema, el conjunto de datos, la vista de datos y los datos de sesión para confirmar que el seguimiento de medios de streaming está configurado y recopila datos correctamente.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja
  {title = Validate dataset quality for Customer Journey Analytics}
  {description = Identifies the datasets that feed your Customer Journey Analytics reporting, then checks schemas, identity quality, and field quality so you can resolve issues before you build dashboards.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/dataset-validation.png}

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep
  {title = Validate data after ingestion into Experience Platform}
  {description = Runs statistical and semantic checks on Experience Platform datasets and fields to find data quality issues, such as invalid values or mapping problems.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/null-values.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate dataset quality for Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Validar la calidad del conjunto de datos para Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/dataset-validation.png" alt="Validar la calidad del conjunto de datos para Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Validar la calidad del conjunto de datos para Customer Journey Analytics">Validar la calidad del conjunto de datos para Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Identifica los conjuntos de datos que alimentan los informes de Customer Journey Analytics y, a continuación, comprueba los esquemas, la calidad de la identidad y la calidad del campo para que pueda resolver los problemas antes de crear los paneles.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data after ingestion into Experience Platform">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" title="Validación de datos después de la ingesta en Experience Platform">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/null-values.png" alt="Validación de datos después de la ingesta en Experience Platform"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" title="Validación de datos después de la ingesta en Experience Platform">Validar datos después de la ingesta en Experience Platform</a>
                    </p>
                    <p class="is-size-6">Ejecuta comprobaciones estadísticas y semánticas en conjuntos de datos y campos de Experience Platform para encontrar problemas de calidad de datos, como valores no válidos o problemas de asignación.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

Para obtener más información sobre estos casos de uso, incluidas las habilidades que utilizan y las muestras de mensajes, consulte [Casos de uso de perspectivas de datos](/help/chat/use-cases/overview.md#data-insights).

### Introducción

Coworker Chat también puede ayudarle a lo siguiente:

* **Comparar rendimiento**: compare métricas de varios canales, períodos de tiempo o segmentos en paralelo.
* **Mida el rendimiento de la campaña**: vea el rendimiento de las campañas, los canales y las propiedades web durante un período determinado.
* **Analizar canales**: recorra canales de conversión de varios pasos y vea la lista desplegable en cada fase.
* **Métricas de pronóstico**: proyecte valores de métricas futuras a partir de datos históricos de Customer Journey Analytics o Adobe Analytics, como si está en el camino correcto para alcanzar un objetivo de ingresos.
* **Crear resúmenes ejecutivos y resúmenes de KPI**: produzca resúmenes de rendimiento preparados para las partes interesadas, recomendaciones y esquemas de diapositivas.
* **Analizar tendencias y causas operacionales**: consulte datos históricos de series temporales para audiencias, conjuntos de datos y recorridos, e identifique qué causó un cambio.
* **Crear habilidades personalizadas de Customer Journey Analytics**: Convierta un análisis que repita en una habilidad reutilizable que persiste entre sesiones.

<!--
CARDS

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat
  {title = Analyze data with Coworker Chat}
  {description = Ask questions in natural language to build funnels, create visualizations, and find where customers drop off in the journey.}
  {cta = Read}
  {image = ../../assets/coworker-funnel-response-card.png}

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis
  {title = Explore trends and root causes}
  {description = Investigate changes in your Customer Journey Analytics data and uncover what drives them, without writing manual queries.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-line-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Analyze data with Coworker Chat">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analizar datos con el chat de compañeros">
                        <img class="is-bordered-r-small" src="../../assets/coworker-funnel-response-card.png" alt="Analizar datos con el chat de compañeros"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analizar datos con el chat de compañeros">Analizar datos con chat de compañeros</a>
                    </p>
                    <p class="is-size-6">Haga preguntas en lenguaje natural para crear canales, crear visualizaciones y encontrar dónde abandonan los clientes en el recorrido.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Explore trends and root causes">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Explorar tendencias y causas básicas">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-line-card.png" alt="Explorar tendencias y causas básicas"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Explorar tendencias y causas básicas">Explorar tendencias y causas básicas</a>
                    </p>
                    <p class="is-size-6">Investigue los cambios en los datos de Customer Journey Analytics y descubra qué los impulsa, sin escribir consultas manuales.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja
  {title = Validate Customer Journey Analytics data}
  {description = Check dataset quality with the data validation skill and resolve issues before you build dashboards.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/dataset-validation.png}

* https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja
  {title = Validate data during your upgrade}
  {description = Compare Adobe Analytics and Customer Journey Analytics data to confirm that your upgrade is on track.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-bar-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate Customer Journey Analytics data">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Validar datos de Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/dataset-validation.png" alt="Validar datos de Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Validar datos de Customer Journey Analytics">Validar datos de Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Compruebe la calidad del conjunto de datos con la aptitud de validación de datos y resuelva problemas antes de crear paneles.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data during your upgrade">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Validación de datos durante la actualización">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-bar-card.png" alt="Validación de datos durante la actualización"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Validación de datos durante la actualización">Validar datos durante la actualización</a>
                    </p>
                    <p class="is-size-6">Compare datos de Adobe Analytics y Customer Journey Analytics para confirmar que la actualización está bien encaminada.</p>
                </div>
                <a href="https://experienceleague.adobe.com/es/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Leer</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->



## Diseño de tabla de casos de uso clave

<!-- The following table are links to each of the stand-alone articles in this folder -->

| Ejemplo de uso | Descripción |
| --- | --- |
| [Analizar datos de Customer Journey Analytics y Adobe Analytics](/help/chat/use-cases/data-insights/analytics-chat.md) | Responde preguntas en lenguaje natural acerca de las vistas de datos o los grupos de informes, crea canales y otras visualizaciones y encuentra dónde abandonan los clientes. Puede abrir cualquier visualización en Analysis Workspace para un análisis más detallado. |
| [Explorar tendencias y causas básicas](/help/chat/use-cases/data-insights/root-cause-analysis.md) | Identifica las tendencias en los datos de Customer Journey Analytics y Adobe Analytics y los factores que impulsan los cambios en el rendimiento, sin consultas manuales. |
| [Planifique su implementación](/help/chat/use-cases/data-insights/implementation-guide.md) | Crea un plan personalizado paso a paso para implementar Customer Journey Analytics, actualizar desde Adobe Analytics o configurar la recopilación de Content Analytics, Marketing Campaign Analytics o medios de streaming en Edge. Los planes incluyen detalles como propietarios, estimaciones de esfuerzo, dependencias y pasos de validación. |
| [Generar una lista de comprobación de implementación](/help/chat/use-cases/data-insights/intelligent-checklist.md) | Convierte el plan de implementación de Customer Journey Analytics en una lista de comprobación en Proyectos de compañeros, donde su equipo puede asignar pasos, rastrear el estado y agregar puertas de aprobación. |
| [Validar datos al actualizar de Adobe Analytics a Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md) | Compara dimensiones, métricas y tendencias entre sus grupos de informes de Adobe Analytics y las vistas de datos de Customer Journey Analytics y, a continuación, recomienda correcciones para admitir la actualización. |
| [Valide su implementación de medios de streaming](/help/chat/use-cases/data-insights/streaming-media-validation.md) | Comprueba la secuencia de datos, el esquema, el conjunto de datos, la vista de datos y los datos de sesión para confirmar que el seguimiento de medios de streaming está configurado y recopila datos correctamente. |
| [Validar la calidad del conjunto de datos para Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md) | Identifica los conjuntos de datos que alimentan los informes de Customer Journey Analytics y, a continuación, comprueba los esquemas, la calidad de la identidad y la calidad del campo para que pueda resolver los problemas antes de crear los paneles. |
| [Validar datos después de la ingesta en Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md) | Ejecuta comprobaciones estadísticas y semánticas en conjuntos de datos y campos de Experience Platform para encontrar problemas de calidad de datos, como valores no válidos o problemas de asignación. |

Para obtener más información sobre estos casos de uso, incluidas las habilidades que utilizan y las muestras de mensajes, consulte [Casos de uso de perspectivas de datos](/help/chat/use-cases/overview.md#data-insights).

