---
title: Modification des propriétés
description: Découvrez comment modifier les propriétés
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---



# Modification des propriétés {#concept_prq_wqt_52b}

Cliquez sur l&#39;icône en forme de crayon, dans la partie supérieure droite pour accéder aux propriétés du voyage.

Vous pouvez modifier le nom du parcours, ajouter une description, autoriser une nouvelle entrée, choisir les dates de début et de fin et définir un **[!UICONTROL délai d’expiration et une durée d’erreur]**si vous êtes administrateur.

![](../assets/journey32.png)

## Entrée{#entrance}

Par défaut, les nouveaux voyages permettent la réadmission. Vous pouvez désélectionner l’option pour les voyages &quot;à un seul coup&quot;, par exemple si vous souhaitez offrir un cadeau unique lorsqu’une personne entre dans une boutique. Dans ce cas, vous ne souhaitez pas que le client puisse reprendre le voyage et recevoir à nouveau l’offre.

Lorsqu&#39;un voyage &quot;se termine&quot;, il aura le statut **[!UICONTROL Terminé]**. Le voyage cessera de laisser de nouveaux individus entrer dans le voyage. Les personnes déjà en voyage finiront le voyage normalement.

## Délai et erreur dans les activités de voyage {#timeout_and_error}

Lorsque vous modifiez une action ou une activité de condition, vous pouvez définir un autre chemin en cas d’erreur ou d’expiration. Si le traitement de l’activité qui interroge un système tiers dépasse la durée d’expiration définie dans les propriétés du parcours (champ **[!UICONTROL Délai d’expiration et erreur]**), le deuxième chemin est choisi pour effectuer une action de secours potentielle.

Les valeurs autorisées sont comprises entre 1 et 30 secondes.

Nous vous recommandons de définir une valeur de **[!UICONTROL dépassement de délai et d’erreur]**très courte si votre voyage est sensible au temps (par exemple : Réaction à l’emplacement en temps réel d’une personne) car vous ne pouvez pas retarder votre action de plus de quelques secondes. Si votre voyage est moins sensible au temps, vous pouvez utiliser une valeur plus longue pour donner plus de temps au système appelé pour envoyer une réponse valide.

L&#39;orchestration de Journey utilise également un délai d&#39;attente global. See the [next section](#global_timeout).

## Délai de voyage global {#global_timeout}

Outre le [délai d’expiration](#timeout_and_error) utilisé dans les activités de voyage, il existe également un délai d’expiration global du voyage qui n’est pas affiché dans l’interface et ne peut pas être modifié. Ce délai d&#39;attente mettra fin à la progression des individus dans le voyage 30 jours après leur entrée. Cela signifie que le voyage d&#39;un individu ne peut pas durer plus de 30 jours. Après le délai d’expiration de 30 jours, les données de l’individu sont supprimées. Les personnes qui circulent encore au cours du voyage à la fin de la période d&#39;attente seront arrêtées et elles seront prises en compte comme des erreurs dans les rapports.

>[!NOTE]
>
>Journey Orchestration ne réagit pas directement aux demandes d’exclusion, d’accès ou de suppression de confidentialité. Cependant, le délai d&#39;attente global garantit que les individus ne restent jamais plus de 30 jours dans un voyage.

En raison du délai d&#39;attente de 30 jours, lorsque le retour n&#39;est pas autorisé, nous ne pouvons pas nous assurer que le blocage du retour à l&#39;entrée fonctionne plus de 30 jours. En effet, lorsque nous supprimons toutes les informations sur les personnes qui sont entrées dans le voyage 30 jours après leur arrivée, nous ne pouvons pas connaître la personne qui est entrée précédemment, il y a plus de 30 jours.
