---
title: Analizar datos de Customer Journey Analytics con el chat de compañeros
description: Aprenda a utilizar el chat de Adobe CX Enterprise Coworker para analizar los datos de Customer Journey Analytics, crear canales y encontrar dónde abandonan los clientes en el recorrido.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 2d4922c334bcc2ec93dec46098a9c021623034ad
workflow-type: tm+mt
source-wordcount: '3338'
ht-degree: 3%
---
# Analizar datos de CX Analytics de Adobe con el chat de Coworker

Adobe CX Enterprise Coworker Chat puede realizar análisis de datos avanzados que anteriormente solo eran posibles en Analysis Workspace. El chat de compañeros accede a los datos de sus vistas de datos de Customer Journey Analytics o grupos de informes de Adobe Analytics, lo que le permite explorar esos datos y obtener respuestas a las preguntas en lenguaje natural.

Puede utilizar el chat de Coworker de dos formas, en función del análisis que necesite:

* **Respuestas rápidas** - Haga una pregunta directa en un lenguaje sencillo y obtenga una respuesta inmediata. Los usuarios empresariales suelen utilizar el chat de Coworker de esta manera, y los analistas también lo utilizan cuando necesitan una respuesta rápida para una parte interesada.
* **Trabajo de reflexión profunda**: mantenga una conversación prolongada y de varias vueltas con Coworker Chat para investigar un problema empresarial, descartar causas y llegar a una recomendación. Los analistas suelen utilizar este método para explorar los datos en profundidad antes de realizar una recomendación.

Antes de empezar, conozca la interfaz de chat de Coworker y las opciones de configuración y, a continuación, asegúrese de que Coworker esté conectado a Customer Journey Analytics o Adobe Analytics y a las vistas de datos o grupos de informes relevantes.

## Introducción al chat con compañeros

### Acceso a datos y permisos

El chat de compañeros hereda los permisos de Customer Journey Analytics o Adobe Analytics. Solo puede acceder a las vistas de datos, los grupos de informes, las dimensiones, las métricas y los segmentos disponibles en Analysis Workspace.

### Opciones de interfaz y configuración

Antes de usar el chat de Coworker con los datos de Customer Journey Analytics o Adobe Analytics, aprenda a iniciar sesión y administrar las opciones de configuración de las siguientes funciones:

* Entradas de chat
* Conversiones
* Marketplaces
* Servidores MCP
* Memoria
* Complementos
* Habilidades
* Y más

Para obtener más información, consulte la [Guía de la interfaz de usuario de Coworker Chat](/help/chat/ui-guide.md).

### Prácticas recomendadas al analizar datos con Coworker Chat

#### Prácticas recomendadas a nivel de organización

* Nombrar a un analista de su organización como Coworker champion.

* Cree una biblioteca de preguntas y habilidades evaluadas que se correlacionen con los datos y los componentes disponibles para los usuarios.

* Cree una o más habilidades que dirijan el chat de compañeros para utilizar solo los componentes que desee utilizar en los análisis. Esto ayuda a Coworker Chat a proporcionar a los usuarios de su organización los datos más relevantes.

* Informe a los usuarios sobre cuándo preguntar a Coworker Chat una respuesta rápida en comparación con cuándo usarla para un trabajo profundo.

#### Prácticas recomendadas a nivel de usuario

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

* Añade direcciones estándar a la memoria de Coworker Chat. Por ejemplo, si siempre utiliza datos de las mismas vistas de datos o grupos de informes, agréguelos a la memoria.

## Compruebe que Chat del compañero está conectado a Customer Journey Analytics

En Coworker Chat, compruebe que Coworker esté conectado a Customer Journey Analytics:

1. Seleccione el icono de MCP en el carril izquierdo y, a continuación, asegúrese de que [!UICONTROL **cja-mcp**] está disponible en su lista de servidores MCP conectados.

   ![Icono de MCP resaltado en el carril izquierdo de Coworker](../../assets/coworker-mcp-cja.png)

