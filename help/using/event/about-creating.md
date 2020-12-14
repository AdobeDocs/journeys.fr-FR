---
product: adobe campaign
solution: Journey Orchestration
title: 'Créer un événement     '
description: Découvrez comment créer un événement
translation-type: tm+mt
source-git-commit: b3ed5d305ddd1c86814373fc923390dc50a80c7e
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 72%

---


# Création d’un événement {#section_tbk_5qt_pgb}

Les principales étapes nécessaires pour configurer un nouvel événement sont les suivantes :

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Événements]**. La liste des événements s’affiche. Refer to [this page](../about/user-interface.md) for more information on the interface.

   ![](../assets/journey5.png)

1. Cliquez sur le bouton **[!UICONTROL Ajouter]** pour créer un événement. Le volet de configuration d’événement s’ouvre dans la partie droite de l’écran. Saisissez le nom de votre événement. Vous pouvez également ajouter une description.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >N’utilisez ni espaces ni caractères spéciaux. Utilisez 30 caractères au maximum.

1. Dans le champ ID de **[!UICONTROL Événement]** , sélectionnez le type d&#39;événement à utiliser.

   ![](../assets/journey6bis.png)

   * **Événements basés sur** des règles : ce type de événement ne génère pas d’eventID. In the **Event ID condition** field, you simply define a rule which will be used by the system to identify the relevant events that will trigger your journeys. Cette règle peut être basée sur n’importe quel champ disponible dans le payload, par exemple l’emplacement du profil ou le nombre d’éléments ajoutés au panier du profil.

   * **Événements générés** par le système : ce type nécessite un eventID. Ce champ eventID est généré automatiquement lors de la création du événement et ajouté à la prévisualisation de charge utile. Le système qui pousse le événement ne doit pas générer d’identifiant, il doit transmettre celui disponible dans la prévisualisation de charge utile. Reportez-vous à [cette section](../event/previewing-the-payload.md).
   >[!NOTE]
   >
   >Pour en savoir plus sur les types d&#39;événement de [cette section](../event/about-events.md).
1. Le nombre de parcours qui font appel à cet événement apparaît dans le champ **[!UICONTROL Utilisé(e) dans]**. Vous pouvez cliquer sur l’icône **[!UICONTROL Afficher les parcours]** pour faire apparaître la liste des parcours utilisant cet événement.
1. Définissez les champs de payload et de schéma : c’est dans ces champs que vous sélectionnez les informations d’événement (désignées généralement sous le nom de payload) que [!DNL Journey Orchestration] s’attend à recevoir. Vous pourrez alors utiliser ces informations dans votre parcours. Voir [cette page](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >When you select the **[!UICONTROL System Generated]** type, only schemas that have the eventID type mixin are available. Lorsque vous sélectionnez le type **[!UICONTROL Basé sur des règles]**, tous les schémas Événement d’expérience sont disponibles.

1. Pour les événements basés sur des règles, cliquez à l’intérieur du champ de condition **[!UICONTROL ID de]** Événement. À l’aide de l’éditeur d’expression simple, définissez la condition qui sera utilisée par le système pour identifier les événements qui déclencheront votre parcours.
   ![](../assets/alpha-event6.png)

   Dans notre exemple, nous avons écrit une condition basée sur la ville du profil. Cela signifie que chaque fois que le système reçoit un événement qui correspond à cette condition (champ **[!UICONTROL Ville]** et valeur **[!UICONTROL Paris]**), il le transmet à Journey Orchestration.

1. Ajoutez un espace de noms. Cette étape est facultative, mais recommandée. En effet, l’ajout d’un espace de noms permet d’exploiter les informations stockées dans le service de profil client en temps réel. Il définit le type de clé dont dispose l’événement. Voir [cette page](../event/selecting-the-namespace.md).
1. Définissez la clé : effectuez votre choix parmi vos champs de payload ou définissez une formule pour identifier la personne associée à l’événement. Cette clé est configurée automatiquement (mais peut toujours être modifiée) si vous sélectionnez un espace de noms. En effet, [!DNL Journey Orchestration] sélectionne la clé qui doit correspondre à l’espace de noms ; par exemple, si vous sélectionnez un espace de noms d’email, la clé d’email est sélectionnée. Voir [cette page](../event/defining-the-event-key.md).
1. Pour les événements générés par le système, vous pouvez ajouter une condition. Cette étape est facultative. Elle permet au système de traiter uniquement les événements qui répondent à la condition. Cette condition ne peut être basée que sur les informations contenues dans l’événement. Voir [cette page](../event/adding-a-condition.md).
1. Cliquez sur **[!UICONTROL Enregistrer]**.

   ![](../assets/journey7.png)

   L’événement est maintenant configuré et prêt à être déposé dans un parcours. Des étapes de configuration supplémentaires sont requises pour la réception d’événements. Voir [cette page](../event/additional-steps-to-send-events-to-journey-orchestration.md).