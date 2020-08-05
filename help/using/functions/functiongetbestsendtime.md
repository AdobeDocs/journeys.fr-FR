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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 95%

---


# getBestSendTime {#getBestSendTime}

Fournit une prédiction de l’heure optimale pour envoyer un email à un individu.

Cette fonction utilise un score calculé dans le Adobe Experience Platform. Le score calcule la propension d’un client à cliquer sur un email ou à l’ouvrir dans le futur en se basant sur son comportement passé. Notez qu’une certaine quantité de données est nécessaire pour que l’algorithme qui calcule le score puisse fonctionner. Par conséquent, lorsque les données sont insuffisantes, l’heure par défaut est appliquée. Pour plus d’informations, reportez-vous à la section [](../building-journeys/wait-activity.md).

Pour utiliser cette fonction, un [espace de noms](../event/selecting-the-namespace.md) est nécessaire.

>[!NOTE]
>
>Notez que le score de l’heure d’envoi optimale peut être indisponible s’il n’y a pas assez de données pour effectuer le calcul. Dans ce cas, vous êtes informé, au moment de la publication, que laps de temps par défaut est appliqué.

## Catégorie

Adobe Experience Platform

## Syntaxe de la fonction

`getBestSendTime(<parameters>)`

## Paramètres

| Paramètre | Description | Type |
|--- |--- |--- |
| Laps de temps | Nombre d’heures à prendre en compte à partir de l’heure actuelle (max. : 168) pour optimiser l’envoi des emails | `<integer>` |
| Type d’optimisation | &quot;open&quot; ou &quot;click&quot; | `<string>` |
| Temps d’attente par défaut en heures | Dans le cas où les scores prédictifs d’horaire d’envoi ne sont pas disponibles | `<integer>` |

## Signature et type renvoyé

`getBestSendTime(<integer>,<string>,<integer>)`

Renvoie une valeur dateTime.

## Exemple 

getBestSendTime(12,&quot;open&quot;,8)

Explication :

La fonction renvoie l’heure optimale pour envoyer un message au cours des 12 heures suivantes afin d’optimiser la probabilité d’ouverture par un individu dans l’instance de parcours. Si les données ne sont pas suffisantes pour effectuer le calcul, l’heure renvoyée sera fixée à 8 heures après l’heure actuelle.
