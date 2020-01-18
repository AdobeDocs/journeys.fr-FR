---
title: Les opérateurs
description: En savoir plus sur les opérateurs dans les expressions avancées
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---



# Les opérateurs {#concept_wd5_pj5_dgb}

Il existe deux types d&#39;opérateurs : opérateurs unaire et binaire. Il existe des opérateurs unaires de gauche et des opérateurs unaires de droite.

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

Voici la liste des opérateurs pris en charge :

## Logique

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale</th><th  >Exemple </th></tr>
</thead>
<tbody>
<tr >&gt;<td>et</td><td><p><pre>&lt;expression1&gt; et &lt;expression2&gt;</pre></p>&lt;expression1&gt; et &lt;expression2&gt; doivent être booléens. Le résultat est booléen.</td><td><pre>3.14 &gt; 2 et 3.15 &lt; 1</pre></td></tr>
<tr ><td>ou</td><td><p><pre>&lt;expression1&gt; ou &lt;expression2&gt;</pre></p><p>&lt;expression1&gt; et &lt;expression2&gt; doivent être booléens.</p><p> Le résultat est booléen.</p></td><td><p><pre>3.14 &gt; 2 ou 3.15 &lt; 1</pre></p></td></tr>
<tr ><td>not</td><td><p><pre>not &lt;expression&gt;</pre></p><p>&lt;expression&gt; doit être booléenne.</p><p> Le résultat est booléen.</p></td><td><pre>pas 3.15 &lt; 1</pre></td></tr>
</tbody>
  </table>

## Comparaison

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale </th><th  >Exemple </th></tr>
</thead>
<tbody><tr ><td>est nul</td><td><p><pre>&lt;expression&gt; est nul</pre></p><p>Le résultat est booléen.</p><p>Notez que null signifie que l’expression n’a pas de valeur évaluée.</p></td><td><pre>@{BarBeacon.location} est nul</pre></td></tr>
<tr ><td>n’est pas nul</td><td><p><pre>&lt;expression&gt; n’est pas nul</pre></p><p>Le résultat est booléen.</p><p>Notez que null signifie que l’expression n’a pas de valeur évaluée.</p></td><td><pre>@ n’est pas nul</pre></td></tr>
<tr ><td>has null</td><td><p><pre>&lt;expression&gt; a la valeur null</pre>&lt;expression&gt; doit être une liste.</p><p>Le résultat est booléen.</p><p>Utile pour identifier qu’une liste contient au moins une valeur nulle.</p></td><td><p><pre>["foo", "bar", null] a la valeur null</pre></p>renvoie true<p><pre>["foo", "bar", ""] a la valeur null</pre></p> renvoie false car "" n'est pas considéré comme nul.</td></tr>
<tr ><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>&lt;expression1&gt; et &lt;expression2&gt; doivent avoir le même type de données.</p><p> Le résultat est booléen.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr ><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> &lt;expression1&gt; et &lt;expression2&gt; doivent avoir le même type de données.</p><p> Le résultat est booléen.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr ><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>L’heure de date peut être comparée à l’heure de date.</p><p>La mesure de données uniquement peut être comparée à la mesure de données uniquement.</p><p>Les nombres entiers ou décimaux peuvent être comparés à des nombres entiers ou décimaux.</p><p>Toute autre combinaison est interdite.</p><p>Le résultat est booléen.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr ><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>L’heure de date peut être comparée à l’heure de date.</p><p>La mesure de données uniquement peut être comparée à la mesure de données uniquement.</p><p>Les nombres entiers ou décimaux peuvent être comparés à des nombres entiers ou décimaux.</p><p>Toute autre combinaison est interdite.</p><p>Le résultat est booléen.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr ><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>L’heure de date peut être comparée à l’heure de date.</p><p>La mesure de données uniquement peut être comparée à la mesure de données uniquement.</p><p>Les nombres entiers ou décimaux peuvent être comparés à des nombres entiers ou décimaux.</p><p>Toute autre combinaison est interdite.</p><p>Le résultat est booléen.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr ><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>L’heure de date peut être comparée à l’heure de date.</p><p>La mesure de données uniquement peut être comparée à la mesure de données uniquement.</p><p>Les nombres entiers ou décimaux peuvent être comparés à des nombres entiers ou décimaux.</p><p>Toute autre combinaison est interdite.</p><p>Le résultat est booléen.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Arithmétique

