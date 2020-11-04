---
title: Passer d'un voyage à un autre
description: Passer d'un voyage à un autre
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 1ec824dcfd54bde5f3aab80ce30dbc9a19b9e4c1
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Passer d&#39;un voyage à un autre {#jump}

>[!NOTE]
>
>Disponibilité efficace : 15 novembre 2020

L&#39;activité **Jump** action vous permet de pousser des individus d&#39;un voyage à l&#39;autre. Cette fonctionnalité vous permet d’effectuer les opérations suivantes :

* simplifier la conception de voyages très complexes en les divisant en plusieurs
* créer des voyages basés sur des schémas de voyage communs et réutilisables

Dans le parcours d&#39;origine, il vous suffit d&#39;ajouter un **Jump** et de sélectionner un parcours de cible. Lorsque l&#39;individu entre dans l&#39;étape de saut, un événement interne est envoyé au premier événement du parcours de cible. Si l&#39;action de saut réussit, l&#39;individu continue à progresser dans le parcours. Le comportement est similaire aux autres actions.

Dans le parcours de cible, le premier événement déclenché en interne par le saut fera couler chaque individu dans le parcours.

## Cycle de vie

Supposons que vous ayez ajouté un saut dans un voyage A à un voyage B. Le voyage A est le voyage **d&#39;** origine et le voyage B, le voyage **de**cible.
Voici les différentes étapes du processus d’exécution :

**Le voyage A** est déclenché par un événement externe :

1. Le voyage A reçoit un événement externe lié à un individu.
1. L&#39;individu atteint le pas de saut.
1. L&#39;individu est poussé au voyage B, et passe aux étapes suivantes du voyage A, après le saut.

Dans le **voyage B**, le premier événement peut être déclenché à l&#39;extérieur (comme un événement ordinaire) ou à l&#39;intérieur, par un saut du voyage A :

1. Le voyage B a reçu un événement interne du voyage A.
1. Le premier événement du voyage B est déclenché par les informations provenant du voyage A.
1. Les débuts individuels qui circulent dans le voyage B.

## Remarques importantes              

* Vous ne pouvez sauter qu&#39;à un voyage qui utilise le même espace de nommage que le voyage d&#39;origine.
* Vous ne pouvez pas accéder directement à un voyage qui début avec un événement de qualification **de** segment.
* Lorsque le saut est exécuté, la dernière version du parcours de cible est déclenchée.
* Vous pouvez inclure autant de sauts que nécessaire dans un voyage. Après un saut, vous pouvez ajouter toute activité nécessaire.
* Vous pouvez avoir autant de niveaux de sauts que nécessaire. Par exemple, le voyage A passe au voyage B, qui passe au voyage C, etc.
* Le parcours de cible peut également inclure autant de sauts que nécessaire.
* Les modèles de boucle ne sont pas pris en charge. Il n&#39;y a aucun moyen de relier deux ou plusieurs voyages ensemble qui créeraient une boucle infinie. L’écran de configuration de l’activité **Jump** vous empêche de procéder ainsi.
* Comme d&#39;habitude, un individu unique ne peut être présent qu&#39;une seule fois dans un même voyage. Par conséquent, si l&#39;individu repoussé du voyage d&#39;origine est déjà dans le voyage de cible, l&#39;individu n&#39;entrera pas dans le voyage de cible. Aucune erreur ne sera signalée lors du saut car il s&#39;agit d&#39;un comportement normal.

## Configuration du saut

1. Concevez votre voyage d&#39;origines.

   ![](../assets/jump1.png)

1. À chaque étape du voyage, ajoutez une **activité de vidage** , à partir de la catégorie **Action** . Ajoutez une étiquette et une description.

   ![](../assets/jump2.png)

1. Cliquez dans le champ **Cible voyage** .
La liste affiche toutes les versions de voyage qui sont en version préliminaire, en direct ou en mode test. Les voyages qui utilisent un autre espace de nommage ou un début avec un événement de qualification **** Segment ne sont pas disponibles. Les voyages de cible qui créeraient un modèle de boucle sont également filtrés.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Vous pouvez cliquer sur l&#39;icône **Ouvrir la cible du voyage** , sur le côté droit, pour ouvrir le parcours de cible dans un nouvel onglet.

1. Sélectionnez le parcours de cible auquel vous souhaitez passer.
Le champ **Premier événement** est prérempli avec le nom du premier événement du parcours de cible. Si votre parcours de cible comporte plusieurs événements, le saut n&#39;est autorisé que le premier événement.

   ![](../assets/jump4.png)

1. La section Paramètres **** d&#39;action affiche tous les champs du événement de cible. De la même manière que pour les autres types d’actions, mappez chaque champ avec les champs du événement d’origine ou de la source de données. Ces informations seront transmises au parcours de cible au moment de l’exécution.
1. Ajoutez les prochaines activités pour terminer votre parcours d&#39;origine.

   ![](../assets/jump5.png)

Votre saut est configuré. Dès que votre voyage est en direct ou en mode test, les personnes qui atteignent le saut seront poussées du voyage à la cible.

Lorsqu’un saut est configuré dans un voyage, une icône d’entrée de saut est automatiquement ajoutée au début du parcours de cible. Cela vous permet d’identifier que le voyage peut être déclenché à l’extérieur mais aussi en interne par un saut.

## Résolution des problèmes

Lorsque le parcours est publié ou en mode test, des erreurs se produisent si :
* le parcours de cible n&#39;existe plus
* le parcours de cible est brouillon, fermé ou arrêté
* si le premier événement du parcours de la cible a changé et si la correspondance est interrompue
