---
product: adobe campaign
solution: Journey Orchestration
title: Configuration de l’événement
description: Découvrez comment configurer l’événement pour le cas d’utilisation simple du parcours
feature: Parcours
role: Professionnel
level: Intermédiaire
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 99%

---


# Configuration de l’événement{#concept_y44_hcy_w2b}

Dans notre scénario, nous devons recevoir un événement chaque fois qu’une personne se rapproche d’une balise située à proximité du spa. Un **utilisateur technique** doit configurer l’événement que le système doit écouter dans notre parcours.

Pour plus d’informations sur la configuration des événements, consultez [cette page](../event/about-events.md).

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Événements]** et sur **[!UICONTROL Ajouter]** pour créer un événement.

   ![](../assets/journeyuc1_1.png)

1. Nous saisissons le nom « SpaBeacon », sans espaces ni caractères spéciaux.

   ![](../assets/journeyuc1_2.png)

1. Nous sélectionnons ensuite le schéma et définissons la payload attendue pour cet événement. Nous sélectionnons les champs nécessaires dans le modèle normalisé XDM. Nous avons besoin de l’Experience Cloud ID pour identifier la personne dans la base de données des profils clients en temps réel : _endUserIDs > experience > mcid > id_. Un identifiant est automatiquement généré pour cet événement et stocké dans le champ **[!UICONTROL eventID]** (_experience > campaign > orchestration > eventID_). Le système à l’origine de l’envoi de l’événement ne doit pas générer d’identifiant, mais plutôt utiliser celui indiqué dans l’aperçu de la payload. Dans notre cas d’utilisation, cet identifiant est utilisé pour déterminer l’emplacement de la balise. Chaque fois qu’une personne se rapproche de la balise du spa, un événement contenant cet identifiant d’événement spécifique est envoyé. Le système sait ainsi quelle balise a déclenché l’envoi de l’événement.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >La liste des champs varie d’un schéma à l’autre. En fonction de la définition du schéma, certains champs peuvent être obligatoires et présélectionnés.

1. Nous devons sélectionner un espace de noms. Il est présélectionné en fonction des propriétés du schéma. Vous pouvez le conserver. Pour plus d’informations sur les espaces de noms, voir [cette page](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. Une clé est présélectionnée en fonction des propriétés du schéma et de l’espace de noms sélectionné. Vous pouvez la conserver.

   ![](../assets/journeyuc1_5.png)

1. Cliquez sur **[!UICONTROL Enregistrer]**.

1. Cliquez sur l’icône **[!UICONTROL Afficher la payload]** pour avoir un aperçu de la payload attendue par le système et la partager avec la personne responsable de l’envoi de l’événement. Cette payload doit être configurée dans le postback de la console d’administration Mobile Services.

   ![](../assets/journeyuc1_7.png)

   L’événement est prêt à être utilisé dans votre parcours. Vous devez maintenant configurer l’application mobile afin qu’elle puisse envoyer la payload attendue au point d’entrée des API d’ingestion en flux continu. Voir [cette page](../event/additional-steps-to-send-events-to-journey-orchestration.md).