---
product: adobe campaign
title: nowWithDelta
description: En savoir plus sur la fonction nowWithDelta
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '110'
ht-degree: 100%

---

# nowWithDelta {#nowWithDelta}

Renvoie la date et l’heure actuelles, ainsi qu’un décalage. Si un identifiant de fuseau horaire est spécifié, le décalage de fuseau horaire est appliqué. Pour plus d’informations sur les types de données, consultez [cette page](../expression/data-types.md).

## Catégorie

Date

## Syntaxe de la fonction

`nowWithDelta(<parameters>)`

## Paramètres

| Paramètre | Description |
|--- |--- |
| delta | valeur entière positive ou négative |
| partie de date | années, mois, jours, heures, minutes ou secondes sous forme de chaîne |
| identifiant de fuseau horaire | Représentation, sous forme de chaîne, de la valeur du fuseau horaire. Pour en savoir plus, voir [Types de données](../expression/data-types.md). L’identifiant de fuseau horaire doit être une constante sous forme de chaîne. Il ne peut pas s’agir d’une référence de champ ni d’une expression. |

## Signatures et type renvoyé

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Renvoie une valeur dateTime.

## Exemples

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Renvoie une valeur dateTime il y a exactement 2 heures.
