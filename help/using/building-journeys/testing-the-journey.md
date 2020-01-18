---
title: Test du parcours
description: 'En savoir plus sur les tests de parcours '
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
source-git-commit: a0ab3528b090e34867d54174421741c689e378e7

---


# Test du parcours{#testing_the_journey}

Avant de pouvoir tester votre voyage, vous devez résoudre toutes les erreurs éventuelles. Voir la section [](../about/troubleshooting.md#section_h3q_kqk_fhb).

Vous avez la possibilité de tester votre voyage avant sa publication, en utilisant des profils de test. Cela vous permet d’analyser le flux des individus dans le parcours et de résoudre les problèmes avant la publication.

>[!NOTE]
>
>En mode test, toutes les activités d’attente sont automatiquement configurées pour durer 5 secondes. Vous pouvez ainsi accéder rapidement aux résultats du test.

Pour utiliser le mode test, procédez comme suit :

1. Avant de tester votre voyage, vérifiez qu’il est valide et qu’il n’y a aucune erreur. Vous ne pourrez pas lancer un test d’un voyage avec des erreurs. Voir la section [](../about/troubleshooting.md#section_h3q_kqk_fhb). Un symbole d’avertissement s’affiche en cas d’erreur.

1. Pour activer le mode test, cliquez sur la bascule **[!UICONTROL Test]**située dans le coin supérieur droit.

   ![](../assets/journeytest1.png)

1. Cliquez sur **[!UICONTROL Déclencher un événement]**pour configurer et envoyer des événements au voyage. Veillez à envoyer des événements liés aux profils de test. Voir[déclenchement de vos événements](#firing_events).

   ![](../assets/journeyuctest1.png)

1. Une fois les événements reçus, cliquez sur le bouton **[!UICONTROL Afficher le journal]**pour afficher le résultat du test et les vérifier. Voir[Affichage des journaux](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. En cas d’erreur, désactivez le mode test, modifiez votre voyage et testez-le à nouveau. Lorsque le test est concluant, vous pouvez publier votre voyage. Voir la section [](../building-journeys/publishing-the-journey.md).

## Remarques importantes {#important_notes}

* Une interface est fournie pour déclencher les événements jusqu&#39;au voyage testé, mais les événements peuvent également être envoyés par des systèmes tiers tels que Postman.
* Seules les personnes identifiées comme &quot;profils de test&quot; dans le service de profil client en temps réel seront autorisées à participer au voyage testé. Le processus de création d’un profil de test est identique à celui de création d’un profil dans la plateforme de données. Vous devez juste vous assurer que l&#39;indicateur de profil de test est vrai. Vous pouvez utiliser la section Segments de l’interface de la plateforme de données pour créer un segment de profils de test dans votre plateforme de données et afficher une liste non exhaustive. La liste exhaustive ne peut pas être affichée pour l&#39;instant.
* Le mode test est disponible uniquement dans les brouillons de voyages qui utilisent un espace de noms. En effet, le mode test doit vérifier si une personne qui entre dans le voyage est un profil test ou non et doit donc être en mesure d’atteindre la plateforme de données.
* Le nombre maximal de profils de test pouvant entrer dans un voyage au cours d’une session de test est de 100.
* Lorsque vous désactivez le mode test, il vide les voyages de toutes les personnes qui y sont entrées dans le passé ou qui y sont actuellement.
* Vous pouvez activer/désactiver le mode test autant de fois que nécessaire.
* Vous ne pouvez pas modifier votre voyage lorsque le mode test est activé. En mode test, vous pouvez publier directement le voyage, sans avoir à désactiver le mode test auparavant.

## Démarrage de vos événements {#firing_events}

Le bouton **[!UICONTROL Déclencher un événement]**vous permet de configurer un événement qui fera entrer une personne dans le voyage.

En tant que prérequis, vous devez savoir quels profils sont marqués comme profils de test dans la plateforme de données. En effet, le mode test n’autorise ces profils que dans le parcours et l’événement doit contenir un identifiant. L’ID attendu dépend de la configuration de l’événement. Il peut s&#39;agir d&#39;un ECID, par exemple.

Cet écran vous permet de configurer les champs transmis dans l’événement et l’exécution de l’envoi d’événement. L’interface vous permet de transmettre les informations appropriées dans la charge utile de l’événement et de vous assurer que le type d’information est correct. Le mode test enregistre les derniers paramètres utilisés dans une session de test pour une utilisation ultérieure.

![](../assets/journeytest4.png)

L&#39;interface vous permet de transmettre des paramètres d&#39;événement simples. Si vous souhaitez transmettre des collections ou d’autres objets avancés dans l’événement, vous pouvez cliquer sur Affichage **[!UICONTROL du]**code pour voir l’intégralité du code de la charge utile et le modifier. Vous pouvez, par exemple, copier et coller des informations d’événement préparées par un utilisateur technique.

![](../assets/journeytest5.png)

Un utilisateur technique peut également utiliser cette interface pour composer des charges d’événement et déclencher des événements sans avoir à utiliser un outil tiers.

## Affichage des journaux {#viewing_logs}

Le bouton **[!UICONTROL Afficher le journal]**vous permet d’afficher les résultats du test. Cette page affiche les informations actuelles du voyage au format JSON. Un bouton permet de copier des noeuds entiers. Vous devez actualiser manuellement la page pour mettre à jour les résultats du test du voyage.

![](../assets/journeytest3.png)

Le nombre d’individus (techniquement, ils sont appelés instances) actuellement à l’intérieur du voyage s’affiche. Voici des informations utiles qui s’affichent pour chaque individu :

* _Id_: l’ID interne de l’individu dans le parcours. Cela peut être utilisé à des fins de débogage.
* _current_: l&#39;étape où l&#39;individu est dans le voyage. Nous vous recommandons d’ajouter des étiquettes à vos activités afin de les identifier plus facilement.
* _current_ > phase : l’état du parcours de l’individu (exécution, achèvement, erreur ou expiration). Voir ci-dessous pour plus d’informations.
* _current_ > _extraInfo_: description de l’erreur et d’autres informations contextuelles.
* _externalKeys_: valeur de la formule clé définie dans l’événement.
* _enrichissementData_: les données que le voyage a récupérées si le voyage utilise des sources de données.
* _transitionHistory_: liste des étapes suivies par l&#39;individu. Pour les événements, la charge utile s’affiche.

