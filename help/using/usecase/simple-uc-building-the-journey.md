---
title: Construire le voyage
description: Découvrez comment créer un parcours simple de cas d'utilisation
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


# Construire le voyage{#concept_eyw_mcy_w2b}

L’utilisateur **** professionnel peut désormais construire le parcours. Notre voyage n&#39;inclura qu&#39;un seul chemin avec les activités suivantes :

* l&#39; **[!UICONTROL événement]**&quot;SpaBeacon&quot; : lorsqu&#39; une personne se rapproche de la balise spa, le système reçoit un événement et le voyage commence pour cette personne.
* une activité **[!UICONTROL Condition]**pour vérifier que la personne est une femme
* une activité de **[!UICONTROL courriel]**(à l’aide d’Adobe Campaign Standard)
* une activité **[!UICONTROL Fin]**

>[!NOTE]
>
>Les activités **[!UICONTROL Push]**et**[!UICONTROL  Email]** ne sont disponibles dans la palette que si vous disposez d’Adobe Campaign Standard.

Pour plus d&#39;informations sur la manière de construire un voyage, consultez [](../building-journeys/journey.md).

1. Dans le menu supérieur, cliquez sur l’onglet **[!UICONTROL Accueil]**et**[!UICONTROL  Créer]** pour créer un nouveau voyage.

   ![](../assets/journey31.png)

1. Modifiez les propriétés du voyage dans le volet de configuration qui s’affiche sur le côté droit. Nous lui donnons le nom de &quot;voyage Spa&quot; et l&#39;organisons pour un mois, du 1er au 31 décembre.

   ![](../assets/journeyuc1_8.png)

1. Commencez à concevoir votre voyage en faisant glisser l’événement &quot;SpaBeacon&quot; de la palette vers la trame. Vous pouvez également cliquer deux fois sur l’événement dans la palette pour l’ajouter à la trame.

   ![](../assets/journeyuc1_9.png)

1. Ajoutons maintenant une condition pour vérifier que la personne est une femme. Faites glisser une activité de condition dans votre voyage.

   ![](../assets/journeyuc1_10.png)

1. Sélectionnez le type Condition **[!UICONTROL de source de]**données, puis cliquez sur dans le champ**[!UICONTROL  Expression]** . Vous pouvez également définir une étiquette de condition qui apparaîtra sur la flèche, dans la trame.

   ![](../assets/journeyuc1_11.png)

1. A l’aide de l’éditeur d’expression simple, recherchez le champ de sexe (_personne > sexe_) et déposez-le à droite pour créer la condition suivante : &quot;Le sexe est égal à &quot;Femme&quot;.

   ![](../assets/journeyuc1_12.png)

1. Déposez une activité de **[!UICONTROL courriel]**et sélectionnez votre modèle de messagerie transactionnelle &quot;Escompte Spa&quot;. Ce modèle a été conçu à l’aide d’Adobe Campaign. Refer to this[page](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. Cliquez dans le champ **[!UICONTROL Courriel]**et sélectionnez l’adresse électronique dans la source de données.

   ![](../assets/journeyuc1_14.png)

1. De la même manière, définissez les champs de personnalisation du prénom et du nom à partir de la source de données.

   ![](../assets/journeyuc1_15.png)

1. Drop an **[!UICONTROL End]**activity.

   ![](../assets/journeyuc1_17.png)

1. Cliquez sur le bouton **[!UICONTROL Tester]**et testez votre parcours à l’aide des profils de test. En cas d’erreur, désactivez le mode test, modifiez votre voyage et testez-le à nouveau. For more information on the test mode, refer to[](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. Lorsque le test est concluant, vous pouvez publier votre voyage à partir du menu déroulant supérieur droit.

   ![](../assets/journeyuc1_18.png)

La prochaine fois qu&#39;une femme se rapprochera de la balise spa, elle recevra immédiatement un e-mail personnalisé &quot;remise Spa&quot;.