<table>
<thead>
<tr ><th  >Opérateur</th><th>Expression littérale </th><th  >Exemple </th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>Les deux expressions doivent être numériques (entières ou décimales). </p><p>Le résultat est également numérique.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Renvoie 3</p></td></tr>
<tr ><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> Les deux expressions doivent être numériques (entières ou décimales).</p><p> Le résultat est également numérique.</p></td><td><p><pre>2 - 1</pre></p>Renvoie 1</td></tr>
<tr ><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>Les deux expressions doivent être numériques (entières ou décimales). </p><p>Le résultat est également numérique.</p><p>&lt;expression2&gt; ne doit pas être égal à 0 (renvoie 0).</p></td><td><p><pre>4 / 2</pre></p>Renvoie 2</td></tr>
<tr ><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> Les deux expressions doivent être numériques (entières ou décimales). </p><p>Le résultat est également numérique.</p></td><td><p><pre>3 * 4</pre></p>Renvoie 12</td></tr>
<tr ><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>Les deux expressions doivent être numériques (entières ou décimales).</p><p> Le résultat est également numérique.</p></td><td><p><pre>3 % 2</pre></p>Renvoie 1.</td></tr>
</tbody>
</table>

## Maths

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale </th><th  >Exemple </th></tr>
</thead>
<tbody><tr ><td>est numérique</td><td><p><pre>&lt;expression&gt; est numérique</pre></p><p>Le type de l’expression est entier ou décimal.</p></td><td><pre>@ est numérique</pre></td></tr>
<tr ><td>est integer</td><td><p><pre>&lt;expression&gt; est integer</pre></p><p>Le type de l’expression est integer.</p></td><td><pre>@ is integer</pre></td></tr>
<tr ><td>est décimal</td><td><p><pre>&lt;expression&gt; est décimal</pre></p><p>Le type de l’expression est décimal.</p></td><td><pre>@ est décimal</pre></td></tr>

## Chaîne

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale </th><th  >Exemple </th></tr>
</thead>
<tbody><tr ><td>+</td><td><p><pre>&lt;string&gt; + &lt;expression&gt;</pre></p><p><pre>&lt;expression&gt; + &lt;chaîne&gt;</pre></p><p>Il concatène deux expressions. </p><p>Une expression doit être une chaîne chaînée.</p></td><td><p><pre>"l’heure actuelle est " + (now()))</pre></p> Renvoie "l’heure actuelle est 2019-09-23T09:30:06.693Z"<p><pre>(now()) + " est l’heure actuelle"</pre></p>Renvoie "2019-09-23T09:30:06.693Z est l’heure actuelle"<p><pre>"a" + "b" + "c" + 1234</pre></p> Renvoie "abc1234".</td></tr>
</tbody>
</table>

## Date

<table>
<thead>
<tr ><th  >Opérateur</th><th  >Expression littérale </th><th  >Exemple </th></tr>
</thead>
<tbody>
<tr ><td>+</td><td><p><pre>&lt;expression + &lt;durée&gt;</pre></p><p>Ajoutez une durée à une dateTime, une dateTimeOnly ou une durée.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Renvoie 2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Renvoie 2011-12-03T15:30:30<p><pre>now() + toDuration("PT1H")</pre></p><p>Renvoie une dateTime (avec fuseau horaire UTC) une heure plus tard à partir de l’heure actuelle</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Renvoie PT2H</p></td></tr>
</tbody>
</table>