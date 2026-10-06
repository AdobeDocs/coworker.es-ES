---
description: Obtenga información acerca de las mejoras y correcciones de funciones en las notas de la versión de Adobe CX Enterprise Coworker Campaign.
title: Notas de la versión de CX Enterprise Coworker Campaign
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: ee66c1cc95ef1dd8c5e45c1fcb699547e63b9c8a
workflow-type: tm+mt
source-wordcount: '3590'
ht-degree: 0%
---
# Notas de la versión de Adobe CX Enterprise Coworker Campaign {#release-notes}

Las versiones de Campañas de compañeros funcionan con un modelo de entrega continua que permite un enfoque más escalable y gradual de la implementación de funcionalidades.

## Septiembre de 2026 {#sep-2026}

**Fecha de la versión: 17 de septiembre de 2026**

* Conectar un espacio de trabajo de Databricks alojado en Azure, GCP o un dominio personalizado
* Las campañas ya no se pueden iniciar hasta que su flujo de trabajo esté completamente configurado
* Las plantillas de campaña se han actualizado con contenido
* Elija un conector directamente al cargar el CSV de la lista de contactos
* Se corrigió un bloqueo que podría producirse después de desplazarse por una larga lista de suscripciones de prueba
* Se ha corregido un problema en el cual la carga de un CSV de audiencia con encabezados en blanco o duplicados podía bloquear la página
* Se ha corregido el texto de marcador de posición en un mensaje de campaña que aparecía sin rellenar después de resolverse
* Se ha corregido un fallo en la página Aptitudes debido a la falta de un degradado de color
* Se ha solucionado el problema del chat que repetía la misma pregunta después de que ya la hubiera contestado
* Las respuestas de chat ya no muestran un prefijo de ID perdido delante de la respuesta seleccionada
* El chat ahora sugiere respuestas rápidas del siguiente paso que puede pulsar para rellenar el cuadro de composición
* Las plantillas de campaña ahora se abren en una vista en página optimizada en lugar de en un cuadro de diálogo independiente
* La barra de progreso expandida del chat ahora se desplaza internamente en lugar de sacar la conversación de la vista
* La configuración de la campaña ahora refleja los detalles más recientes del tablero con mayor precisión
* El cuadro de diálogo del plan de actualización ahora utiliza una apariencia más coherente
* Se ha eliminado un indicador de estado redundante del encabezado del plan de campaña para lograr un aspecto más limpio
* Las ediciones rápidas por correo electrónico ahora se guardan juntas como una sola entrada del historial de versiones en lugar de muchas
* Se corrigieron algunos títulos de kits de marca que ocasionalmente quedaban en blanco mientras se generaba un borrador
* Edite una imagen con Adobe Express directamente desde la barra de herramientas de imágenes
* Los datos básicos de audiencia del agente ahora permanecen sincronizados en el tablero de campañas sin una actualización manual
* Los logotipos de marca del tablero de campaña se recortan con mayor cuidado para adaptarse a su espacio
* Entrega visual más suave cuando el plan de campaña pasa al tablero de campañas

**Fecha de la versión: 3 de septiembre de 2026**

* Copie cualquier mensaje de chat y clasifique las respuestas de IA con un pulgar hacia arriba o hacia abajo, directamente desde el mensaje
* La lista de tareas del plan de campaña ahora permanece anclada encima de la entrada del chat mientras se ejecuta la campaña, para que pueda rastrear el progreso sin desplazarse
* Conecte un almacén de SQL de Databricks como una nueva fuente de datos para sus campañas
* El antiguo editor de correo electrónico basado en chat se ha sustituido por el nuevo editor de recursos de correo electrónico
* La administración de usuarios de prueba ahora permite excluir usuarios de Adobe, lo que facilita la visualización de las suscripciones de prueba reales
* Se ha corregido un problema en el cual las sugerencias de campañas similares no se podían cargar
* Los mensajes de chat ahora tienen un espaciado más estrecho y coherente

**Fecha de la versión: 1 de septiembre de 2026**

