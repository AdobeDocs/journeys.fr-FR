---
title: Instruction conditionnelle (if, then, else)
description: En savoir plus sur l’instruction conditionnelle
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 100%

---


# Instruction conditionnelle (if, then, else) {#section_cdz_lsk_w3b}

L’instruction conditionnelle (if, then, else) est prise en charge dans l’éditeur avancé. Elle permet de définir des expressions plus complexes. Elle se compose des éléments suivants :

* **[!UICONTROL If]** : condition à évaluer en premier.
* **[!UICONTROL then]** : expression à évaluer au cas où le résultat de l’évaluation de la condition serait vrai.
* **[!UICONTROL else]** : expression à évaluer au cas où le résultat de l’évaluation de la condition serait faux.

>[!NOTE]
>
>Toutes les expressions doivent être mises entre parenthèses.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` doit renvoyer une valeur **booléenne**.

`<expression2>` et `<expression3>` doit avoir le même type ou des types compatibles. Les signatures prises en charge et les types renvoyés sont les suivants :

```
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Utilisation**

L’instruction conditionnelle vous permet d’optimiser le workflow de parcours en réduisant le nombre d’activités de condition. Vous pouvez, par exemple, spécifier dans la même activité d’action, deux options pour une définition de champ en utilisant une seule expression de condition.

Exemple pour une activité d’action (pour un champ qui attend une chaîne comme résultat de l’instruction conditionnelle) :

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
