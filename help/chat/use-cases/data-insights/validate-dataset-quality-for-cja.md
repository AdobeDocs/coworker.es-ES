---
title: Validar datos de Customer Journey Analytics con la habilidad de validación de datos de Coworker
description: Obtenga información sobre cómo validar datos de Customer Journey Analytics con la aptitud Validación de datos en Coworker y resolver problemas antes de crear paneles.
feature: AI Tools
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 330
last-substantial-update: 2026-09-16
jira: KT-22622
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 0%
---
# Validar datos de Customer Journey Analytics con la aptitud de validación de datos en [!DNL Coworker]

La calidad de los datos es la base de unos informes precisos en Adobe Customer Journey Analytics (CJA). Antes de crear métricas, tableros, segmentos o recorridos de clientes, es fundamental saber si se puede confiar en los datos de Adobe Experience Platform (AEP) subyacentes.

En este vídeo, aprenderá a utilizar la habilidad **Validación de datos en Adobe CX Enterprise Coworker** para evaluar rápidamente la calidad de los conjuntos de datos que alimentan la implementación de Customer Journey Analytics, sin necesidad de escribir consultas ni inspeccionar datos manualmente.

>[!VIDEO](https://video.tv.adobe.com/v/3503519/?learn=on&enablevpops)

## Descubra los conjuntos de datos subyacentes a los informes de CJA

Consulte cómo el Compañero de trabajo puede identificar:

- Qué conjuntos de datos están conectados a Customer Journey Analytics
- Las conexiones y vistas de datos asociadas a una zona protegida específica
- Los conjuntos de datos que alimentan activamente la creación de informes
- Características clave del conjunto de datos, como el estado de flujo continuo y las áreas de nombres de identidad

Si comprende exactamente qué conjuntos de datos alimentan los informes, puede enfocar los esfuerzos de validación donde más importan.

## Explorar esquemas de conjuntos de datos y campos disponibles

Aprenda a inspeccionar esquemas de conjuntos de datos directamente desde Adobe Experience Platform.

El compañero recupera los detalles y las superficies del esquema:

- Campos de Commerce y de transacción
- Información del producto
- Datos de interacción web
- Campos de identidad
- Atributos de campaña y marketing
- Dimensiones geográficas y de dispositivo

Esto proporciona un inventario de los campos disponibles para el análisis y resalta la diferencia entre los campos que existen en un esquema y los campos que contienen datos utilizables.

## Validar la calidad de identidad

Los datos de identidad son esenciales para Customer Journey Analytics porque admiten informes de nivel de persona y análisis de recorrido en canales múltiples.

En este vídeo, verá cómo Coworker:

- Valida campos de identidad
- Comprueba los valores nulos y la integridad de los datos
- Evalúa la calidad del identificador
- Atributos de identidad de superficies ausentes o no disponibles

La validación del ejemplo muestra que las identidades de ECID y de correo electrónico están completamente rellenadas y son válidas en el ejemplo, mientras que el ID de Analytics no se pudo recuperar. Esto proporciona una señal útil a la hora de decidir qué identificadores pueden admitir la vinculación de perfiles y la creación de informes.

## Analizar la calidad de campo individual

Un campo puede existir en un conjunto de datos, pero sigue siendo inadecuado para el sistema de informes.

Descubra cómo el Compañero de trabajo valida un campo de seguimiento de campaña e informa:

- Tasas de población
- Porcentajes nulos
- Coherencia de datos
- Detección de valor no válido

En el ejemplo, los valores del código de seguimiento presentes son limpios y coherentes, pero aproximadamente el 85 % de las filas son nulas. Esto revela un punto ciego importante en la creación de informes antes de que se cree una dimensión de CJA o una métrica de campaña en el campo.

## Realizar validación de conjuntos de datos con IA

En lugar de validar campos individuales de uno en uno, el colaborador puede evaluar un conjunto de datos completo.

Aprenderá cómo la aptitud Validación de datos:

- Selecciona campos importantes para la validación
- Evalúa la integridad y la calidad
- Compara el estado de los datos entre campos
- Destaca los puntos fuertes y los posibles riesgos de notificación

Los resultados de validación proporcionan un mapa de viabilidad para CJA. Es posible que los campos limpios, como el nombre de la página web y el código de correo electrónico, estén listos para la creación de informes, mientras que los campos dispersos, como el valor de compra, el nombre de la campaña y el código de seguimiento, requieren investigación.

## Identificación de ingresos y riesgos de atribución

El vídeo también muestra cómo la validación de datos puede descubrir problemas que afectan a la precisión de la creación de informes, como:

- Datos de campaña dispersos
- Falta información de atribución
- Valores de transacción incompletos
- Brechas de medición de ingresos

En el conjunto de datos que se muestra, los recuentos de compras están disponibles, pero las cantidades de los pedidos no se rellenan de forma fiable. Este es un problema que se debe investigar antes de confiar en los informes de ingresos.

## Por qué la validación de datos es importante para Customer Journey Analytics

Customer Journey Analytics es tan fiable como los datos subyacentes.

La validación de conjuntos de datos antes de crear informes ayuda a los equipos a:

- Aumentar la confianza en los resultados de análisis
- Mejore las prácticas de gobernanza de datos
- Reducción de errores de informes
- Identificación anterior de problemas de implementación
- Solucionar problemas de métricas inesperadas de forma más eficaz

Con Coworker, estas comprobaciones se pueden iniciar utilizando indicaciones en lenguaje natural, lo que hace que la validación de datos sea más accesible para los usuarios técnicos y no técnicos.

