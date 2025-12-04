---
product: adobe campaign
title: inSegment
description: En savoir plus sur la fonction inSegment
feature: Journeys
role: Developer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 100%

---

# inSegment {#inSegment}

Vérifie si un individu appartient à un segment donné.

>[!NOTE]
>
>Vous pouvez récupérer jusqu’à 100 segments.

Le nom du segment doit être une constante sous forme de chaîne. Il ne peut pas s’agir d’une référence de champ ni d’une expression.

Les segments sont définis dans [Adobe Experience Platform](https://platform.adobe.com/segment/overview). L’éditeur d’expression fournit une liste des segments avec saisie semi-automatique .

Les segments peuvent posséder trois statuts :

* existing : lʼentité reste dans le segment.
* realized : lʼentité entre dans le segment.
* exited : lʼentité quitte le segment.

Seuls les individus présentant les statuts de participation **Réalisé** et **Existant** sont considérés comme membres du segment. Pour plus d&#39;informations sur l&#39;évaluation d&#39;un segment, consultez la [documentation du service de segmentation](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=fr#interpret-segment-results).

`IF inSegment('segmentName') == true` signifie que vous avez un mappage segmentMembership avec le statut « entered/existing ».

`ELSE inSegment('segmentName') == false` signifie que vous avez un mappage segmentMembership avec le statut « exited ».

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