* Los correos electrónicos de campaña grandes ahora se muestran completamente en el editor en lugar de cortarse
* El botón de inicio del tablero de campaña ahora está etiquetado como &quot;Revisar e iniciar&quot; para una mayor claridad
* La conexión de una cuenta de Salesforce ya no muestra un mensaje de error de Marketo incorrecto
* Salesforce ahora tiene su propio logotipo en la lista de conectores
* Los conectores disponibles ahora se enumeran antes de los que vendrán pronto
* La incorporación ahora muestra un indicador de progreso mientras se carga su kit de marca
* Las vistas previas de audiencias y fuentes de conocimiento ahora tienen un botón de cierre y pueden abrirse a pantalla completa
* Las tarjetas de plan de campaña ya no se quedan atascadas cuando se muestra &quot;creando&quot; después de que la campaña comience a ejecutarse
* El chat ya no mantiene los mensajes de progreso temporales (como &quot;Explorando...&quot;) en su historial de conversaciones
* Los controles de la barra de herramientas ahora se bloquean correctamente mientras se aplican sugerencias de imagen o texto de IA
* Se ha corregido un problema en el cual el reemplazo de una imagen en el editor de recursos no funcionaba correctamente

## Agosto de 2026 {#aug-2026}

**Fecha de la versión: 26 de agosto de 2026**

* Al hacer clic en cualquier lugar de una tarjeta de plantilla de campaña, ahora se abre su vista previa, no solo el título
* El marcador de posición de la barra de mensajes de campaña vuelve a aparecer correctamente después de borrar la entrada, con una compatibilidad de lector de pantalla más clara
* La sugerencia &quot;Ayúdame a preguntar&quot; ahora reemplaza correctamente el texto existente en la barra de mensajes de la campaña
* La descarga de las cancelaciones de suscripción como CSV ahora refleja únicamente la ejecución de la campaña que está viendo
* La comparación del plan de prueba ahora muestra campañas de Launch y perspectivas de Campaign como funciones incluidas
* Las audiencias creadas sin un flujo de trabajo completo ahora se muestran correctamente en la tarjeta Audiencia del tablero de la campaña
* Las indicaciones de comentarios de estado vacío se leen de forma más natural en toda la aplicación

**Fecha de la versión: 25 de agosto de 2026**

* Al iniciar sesión en una pestaña del explorador, ahora se sincronizan las demás automáticamente, lo que corrige los desajustes de cuenta entre las pestañas
* Al hacer clic en Generar ahora el plan avanza de forma fiable en lugar de volver a generarlo ocasionalmente
* Los diagramas de flujo de trabajo del chat muestran más partes del lienzo, por lo que los controles de zoom ya no cubren los pasos
* Las pestañas de detalles de campaña tienen una apariencia actualizada y más coherente
* Guardar o eliminar un dominio de envío en Dominios y remitentes ahora es más rápido y fiable

**Fecha de la versión: 24 de agosto de 2026**

* Ver la estrategia de campaña generada directamente en el tablero de campañas
* Sustituya la audiencia directamente desde el cuadro de diálogo de validación de la campaña
* Las exportaciones de Campaign PDF y Word ahora incluyen el diagrama de flujo de trabajo real
* La pestaña Perspectivas permanece visible con un útil estado vacío justo después del lanzamiento
* Añadir o eliminar puntos de contacto al revisar los campos de la campaña
* La barra de herramientas del tablero de campaña es más sencilla, con botones innecesarios eliminados
* El asistente Dominios y remitentes analiza los subdominios y guía la configuración por primera vez con un marcador
* El asistente Dominios y remitentes muestra los errores de validación de subdominios en línea mientras escribe
* Se ha eliminado la call-to-action de campaña posterior a la prueba para un flujo más limpio
* Los nombres en chino ahora se muestran correctamente en el selector de idioma
* Las miniaturas de variante generadas por IA se cargan de forma fiable sin etiquetas duplicadas
* Las campañas recién creadas ahora aparecen inmediatamente en la lista de campañas recientes en Inicio
* Las perspectivas de todas las campañas ahora incluyen un resumen generado por IA del rendimiento de la campaña de su organización
* Proporcionar la entrada solicitada en una conversación de flujo de trabajo ya no lo deja atascado
* La incorporación de prueba ya no parpadea una pantalla de carga adicional al comprobar si hay un kit de marca existente
* Las fuentes de audiencia de muestra antiguas ahora se borran automáticamente del flujo de trabajo
* El diseño, el tema y las fuentes ahora se representan correctamente dentro del shell unificado de Experience Cloud
* Sugerencias de campaña similares ya no muestran un campo de canal innecesario

