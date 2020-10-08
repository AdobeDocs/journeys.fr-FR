---
title: Opérateurs
description: En savoir plus sur les opérateurs dans les expressions avancées
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
source-wordcount: '618'
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

## Logique

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale</th><th  >Exemple </th></tr>
</thead>
<tbody>
<tr >&gt;<td>and</td><td><p><pre>&lt;expression1&gt; and &lt;expression2&gt;</pre></p>&lt;expression1&gt; et &lt;expression2&gt; doivent être booléens. Le résultat est booléen.</td><td><pre>3.14 &gt; 2 and 3.15 &lt; 1</pre></td></tr>
<tr ><td>or</td><td><p><pre>&lt;expression1&gt; or &lt;expression2&gt;</pre></p><p>&lt;expression1&gt; et &lt;expression2&gt; doivent être booléens.</p><p> Le résultat est booléen.</p></td><td><p><pre>3.14 &gt; 2 or 3.15 &lt; 1</pre></p></td></tr>
<tr ><td>not</td><td><p><pre>not &lt;expression&gt;</pre></p><p>&lt;expression&gt; doit être booléen.</p><p> Le résultat est booléen.</p></td><td><pre>not 3.15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## Comparaison

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale </th><th  >Exemple</th></tr>
</thead>
<tbody><tr ><td>is null</td><td><p><pre>&lt;expression&gt; is null</pre></p><p>Le résultat est booléen.</p><p>Notez que null signifie que l’expression n’a pas de valeur évaluée.</p></td><td><pre>@{BarBeacon.location} is null</pre></td></tr>
<tr ><td>is not null</td><td><p><pre>&lt;expression&gt; is not null</pre></p><p>Le résultat est booléen.</p><p>Notez que null signifie que l’expression n’a pas de valeur évaluée.</p></td><td><pre>@ is not null</pre></td></tr>
<tr ><td>has null</td><td><p><pre>&lt;expression&gt; has null</pre>&lt;expression&gt; doit être une liste.</p><p>Le résultat est booléen.</p><p>Utile pour identifier qu’une liste contient au moins une valeur « null ».</p></td><td><p><pre>["foo", "bar", null] has null</pre></p>Renvoie true<p><pre>["foo", "bar", ""] has null</pre></p> Renvoie false car "" n’est pas considéré comme « null ».</td></tr>
<tr ><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>&lt;expression1&gt; et &lt;expression2&gt; doivent avoir le même type de données.</p><p> Le résultat est booléen.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> &lt;expression1&gt; et &lt;expression2&gt; doivent avoir le même type de données.</p><p> Le résultat est booléen.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>Il est possible de comparer une valeur Datetime à une autre valeur Datetime.</p><p>Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.</p><p>Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.</p><p>Toute autre combinaison est interdite.</p><p>Le résultat est booléen.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>Il est possible de comparer une valeur Datetime à une autre valeur Datetime.</p><p>Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.</p><p>Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.</p><p>Toute autre combinaison est interdite.</p><p>Le résultat est booléen.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>Il est possible de comparer une valeur Datetime à une autre valeur Datetime.</p><p>Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.</p><p>Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.</p><p>Toute autre combinaison est interdite.</p><p>Le résultat est booléen.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>Il est possible de comparer une valeur Datetime à une autre valeur Datetime.</p><p>Il est possible de comparer une valeur Datetimeonly à une autre valeur Datetimeonly.</p><p>Il est possible de comparer des nombres entiers ou décimaux à d’autres nombres entiers ou décimaux.</p><p>Toute autre combinaison est interdite.</p><p>Le résultat est booléen.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Arithmétique

<table>
<thead>
<tr ><th  >Opérateur</th><th>Expression littérale </th><th  >Exemple</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>Les deux expressions doivent être numériques (nombres entiers ou décimaux). </p><p>Le résultat est également numérique.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Renvoie 3</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> Les deux expressions doivent être numériques (nombres entiers ou décimaux).</p><p> Le résultat est également numérique.</p></td><td><p><pre>2 - 1</pre></p>Renvoie 1</td></tr>
<tr ><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>Les deux expressions doivent être numériques (nombres entiers ou décimaux). </p><p>Le résultat est également numérique.</p><p>&lt;expression2&gt; ne doit pas être égale à 0 (renvoie 0).</p></td><td><p><pre>4 / 2</pre></p>Renvoie 2</td></tr>
<tr ><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> Les deux expressions doivent être numériques (nombres entiers ou décimaux). </p><p>Le résultat est également numérique.</p></td><td><p><pre>3 * 4</pre></p>Renvoie 12</td></tr>
<tr ><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>Les deux expressions doivent être numériques (nombres entiers ou décimaux).</p><p> Le résultat est également numérique.</p></td><td><p><pre>3 % 2</pre></p>Renvoie 1.</td></tr>
</tbody>
</table>

## Mathématique

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale </th><th  >Exemple</th></tr>
</thead>
<tbody><tr ><td>is numeric</td><td><p><pre>&lt;expression&gt; is numeric</pre></p><p>Expression est de type entier ou décimal.</p></td><td><pre>@ is numeric</pre></td></tr>
<tr ><td>is integer</td><td><p><pre>&lt;expression&gt; is integer</pre></p><p>Expression est de type entier.</p></td><td><pre>@ is integer</pre></td></tr>
<tr ><td>is decimal</td><td><p><pre>&lt;expression&gt; is decimal</pre></p><p>Expression est de type décimal.</p></td><td><pre>@ is decimal</pre></td></tr>

## Chaîne

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale </th><th  >Exemple</th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;chaîne&gt; + &lt;expression&gt;</pre></p><p><pre>&lt;expression&gt; + &lt;chaîne&gt;</pre></p><p>Cet opérateur concatène deux expressions. </p><p>L’une des expressions doit être une chaîne de caractères.</p></td><td><p><pre>"il est actuellement " + (now())</pre></p> Renvoie « Il est actuellement 2019-09-23T09:30:06.693Z »<p><pre>(now()) + " est l’heure actuelle"</pre></p>Renvoie « 2019-09-23T09:30:06.693Z est l’heure actuelle »<p><pre>"a" + "b" + "c" + 1234</pre></p> Renvoie « abc1234 ».</td></tr>
</tbody>
</table>

## Date

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale </th><th  >Exemple</th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;expression&gt; + &lt;durée&gt;</pre></p><p>Permet d’ajouter une durée à une valeur dateTimeOnly ou à une durée.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Renvoie 2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Renvoie 2011-12-03T15:30:30<p><pre>now() + toDuration("PT1H")</pre></p><p>Renvoie une valeur dateTime (avec fuseau horaire UTC) une heure plus tard que l’heure actuelle</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Renvoie PT2H</p></td></tr>
</tbody>
</table>