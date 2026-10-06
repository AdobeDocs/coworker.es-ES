---
description: 'Conozca las campañas de los compañeros que ofrecen recomendaciones: el marco de trabajo CO-STAR, las acciones y no acciones, el contenido no compatible y una lista de comprobación de calidad para las peticiones de datos.'
title: Prácticas recomendadas en materia de solicitudes
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: ee66c1cc95ef1dd8c5e45c1fcb699547e63b9c8a
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 1%
---
# Impulso de las prácticas recomendadas {#best-practices}

Para sacar el máximo partido a las campañas de Coworker, comience con la forma en que se le solicita. Conozca las prácticas que producen los mejores resultados: el marco de trabajo CO-STAR para estructurar los indicadores, qué incluir y qué evitar, y ejemplos basados en escenarios que dan a la IA el contexto que necesita para generar contenido relevante en el objetivo.

>[!NOTE]
>
>Actualmente, solo puede conectarse a integraciones compatibles con Campañas de colaboración. Si ya tiene aplicaciones de Adobe Enterprise, donde almacena audiencias o genera recorridos, le recomendamos que use [CX Enterprise Coworker](/help/chat/use-cases/overview.md) en su lugar.

## Uso del marco CO-STAR

Para obtener los mejores resultados, organice las indicaciones mediante el marco de trabajo CO-STAR. Este enfoque estructurado garantiza que la IA entienda exactamente lo que necesita.

| Componente | Lo que significa | Por qué importa |
|-|-|-|
| **C - Contexto** | Antecedentes de su campaña, producto o situación | Ayuda a la IA a comprender el panorama general |
| **O - Objetivo** | Su objetivo de marketing específico | Controla lo que el contenido debe lograr |
| **S - Estilo** | Cómo desea comunicarse. | Establece el enfoque |
| **T - Tono** | Estilo emocional y voz | Da forma a cómo se siente el mensaje |
| **A - Audiencia** | Audiencia a la que está dirigiendo | Garantiza que el mensaje resuene con las personas adecuadas |
| **R - Requisitos** | Restricciones específicas o elementos imprescindibles | Define límites y elementos críticos |

## Aspectos básicos del prompt AI

### Lo que se hace y lo que no se hace

<table style="table-layout: fixed; width: 100%; border: 0;">
<thead style="border: 0; background-color: #FFFFFF;">
<tr>
<th>Hacer</th>
<th>No lo hagas</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<p>Utilice el marco CO-STAR para la estructura</p>
<p>Información de marketing centrada con directrices de extracción específicas</p>
<p>Borre los mensajes para producir la intención deseada</p>
</td>
<td>
<p>Solicite cambios estructurales, estilo o edición de imágenes en las solicitudes</p>
<p>Utilice instrucciones vagas como "promocionar nuestro producto"</p>
<p>Esperar modificaciones de diseño mediante mensajes</p>
</td>
</tr>
</tbody>
</table>

### Contenido admitido en las peticiones de datos

Use el **editor de correo electrónico** o **Adobe Express** para realizar modificaciones visuales o de imagen. Se admiten los siguientes tipos de solicitud.

- **Especifique la frecuencia y la cadencia de la campaña**: &quot;Cree una campaña de correo electrónico que se envíe semanalmente...&quot;

- **Dirigirse a una audiencia específica desde una lista más grande**: &quot;Cree una campaña solo para asistentes con perros para el evento _Bark in the Park_ de &#39;all-attendees.csv&#39;&quot;

- **Cargar un archivo HTML**: &quot;Use mi archivo HTML adjunto como base para crear una campaña de correo electrónico&quot;.

- **Realice cambios a mitad de la conversación**: &quot;Cambie el número de días antes de que esta campaña pase de dos a tres&quot;.

### Contenido no admitido en las peticiones de datos

Estas solicitudes **no** son compatibles y se deben administrar con otras herramientas:

