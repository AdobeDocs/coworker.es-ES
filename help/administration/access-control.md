---
title: Control de acceso para compañeros
description: Obtenga información acerca del control de acceso para Adobe CX Enterprise Coworker y los permisos en productos de Adobe compatibles. Busque controles de administrador y obtenga ayuda con el acceso.
last-substantial-update: 2026-11-04
level: beginner
role: Admin
jira: KT-22980
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: a14bd350d7259294368acdcb08549ea6e084f1c1
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 0%
---
# Control de acceso para el compañero {#access-control}

Utilice el control de acceso de Adobe CX Enterprise Coworker para administrar quién puede utilizar Coworker y qué capacidades pueden utilizar.

>[!NOTE]
>
>Su organización debe estar habilitada para que sus compañeros utilicen esta función. El control de acceso estará disponible de forma progresiva y es posible que no esté habilitado para todas las organizaciones de compañeros en el momento del lanzamiento. Para obtener más información, consulte la [Descripción general del chat de compañeros](https://experienceleague.adobe.com/en/docs/coworker/content/chat/overview).

## Cómo se determina el acceso {#how-access-is-determined}

El acceso de los compañeros de trabajo se controla mediante una configuración que abarca toda la organización y las invalidaciones opcionales de usuarios o grupos. La configuración de toda la organización habilita o deshabilita el acceso de Colaborador para los usuarios de su organización. El acceso está habilitado para todos de forma predeterminada.

| Configuración | Cómo afecta al acceso |
| --- | --- |
| Configuración en toda la organización | Habilite el acceso de Compañeros para todos o deshabilite para su organización. |
| Anulación de usuario o grupo de usuarios | Las invalidaciones proporcionan a los administradores control sobre el acceso de los compañeros para usuarios o grupos de usuarios específicos. |
| Permisos de aplicación compatibles | Los controles de acceso de los compañeros determinan si se puede acceder a alguna funcionalidad de los compañeros disponible de forma general. El colaborador hereda los permisos de usuario de las aplicaciones de CX Enterprise compatibles con el colaborador y respeta los permisos que cada aplicación ya aplica. |


## Administradores de compañeros {#add-coworker-admins}

Un administrador de compañeros es un usuario asignado como **[!UICONTROL Administrador del sistema]** para la organización o como **[!UICONTROL Administrador de productos]** de [!DNL Adobe Experience Platform] en [!DNL Adobe Admin Console].

## Administrar el acceso de usuario {#manage-user-access}

1. Abra la experiencia Colaborador. Para obtener instrucciones, consulta [Iniciar sesión en Compañero](/help/chat/ui-guide.md#sign-in).
2. Abra el menú de perfil y seleccione **[!UICONTROL Configuración de administración]**.

   ![Inicio de compañero con el control de menú de perfil resaltado.](./assets/access-control/coworker-home.png)

   ![Menú de perfil de compañero con la configuración de administración resaltada.](./assets/access-control/admin-settings.png)

3. Seleccione **[!UICONTROL Control de acceso]**.

   ![Configuración de administración con la tarjeta de control de acceso resaltada.](./assets/access-control/access-control.png)

   Utilice este vídeo para aprender a administrar los usuarios de Coworker.

   >[!VIDEO](https://video.tv.adobe.com/v/3507151?learn=on){transcript=true}

4. En Compañero de trabajo, use **[!UICONTROL Usuarios]** para administrar el acceso de individuos o **[!UICONTROL Grupos de usuarios]** para administrar el acceso de Compañero de trabajo para grupos de usuarios. Se aplica una configuración de grupo de usuarios a sus miembros.

   Los grupos de usuarios de compañeros de trabajo son independientes de [!DNL Adobe Admin Console] grupos. La sincronización de grupos de usuarios de [!DNL Adobe Admin Console] con el Compañero de trabajo está disponible próximamente.

   La lista Usuarios incluye a los usuarios de su organización. El acceso de compañeros de trabajo está habilitado para estos usuarios de forma predeterminada.

   * **Habilitado:** El usuario o grupo de usuarios está activo.
   * **Deshabilitado:** El usuario o grupo de usuarios está inactivo.

   Cuando se deshabilite el acceso para todos, active **[!UICONTROL Permitir invalidaciones]** y seleccione **[!UICONTROL Agregar invalidación]** para agregar usuarios o grupos que aún deben tener acceso.

## Permisos en aplicaciones CX Enterprise compatibles con Coworker {#permissions-in-compatible-applications}

Las aplicaciones de CX Enterprise compatibles con los compañeros de trabajo siguen aplicando sus propios permisos.

El compañero respeta los permisos en aplicaciones compatibles. Por ejemplo, si no puede obtener acceso a un conjunto de datos en [!DNL Adobe Experience Platform], el colaborador no podrá recuperar ni actuar en ese conjunto de datos por usted.

## Obtener ayuda con el acceso {#get-help-with-access}

Si no ves [!UICONTROL Control de acceso], ponte en contacto con el administrador de Adobe o con el representante de Adobe. Pueden confirmar si la función está habilitada para su organización y si tiene acceso a su configuración.

Si se le deniega el acceso, pida al administrador que revise la configuración predeterminada de toda la organización y de cualquier usuario o grupo. Para una aplicación CX Enterprise compatible con Coworker, pídale que compruebe los permisos administrados por separado para esa aplicación.

## Más ayuda sobre este tema {#more-help}

Utilice estos recursos para obtener más información sobre los colaboradores y la administración.

* [Resumen de chat con compañeros](/help/chat/overview.md)
* [Introducción al chat con compañeros](/help/chat/ui-guide.md)
* [Administración de complementos y mercados](/help/customizations/plugins/manage-plugins-for-your-org.md)
