---
description: Descubra cómo Campañas de Coworker adjunta y conserva automáticamente los metadatos de C2PA en las imágenes, desde la generación hasta la entrega por correo electrónico.
title: Metadatos de C2PA en campañas de compañeros de trabajo
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%
---
# Metadatos de C2PA en campañas de compañeros de trabajo {#overview}

Están surgiendo nuevas leyes en torno a la transparencia generativa de la IA, y Adobe está trabajando para cumplir con los requisitos aplicables en todas las jurisdicciones. [Metadatos de C2PA](https://c2pa.org/) es la herramienta de procedencia que Adobe usa para cumplir con los requisitos de estas leyes.

Los metadatos de C2PA son metadatos duraderos e invisibles que registran cómo se creó o editó un fragmento de contenido. Cuando se genera o edita una imagen con herramientas de IA generativa en Campañas de Coworker, los metadatos de C2PA se adjuntan automáticamente a esa imagen. No se requiere ninguna acción por su parte.

## Metadatos de C2PA en campañas de correo electrónico {#c2pa-metadate-email}

Las imágenes enviadas en sus campañas de correo electrónico mantienen intactos los metadatos de C2PA, de modo que los destinatarios pueden verificar el origen y la autenticidad de cualquier imagen directamente desde el correo electrónico enviado.

## Acciones que adjuntan metadatos de C2PA {#actions}

La siguiente tabla resume cuándo se adjuntan los metadatos de C2PA, en función de la acción de imagen realizada en la generación de imágenes en Campañas de Coworker.

| Acción | Descripción | ¿Metadatos de C2PA adjuntos? | Ejemplo de caso de uso |
| --- | --- | --- | --- |
| **Generar una imagen** | Cree una nueva imagen a partir de un mensaje de texto o una imagen de referencia, o genere una imagen similar a partir de una existente. | Siempre. La imagen se genera mediante IA generativa, por lo que siempre lleva metadatos frescos de C2PA. | Se genera una imagen de titular para una campaña de correo electrónico a partir de un mensaje de texto que describe el elemento visual deseado. |

## Tipos de contenido y su ámbito {#content-types}

* **Imágenes**: Cubiertas. Los metadatos de C2PA se adjuntan cuando las imágenes se generan con IA generativa y se conservan mediante las operaciones de recorte, superposición de texto y superposición de imágenes realizadas por la generación de imágenes en Campañas de colaboración.
* **Texto**: No aplicable. Las salidas solo de texto en Campañas de Coworker, como la generación de copias, la traducción y las sugerencias de alineación de marca, no requieren metadatos de C2PA.

## Qué sucede a medida que se mueve el contenido {#content-moves}

Coworker Campaigns conserva los metadatos de C2PA asociados a los recursos de imagen admitidos. Si una imagen contiene metadatos de C2PA cuando se importa en Campañas de compañeros, esas credenciales se retienen cuando el recurso se utiliza en el contenido de campaña generado y en las experiencias de correo electrónico saliente.

## Recursos adicionales {#resources}

* [Transparencia de contenido de IA generativa](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"}
* [Directrices de usuario de IA generativa de Adobe Experience Cloud](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}
* [Mecanismos de protección y limitaciones](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/generate-content/gs-generative#generative-guardrails){target="_blank"}
