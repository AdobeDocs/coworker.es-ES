---
source-git-commit: e5bf2a0a2ee55513b32442f70d01dc5825ac9d6a
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# Documentación de CX Enterprise Coworker

Source para el conjunto de documentación de Adobe CX Enterprise Coworker.

## Publicando configuración

Usar los flujos de trabajo de validación y creación de reflejo de artículos compartidos en `.github/workflows/`.
El flujo de trabajo de validación se ejecuta para las solicitudes de extracción y se envía a `main`.
El flujo de trabajo de creación de reflejo se ejecuta cuando se inserta `main`.

Use `markdownlint_custom.json` para invalidaciones de reglas de Markdown y `linkcheckexclude.json` para, por ejemplo, exclusiones de URL.
El archivo `pipeline.opts` sigue la configuración de comprobación de vínculos de `cx-enterprise-ai.en`.
Agregar redirecciones de URL a `redirects.csv` mediante las columnas `source,dest`.
