---
product: adobe campaign
title: Types de données
description: En savoir plus sur les types de données dans les expressions avancées
feature: Journeys
role: Developer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 100%

---

# Types de données {#concept_gp3_rj5_dgb}


>[!CAUTION]
>
>**Vous recherchez Adobe Journey Optimizer** ? Cliquez [ici](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/ajo-home){target="_blank"} pour consulter la documentation de Journey Optimizer.
>
>
>_Cette documentation se rapporte aux anciens contenus de Journey Orchestration qui ont été remplacés par Journey Optimizer. Pour toute question concernant votre accès à Journey Orchestration ou Journey Optimizer, contactez votre équipe en charge des comptes._


D’un point de vue technique, une constante contient toujours un type de données. Dans une expression littérale, nous ne spécifions que la valeur. Le type de données peut être déduit de la valeur (par exemple : chaîne, entier, décimal, etc.). Pour des cas spécifiques, tels que la date et l’heure, des fonctions dédiées sont utilisées pour la représentation.

Les sections ci-dessous fournissent des informations sur les différentes expressions de type de données et sur leur représentation.

## string {#string}

**Description**

Séquence de caractères courante. Pas de taille spécifique, à l’exception de la taille implicite provenant de l’environnement, comme la quantité de mémoire disponible.

Format JSON : chaîne

Format de sérialisation : UTF-8

**Représentation littérale**

```json
"<value>"
```

```json
'<value>'
```

**Exemple**

```json
"hello world"
```

```json
'hello world'
```

## integer {#integer}

**Description**

Valeur entière comprise entre -2^63 et 2^63-1.

Format JSON : nombre

**Représentation littérale**

```json
<integer value>
```

**Exemple**

```json
42
```

## decimal {#decimal}

**Description**

Nombre décimal. Représente une valeur flottante :

* valeur finie positive la plus grande de type double, (2-2^-52)x2^1023
* valeur normale positive la plus petite de type double, 2-1022
* valeur non nulle positive la plus petite de type double, 2 p-1074

Format JSON : nombre

Format de sérialisation : utilisation de « . » comme séparateur décimal.

**Représentation littérale**

```json
<integer value>.<integer value>
```

**Exemple**

```json
3.14
```

## boolean {#boolean}

**Description**

Valeur booléenne en minuscules : true ou false

Format JSON : booléen

**Représentation littérale**

```json
true
```

```json
false
```

**Exemple**

```json
true
```

## dateOnly {#date-only}

**Description**

Représente une valeur de date uniquement sans fuseau horaire, sous la forme année-mois-jour.

Il sʼagit dʼune description de la date, telle quʼelle est utilisée pour les anniversaires.

Format JSON : chaîne.

Format : AAAA-MM-JJ (ISO-8601), par exemple : « 2021-03-11 ».

Elle doit être encapsulée dans une fonction toDateOnly.

Il utilise DateTimeFormatter SO_LOCAL_DATE_TIME pour désérialiser et sérialiser la valeur. [En savoir plus](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**Représentation littérale**

```json
date("<dateOnly in ISO-8601 format>")  
```

**Exemple**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**Description**

Représente une valeur de date et d’heure sans fuseau horaire, sous la forme année-mois-jour-heure-minute-seconde-milliseconde.

Format JSON : chaîne.

Ce type ne stocke ni ne représente un fuseau horaire. Il s’agit plutôt d’une description de la date, telle qu’elle est utilisée pour les anniversaires, associée à l’heure locale telle qu’elle est affichée sur une horloge murale.

Il ne peut pas représenter un instant sur la ligne de temps sans informations supplémentaires telles qu’un décalage ou un fuseau horaire.

Elle doit être encapsulée dans une fonction toDateTimeOnly.

Format de sérialisation : format date-heure avec décalage étendu ISO-8601.

Il utilise DateTimeFormatter SO_LOCAL_DATE_TIME pour désérialiser et sérialiser la valeur. [En savoir plus](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME")

**Représentation littérale**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**Exemples**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**Description**

Constante de date et d’heure qui tient également compte du fuseau horaire. Elle représente une valeur de date et d’heure avec un décalage par rapport à UTC.

Elle peut être vue comme un point de la ligne du temps avec les informations supplémentaires du décalage. C’est une façon de représenter un « moment » précis en un point du globe.

Format JSON : chaîne.

Elle doit être encapsulée dans une fonction toDateTime.

Format de sérialisation : format date-heure avec décalage étendu ISO-8601.

Il utilise DateTimeFormatter ISO_OFFSET_DATE_TIME pour désérialiser et sérialiser la valeur. [En savoir plus](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

Vous pouvez également transmettre un entier qui transmet une valeur d’époque. [En savoir plus](https://www.epochconverter.com)

Le fuseau horaire peut être spécifié par un décalage ou un code de fuseau horaire (par exemple : Europe/Paris, Z ; ce qui signifie UTC).

**Représentation littérale**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**Exemples**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## durée {#duration}

**Description**

Ce type représente une durée basée sur le temps, telle que « 34,5 secondes ». Elle modélise une durée ou un laps de temps exprimé en millisecondes.

Les unités temporelles prises en charge sont les suivantes : millisecondes, secondes, minutes, heures, jours où un jour équivaut à 24 heures. Les années et les mois ne sont pas pris en charge, car ils ne représentent pas un laps de temps fixe.

Format JSON : chaîne.

Elle doit être encapsulée dans une fonction toDuration.

Format de sérialisation : pour désérialiser un identifiant de fuseau horaire, la fonction Java java.time est utilisée.

Duration.parse : les formats acceptés sont basés sur le format de durée ISO-8601 PnDTnHnMn.nS, avec des jours durant exactement 24 heures. [En savoir plus](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Représentation littérale**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**Exemple**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**Description**

Liste d’expressions séparées par des virgules utilisant des crochets comme délimiteurs.

Le polymorphisme n’est pas pris en charge. Par conséquent, toutes les expressions contenues dans la liste doivent être du même type.

**Représentation littérale**

```json
[<expression>, <expression>, ... ]
```

**Exemple**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