**Fecha de la versión: 14 de agosto de 2026**

* Elimine los dominios de borrador que ya no necesite en Dominios y remitentes
* Consulte Estado de verificación de DNS para cada registro durante la configuración del dominio
* Los detalles del dominio ahora muestran el remitente de correo electrónico configurado
* Los valores de registro DNS se truncan perfectamente con información de objeto para el texto completo
* Dar formato a varios bloques de texto de correo electrónico a la vez con selección múltiple
* Obtenga sugerencias de campaña similares al crear una nueva campaña
* Perspectivas de campaña de ámbito a una sola ejecución de una campaña recurrente
* Elija su idioma preferido en el menú de perfil
* Obtenga un empujón cuando las descripciones de plantillas de campaña necesiten más detalles
* Las notas de la versión son más fáciles de examinar y tienen una mejor navegación y paginación
* Contraer la lista de campañas recientes de la barra lateral para ahorrar espacio
* La vista del inventario de campañas ahora sigue siendo la misma que la dejó
* Reordenar los filtros de ejecución y saltar a un intervalo de fechas desde un selector de calendarios
* Vista previa de detalles de audiencia incluso en tarjetas de audiencia de solo lectura
* Se han corregido los parpadeos de la pantalla de flujo de prueba de incorporación y un problema de tiempo de inicio de sesión
* El controlador de cambio de tamaño del carril de chat ya no bloquea la barra de desplazamiento de la lista de mensajes
* La creación del kit de marca ahora muestra la verdadera razón por la que falló un guardado

**Fecha de la versión: 6 de agosto de 2026**

* Ahora, las perspectivas de campaña muestran las cancelaciones de suscripción con un CSV descargable de quién se excluyó
* Ahora hay una tabla de desglose de rendimiento por correo electrónico en la pestaña Perspectivas
* Consulte el mapa de recorrido de la campaña directamente en la pestaña Información
* Los pasos de espera basados en la duración ahora están visibles en la vista de flujo de trabajo de recorrido
* Las ramas de recorridos ponderados se muestran en la vista de edición del flujo de trabajo
* Las listas de contactos ahora están conectadas a los datos activos
* Las campañas recurrentes muestran 0 envíos inmediatamente en lugar de &quot;perspectivas pendientes&quot;
* Editar texto de mensaje de remezcla directamente alrededor de chips de marcador de posición
* Se mejoraron los chips de marcador de posición y limpiadores en el editor de remix
* Las tarjetas de flujo de trabajo de Campaign ahora muestran un estado vacío útil cuando no se está ejecutando nada
* El botón de actualizar plan ya no desborda el encabezado de detalles de la campaña
* Las tarjetas de flujo de trabajo tienen un diseño más sencillo con el nombre y la descripción del recorrido eliminados

## Julio de 2026 {#july-2026}

**Fecha de la versión: 30 de julio de 2026**

* Las perspectivas de todas las campañas ahora coinciden con el diseño de las perspectivas de campaña individuales, además de un nuevo gráfico de rendimiento diario
* Detenga una campaña en directo directamente desde la página de campaña
* Duplicar una campaña ahora solo pide un nombre nuevo
* Editar plantillas de correo electrónico directamente desde la lista de plantillas
* Filtrado de la vista del recorrido de campaña recurrente por ejecución
* Añada una imagen de marca directamente desde el tablero de campañas
* La tabla de administración de prueba ahora admite la búsqueda de correo electrónico, la paginación y la exportación completa de CSV
* El botón &quot;Sorpréndeme&quot; ahora responde instantáneamente, sin retraso de la animación
* Se ha eliminado la configuración de cancelación de suscripción del correo electrónico de campaña mientras reprocesamos esta función
* Editar la programación de una campaña después de haberla establecido, sin volver a empezar
* Abra el editor de estilos de escritura desde el menú de desbordamiento para acceder más rápido
* Al pulsar Intro, ahora se realiza el envío de forma coherente en todas las barras de mensajes de la aplicación

