---
product: adobe campaign
title: Test du parcours
description: En savoir plus sur le test d’un parcours
feature: Journeys
role: User
level: Intermediate
exl-id: be413905-0631-4229-a954-80a92651206d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '1635'
ht-degree: 100%

---

# Test du parcours{#testing_the_journey}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._


Avant de pouvoir tester votre parcours, vous devez résoudre toutes les erreurs qu’il comporte, le cas échéant. Consultez [cette section](../about/troubleshooting.md#section_h3q_kqk_fhb).

Vous avez la possibilité de tester votre parcours avant sa publication, en utilisant des profils de test. Vous pouvez ainsi analyser le flux des personnes dans le parcours et résoudre les problèmes avant la publication.

Seuls les profils de test peuvent rejoindre un parcours en mode test. Vous pouvez soit créer un profil de test, soit transformer un profil existant en profil de test. Reportez-vous à cette [section](../building-journeys/creating-test-profiles.md).

Pour utiliser le mode test, procédez comme suit :

1. Avant de tester votre parcours, vérifiez qu&#39;il est valide et qu&#39;il ne comporte aucune erreur, sans quoi il vous sera impossible de lancer un test. Consultez [cette section](../about/troubleshooting.md#section_h3q_kqk_fhb). Un symbole d’avertissement est affiché en cas d’erreur.

1. Pour activer le mode test, cliquez sur le bouton bascule **[!UICONTROL Test]** dans le coin supérieur droit de l’écran.

   ![](../assets/journeytest1.png)

1. Utilisez le paramètre **[!UICONTROL Durée d’attente]**, dans le coin inférieur gauche, pour définir la durée de chaque activité d’attente et temporisation d’événement en mode test. La durée par défaut est de 10 secondes pour les attentes et les temporisations d’événement. Vous obtiendrez ainsi rapidement les résultats du test. Ce paramètre n’apparaît que si vous avez placé une ou plusieurs activités d’attente dans votre parcours.

   ![](../assets/journeytest_wait.png)

   >[!NOTE]
   >
   >Lorsqu’un événement de réaction est utilisé avec une temporisation dans un parcours, la durée d’attente par défaut ainsi que la valeur minimale sont de 40 secondes. Consultez [cette section](../building-journeys/reaction-events.md).

1. Cliquez sur **[!UICONTROL Déclencher un événement]** pour configurer des événements et les envoyer au parcours.

   ![](../assets/journeyuctest1.png)

1. Configurez les différents champs attendus. Dans le champ **Identifiant de profil**, saisissez la valeur du champ utilisé pour identifier le profil de test. Il peut s’agir, par exemple, de l’adresse e-mail. Veillez à envoyer des événements liés aux profils de test. Voir [Déclenchement d’événements](#firing_events).

   ![](../assets/journeyuctest1-bis.png)

1. Une fois les événements reçus, cliquez sur le bouton **[!UICONTROL Afficher le journal]** pour afficher les résultats du test et les valider. Voir [Affichage des journaux](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. En cas d’erreur, désactivez le mode test, modifiez votre parcours et lancez un nouveau test. Si le test est concluant, vous pouvez publier votre parcours. Voir [cette page](../building-journeys/publishing-the-journey.md).

## Remarques importantes {#important_notes}

* Une interface permet de déclencher des événements sur le parcours testé. Cependant, des événements peuvent également être envoyés par des systèmes tiers tels que Postman.
* Seules les personnes identifiées comme « profils de test » dans le service de profil client en temps réel seront autorisées à entrer dans le parcours testé. Reportez-vous à cette [section](../building-journeys/creating-test-profiles.md).
* Le mode test n’est disponible que dans les parcours dans un état de brouillon qui utilisent un espace de noms. Le mode test doit vérifier si une personne qui participe au parcours est un profil de test ou non et doit donc être en mesure d’accéder à Adobe Experience Platform.
* Le nombre maximal de profils de test pouvant entrer dans un parcours au cours d’une session de test est de 100.
* Lorsque vous désactivez le mode test, les parcours sont vidés de toutes les personnes qui y sont entrées dans le passé ou qui s’y trouvent actuellement. Les rapports son également effacés.
* Vous pouvez activer/désactiver le mode test autant de fois que nécessaire.
* Vous ne pouvez pas modifier votre parcours lorsque le mode test est activé. En mode test, vous pouvez publier directement le parcours, sans avoir à désactiver le mode test avant.
* Lors qu&#39;un partage est atteint, la branche supérieure est toujours choisie. Vous pouvez réorganiser la position des branches partagées si vous souhaitez que le test choisisse un autre chemin.
* Pour optimiser les performances et empêcher l’utilisation des ressources obsolètes, tous les parcours en mode test qui n’ont pas été déclenchés pendant une semaine repassent au statut Brouillon.

## Transformation d’un profil en profil de test{#turning-profile-into-test}

Vous pouvez transformer un profil existant en profil de test. Dans Adobe Experience Platform, vous pouvez mettre à jour les attributs des profils par le biais d’appels d’API, mais il n’est pas possible de le faire par le biais de l’interface.

Pour ce faire, la méthode la plus simple consiste à utiliser une activité d’action **Mettre à jour le profil** et à modifier le champ booléen du profil de test en le passant de false à true. Consultez [cette section](../building-journeys/update-profiles.md#using-the-test-mode).

## Création d’un profil de test{#create-test-profile}

Si vous souhaitez créer un profil de test, la procédure à suivre est identique à celle utilisée pour créer un profil dans Adobe Experience Platform. Il est effectué par le biais d’appels API. Voir cette [page](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr)

Vous devez utiliser un schéma de profil contenant le mixin « Détails du test de profil ». L&#39;indicateur testProfile fait partie de ce mixin.

Lors de la création d&#39;un profil, veillez à transmettre la valeur : testProfile = true.

Veuillez noter que vous pouvez également mettre à jour un profil existant pour remplacer son indicateur testProfile par « true ».

Voici un exemple d&#39;appel API pour créer un profil de test :

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

## Déclenchement d’événements {#firing_events}

Le bouton **[!UICONTROL Déclencher un événement]** vous permet de configurer un événement qui fera qu’un individu rejoint le parcours.

>[!NOTE]
>
>Lorsque vous déclenchez un événement en mode test, un événement réel est généré, ce qui signifie qu’il sera également utilisé pour un autre parcours qui écoute cet événement.

Vous devez, au préalable, savoir quels profils sont identifiés comme profils de test dans Adobe Experience Platform. En effet, le mode test autorise uniquement ces profils dans le parcours et l’événement doit contenir un identifiant. L’identifiant attendu dépend de la configuration de l’événement. Il peut s’agir d’un ECID ou d’une adresse e-mail, par exemple. La valeur de cette clé doit être ajoutée dans le champ **Identifiant du profil**.

>[!NOTE]
>
>Une liste déroulante s’affiche pour les champs qui prévoient une énumération. Il vous suffit de sélectionner l’une des valeurs disponibles.

Si votre parcours contient plusieurs événements, sélectionnez-les dans la liste déroulante. Ensuite, pour chaque événement, configurez les champs transmis et l&#39;exécution de l&#39;envoi de l’événement. L’interface vous permet de transmettre les informations appropriées dans le payload de l’événement et de vous assurer que le type d’information est correct. Le mode test enregistre les derniers paramètres utilisés dans une session de test en vue d’une utilisation ultérieure.

![](../assets/journeytest4.png)

L’interface vous permet de transmettre des paramètres d’événement simples. Pour transmettre des collections ou d’autres objets avancés dans l’événement, vous pouvez cliquer sur **[!UICONTROL Affichage du code]** pour afficher le code entier du payload et le modifier. Vous pouvez par exemple copier et coller des informations d’événement préparées par un utilisateur ou une utilisatrice technique.

![](../assets/journeytest5.png)

Un utilisateur ou une utilisatrice technique peut également utiliser cette interface pour composer des payloads d’événement et déclencher des événements sans avoir à utiliser un outil tiers.

Lorsque vous cliquez sur le bouton **[!UICONTROL Envoyer]**, le test commence. La progression de la personne dans le parcours est représentée par un flux visuel. Le chemin devient progressivement vert lorsque la personne se déplace sur le parcours. Si une erreur se produit, un symbole d’avertissement s’affiche à l’étape correspondante. Vous pouvez y placer le curseur pour afficher plus d’informations sur l’erreur et accéder à tous les détails (le cas échéant).

![](../assets/journeytest6.png)

Lorsque vous sélectionnez un autre profil de test dans l’écran de configuration de l’événement et exécutez à nouveau le test, le flux visuel est effacé et affiche le chemin de la nouvelle personne.

Lors de l’ouverture d’un parcours dans le test, le chemin affiché correspond au dernier test exécuté.

Le flux visuel fonctionne que l’événement soit déclenché par l’interface ou de manière externe (à l’aide de Postman, par exemple).

## Mode test pour les parcours basés sur des règles {#test-rule-based}

Le mode test est également disponible pour les parcours qui utilisent un événement basé sur des règles. Pour plus d’informations sur les événements de test, consultez [cette page](../event/about-events.md).

Lors du déclenchement d’un événement, l’écran **Configuration de l’événement** vous permet de définir les paramètres d’événement à transmettre au test. Vous pouvez afficher la condition de l’identifiant d’événement en cliquant sur l’icône Info-bulle dans la partie supérieure droite. Une info-bulle est également disponible en regard de chaque champ qui fait partie de l’évaluation des règles.

![](../assets/alpha-event8.png)

Pour plus d’informations sur l’utilisation du mode test, consultez [cette page](../building-journeys/testing-the-journey.md).

## Affichage des journaux {#viewing_logs}

Le bouton **[!UICONTROL Afficher le journal]** vous permet d’afficher les résultats du test. Cette page affiche des informations actuelles sur le parcours au format JSON. Un bouton vous permet de copier des nœuds entiers. Vous devez actualiser manuellement la page pour mettre à jour les résultats de test du parcours.

![](../assets/journeytest3.png)

>[!NOTE]
>
>Dans les journaux de test, en cas d’erreur lors de l’appel d’un système tiers (source de données ou action), le code d’erreur et la réponse d’erreur s’affichent.

Le nombre de personnes (ou instances) actuellement dans le parcours s’affiche. Voici des informations utiles qui s’affichent pour chaque personne :

* _ID_ : identifiant interne de la personne dans le parcours. Il peut être utilisé à des fins de débogage.
* _currentstep_ : étape à laquelle se trouve la personne dans le parcours. Nous vous recommandons d’ajouter des libellés à vos activités afin de les identifier plus facilement.
* _currentstep_ > phase : statut du parcours de la personne (en cours, terminé, erreur ou expiré). Plus d’informations ci-dessous.
* _currentstep_ > _extraInfo_ : description de l’erreur et autres informations contextuelles.
* _currentstep_ > _fetchErrors_ : informations sur les erreurs de récupération de données qui se sont produites au cours de cette étape.
* _externalKeys_ : valeur de la formule de clé définie dans l’événement.
* _enrichedData_ : données récupérées par le parcours si le parcours utilise des sources de données.
* _transitionHistory_ : liste des étapes suivies par la personne. Pour les événements, le payload s’affiche.
* _actionExecutionErrors_ : informations sur les erreurs qui se sont produites.

Voici les différents statuts du parcours d’une personne :

* _En cours_ : la personne se trouve actuellement dans le parcours.
* _Terminé_ : la personne est à la fin du parcours.
* _Erreur_ : la personne est arrêtée dans le parcours en raison d’une erreur.
* _Expiré_ : la personne est arrêtée dans le parcours à cause d’une étape qui a pris trop de temps.

Lorsqu’un événement est déclenché en mode test, un jeu de données est automatiquement généré avec le nom de la source.

Lorsqu’un événement est déclenché en mode test, un jeu de données est automatiquement généré avec le nom de la source.

Le mode test crée automatiquement un événement d’expérience et l’envoie à Adobe Experience Platform. Le nom de la source de cet événement d’expérience est « Événements de test Journey Orchestration ».
