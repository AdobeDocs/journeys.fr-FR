---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: En savoir plus sur la fonction nowWithDelta
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 86%

---


# nowWithDelta {#nowWithDelta}

Renvoie la date et l’heure actuelles, ainsi qu’un décalage. Si un identifiant de fuseau horaire est spécifié, le décalage de fuseau horaire est appliqué. For more information on data types, refer to [this page](../expression/data-types.md).

## Catégorie

Date

## Syntaxe de la fonction

`nowWithDelta(<parameters>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| delta | valeur entière positive ou négative |
| partie de date | années, mois, jours, heures, minutes ou secondes sous forme de chaîne |
| identifiant de fuseau horaire | Représentation, sous forme de chaîne, de la valeur du fuseau horaire. Pour plus d’informations, voir Types [de](../expression/data-types.md)données. L’identifiant de fuseau horaire doit être une constante sous forme de chaîne. Il ne peut pas s’agir d’une référence de champ ni d’une expression. |

## Signatures et type renvoyé

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Renvoie une valeur dateTime.

## Exemples

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Renvoie une valeur dateTime il y a exactement 2 heures.