**Fecha de la versión: 23 de julio de 2026**

* Programe campañas para enviarlas de inmediato, una vez a la hora elegida o de forma recurrente
* Administre las listas de cancelación de suscripción de las listas de contactos y establezca los parámetros de cancelación de suscripción en la configuración del correo electrónico de la campaña
* Crear y administrar formularios con un nuevo inventario y editor de formularios
* La configuración del conector muestra una guía más clara cuando las credenciales fallan, incluso al actualizar una conexión existente
* Las conexiones de Marketo ahora admiten las direcciones URL de Experience Cloud
* El asistente Dominios y remitentes detecta más problemas de registro DNS antes de que su dominio se active
* Añadir conectores directamente desde el menú Añadir de la entrada de la campaña
* Las páginas de inventario muestran estados vacíos ilustrados más descriptivos cuando aún no hay nada que mostrar
* Las perspectivas de Campaign muestran qué fuente de datos alimenta cada métrica
* Los editores de marcas ahora están integrados en la incorporación para una configuración inicial más fluida
* Previsualice una audiencia de muestra antes de comprometerse con la campaña
* Campañas de compañero ahora vive dentro del shell de navegación unificado de Experience Cloud
* Se ha eliminado la barra de sugerencias de comentarios flotante para un tablero de campañas más limpio
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 14 de julio de 2026**

* Despliegue de dominios y remitentes, progreso del flujo de trabajo en directo y perspectivas de campaña reales
* La configuración de Dominios y remitentes ya está disponible y la opción de remitente se guarda automáticamente
* Elija o actualice el remitente del correo electrónico de su campaña desde la configuración de la campaña
* La pestaña Remitentes permanece explorable incluso antes de comprobar un dominio
* Los borradores de correo electrónico añadidos a mitad de la conversación ahora aparecen de forma fiable en el tablero de campañas
* La ayuda y los comentarios se combinan en una ventana emergente optimizada
* Al iniciar una nueva conversación ya no se muestran los mensajes restantes de la última
* Las conversaciones de varias vueltas ya no muestran avisos obsoletos en el cajón de respuestas
* Las listas numeradas en los mensajes de chat mantienen el orden correcto
* La configuración del conector HubSpot ahora solicita una clave de servicio, que coincide con la terminología propia de HubSpot
* La tabla de administración de prueba muestra un recuento de usuarios y ya no recorta la última fila
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 9 de julio de 2026**

* Ahora, un mensaje y un cuadro de diálogo de mantenimiento le avisan antes del tiempo de inactividad programado
* Dominios y remitentes tiene un asistente de configuración guiada para verificar dominios y agregar remitentes
* Los borradores de campañas ahora le piden que finalice la configuración de correo electrónico y canal antes de enviar
* La validación de dominios y remitentes detecta más problemas, incluidos los casos extremos de registros DNS
* El menú de perfil se ha trasladado a la barra lateral para acceder más rápido
* Los documentos de Source PDF ahora se muestran como una píldora en los detalles del kit de la marca
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 26 de junio de 2026**

* Un nuevo panel de Insights muestra los KPI de rendimiento de la campaña: envíos, aperturas, clics, devoluciones y más
* Las campañas muestran un distintivo de estado activo en el tablero para que pueda ver los envíos activos de un vistazo
* Las sugerencias contextuales aparecen en el tablero de campañas para guiarle por los pasos siguientes
* La incorporación de nuevos usuarios utiliza los datos de marca reales para personalizar la experiencia de configuración
* El selector de color de la marca maneja los códigos hexadecimales cortos y se abre en una ventana emergente ordenada
* Los parámetros de UTM y el límite de mensajes ahora se pueden configurar desde Configuración de aplicación
* Los vínculos de ayuda ahora abren el contenido más reciente directamente en Experience League
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 24 de junio de 2026**

