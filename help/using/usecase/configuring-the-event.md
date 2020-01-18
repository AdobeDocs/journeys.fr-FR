---
title: Configuration de l’événement
description: Découvrez comment configurer l'événement pour le cas d'utilisation simple du voyage
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Configuration de l’événement{#concept_y44_hcy_w2b}

Dans notre scénario, nous devons recevoir un événement chaque fois qu&#39;une personne se rapproche d&#39;une balise située à côté du spa. L&#39;utilisateur **** technique doit configurer l&#39;événement que le système écoute dans notre voyage.

Pour plus d’informations sur la configuration des événements, voir [](../event/about-events.md).

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Evénements]**et cliquez sur**[!UICONTROL  Ajouter]** pour créer un événement.

   ![](../assets/journeyuc1_1.png)

1. Nous saisissons le nom sans espaces ni caractères spéciaux : &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

   <!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc1_4.png" placement="break" width="800" id="image_qgr_2mn_z2b"/></li-->

1. Nous sélectionnons ensuite le schéma et définissons la charge utile attendue pour cet événement. Nous sélectionnons les champs nécessaires dans le modèle normalisé XDM. Nous avons besoin de l’ID Experience Cloud pour identifier la personne dans la base de données Profil du client en temps réel : _endUserIDs > expérience > mcid > id_. Un ID est généré automatiquement pour cet événement. Cet ID est stocké dans le champ **[!UICONTROL eventID]**(_expérience > campagne > orchestration > eventID_). Le système poussant l’événement ne doit pas générer d’identifiant, il doit utiliser celui disponible dans l’aperçu de la charge utile. Dans notre cas d’utilisation, cet identifiant est utilisé pour identifier l’emplacement de la balise. Chaque fois qu&#39;une personne se rapproche de la balise spa, un événement contenant cet identifiant spécifique est envoyé. Cela permet au système de savoir quelle balise a déclenché l’envoi de l’événement.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >La liste des champs varie d’un schéma à l’autre. Selon la définition du schéma, certains champs peuvent être obligatoires et présélectionnés.

1. Nous devons sélectionner un espace de noms. Un espace de noms est présélectionné en fonction des propriétés du schéma. Vous pouvez garder l&#39;un présélectionné. Pour plus d’informations sur les espaces de noms, voir [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Une clé est présélectionnée en fonction des propriétés du schéma et de l’espace de noms sélectionné. Tu peux le garder.

   ![](../assets/journeyuc1_5.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

1. Cliquez sur l’icône **[!UICONTROL Afficher la charge utile]**pour prévisualiser la charge utile attendue par le système et la partager avec la personne responsable de l’envoi de l’événement. Cette charge doit être configurée dans le postback de Mobile Services Administration Console.

   ![](../assets/journeyuc1_7.png)

   L&#39;événement est prêt à être utilisé dans votre voyage. Vous devez maintenant configurer l’application mobile afin qu’elle puisse envoyer la charge utile attendue au point de terminaison des API d’importation en flux continu. Voir la section [](../event/additional-steps-to-send-events-to-journey-orchestration.md).