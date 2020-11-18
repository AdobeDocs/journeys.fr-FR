---
title: Passage d’un parcours à un autre
description: Passage d’un parcours à un autre
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: 1ec824dcfd54bde5f3aab80ce30dbc9a19b9e4c1
workflow-type: ht
source-wordcount: '758'
ht-degree: 100%

---


# Passage d’un parcours à un autre {#jump}

>[!NOTE]
>
>Disponibilité effective : 15 novembre 2020

L’activité d’action **Saut** permet d’inviter des individus à passer d’un parcours à un autre. Cette fonctionnalité permet d’effectuer les opérations suivantes :

* simplifier la conception de parcours très complexes en les divisant en plusieurs autres ;
* créer des parcours basés sur des schémas de parcours communs et réutilisables.

Dans le parcours d’origine, il suffit d’ajouter un **saut** et de sélectionner un parcours cible. Lorsque l’individu parvient à l’étape de saut, un événement interne est envoyé au premier événement du parcours cible. Si l’action de saut réussit, l’individu continue à progresser dans le parcours. Le comportement est similaire aux autres actions.

Dans le parcours cible, le premier événement déclenché en interne par le saut permettra à chaque individu de s’insérer dans le parcours.

## Cycle de vie

Supposons que vous ayez ajouté un saut d’un parcours A à un parcours B. Le parcours A est le **parcours d’origine** et le parcours B, le **parcours cible**.
Voici les différentes étapes du processus d’exécution :

Le **parcours A** est déclenché par un événement externe :

1. Le parcours A reçoit un événement externe lié à un individu.
1. L’individu atteint l’étape du saut.
1. L’individu est amené au parcours B et passe aux étapes suivantes du parcours A, suite au saut.

Dans le **parcours B**, le premier événement peut être déclenché à l’extérieur (comme un événement ordinaire) ou à l’intérieur, par un saut depuis le parcours A :

1. Le parcours B a reçu un événement interne du parcours A.
1. Le premier événement du parcours B est déclenché par les informations issues du parcours A.
1. L’individu commence à effectuer le parcours B.

## Remarques importantes

* Vous ne pouvez accéder qu’à un parcours qui utilise le même espace de noms que le parcours d’origine.
* Vous ne pouvez pas accéder à un parcours commençant par un événement de **qualification de segment**.
* Lorsque le saut est exécuté, la dernière version du parcours cible est déclenchée.
* Vous pouvez inclure autant de sauts que nécessaire dans un parcours. Après un saut, vous pouvez ajouter toutes les activités nécessaires.
* Vous pouvez avoir autant de niveaux de saut que nécessaire. Par exemple, le parcours A passe au parcours B, qui passe au parcours C, etc.
* Le parcours cible peut également comporter autant de sauts que nécessaire.
* Les schémas de boucle ne sont pas pris en charge. Il n’y a aucun moyen de relier deux parcours, ou plus, qui créeraient une boucle infinie. L’écran de configuration de l’activité **Saut** vous empêche de le faire.
* Comme à l’accoutumée, un individu donné ne peut être présent qu’une seule fois dans un même parcours. Ainsi, si un individu provenant d’un parcours d’origine est déjà engagé dans le parcours cible, il ne rejoindra pas le parcours cible. Aucune erreur ne sera signalée lors du saut, car il s’agit d’un comportement normal.

## Configuration du saut

1. Concevez votre parcours d’origine.

   ![](../assets/jump1.png)

1. À chaque étape du parcours, ajoutez une activité **Saut**, depuis la catégorie **Action**. Ajoutez un libellé et une description.

   ![](../assets/jump2.png)

1. Cliquez dans le champ **Parcours cible**.
La liste contient toutes les versions de parcours en version brouillon, version active ou en mode test. Les parcours qui utilisent un autre espace de noms ou commençant par un événement de **qualification de segment** ne sont pas disponibles. Les parcours cible qui créeraient un schéma de boucle sont également filtrés.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Vous pouvez cliquer sur l’icône **Ouvrir le parcours cible**, sur le côté droit, pour ouvrir le parcours cible dans un nouvel onglet.

1. Sélectionnez le parcours cible auquel vous souhaitez accéder.
Le champ **Premier événement** est prérenseigné avec le nom du premier événement du parcours cible. Si votre parcours cible comporte plusieurs événements, le saut n’est autorisé que pour le premier.

   ![](../assets/jump4.png)

1. La section **Paramètres d’action** affiche tous les champs de l’événement cible. De la même manière que pour les autres types d’actions, mappez chaque champ avec les champs de l’événement ou de la source de données d’origine. Ces informations seront transmises au parcours cible au moment de l’exécution.
1. Ajoutez les activités suivantes pour terminer le parcours d’origine.

   ![](../assets/jump5.png)

Votre saut est configuré. Dès que votre parcours est actif ou en mode test, les individus qui atteignent le saut sont amenés au parcours cible.

Lorsqu’un saut est configuré dans un parcours, une icône d’entrée de saut est automatiquement ajoutée au début du parcours cible. Vous pouvez ainsi identifier que le parcours peut être déclenché depuis l’extérieur mais aussi en interne par le biais d’un saut.

## Résolution des problèmes

Lorsque le parcours est publié ou en mode test, des erreurs se produisent dans les cas suivants :
* le parcours cible n’existe plus ;
* le parcours cible est en version brouillon, fermé ou arrêté ;
* le premier événement du parcours cible a changé et le mappage est interrompu.
