---
title: Instruction conditionnelle (si, alors, sinon)
description: En savoir plus sur l’instruction conditionnelle
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Instruction conditionnelle (si, alors, sinon) {#section_cdz_lsk_w3b}

L’instruction conditionnelle (si, alors, elle est prise en charge) est prise en charge dans l’éditeur avancé. Il permet de définir des expressions plus complexes. Il se compose des éléments suivants :

* **[!UICONTROL if]**: la condition à évaluer en premier.
* **[!UICONTROL puis]**: l’expression à évaluer au cas où le résultat de l’évaluation de la condition serait vrai.
* **[!UICONTROL else]**: l’expression à évaluer au cas où le résultat de l’évaluation de la condition serait faux.

>[!NOTE]
>
>Des parenthèses sont requises autour de toutes les expressions.

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` doit renvoyer une valeur **booléenne**.

`<expression2>` et `<expression3>` doit avoir le même type ou les mêmes types compatibles. Les signatures prises en charge et les types renvoyés sont les suivants :

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

**Usage**

L’instruction conditionnelle vous permet d’optimiser le processus de voyage en réduisant le nombre d’activités de condition. Par exemple, dans la même activité d’action, vous pouvez spécifier deux alternatives pour une définition de champ à l’aide d’une seule expression de condition.

Exemple pour une activité d’action (pour un champ qui attend une chaîne du résultat de l’instruction conditionnelle) :

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
