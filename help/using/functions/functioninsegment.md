---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: En savoir plus sur la fonction inSegment
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 100%

---


# inSegment {#inSegment}

Vérifie si un individu appartient à un segment donné.

Le nom du segment doit être une constante sous forme de chaîne. Il ne peut pas s’agir d’une référence de champ ni d’une expression.

Les segments sont définis dans [Adobe Experience Platform](https://platform.adobe.com/segment/overview). L’éditeur d’expression fournit une liste des segments avec saisie semi-automatique .

>[!NOTE]
>
>Vous pouvez récupérer jusqu’à 100 segments.

## Catégorie

Adobe Experience Platform

## Syntaxe de la fonction

`inSegment(<parameter>)`

## Paramètres

| Paramètre | Description | Type |
|--- |--- |--- |
| Segment | Nom du segment | `<string>` |

## Signature et type renvoyé

`inSegment(<string>)`

Renvoie une valeur booléenne.

## Exemple

`inSegment("men over 50")`

Explication :

La fonction renvoie **[!UICONTROL true]** si l’individu concerné par l’instance de parcours figure dans le segment Adobe Experience Platform « men over 50 » (hommes de plus de 50 ans), **[!UICONTROL false]** dans le cas contraire.
