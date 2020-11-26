---
product: adobe campaign
solution: Journey Orchestration
title: Opérateurs
description: En savoir plus sur les opérateurs dans les expressions avancées
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 83%

---



# Opérateurs {#concept_wd5_pj5_dgb}

Il existe deux types d’opérateurs : unaires et binaires. Les opérateurs unaires sont répartis en deux catégories : gauche et droite.

```
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

Voici la liste des opérateurs pris en charge :

## Logique  {#logical}

### et

**Expression littérale**

```<expression1> and <expression2>```

&lt;expression1> et &lt;expression2> doivent être booléens. Le résultat est booléen.

**Exemple**

```3.14 > 2 and 3.15 < 1```

### ou

**Expression littérale**

```<expression1> or <expression2>```

&lt;expression1> et &lt;expression2> doivent être booléens. Le résultat est booléen.

**Exemple**

```3.14 > 2 or 3.15 < 1```

### not

**Expression littérale**

```not <expression>```

&lt;expression> doit être booléen. Le résultat est booléen.

**Exemple**

```not 3.15 < 1```

## Comparaison {#comparison}

### is null

**Expression littérale**

```<expression> is null```

Le résultat est booléen.

Notez que null signifie que l’expression n’a pas de valeur évaluée.

**Exemple**

```@{BarBeacon.location} is null```

### is not null

**Expression littérale**

```<expression> is not null```

Le résultat est booléen.

Notez que null signifie que l’expression n’a pas de valeur évaluée.

**Exemple**

```@ is not null```

### has null

**Expression littérale**

```<expression> has null```

&lt;expression> doit être une liste. Le résultat est booléen.

Utile pour identifier qu’une liste contient au moins une valeur « null ».

**Exemple**

```["foo", "bar", null] has null``` renvoie true.

```["foo", "bar", ""] has null```Renvoie false car &quot;&quot; n’est pas considéré comme « null ».

### ==

**Expression littérale**

```<expression1> == <expression2>```

&lt;expression1> et &lt;expression2> doivent avoir le même type de données. Le résultat est booléen.

**Exemple**

```3.14 == 42```

```"foo" == "bar"```

### !=

**Expression littérale**

```<expression1> != <expression2>```

&lt;expression1> et &lt;expression2> doivent avoir le même type de données. Le résultat est booléen.

**Exemple**

```3.14 != 42```

```"foo" != "bar"```

### >

**Expression littérale**

```<expression1> > <expression2>```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

**Exemple**

```3.14 > 42```

### >=

**Expression littérale**

```<expression1> >= <expression2>```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

**Exemple**

```42 >= 3.14```

### &lt;

**Expression littérale**

```<expression1> < <expression2>```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

**Exemple**

```42 < 3.14```

### &lt;=

**Expression littérale**

```<expression1> <= <expression2>```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

**Exemple**

```42 <= 3.14```

## Arithmétique {#arithmetic}

### +

**Expression littérale**

```<expression1> + <expression2>```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

**Exemple**

```1 + 2``` renvoie 3

### -

**Expression littérale**

```<expression1> - <expression2>```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

**Exemple**

```2 - 1``` renvoie 1

### /

**Expression littérale**

```<expression1> / <expression2>```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

&lt;expression2> ne doit pas être égale à 0 (renvoie 0).

**Exemple**

```4 / 2``` renvoie 2

### *

**Expression littérale**

```<expression1> * <expression2>```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

**Exemple**

```3 * 4``` renvoie 12

### %

**Expression littérale**

```<expression1> % <expression2>```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

**Exemple**

```3 % 2``` renvoie 1.

## Mathématiques {#math}

### is numeric

**Expression littérale**

```<expression> is numeric```

Expression est de type entier ou décimal.

**Exemple**

```@ is numeric```

### is integer

**Expression littérale**

```<expression> is integer```

Expression est de type entier.

**Exemple**

```@ is integer```

### is decimal

**Expression littérale**

```<expression> is decimal```

Expression est de type décimal.

**Exemple**

```@ is decimal```

## Chaîne {#string}

### +

**Expression littérale**

```<string> + <expression>```

```<expression> + <string>```

Cet opérateur concatène deux expressions.

L’une des expressions doit être une chaîne de caractères.

**Exemple**

```"the current time is " + (now())``` renvoie &quot;l’heure actuelle est 2019-09-23T09:30:06.693Z&quot;

```(now()) + " is the current time"``` renvoie &quot;2019-09-23T09:30:06.693Z est l&#39;heure actuelle&quot;

```"a" + "b" + "c" + 1234``` renvoie &quot;abc1234&quot;.

## Date {#date}

### +

**Expression littérale**

```<expression + <duration>```

Permet d’ajouter une durée à une valeur dateTimeOnly ou à une durée.

**Exemple**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` renvoie 2011-12-03T15:30:30Z

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` renvoie 2011-12-03T15:30:30

```now() + toDuration("PT1H")``` renvoie une dateTime (avec fuseau horaire UTC) une heure après l&#39;heure actuelle

```toDuration("PT1H") + toDuration("PT1H")``` renvoie PT2H
