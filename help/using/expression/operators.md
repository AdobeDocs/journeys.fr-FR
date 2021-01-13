---
product: adobe campaign
solution: Journey Orchestration
title: Opérateurs
description: En savoir plus sur les opérateurs dans les expressions avancées
translation-type: ht
source-git-commit: 062b4648e2eb3a4270f9c09e4478d541209e1247
workflow-type: ht
source-wordcount: '435'
ht-degree: 100%

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

## Logique    {#logical}

### et

```
<expression1> and <expression2>
```

&lt;expression1> et &lt;expression2> doivent être booléens. Le résultat est booléen.

Exemple :

```
3.14 > 2 and 3.15 < 1
```

### ou



```
<expression1> or <expression2>
```

&lt;expression1> et &lt;expression2> doivent être booléens. Le résultat est booléen.

Exemple :

```
3.14 > 2 or 3.15 < 1
```

### pas



```
not <expression>
```

&lt;expression> doit être booléen. Le résultat est booléen.

Exemple :

```
not 3.15 < 1
```

## Comparaison {#comparison}

### est nul



```
<expression> is null
```

Le résultat est booléen.

Notez que null signifie que l’expression n’a pas de valeur évaluée.

Exemple :

```
@{BarBeacon.location} is null
```

### n’est pas nul



```
<expression> is not null
```

Le résultat est booléen.

Notez que null signifie que l’expression n’a pas de valeur évaluée.

Exemple :

```
@ is not null
```

### est nul



```
<expression> has null
```

&lt;expression> doit être une liste. Le résultat est booléen.

Utile pour identifier qu’une liste contient au moins une valeur « null ».

Exemple :

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

&lt;expression1> et &lt;expression2> doivent avoir le même type de données. Le résultat est booléen.

Exemple :

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

&lt;expression1> et &lt;expression2> doivent avoir le même type de données. Le résultat est booléen.

Exemple :

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

Exemple :

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

Exemple :

```
42 >= 3.14
```

### &lt;



```
<expression1> < <expression2>
```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

Exemple :

```
42 < 3.14
```

### &lt;=



```
<expression1> <= <expression2>
```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

Exemple :

```
42 <= 3.14
```

## Arithmétique {#arithmetic}

### +



```
<expression1> + <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

Exemple :

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

Exemple :

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

&lt;expression2> ne doit pas être égale à 0 (renvoie 0).

Exemple :

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

Exemple :

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

Exemple :

```
3 % 2 -- returns 1.
```

## Mathématiques {#math}

### est numérique



```
<expression> is numeric
```

Le type d’expression est entier ou décimal.

Exemple :

```
@ is numeric
```

### est un entier



```
<expression> is integer
```

Le type d’expression est entier.

Exemple :

```
@ is integer
```

### est décimal



```
<expression> is decimal
```

Le type d’expression est décimal.

Exemple :

```
@ is decimal
```

## Chaîne {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

Cet opérateur concatène deux expressions.

L’une des expressions doit être une chaîne de caractères.

Exemple :

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Date {#date}

### +



```
<expression + <duration>
```

Permet d’ajouter une durée à une valeur dateTimeOnly ou à une durée.

Exemple :

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