* El lanzamiento de una campaña ahora déclencheur una celebración de confeti
* Las campañas muestran un distintivo de estado y el tablero se bloquea como de solo lectura una vez iniciado
* La descripción general de la marca se adapta a su pantalla con mensajes en estado vacío y una mejor visualización del logotipo
* La validación muestra un cuadro de diálogo claro incluso cuando se devuelve un tipo de error inesperado
* El contenido del correo electrónico generado utiliza el objetivo de la campaña para obtener resultados más relevantes

## Junio de 2026 {#june-2026}

**Fecha de la versión: 23 de junio de 2026**

* Un paso de validación comprueba que la campaña está lista antes de iniciarse
* Vea por qué cada variante de correo electrónico se creó con una nueva justificación de variación
* La vista de plan de campaña muestra un carril de progreso de hito activo a medida que las tareas se transfieren
* La incorporación de nuevos usuarios utiliza los datos de marca reales para personalizar la experiencia de configuración
* El selector de color de la marca maneja los códigos hexadecimales cortos y se abre en una ventana emergente ordenada
* Los parámetros de UTM y el límite de mensajes ahora se pueden configurar desde Configuración de aplicación
* Los vínculos de ayuda ahora abren el contenido más reciente directamente en Experience League
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 19 de junio de 2026**

* Compruebe la compatibilidad del cliente de correo electrónico para cada elemento antes de enviar
* Examine y restaure las versiones anteriores del correo electrónico con un panel del historial de versiones nuevas
* Edite los colores de marca con un selector de primera hexagonal y edite en línea en la página de marca
* La biblioteca de marcas carga más marcas automáticamente al desplazarse
* El menú de perfil se ha trasladado a la barra lateral para acceder más rápido
* Los documentos de Source PDF ahora se muestran como una píldora en los detalles del kit de la marca
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 12 de junio de 2026**

* Examine la ayuda y las guías del producto sin salir de la aplicación
* Los planes de campaña aparecen sección por sección a medida que se generan
* Recoja las conversaciones de campaña donde las dejó de manera más confiable
* Inicie campañas desde un cuadro de diálogo dedicado cuando su plan esté listo para funcionar
* La incorporación utiliza una nomenclatura de productos y una guía de inicio más claras
* La configuración del conector muestra los campos adecuados para la clave de API y las conexiones de inicio de sesión
* Las respuestas de chat fuera de ámbito sugieren qué preguntar a continuación con mensajes de un solo clic
* Las exportaciones de Campaign PDF muestran los iconos, la marca del producto y una etiqueta de marca de forma fiable
* Hable con un experto y los flujos de actualización cargan los detalles de la prueba de forma más fiable
* La escritura de etiquetas de estilo se expande para mostrar texto completo y un vínculo a la página de marca
* Inicie una marca desde el estado vacío de la biblioteca con categorías útiles
* Inicie sesión de nuevo sin problemas cuando caduque la sesión
* La aplicación ahora se encuentra en coworker-campaigns.adobe.com con la misma experiencia
* La suscripción de prueba le lleva al siguiente paso correcto después de crear su cuenta
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 11 de junio de 2026**

* Las páginas próximas a aparecer muestran un marcador de posición limpio sin desorden de fondo
* Las barras de herramientas del editor de correo electrónico se ven bien en el tema claro
* Al eliminar una imagen de correo electrónico, se borra la selección y la barra de herramientas desaparece
* Las importaciones de audiencia CSV ya no muestran una lista duplicada en la tarjeta de audiencia
* El elemento Chats de la barra lateral se resalta al iniciar una nueva conversación
* El encabezado de la aplicación ahora solo muestra el asunto del correo electrónico (o &quot;Borrador&quot;) al editar un correo electrónico, lo que elimina el prefijo numérico &quot;N de correo electrónico&quot; para un título más ordenado
* El menú de perfil se ha trasladado a la barra lateral para acceder más rápido
* Los documentos de Source PDF ahora se muestran como una píldora en los detalles del kit de la marca
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 10 de junio de 2026**

