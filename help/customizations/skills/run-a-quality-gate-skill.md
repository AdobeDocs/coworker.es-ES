---
title: Crear y ejecutar una habilidad de puerta de calidad en Coworker
description: Aprenda a utilizar una habilidad de Coworker personalizada para validar automáticamente las activaciones de audiencia con listas de supresión, límites de frecuencia y estándares de nomenclatura antes de la implementación.
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 101
last-substantial-update: 2026-09-08
jira: KT-22379
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%
---

# Cree y ejecute una habilidad de puerta de calidad con habilidades de IA personalizadas

Los equipos de marketing dependen de las reglas y los procesos de gobernanza para garantizar que las audiencias se activen correctamente. Antes de lanzar una audiencia a un destino, los equipos suelen tener que verificar las listas de supresión, los límites de frecuencia, los requisitos de consentimiento y las convenciones de nomenclatura.
 
El desafío es que estas comprobaciones dependen con frecuencia de los conocimientos tribales y de las revisiones manuales. Cuando los procesos viven en la cabeza de las personas, pueden producirse errores.

En este vídeo, verá cómo una habilidad de Coworker personalizada actúa como una puerta de activación, validando automáticamente las audiencias con los estándares de activación de su organización antes de que se desplacen hacia abajo.

>[!VIDEO](https://video.tv.adobe.com/v/3503168/?captions=spa&learn=on&enablevpops)

## Aptitud de puerta de calidad de activación de muestra
 
Puede crear su propia habilidad **Puerta de calidad de activación** reutilizable pegando un mensaje en Compañero de trabajo. Las capacidades de creación de habilidades de los compañeros convierten el aviso en una habilidad guardada dentro de **su propio entorno**. A continuación se muestra un ejemplo basado en la demostración de vídeo.
 
La clave es definir **sus propios estándares de aprobado/suspenso** para las tres puertas de control:
 
1. Supresión/consentimiento
2. Límite de frecuencia
3. Convención de nomenclatura
 
El marco sigue siendo el mismo para todos. Personalice las secciones marcadas con **`[...]`** para que coincidan con los estándares de su organización.

## Mensaje maestro

> **Guarde esto como una habilidad denominada &quot;Puerta de calidad de activación&quot;.**

```text
It's a governance gate that runs a pre-activation checklist before any audience is sent to a destination.

It is read-only. It never activates, mutates, or copies anything.

Resolve the named audience and destination from our Knowledge Graph, evaluate the three gates below, then render one visual scorecard containing:

- An Alert banner
- One MetricCard per gate
- A DataTable with:
- Gate
- Status
- Finding
- Required Fix

Provide a single verdict:

- CLEARED only if all three gates pass
- BLOCKED if any gate fails

For every failed gate, provide the specific remediation needed.
 
All gates fail closed:

- Missing data = BLOCKED
- Never assume success when information is unavailable
 
Trigger phrases:

- "run the activation gate"
- "is this audience ready to activate"
- "pre-activation checklist"
- "can I activate to ..."

The three gates are:
 
[Paste Gate 1, Gate 2, and Gate 3 definitions here]
```

## Puerta 1: supresión/consentimiento
 
> Edite esta sección para que coincida con los requisitos de supresión y consentimiento de su organización.
 

```text
Gate 1 – Suppression List

Pass only if a recognized suppression, opt-out, or consent audience is applied alongside the target audience.

Discover eligible lists using name patterns such as:

- suppress
- opt-in
- opt out
- consent
- do not contact
 
Because suppression lists may live in destination dataflows rather than audience metadata, require the marketer to confirm one is attached.
 
If no suppression or consent list exists anywhere in the sandbox, fail hard.
 
Our standard:

[Example: A consent audience is mandatory for all email and SMS destinations. For direct mail destinations it is optional.]
```

## Puerta 2: Límite de frecuencia

> Edite esta sección para que coincida con los requisitos de frecuencia de entrega de su organización.

```text
Gate 2 – Frequency Cap
 
Read the delivery frequency on the resolved destination.

Pass if:

- Frequency is present
- Frequency is bounded

Fail if:

- Frequency is blank
- Frequency is unbounded

Our standard:

[Example: Frequency must be DAILY or less frequent. Any hourly cadence or blank value is blocked.]
```

## Puerta 3: Convención de nomenclatura
 
> Edite esta sección para que coincida con las reglas de nomenclatura de audiencias de su organización.
 

```text
Gate 3 – Naming Convention

Evaluate the audience name programmatically.

Any rule violation causes failure.

Block names that:

- Contain "test"
- Contain "copy"
- Contain an auto-copy suffix such as _[6-hex]
- Contain timestamps
- Contain 24-character object IDs
- Start with a bare number or cryptic short code
- Are entirely lowercase
- Are excessively short or unclear
- Use generic defaults such as:
- Save audience
- Email
- New Accounts
- Lack a category–qualifier separator

Our standard:

[Example: [Line of Business] – [Criteria] in title case]

Example:

Mortgage – High Propensity Prospects

When blocked on naming, always propose a compliant replacement name.
```

## Guía

### &#x200B;1. Personalizar sólo las secciones entre corchetes

Actualice solamente las secciones contenidas en **`[...]`**.
 
Estas secciones definen los estándares de gobernanza específicos de la organización.
 
Todo lo demás debería permanecer igual:

- Resolución de audiencia
- Evaluación de puerta
- Renderización del informe de valoración
- Lógica de veredicto


### &#x200B;2. Verificar requisitos previos
 
Esta aptitud depende de lo siguiente:
 
- Acceso a Knowledge Graph
- Descubrimiento de públicos
- Detección de destino
- Detección de lista de supresión
- Compatibilidad con artefactos visuales
- Titular de alerta
- MetricCards
- Renderización de DataTable

Si estas capacidades no están disponibles en el entorno del cliente, la aptitud no puede ejecutarse como está previsto.

### &#x200B;3. Mantener la aptitud de solo lectura

La aptitud siempre debe ser de solo lectura.

Incluya este requisito explícitamente en el mensaje para garantizar que la aptitud nunca se confunda con un flujo de trabajo de activación.

La Puerta de calidad de activación solo evalúa la preparación de la activación. **no** activa audiencias, modifica configuraciones o copia datos.
