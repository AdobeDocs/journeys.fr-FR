---
title: inSegment
description: En savoir plus sur la fonction inSegment
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# inSegment {#inSegment}

Vérifie si une personne appartient à un segment donné.

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

La fonction renvoie **[!UICONTROL true]** si la personne concernée par l’instance de parcours figure dans le segment de plate-forme « men over 50 » (hommes de plus de 50 ans), **[!UICONTROL false]** dans le cas contraire.
