---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: En savoir plus sur la fonction inSegment
feature: Parcours
role: Ingénieur de données
level: Expérimenté
translation-type: ht
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: ht
source-wordcount: '155'
ht-degree: 100%

---


# inSegment {#inSegment}

Vérifie si un individu appartient à un segment donné.

>[!NOTE]
>
>Vous pouvez récupérer jusqu’à 100 segments.

Le nom du segment doit être une constante sous forme de chaîne. Il ne peut pas s’agir d’une référence de champ ni d’une expression.

Les segments sont définis dans [Adobe Experience Platform](https://platform.adobe.com/segment/overview). L’éditeur d’expression fournit une liste des segments avec saisie semi-automatique .

>[!NOTE]
>
>Seuls les individus présentant les statuts de participation **Réalisé** et **Existant** sont considérés comme membres du segment. Pour plus d’informations sur l’évaluation d’un segment, consultez la [documentation du service de segmentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=fr#interpret-segment-results).

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