* La aplicación ahora es Campañas de compañeros con un nombre actualizado en
* Un recorrido de incorporación por primera vez le guiará a través de la creación de una marca de demostración
* Inicie campañas desde un cuadro de diálogo dedicado cuando su plan esté listo para funcionar
* Conecte HubSpot con una clave de API del catálogo de integraciones
* Explora chats con una lista de conversaciones rediseñada y estados vacíos más claros
* Deshacer y rehacer ediciones de correo electrónico con métodos abreviados de teclado conocidos
* Vuelva a intentar guardar cuando el editor de correo electrónico encuentre un error temporal
* Reemplace las imágenes de correo electrónico por dimensiones de tamaño y Adobe Express correctas
* Cargar listas de audiencias desde CSV con un cuadro de diálogo de importación más claro en el chat
* La escritura de etiquetas de estilo se expande para mostrar texto completo y un vínculo a la página de marca
* Inicie una marca desde el estado vacío de la biblioteca con categorías útiles
* Inicie sesión de nuevo sin problemas cuando caduque la sesión
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 9 de junio de 2026**

* Comparar el uso de prueba y las opciones de actualización en un cuadro de diálogo de plan rediseñado
* Examine y administre Data Connectors desde un catálogo en directo en la aplicación
* Rellene la configuración general y las preferencias de notificación en Configuración
* Su inicio de sesión permanece actualizado con un mensaje claro cuando caduca la sesión
* Su dirección de correo electrónico aparece automáticamente al enviar un correo electrónico de prueba
* Confirmar antes de convertir un kit de marca en el predeterminado
* Las cargas de Brand Kit ahora respetan un límite de tamaño de archivo de 100 MB
* Edite el nombre de su campaña directamente en el tablero de campañas
* Previsualice las plantillas y confirme antes de enviar una campaña
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 4 de junio de 2026**

* Los chats recientes aparecen en la barra lateral y puede cambiarles el nombre en línea
* Abrir la página Chats para buscar y continuar conversaciones anteriores
* Los flujos de trabajo de inicio ahora son plantillas de campaña con un flujo de remix más sencillo
* Las plantillas de biblioteca utilizan una tabla más clara con descripciones y filtros de canal
* Los kits de marca muestran primero su valor predeterminado y filtran por versión publicada o borrador
* Después de publicar un borrador de marca, llega al kit de marca en directo automáticamente
* Los datos de marca y de campaña se cargan de forma más fiable justo después de iniciar sesión
* Varias mejoras de rendimiento y fiabilidad en

## Mayo de 2026 {#may-2026}

**Fecha de la versión: 29 de mayo de 2026**

* Genere variantes de imagen y elija entre sus propias imágenes dentro del editor de correo electrónico
* Agregue imágenes del equipo mediante un selector de archivos local en la barra de herramientas de imágenes
* Describa lo que quiere y deje que AI genere la imagen perfecta para su correo electrónico
* Exporte el correo electrónico finalizado como archivo HTML desde el menú Más
* Las sugerencias de copia inteligente ahora aparecen en la barra de herramientas de correo electrónico al editar el texto
* Haga clic en una marca en el tablero de campaña para ver instantáneamente los detalles de la marca
* Configure su kit de marca predeterminado directamente desde la biblioteca
* Los correos electrónicos en el editor ahora siguen la secuencia de flujo de trabajo para un orden más claro
* Los archivos adjuntos de los archivos de la pantalla de inicio ahora se limitan a PDF para un procesamiento fiable
* La navegación mediante el teclado, la compatibilidad con lectores de pantalla y las preferencias de movimiento son más coherentes en toda la aplicación
* Las etiquetas de &quot;próximamente&quot; marcan páginas que se están creando activamente
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 21 de mayo de 2026**

* Editar imágenes de correo electrónico con Adobe Express sin salir del editor
* Crear marcas con un progreso claro mientras se extraen y publican los recursos
* Administrar dominios y remitentes desde la sección Personas
* Examine y administre listas de contactos desde la sección Personas
* Cambiar plantillas de recursos al trabajar con recursos de marketing
* Descargar planes de campaña como archivos de Word con diagramas de flujo de trabajo
* Las listas entre campañas, habilidades y flujos de trabajo comparten un diseño más claro
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 14 de mayo de 2026**

