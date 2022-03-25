---
product: adobe campaign
title: Opérateurs
description: En savoir plus sur les opérateurs dans les expressions avancées
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: a0b6ab595bc16a75aa5a56a858900418e2381ab9
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 100%

---

# Opérateurs {#concept_wd5_pj5_dgb}

Il existe deux types d’opérateurs : unaires et binaires. Les opérateurs unaires sont répartis en deux catégories : gauche et droite.

```json
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

## Remarques importantes{#important-notes}

* Lors de l’utilisation d’une multiplication (`*`), les deux champs d’opération doivent avoir le même type, entier ou décimal. Exemple :
   * L’exemple suivant est correct :`3.0 * 4.0`
   * `3 * 4.0` entraîne une erreur

## Logique  {#logical}

### and

```json
<expression1> and <expression2>
```

&lt;expression1> et &lt;expression2> doivent être booléens. Le résultat est booléen.

Exemple :

```json
3.14 > 2 and 3.15 < 1
```

### or



```json
<expression1> or <expression2>
```

&lt;expression1> et &lt;expression2> doivent être booléens. Le résultat est booléen.

Exemple :

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> doit être booléen. Le résultat est booléen.

Exemple :

```json
not 3.15 < 1
```

## Comparaison {#comparison}

### est nul



```json
<expression> is null
```

Le résultat est booléen.

Notez que null signifie que l’expression n’a pas de valeur évaluée.

Exemple :

```json
@{BarBeacon.location} is null
```

### n’est pas nul



```json
<expression> is not null
```

Le résultat est booléen.

Notez que null signifie que l’expression n’a pas de valeur évaluée.

Exemple :

```json
@ is not null
```

### est nul



```json
<expression> has null
```

&lt;expression> doit être une liste. Le résultat est booléen.

Utile pour identifier qu’une liste contient au moins une valeur « null ».

Exemple :

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

&lt;expression1> et &lt;expression2> doivent avoir le même type de données. Le résultat est booléen.

Exemple :

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

&lt;expression1> et &lt;expression2> doivent avoir le même type de données. Le résultat est booléen.

Exemple :

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

Exemple :

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

Exemple :

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

Exemple :

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Il est possible de comparer une valeur Datetime à une autre valeur Datetime.

Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.

Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.

Toute autre combinaison est interdite.

Le résultat est booléen.

Exemple :

```json
42 <= 3.14
```

## Arithmétique {#arithmetic}

### +



```json
<expression1> + <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

Exemple :

```json
1 + 2 -- returns 3
```

### -



```json
<expression1> - <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

Exemple :

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

&lt;expression2> ne doit pas être égale à 0 (renvoie 0).

Exemple :

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

Exemple :

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Les deux expressions doivent être numériques (nombres entiers ou décimaux).

Le résultat est également numérique.

Exemple :

```json
3 % 2 -- returns 1.
```

## Math {#math}

### est numérique



```json
<expression> is numeric
```

Le type d’expression est entier ou décimal.

Exemple :

```json
@ is numeric
```

### est un entier



```json
<expression> is integer
```

Le type d’expression est entier.

Exemple :

```json
@ is integer
```

### est décimal



```json
<expression> is decimal
```

Le type d’expression est décimal.

Exemple :

```json
@ is decimal
```

## Chaîne {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

Cet opérateur concatène deux expressions.

L’une des expressions doit être une chaîne de caractères.

Exemple :

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Date {#date}

### +



```json
<expression> + <duration>
```

Permet d’ajouter une durée à une valeur dateTimeOnly ou à une durée.

Exemple :

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
