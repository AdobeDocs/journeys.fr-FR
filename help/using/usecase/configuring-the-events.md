---
title: Configuration des événements
description: Découvrez comment configurer les événements pour un cas d’utilisation avancé de parcours
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Configuration des événements {#concept_sbp_5cy_w2b}

Dans notre scénario, nous devons recevoir un événement chaque fois qu’une personne entre à l’hôtel Marlton et au restaurant. Un **utilisateur technique** doit configurer les deux événements que, selon nous, le système doit écouter dans notre parcours.

Pour plus d’informations sur la configuration des événements, voir [](../event/about-events.md).

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Événements]** et sur **[!UICONTROL Ajouter]** pour créer un événement.

   ![](../assets/journeyuc1_1.png)

1. Nous saisissons le nom « LobbyBeacon », sans espaces ni caractères spéciaux.

   ![](../assets/journeyuc2_1.png)

<!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc2_3.png" placement="break" width="800" id="image_is5_2sn_z2b"/></li-->

1. Nous sélectionnons ensuite le schéma et définissons la payload attendue pour cet événement. Nous sélectionnons les champs nécessaires dans le modèle normalisé XDM. Nous avons besoin de l’Experience Cloud ID pour identifier la personne dans la base de données des profils clients en temps réel : &quot;endUserIDs > _experience > mcid > id&quot;.

   Nous avons également besoin du jeton d’enregistrement pour envoyer des messages push : &quot;_experience > campaign > message > profile > pushNotificationTokens > token&quot;

   Un identifiant est automatiquement généré pour cet événement et stocké dans le champ **[!UICONTROL eventID]** (&quot;_experience > campaign > orchestration > eventID&quot;). Le système à l’origine de l’envoi de l’événement ne doit pas générer d’identifiant, mais plutôt utiliser celui indiqué dans l’aperçu de la payload. Dans notre cas d’utilisation, cet identifiant est utilisé pour déterminer l’emplacement de la balise. Chaque fois qu’une personne se rapproche de la balise du hall d’entrée de l’hôtel, un événement contenant cet identifiant d’événement spécifique est envoyé. Le même principe s’applique aux événements relatifs à la balise du restaurant. Le système sait ainsi quelle balise a déclenché l’envoi de l’événement.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >La liste des champs varie d’un schéma à l’autre. En fonction de la définition du schéma, certains champs peuvent être obligatoires et présélectionnés.

1. Nous devons sélectionner un namespace. Il est présélectionné en fonction des propriétés du schéma. Vous pouvez le conserver. Pour plus d’informations sur les namespaces, consultez la section [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. Une clé est présélectionnée en fonction des propriétés du schéma et du namespace sélectionné. Vous pouvez la conserver.

   ![](../assets/journeyuc2_4bis.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

1. Cliquez sur l’icône **[!UICONTROL Afficher la payload]** pour avoir un aperçu de la payload attendue par le système et la partager avec la personne responsable de l’envoi de l’événement. Cette payload doit être configurée dans le postback de la console d’administration Mobile Services.

   ![](../assets/journeyuc2_5.png)

De la même manière, créez l’événement « RestaurantBeacon ». Ces deux événements de balise sont créés et utilisables dans le parcours. Vous devez maintenant configurer l’application mobile afin qu’elle puisse envoyer la payload attendue au point d’entrée des API d’ingestion en flux continu. Voir [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