* La biblioteca reúne Assets, plantillas y marcas en un solo lugar
* La barra lateral y la navegación facilitan el acceso a las audiencias y al kit de marca predeterminado
* Descargue su plan de campaña as a PDF directamente desde los detalles de la campaña
* La edición de marca abre paneles más claros para obtener información general, estilo de escritura y colores
* La cuenta atrás de prueba aparece en el encabezado para que los días restantes permanezcan visibles
* Los flujos de trabajo de marketing deportivo están listos cuando el informe se ajuste a esa categoría
* La configuración de prueba manual gestiona las direcciones de sitios web de la empresa de forma más predecible
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 8 de mayo de 2026**

* El chat de Campaign ofrece un claro reintento cuando falla la comprobación de una tarea en segundo plano
* Las actualizaciones de estado de las tareas y el diseño de pantalla completa son más suaves en los tableros de campaña
* La aplicación se inicia más rápido cargando rutas y traducciones a medida que las necesita
* Los datos de campaña y marca son coherentes en toda la aplicación
* Las ediciones de Deshacer y Rehacer correo electrónico funcionan de forma más predecible
* Vuelva a intentar guardar cuando el editor de correo electrónico encuentre un error temporal
* Reemplace las imágenes de correo electrónico por dimensiones de tamaño y Adobe Express correctas
* Cargar listas de audiencias desde CSV con un cuadro de diálogo de importación más claro
* La escritura de etiquetas de estilo se expande para mostrar texto completo y un vínculo a la página de marca
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de la versión: 6 de mayo de 2026**

* Los tableros y las listas de campañas permanecen alineados con los detalles más recientes mientras trabaja
* Aparece un claro descargo de responsabilidad de IA generativa en el chat de Campaign y en el generador de agentes
* Los datos de contacto de la asistencia ahora utilizan la dirección de correo electrónico específica de CX Coworker Campaign
* La página de inicio de marketing elimina la sección de lista de espera y muestra el vídeo a pantalla completa con mayor claridad
* Más pantallas respetan automáticamente el idioma y los formatos de fecha locales
* Varias mejoras de rendimiento y fiabilidad en

## Abril de 2026 {#apr-2026}

**Fecha de publicación: 28 de abril de 2026**

* Las listas y tableros de campañas se mantienen sincronizados y se sienten más ágiles al abrir o actualizar una campaña
* Los flujos de trabajo de inicio ahora son plantillas de campaña con un flujo de remix más sencillo
* Los temas oscuros y claros utilizan un estilo Spectrum actualizado para lograr un aspecto más coherente en toda la aplicación
* El chat gestiona el contenido del asistente vacío correctamente, con animaciones de estado más suaves y animaciones de estado más claras
* Las conversaciones restauradas se abren sin un flash de carril de chat en blanco, y cambiar las variantes de correo electrónico ya no parpadea el carril
* Los controles de carga de archivos no se interactúan después de enviar o continuar la conversación
* &quot;Ayúdame a escribir&quot; obtiene ideas rápidas solo después de abrir la ventana emergente
* Las actualizaciones de estado solo muestran un control de expansión cuando hay una lista que mostrar
* Las tarjetas de las campañas, las habilidades y los flujos de trabajo comparten un diseño más coherente
* Las listas de campañas y los datos de marca se cargan de forma más fiable justo después de iniciar sesión
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de publicación: 19 de abril de 2026**

* El encabezado de la aplicación ahora solo muestra el asunto del correo electrónico (o &quot;Borrador&quot;) al editar un correo electrónico, lo que elimina el prefijo numérico &quot;N de correo electrónico&quot; para un título más ordenado
* El menú de perfil se ha trasladado a la barra lateral para acceder más rápido
* Los documentos de Source PDF ahora se muestran como una píldora en los detalles del kit de la marca
* El menú de perfil se ha trasladado a la barra lateral para acceder más rápido
* Varias mejoras de rendimiento y fiabilidad en

**Fecha de publicación: 18 de abril de 2026**

* La entrada de la campaña de la página de inicio ahora tiene un anillo de resplandor animado y un degradado de héroe más alto y brillante
* &quot;Sorpréndeme&quot; déclencheur un brillante degradado de colores en el borde de entrada
* La aplicación ahora admite un diseño más coherente en todas las páginas de productos
* Los vínculos de documentación ahora abren el contenido más reciente directamente en una nueva pestaña
* Varias mejoras de rendimiento y fiabilidad en