<table style="table-layout: fixed; border: 0;">
<thead style="border: 0; background-color: #FFFFFF">
<tr>
<th>✗ modificaciones de estructura de correo electrónico</th>
<th>✗ Cambios de estilo visuales</th>
<th>✗ operaciones en el editor</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul>
<li>Selección de secciones específicas para cambiar</li>
<li>Eliminación o clonación de elementos</li>
<li>Selecciones condicionales</li>
<li>Adición o eliminación de secciones de diseño</li>
</ul>
</td>
<td>
<ul>
<li>Fuentes personalizadas</li>
<li>Modificaciones de color</li>
<li>Estilo del diseño (bordes, relleno, márgenes)</li>
<li>Efectos visuales (sombras)</li>
</ul>
</td>
<td>
<ul>
<li>Cambios de fondo</li>
<li>Adición de superposiciones de texto o logotipos</li>
<li>Recorte o cambio de tamaño de imagen</li>
<li>Ajustes de color</li>
</ul>
</td>
</tr>
</tbody>
</table>

### Lista de comprobación de calidad

Antes de generar contenido, asegúrese de lo siguiente:

✓ **Borrar objetivo**: Indica claramente la acción, el producto/servicio, el valor y el contexto.

✓ **Audiencia de destino definida**: Especifica el grupo demográfico, la función o el segmento.

✓ **Marca correcta asignada como predeterminada**: se han seleccionado las directrices de marca adecuadas.

✓ **Ámbito realista**: evite solicitudes de cambios de diseño, estilo o ediciones estructurales.

## Ejemplos de mensajes basados en escenarios

Proporcione siempre el contexto y la propuesta de valor para que la API pueda generar contenido relevante.

>[!NOTE]
>
>Aunque actualmente solo puede generar e iniciar campañas por correo electrónico, siempre puede pedir a su compañero que genere una copia para medios sociales, WhatsApp o SMS.

<table style="table-layout: fixed; border-collapse: collapse; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Industria</th>
<th>Mensaje de ejemplo</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Tecnología B2B</strong></td>
<td>"Genere una campaña de correo electrónico de cuatro toques para demostrar el retorno de la inversión y las especificaciones técnicas, al tiempo que se abordan los problemas de seguridad para los responsables de la toma de decisiones de TI que evalúan nuestra solución de infraestructura en la nube, haciendo hincapié en el 99,9% del tiempo de actividad de SLA, el cumplimiento de SOC 2 y el ahorro de costes del 40%".</td>
</tr>
<tr>
<td><strong>Comercio electrónico minorista</strong></td>
<td>"Genere una campaña de un solo toque para crear urgencia en torno a los artículos festivos de existencias limitadas, al tiempo que resalta el envío gratuito y las devoluciones sencillas para los compradores de último minuto, haciendo hincapié en las cantidades limitadas (quedan menos de 50) y el límite de envío de 24 horas".</td>
</tr>
<tr>
<td><strong>Educación y formación</strong></td>
<td>"Genere una campaña de dos toques que enfatice los resultados de avance profesional y las certificaciones de la industria, mientras muestra la experiencia del instructor, destacando una tasa de colocación laboral del 92% y un currículo basado en proyectos".</td>
</tr>
<tr>
<td><strong>Asesoramiento</strong></td>
<td>"Genere una campaña de tres toques para nutrir a las perspectivas empresariales mostrando tres casos de éxito de clientes con métricas detalladas de ROI (IBM: reducción de costes del 45%, Accenture: aumento de posibles clientes del 200%, Microsoft: ahorro de tiempo del 60%), dirigiéndose a directores de TI en empresas con más de 1000 empleados".</td>
</tr>
</tbody>
</table>

## Ideas generales de mensajes de marketing

### Marketing de contenido

- &quot;Genera 20 temas de blogs que respondan a preguntas comunes de los nuevos compradores de viviendas&quot;.
- &quot;Ideas de LinkedIn para una startup de ciberseguridad B2B&quot;.
- &quot;Cree un calendario de contenido de tres meses centrado en formar nuevos clientes&quot;.
- &quot;Sugerir temas de contenido que se puedan reutilizar en blogs, vídeos, boletines informativos y publicaciones sociales&quot;.

### Marketing por correo electrónico

- &quot;Genere una secuencia de correo electrónico de bienvenida para los nuevos suscriptores interesados en la moda sostenible&quot;.
- &quot;Haga una lluvia de ideas sobre líneas de asunto que crean curiosidad sin parecer un señuelo&quot;.
- &quot;Sugerir ideas de campañas de renovación de la participación para clientes inactivos&quot;.
- &quot;Cree ideas de correo electrónico del ciclo vital para los usuarios que han completado la incorporación&quot;.

>[!MORELIKETHIS]
>
>Examine más [patrones de solicitud](use-cases.md) para Campañas de compañeros de trabajo.