1. (Condicional) Si [!UICONTROL **cja-mcp**] aún no está conectado, seleccione [!UICONTROL **Agregar servidor MCP**], especifique cja en el campo [!UICONTROL **Nombre de servidor**] y selecciónelo cuando aparezca, luego seleccione [!UICONTROL **Agregar servidor**].

## Conéctese a la vista de datos o al grupo de informes adecuados

Una vista de datos es un contenedor de Customer Journey Analytics que determina cómo se interpretan los datos. Un grupo de informes es un contenedor de Adobe Analytics que contiene los datos recopilados de sus sitios y aplicaciones.

Puede tener acceso a varias vistas de datos en Customer Journey Analytics o a grupos de informes en Adobe Analytics. Cada una de ellas puede contener diferentes dimensiones y métricas que el Compañero de trabajo puede utilizar al analizar los datos.

### Decida qué vistas de datos o grupos de informes desea utilizar

Indique a los compañeros los tipos de preguntas que desea responder y pregúntele a qué vistas de datos o grupos de informes tiene acceso que proporcionen esa información. También puede [establecer su vista de datos o grupo de informes como preferencia en la memoria](#add-a-data-view-or-report-suite-preference-in-memory).

**Usted:**

>[!BEGINSHADEBOX]

Me interesa saber dónde caen los clientes en el recorrido de clientes. ¿A qué vistas de datos de Customer Journey Analytics tengo acceso que puedan responder a esta pregunta?

>[!ENDSHADEBOX]

**Respuesta de chat de compañero:**

>[!BEGINSHADEBOX]

Tiene acceso a tres vistas de datos. La vista de datos `Customer lifecycle` contiene las siguientes dimensiones y métricas, que serían las mejores para responder a su pregunta.

>[!ENDSHADEBOX]

**Usted:**

>[!BEGINSHADEBOX]

Genial, vamos a usar esa vista de datos.

>[!ENDSHADEBOX]

**Respuesta de chat de compañero:**

>[!BEGINSHADEBOX]

De acuerdo, usaré la vista de datos de `Customer lifecycle` para responder preguntas futuras en esta sesión de chat.

>[!ENDSHADEBOX]

### Añadir una vista de datos o una preferencia de grupo de informes en la memoria

El Chat de Coworker contiene una función de memoria que le permite proporcionarle acceso a la información que abarca todos los chats. Se recomienda añadir las vistas de datos o los grupos de informes preferidos como preferencias en la memoria del colaborador.

1. En Chat del compañero, en la barra de navegación izquierda, seleccione el icono Memoria.

1. En la página Memoria, en la sección [!UICONTROL **Preferencias almacenadas**], especifique una o más vistas de datos o grupos de informes que quiera que Chat del compañero use en sus charlas.

   ![Sección de memoria en el carril izquierdo](../../assets/coworker-memory.png)

## Analizar en Customer Journey Analytics

Una vez que su compañero haya creado una visualización, puede abrirla en Analysis Workspace para realizar un análisis más profundo y un control granular. La visualización se abre en un nuevo proyecto de Analysis Workspace en Customer Journey Analytics.

Para abrir una visualización en un nuevo proyecto de Analysis Workspace:

1. Seleccione [!UICONTROL **Analizar en CJA**] junto a cualquier visualización que se cree en Coworker.

1. Con la visualización abierta en Customer Journey Analytics, puede utilizar la interfaz del explorador de arrastrar y soltar de Analysis Workspace para realizar modificaciones, desarrollar aún más el análisis, crear una audiencia y mucho más. Incluso puede compartir su proyecto de Workspace con quien desee.

   Para obtener más información sobre Analysis Workspace, consulte [Información general de Analysis Workspace](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-workspace/home).

### Casos de uso para Customer Journey Analytics

Puede ver casos de uso de Customer Journey Analytics e instrucciones de ejemplo que los profesionales utilizan en Adobe CX Enterprise Coworker Chat, desde respuestas rápidas hasta investigaciones de trabajo profundas. Cada mensaje se crea para copiarse, adaptarse con sus propios datos y contexto, y refinarse a través de la conversación.

Para obtener más información, consulte [Casos de uso](/help/chat/use-cases/overview.md).

## Aptitudes de Analytics

Las siguientes habilidades están disponibles para analizar datos de Customer Journey Analytics o Adobe Analytics.

### Consulta y análisis de datos

Estas habilidades le permiten consultar los datos en tiempo real y analizar los resultados sin crear la solicitud personalmente en Analysis Workspace:

* `cja` - Vistas de datos de Query Customer Journey Analytics
* `aa` - Grupos de informes de Query Adobe Analytics

#### Permisos necesarios

* Ver el acceso a la vista de datos o al grupo de informes que desea consultar

#### Casos de uso clave

| Ejemplo de uso | Función | Ejemplos de peticiones de datos |
|---------|----------|---------|
| **Informes y métricas de extracción** | Consulte Customer Journey Analytics o Adobe Analytics en tiempo real para extraer métricas, dimensiones, segmentos, vistas de datos y grupos de informes. | <ul><li>&quot;Mostrarme las vistas de página de los últimos 30 días&quot;</li><li>&quot;Enumerar los segmentos principales en la vista de datos maestra&quot;</li></ul> |
| **Análisis comparativo** | Comparar métricas en varios canales, períodos de tiempo o segmentos en paralelo. | <ul><li>&quot;Comparar ingresos por canal mes tras mes&quot;</li><li>&quot;¿Qué aspecto tienen las conversiones de móviles y equipos de escritorio este trimestre?&quot;</li></ul> |
| **Análisis de Funnel** | Pase por los canales de conversión de varios pasos con entrega en cada fase. | <ul><li>&quot;Guíame a través del funnel de pago y envío&quot;</li><li>&quot;Mostrar funnel de conversión de PDP a compra&quot;</li></ul> |
| **Previsión** | Proyecte valores de métricas futuras basados en datos históricos. | <ul><li>&quot;Prever sesiones para los próximos 30 días&quot;</li><li>&quot;¿Estamos en camino de alcanzar nuestra meta de ingresos?&quot;</li></ul> |

#### En ámbito

* Consulta en tiempo real de métricas, dimensiones, segmentos, vistas de datos y grupos de informes
* Comparaciones paralelas entre canales, períodos de tiempo o segmentos
* Análisis de abandonos y funnel de varios pasos
* Previsión de métricas basada en tendencias históricas

#### Fuera de ámbito

* Creación o edición de componentes de vista de datos o de grupo de informes
* Datos fuera de las vistas de datos o los grupos de informes a los que tiene acceso
* Modelado predictivo más allá de la previsión de métricas

### Análisis de la causa raíz

Estas habilidades investigan por qué ha cambiado una métrica en lugar de solo informar de que ha cambiado:

* `cja-root-cause-analysis` - Analizar cambios de métricas en vistas de datos de Customer Journey Analytics
* `aa-root-cause-analysis` - Analizar cambios de métricas en grupos de informes de Adobe Analytics

#### Permisos necesarios

* Ver el acceso a la vista de datos o al grupo de informes que se analiza

#### Casos de uso clave

| Ejemplo de uso | Función | Ejemplos de peticiones de datos |
|---------|----------|---------|
| **Diagnóstico de cambios de métricas** | Investigue por qué ha cambiado una métrica, incluidas caídas, picos y anomalías. | <ul><li>&quot;¿Por qué cayeron las conversiones la semana pasada?&quot;</li><li>&quot;¿Qué causó el pico de ingresos el 15 de enero?&quot;</li></ul> |

#### En ámbito

* Investigación de un cambio en una métrica conocida durante un período conocido
* Aparición de dimensiones y segmentos que contribuyeron al cambio

#### Fuera de ámbito

* Detección de anomalías que no le ha preguntado (sin alertas automatizadas o en tiempo real)
* Análisis de la causa raíz de las métricas fuera de una vista de datos o un grupo de informes al que tenga acceso

### Resúmenes ejecutivos y resúmenes de rendimiento

Esta aptitud (`cja-executive-summary`) genera resúmenes de los datos de Customer Journey Analytics o Adobe Analytics preparados para las partes interesadas.

#### Permisos necesarios

* Ver el acceso a las vistas de datos o a los grupos de informes incluidos en el resumen

#### Casos de uso clave

| Ejemplo de uso | Función | Ejemplos de peticiones de datos |
|---------|----------|---------|
| **Resúmenes de rendimiento** | Produzca resúmenes de rendimiento preparados para las partes interesadas, recomendaciones prescriptivas y descripciones de diapositivas. | <ul><li>&quot;Dame un resumen ejecutivo del mes pasado&quot;</li><li>&quot;Crear un esquema de presentación a partir de los datos de este trimestre&quot;</li></ul> |

#### En ámbito

* Resumen del rendimiento durante un periodo especificado
* Generar recomendaciones prescriptivas basadas en los datos
* Esquematización del contenido de un paquete de diapositivas o de la lectura de las partes interesadas

#### Fuera de ámbito

* Generación de la presentación final o del archivo de presentación
* Resúmenes que abarcan vistas de datos o grupos de informes a los que no tiene acceso

### Validación de datos con Adobe Analytics

Esta aptitud (`aa-cja-validation`) compara, audita y concilia datos entre [!DNL Adobe Analytics] y Customer Journey Analytics.

#### Permisos necesarios

* Ver el acceso al grupo de informes [!DNL Adobe Analytics] y a la vista de datos de Customer Journey Analytics que se compara

#### Casos de uso clave

| Ejemplo de uso | Función | Ejemplos de peticiones de datos |
|---------|----------|---------|
| **Validar datos al actualizar de Adobe Analytics a Customer Journey Analytics** | Comparar, auditar y reconciliar datos entre [!DNL Adobe Analytics] y Customer Journey Analytics.<p>Para obtener más información, vea [Validar datos con el compañero al actualizar de Adobe Analytics a Customer Journey Analytics](data-validation-aa-cja.md).</p> | <ul><li>&quot;Comparar mi grupo de informes de Adobe Analytics con mi vista de datos de Customer Journey Analytics&quot;</li><li>&quot;Validar vistas de página entre Adobe Analytics y Customer Journey Analytics&quot;</li></ul> |

#### En ámbito

* Comparación de valores de métricas entre un grupo de informes y una vista de datos
* Indicación de discrepancias entre las dos fuentes de datos

#### Fuera de ámbito

* Solución de la causa subyacente de una discrepancia de datos
* Validando orígenes de datos distintos de [!DNL Adobe Analytics] y Customer Journey Analytics

### Crear habilidades personalizadas

Esta aptitud (`cja-skill-creator`) convierte un análisis que ya ha ejecutado en una aptitud reutilizable que persiste entre sesiones.

#### Permisos necesarios

* Administrar aptitudes

#### Casos de uso clave

| Ejemplo de uso | Función | Ejemplos de peticiones de datos |
|---------|----------|---------|
| **Patrones de análisis reutilizables** | Convierta los patrones analíticos en habilidades reutilizables y repetibles que persistan entre sesiones. | <ul><li>&quot;Convierta este análisis de ingresos semanal en una aptitud reutilizable&quot;</li><li>&quot;Guarde esta aptitud para la creación de informes mensuales de funnel&quot;</li></ul> |

#### En ámbito

* Conversión de un análisis completado en una aptitud con nombre y reutilizable
* Disponibilidad de una aptitud guardada en las futuras sesiones de chat

#### Fuera de ámbito

* Compartir automáticamente una aptitud guardada con otros usuarios (las bibliotecas de aptitudes de nivel de organización requieren la configuración del administrador)
* Edición de los componentes de vista de datos o de grupo de informes a los que hace referencia una aptitud

## Ejemplo: Encuentre el lugar de entrega de los clientes

Puede pedirle a Coworker Chat que use sus datos para analizar cualquier pregunta comercial.

Por ejemplo, como administrador de marketing, comerciante o líder de crecimiento, es posible que desee comprender dónde abandonan los clientes la ruta de compra, por qué lo hicieron y qué se puede hacer para aumentar las tasas de conversión.

>[!NOTE]
>
>Las figuras siguientes son datos de ejemplo ilustrativos de un retailer ficticio, [!DNL TechPulse Electronics], que se usa para mostrar la forma de la conversación.

### Los tipos de preguntas que puede hacer

No necesita saber qué es una &quot;visualización de abandonos&quot; o qué métrica se incluye en qué ranura. En su lugar, describa el resultado que le interesa en lenguaje sencillo:

* &quot;¿Dónde estamos perdiendo gente en el camino a comprar?&quot;
* &quot;¿Cuál es mi funnel de conversión completo, de vista de producto a cierre de compra?&quot;
* &quot;¿Qué canales de marketing pierden más entre el carro de compras y la compra?&quot;
* &quot;¿El abandono del carro de compras es peor en móviles o equipos de escritorio?&quot;
* &quot;¿La gente de las redes sociales pagadas se convierte de forma diferente que la gente del correo electrónico?&quot;

### La conversación

#### &#x200B;1. Comience con la pregunta empresarial

**Usted:**

>[!BEGINSHADEBOX]

¿Dónde estamos perdiendo gente en el camino a comprar?

>[!ENDSHADEBOX]

**Respuesta de chat de compañero:**

Tenga en cuenta que Coworker Chat elige la visualización correcta, secuencia los puntos de contacto e incluso añade los pasos siguientes recomendados.

>[!BEGINSHADEBOX]

![Tabla de Funnel que muestra los recuentos de sesiones, las tasas de conversión y la caída en cada paso desde las sesiones hasta la compra](../../assets/coworker-funnel-response.png)

Esta es una pregunta de funnel. Permítanme ejecutar funnel de conversión para ver dónde se producen los descensos en la ruta de compra.

Aquí es donde estás perdiendo gente:

| Paso de funnel | Count | Conversión a siguiente | Entrega |
| --- | --- | --- | --- |
| Sessions | 137,476 | 45,0% ve un producto | El 55% se va sin explorar los productos |
| Vistas del producto | 61,845 | 55,0 % añadir al carrito | 45% de exploración, pero no agregar |
| El carro agrega | 34,045 | 16,4% de compra | 83,6 % abandonan el carro |
| Compras | 5,582 | — | — |

**El gran hallazgo: el carro de compras es tu mayor fuga**

28.463 personas agregan artículos al carro de compras, pero nunca completan la compra. Esto representa una tasa de entrega del 83,6% del carro de compras, que es, con mucho, el mayor punto de fallo.

**Lo que esto le dice sobre las prioridades:**

| Prioridad | Problema | Escala de oportunidad |
| --- | --- | --- |
| #1 | Abandono del carro de compras (caída del 83,6 %) | 28.463 compradores perdidos |
| #2 | Sesión a vista de producto (55 % no examinar nunca) | 75.631 sesiones sin participación del producto |
| #3 | Vista del producto al carro de compras (el 45 % no agrega) | 27.800 interesados pero no comprometidos |

**Pasos siguientes recomendados:**

1. Desglose el abandono del carro de compras por canal de marketing: ¿ciertos canales aportan tráfico de baja intención que se añade al carro de compras, pero nunca se compra?
1. Observen el abandono del carro de compras por tipo de dispositivo: ¿la fricción del cierre de compra móvil mata las conversiones?
1. Identificar qué productos se abandonan más: ¿problema de precios? ¿Sorpresa de envío?

**¿Cuál de ellos desea que investigue a continuación?** El desglose de canal le indicaría directamente qué acciones de marketing le están trayendo &quot;casi compradores&quot; en comparación con los compradores reales.

>[!ENDSHADEBOX]

#### &#x200B;2. Profundizar en la fuga

**Usted:**

>[!BEGINSHADEBOX]

Vale, vamos a desglosar por canal de marketing

>[!ENDSHADEBOX]

**Respuesta de chat de compañero:**

>[!BEGINSHADEBOX]

![Tabla de Funnel que muestra las tasas de conversión y la lista desplegable desglosada por canal de marketing](../../assets/coworker-funnel-response2.png)

Hay una dimensión **Canal de mercadotecnia** personalizada. Permítanme extraer el funnel y, a continuación, calcular las tasas de conversión por canal e identificar dónde se filtra cada canal.

**El veredicto: la filtración no es específica del canal**

Este es un hallazgo realmente revelador. Este es el desglose de funnel por canal:

| Canal | Sessions | A la vista de producto | Añadir al carro de compras | Para comprar | Conversión general | Ingresos/sesión |
| --- | --- | --- | --- | --- | --- | --- |
| Búsqueda de pago | 43,958 | 45.1% | 54.6% | 16.6% | 4.09% | $499.58 |
| Búsqueda orgánica | 31,492 | 44.9% | 54.9% | 16.9% | 4.17% | $494.76 |
| Directo | 25,245 | 43.6% | 55.4% | 15.8% | 3.82% | $497.29 |
| Correo electrónico | 17,586 | 45.3% | 55.4% | 16.2% | 4.07% | $501.13 |
| Social de pago | 12,684 | 45.4% | 55.7% | 16.0% | 4.03% | $512.17 |
| Mostrar | 6,511 | 45.3% | 55.7% | 16.2% | 4.09% | $501.45 |

**Extras de claves:**

1. La lista desplegable del carro de compras es errónea de forma uniforme en todos los canales (83-84 %). Esto significa que el problema no se trata de la calidad del tráfico, sino de que cada canal está convirtiendo a las personas en el carro de compras a tasas similares. La fuga está en su propia experiencia de pago, no en su marketing.
1. Ningún canal es significativamente mejor o peor en la conversión. Las tasas de conversión generales se agrupan estrechamente entre el 3,8 % y el 4,2 %, y los ingresos por sesión son casi idénticos (de 495 a 512 dólares).
1. Donde más importa el impacto del volumen: la búsqueda de pago pierde más personas en términos absolutos (9.015 abandonos del carro de compras), seguida de la búsqueda orgánica (6.449 perdidos). Estas son las mayores oportunidades de valor en dólares porque son las que generan la mayor cantidad de tráfico.

**Lo que esto le dice estratégicamente**

Los canales de mercadotecnia están haciendo su trabajo. Todos están interesando a la gente y agregando al carro de compras a tasas similares. El problema es el flujo descendente del marketing: su pago y flujo de pago es donde el dinero se está filtrando.

**Próximas investigaciones recomendadas:**

1. Desglose el abandono del carro de compras móvil por categoría de producto: ¿es peor para los artículos de alto precio (lo que sugiere problemas de fideicomiso de pagos móviles)?
1. Observe qué canales de marketing generan la mayor cantidad de tráfico móvil: ¿está gastando dinero de los medios de comunicación para enviar a la gente a un funnel móvil dañado?
1. Compruebe si hay una señal de página o de sección del sitio. ¿Podemos ver qué páginas de cierre de compra visitaron los usuarios móviles los últimos antes de abandonarlas?

**¿Qué ángulo desea explorar a continuación?**

>[!ENDSHADEBOX]

#### &#x200B;3. Sigue investigando

**Usted:**

>[!BEGINSHADEBOX]

Interesante. Intentemos desglosar por tipo de dispositivo.

>[!ENDSHADEBOX]

**Respuesta de chat de compañero:**

>[!BEGINSHADEBOX]

![Tabla de Funnel que muestra las tasas de conversión y la lista desplegable desglosada por tipo de dispositivo](../../assets/coworker-funnel-response3.png)

**Lo encontró: el cierre de compra móvil está roto**

El funnel es idéntico en todos los dispositivos hasta el cierre de compra, luego el móvil se cae por un precipicio:

| Device | Sessions | A la vista de producto | Añadir al carro de compras | Para comprar | Conversión general |
| --- | --- | --- | --- | --- | --- |
| Escritorio | 70,172 | 44.9% | 54.8% | 23.2% | 5.70% |
| Tableta | 13,855 | 44.7% | 55.6% | 14.3% | 3.56% |
| Móvil | 53,449 | 44.9% | 55.3% | 8.1% | 2.02% |

**La pistola humeante**

| Métrica | Escritorio | Móvil | Espacio |
| --- | --- | --- | --- |
| Tasa de carro de compras | 23.2% | 8.1% | 15 puntos porcentuales |
| El móvil es | — | 2,8x peor | — |
| Carros abandonados | 13,274 | 12,178 | Casi el mismo volumen absoluto |

La experiencia de navegación y complementos al carro de compras está bien en dispositivos móviles (idéntica tasa de navegación de ~45%, ~55% tasa de adición al carro de compras). La gente está igualmente interesada y comprometida. Pero algo en el flujo de pago móvil está matando las conversiones.

**La oportunidad de ingresos**

Si el cierre de compra móvil se convirtiera a la misma velocidad que el equipo de escritorio, obtendría ~1.991 compras adicionales, un aumento del 35% en el volumen total de compras al corregir una experiencia.

**Qué es lo más probable**

El patrón de datos (participación igual, caída catastrófica de cierre de compra) es una señal clásica para:

* Fricción del formulario de pago en pantallas pequeñas (problemas de relleno automático, diseño del formulario)
* Costes inesperados revelados en el cierre de compra (envío, impuestos) que causan un shock por pegatinas
* Cierre de compra de invitado no disponible o un muro de inicio de sesión en dispositivos móviles
* Problemas de carga de página o tiempo de espera durante el procesamiento de pagos en dispositivos móviles

**Pasos siguientes recomendados:**

1. Desglose el abandono del carro de compras móvil por categoría de producto: ¿es peor para los artículos de alto precio (lo que sugiere problemas de fideicomiso de pagos móviles)?
1. Observe qué canales de marketing generan la mayor cantidad de tráfico móvil: ¿está gastando dinero de los medios de comunicación para enviar a la gente a un funnel móvil dañado?
1. Compruebe si la campaña &quot;holiday_flash_sale&quot; tuvo una mejor conversión de cierre de compra; las campañas impulsadas por la urgencia podrían superar la fricción de cierre de compra

**¿Cuál desea explorar o es evidencia suficiente para llevar a su equipo de UX y de pago?**

>[!ENDSHADEBOX]

#### &#x200B;4. Conviértalo en una decisión

**Usted:**

>[!BEGINSHADEBOX]

Entonces, ¿qué debo hacer?

>[!ENDSHADEBOX]

**Respuesta de chat de compañero:**

>[!BEGINSHADEBOX]

Basándome en lo que muestran los datos, aquí es donde me enfocaría:

* **Corrija el cierre de compra móvil; no es un problema de canal.** Cada canal está convirtiendo a las personas en el carro de compras a una tasa similar y saludable, por lo que el gasto en publicidad está funcionando en todos los ámbitos. Los ingresos se pierden específicamente en el flujo de cierre de compra móvil, que es donde pertenece la corrección.
* **Empiece con el pago y la fricción del formulario.** Estas son las razones más comunes por las que los compradores móviles de alta intención abandonan un carro de compras. Ofrecer opciones de billetera móvil y acortar el formulario suelen ser las ganancias más rápidas.
* **Vuelva a comprobar después de la corrección.** Una vez que se envían los cambios de cierre de compra, observe si la tasa de compra del carro de compras del móvil se desplaza hacia la tasa de escritorio del 23,2 %.

¿Quiere que guarde esto como un proyecto para que pueda rastrearlo o que establezca una alerta si el carro de compras móvil cae por debajo de un umbral?

>[!ENDSHADEBOX]

### Qué ha pasado

En cuatro preguntas en lenguaje simple, Coworker nos ayudó:

* Cree un funnel de conversión de varios pasos y marque el carro de compras como la mayor fuga
* Descartar el canal de marketing como causa: todos los canales se filtraron casi al mismo ritmo
* Aísle el problema real del cierre de compra móvil y cuantifique la corrección en un alza del 35 % en las compras
* Salga con una solución específica para priorizar: pago móvil y fricción de formularios. Esto se compara con la tasa de conversión del 23,2% de los equipos de sobremesa
