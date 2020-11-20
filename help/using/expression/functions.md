---
product: adobe campaign
solution: Journey Orchestration
title: Fonctions
description: En savoir plus sur les fonctions
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 100%

---


# Fonctions {#concept_p1r_qj5_dgb}

Une fonction peut avoir différentes signatures (ensemble différent de paramètres ordonnés). Une signature de fonction peut avoir de 0 à N expressions sous la forme de paramètres ordonnés.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Chaque fonction renvoie une valeur de type spécifique.

Voici la liste des fonctions prises en charge :

## Principales fonctions

| Catégorie | Fonction |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| Agrégation | [avg](../functions/functionavg.md) |
| Agrégation | [count](../functions/functioncount.md) |
| Agrégation | [countOnlyNull](../functions/functioncountonlynull.md) |
| Agrégation | [countWithNull](../functions/functioncountwithnull.md) |
| Agrégation | [distinctCount](../functions/functiondistinctcount.md) |
| Agrégation | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Agrégation | [max](../functions/functionmax.md) |
| Agrégation | [min](../functions/functionmin.md) |
| Agrégation | [sum](../functions/functionsum.md) |
| Conversion | [toBool](../functions/functiontobool.md) |
| Conversion | [toDateTime](../functions/functiontodatetime.md) |
| Conversion | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| Conversion | [toDecimal](../functions/functiontodecimal.md) |
| Conversion | [toDuration](../functions/functiontoduration.md) |
| Conversion | [toInteger](../functions/functiontointeger.md) |
| Conversion | [toString](../functions/functiontostring.md) |
| Date | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| Date | [inLastDays](../functions/functioninlastdays.md) |
| Date | [inLastHours](../functions/functioninlasthours.md) |
| Date | [inLastMonths](../functions/functioninlastmonths.md) |
| Date | [inLastYears](../functions/functioninlastyears.md) |
| Date | [inNextDays](../functions/functioninnextdays.md) |
| Date | [inNextHours](../functions/functioninnexthours.md) |
| Date | [inNextMonths](../functions/functioninnextmonths.md) |
| Date | [inNextYears](../functions/functioninnextyears.md) |
| Date | [now](../functions/functionnow.md) |
| Date | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Date | [setHours](../functions/functionsethours.md) |
| Date | [setDays](../functions/functionsetdays.md) |
| Liste | [distinct](../functions/functiondistinct.md) |
| Liste | [distinctCount](../functions/functiondistinctcount.md) |
| Liste | [in](../functions/functionin.md) |
| Liste | [listSize](../functions/functionlistsize.md) |
| Liste | [serializeList](../functions/functionserializelist.md) |
| Liste | [sort](../functions/functionsort.md) |
| Mathématique | [random](../functions/functionrandom.md) |
| Mathématique | [round](../functions/functionround.md) |
| Chaîne | [concat](../functions/functionconcat.md) |
| Chaîne | [contain](../functions/functioncontain.md) |
| Chaîne | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Chaîne | [endWith](../functions/functionendwith.md) |
| Chaîne | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Chaîne | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| Chaîne | [indexOf](../functions/functionindexof.md) |
| Chaîne | [isEmpty](../functions/functionisempty.md) |
| Chaîne | [isNotEmpty](../functions/functionisnotempty.md) |
| Chaîne | [lastIndexOf](../functions/functionlastindexof.md) |
| Chaîne | [length](../functions/functionlength.md) |
| Chaîne | [lower](../functions/functionlower.md) |
| Chaîne | [matchRegExp](../functions/functionmatchregexp.md) |
| Chaîne | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| Chaîne | [replace](../functions/functionreplace.md) |
| Chaîne | [replaceAll](../functions/functionreplaceall.md) |
| Chaîne | [startWith](../functions/functionstartwith.md) |
| Chaîne | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Chaîne | [substr](../functions/functionsubstr.md) |
| Chaîne | [trim](../functions/functiontrim.md) |
| Chaîne | [upper](../functions/functionupper.md) |
| Chaîne | [uuid](../functions/functionuuid.md) |