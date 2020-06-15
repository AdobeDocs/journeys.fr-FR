---
title: Test du parcours
description: 'En savoir plus sur le test d’un parcours '
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
source-git-commit: be21573973600758cbf13bd25bc3b44ab4cd08ca
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 98%

---


# Test du parcours{#testing_the_journey}

Avant de pouvoir tester votre parcours, vous devez résoudre toutes les erreurs qu’il comporte, le cas échéant. Voir [](../about/troubleshooting.md#section_h3q_kqk_fhb).

Vous avez la possibilité de tester votre parcours avant sa publication, en utilisant des profils de test. Vous pouvez ainsi analyser le flux des individus dans le parcours et résoudre les problèmes avant la publication.

Pour utiliser le mode test, procédez comme suit :

1. Avant de tester votre parcours, vérifiez qu’il est valide et qu’il ne comporte aucune erreur, sans quoi il vous sera impossible de lancer un test. Voir [](../about/troubleshooting.md#section_h3q_kqk_fhb). Un symbole d’avertissement est affiché en cas d’erreur.

1. Pour activer le mode test, cliquez sur le bouton bascule **[!UICONTROL Test]** dans le coin supérieur droit de l’écran.

   ![](../assets/journeytest1.png)

1. Utilisez le paramètre **Temps d’attente en test**, dans le coin inférieur gauche, pour définir la durée d’attente de chaque activité d’attente en mode test. La durée par défaut est de 10 secondes. Vous obtiendrez ainsi rapidement les résultats du test. Ce paramètre n’apparaît que si vous avez placé une ou plusieurs activités d’attente dans votre parcours.

   ![](../assets/journeytest_wait.png)

1. Cliquez sur **[!UICONTROL Déclencher un événement]** pour configurer des événements et les envoyer au parcours. Veillez à envoyer des événements liés aux profils de test. Voir [Déclenchement d’événements](#firing_events).

   ![](../assets/journeyuctest1.png)

1. Une fois les événements reçus, cliquez sur le bouton **[!UICONTROL Afficher le journal]** pour afficher les résultats du test et les valider. Voir [Affichage des journaux](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. En cas d’erreur, désactivez le mode test, modifiez votre parcours et lancez un nouveau test. Si le test est concluant, vous pouvez publier votre parcours. Voir [](../building-journeys/publishing-the-journey.md).

## Remarques importantes       {#important_notes}

* Une interface permet de déclencher des événements sur le parcours testé. Cependant, des événements peuvent également être envoyés par des systèmes tiers tels que Postman.
* Seuls les individus identifiés comme « profils de test » dans le service de profil client en temps réel sont autorisés à participer au parcours testé. Le processus de création d’un profil de test est identique à celui utilisé pour créer un profil dans Data Platform. Vous devez simplement vous assurer que l’indicateur de profil de test est défini sur « true ». Vous pouvez utiliser la section Segments de l’interface de Data Platform pour créer un segment de profils de test dans Data Platform et afficher une liste non exhaustive. La liste exhaustive ne peut pas être affichée pour l’instant.
* Le mode test n’est disponible que dans les parcours dans un état de brouillon qui utilisent un espace de noms. En effet, le mode test doit vérifier si une personne qui participe au parcours est un profil de test ou non et doit donc être en mesure d’accéder à Data Platform.
* Le nombre maximum de profils de test pouvant participer à un parcours au cours d’une session de test est de 100.
* Lorsque vous désactivez le mode test, les parcours sont vidés de toutes les personnes qui y ont participé précédemment ou qui y sont actuellement actives.
* Vous pouvez activer/désactiver le mode test autant de fois que nécessaire.
* Vous ne pouvez pas modifier votre parcours lorsque le mode test est activé. En mode test, vous pouvez publier directement le parcours, sans avoir à désactiver ce mode au préalable.

## Déclenchement d’événements {#firing_events}

Le bouton **[!UICONTROL Déclencher un événement]** vous permet de configurer un événement qui fera entrer une personne dans le parcours.

Vous devez, au préalable, savoir quels profils sont identifiés comme profils de test dans Data Platform. En effet, le mode test autorise uniquement ces profils dans le parcours et l’événement doit contenir un identifiant. L’identifiant attendu dépend de la configuration de l’événement. Il peut s’agir, par exemple, d’un ECID.

Si votre parcours contient plusieurs événements, sélectionnez-les dans la liste déroulante. Ensuite, pour chaque événement, configurez les champs transmis et l’exécution de l’envoi de l’événement. L’interface vous permet de transmettre les informations appropriées dans la payload de l’événement et de vous assurer que le type d’information est correct. Le mode test enregistre les derniers paramètres utilisés dans une session de test en vue d’une utilisation ultérieure.

![](../assets/journeytest4.png)

L’interface vous permet de transmettre des paramètres d’événement simples. Si vous souhaitez transmettre des collections ou d’autres objets avancés dans l’événement, vous pouvez cliquer sur **[!UICONTROL Affichage du code]** pour voir l’intégralité du code de la payload et le modifier. Vous pouvez, par exemple, copier et coller des informations d’événement préparées par un utilisateur technique.

![](../assets/journeytest5.png)

Un utilisateur technique peut également se servir de cette interface pour composer des payloads d’événement et déclencher des événements sans recourir à un outil tiers.

Lorsque vous cliquez sur le bouton **Envoyer**, le test commence. La progression de l’individu dans le parcours est représentée par un flux visuel. Le chemin devient progressivement vert à mesure du déplacement de l’individu dans le parcours. Si une erreur se produit, un symbole d’avertissement s’affiche à l’étape correspondante. Vous pouvez y placer le curseur pour afficher des informations plus précises sur l’erreur et accéder aux détails complets (le cas échéant).

![](../assets/journeytest6.png)

Si vous sélectionnez un autre profil de test dans l’écran de configuration d’un événement et que vous exécutez de nouveau le test, le flux visuel est effacé et indique le chemin du nouvel individu.

Lorsque vous ouvrez un parcours en cours de test, le chemin affiché correspond au dernier test exécuté.

Le flux visuel fonctionne si le événement est déclenché par l&#39;interface ou de manière externe (à l&#39;aide de Postman, par exemple).

## Affichage des journaux {#viewing_logs}

Le bouton **[!UICONTROL Afficher le journal]** vous permet d’afficher les résultats du test. Cette page affiche des informations actuelles sur le parcours au format JSON. Un bouton vous permet de copier des nœuds entiers. Vous devez actualiser manuellement la page pour mettre à jour les résultats de test du parcours.

![](../assets/journeytest3.png)

>[!NOTE]
>
>En cas d’erreur lors de l’appel d’un système tiers (source de données ou action), le code d’erreur et la réponse d’erreur s’affichent dans les journaux de test.

Le nombre d’individus (appelés instances d’un point de vue technique) présents actuellement à l’intérieur du parcours est affiché. Voici des informations utiles affichées pour chaque individu :

* _Id_ : identifiant interne de l’individu dans le parcours. Il peut être utilisé à des fins de débogage.
* _Currentstep_ : étape du parcours à laquelle se trouve l’individu. Nous vous recommandons d’ajouter des libellés à vos activités afin de les identifier plus facilement.
* _currentstep_ > phase : statut du parcours de l’individu (en cours, terminé, erreur ou délai dépassé). Pour plus d’informations, voir ci-dessous.
* _currentstep_ > _extraInfo_ : description de l’erreur et autres informations contextuelles.
* _Currentstep_ > _fetchErrors_ : informations sur les erreurs de récupération de données qui se sont produites au cours de cette étape.
* _externalKeys_ : valeur de la formule de clé définie dans l’événement.
* _enrichedData_ : données récupérées par le parcours si ce dernier utilise des sources de données.
* _transitionHistory_ : liste des étapes suivies par l’individu. Pour les événements, la payload est affichée.
* _actionExecutionErrors_ : informations sur les erreurs qui se sont produites.

Les différents statuts du parcours d’un individu sont les suivants :

* _En cours_ : l’individu figure actuellement dans le parcours.
* _Terminé_ : l’individu a atteint la fin du parcours.
* _Erreur_ : le parcours de l’individu a été arrêté en raison d’une erreur.
* _Délai dépassé_ : le parcours de l’individu a été arrêté, car l’exécution d’une étape a pris trop de temps.
