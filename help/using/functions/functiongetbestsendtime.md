---
title: getBestSendTime
description: En savoir plus sur la fonction getBestSendTime
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

Fournit une heure prédictive du meilleur moment pour envoyer un courriel à une personne.

Cette fonction utilise un score calculé dans la plateforme. Le score calcule la propension à cliquer ou à ouvrir un courrier électronique dans le futur en fonction du comportement passé. Notez que l’algorithme qui calcule le score nécessite une certaine quantité de données pour fonctionner. Par conséquent, lorsque les données sont insuffisantes, l’heure par défaut s’applique. For more information, see [](../building-journeys/wait-activity.md).

Pour utiliser cette fonction, un [espace de noms](../event/selecting-the-namespace.md) est nécessaire.

>[!NOTE]
>
>Notez que le meilleur score de temps d’envoi peut être indisponible s’il n’y a pas assez de données pour effectuer le calcul. Dans ce cas, vous serez informé, au moment de la publication, que l’heure par défaut s’applique.

## Catégorie

Adobe Experience Platform

## Syntaxe de la fonction

`getBestSendTime(<parameters>)`

## Paramètres

| Paramètre | Description | Type |
|--- |--- |--- |
| durée | Nombre d’heures à prendre en compte à partir de l’heure actuelle (max. : 168) pour optimiser l’envoi des courriers électroniques | `<integer>` |
| type d&#39;optimisation | &quot;open&quot; ou &quot;click&quot; | `<string>` |
| temps d’attente par défaut en heures | Au cas où les scores de temps d’envoi prédictif ne seraient pas disponibles | `<integer>` |

## Signature et type renvoyé

`getBestSendTime(<integer>,<string>,<integer>)`

Renvoie une dateTime.

## Exemple 

getBestSendTime(12,&quot;open&quot;,8)

Explication :

La fonction renvoie le meilleur moment pour envoyer un message dans les 12 heures suivantes, afin d&#39;optimiser la probabilité que l&#39;individu de l&#39;instance de voyage l&#39;ouvre. Si les données ne sont pas suffisantes pour effectuer le calcul, l’heure renvoyée est dans 8 heures à partir de l’heure actuelle.
