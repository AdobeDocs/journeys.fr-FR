---
product: adobe campaign
solution: Journey Orchestration
title: Types de données
description: En savoir plus sur les types de données dans les expressions avancées
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 99%

---


# Types de données {#concept_gp3_rj5_dgb}

D’un point de vue technique, une constante contient toujours un type de données. Dans une expression littérale, nous ne spécifions que la valeur. Le type de données peut être déduit de la valeur (par exemple : chaîne, entier, décimal, etc.). Pour des cas spécifiques, tels que la date et l’heure, des fonctions dédiées sont utilisées pour la représentation.

Les sections ci-dessous fournissent des informations sur les différentes expressions de type de données et sur leur représentation.

## chaîne {#string}

**Description**

Séquence de caractères courante. Pas de taille spécifique, à l’exception de la taille implicite provenant de l’environnement, comme la quantité de mémoire disponible.

Format JSON : chaîne

Format de sérialisation : UTF-8

**Représentation littérale**

```
"<value>"
```

```
'<value>'
```

**Exemple**

```
"hello world"
```

```
'hello world'
```

## entier {#integer}

**Description**

Valeur entière comprise entre -2^63 et 2^63-1.

Format JSON : nombre

**Représentation littérale**

```
<integer value>
```

**Exemple**

```
42
```

## décimal {#decimal}

**Description**

Nombre décimal. Représente une valeur flottante :

* valeur finie positive la plus grande de type double, (2-2^-52)x2^1023
* valeur normale positive la plus petite de type double, 2-1022
* valeur non nulle positive la plus petite de type double, 2 p-1074

Format JSON : nombre

Format de sérialisation : utilisation de « . » comme séparateur décimal.

**Représentation littérale**

```
<integer value>.<integer value>
```

**Exemple**

```
3.14
```

## boolean {#boolean}

**Description**

Valeur booléenne en minuscules : true ou false

Format JSON : booléen

**Représentation littérale**

```
true
```

```
false
```

**Exemple**

```
true
```

## dateTimeOnly {#date-time-only}

**Description**

Représente une valeur de date et d’heure sans fuseau horaire, sous la forme année-mois-jour-heure-minute-seconde-milliseconde.

Ce type ne stocke ni ne représente un fuseau horaire. Il s’agit plutôt d’une description de la date, telle qu’elle est utilisée pour les anniversaires, associée à l’heure locale telle qu’elle est affichée sur une horloge murale.

Il ne peut pas représenter un instant sur la ligne de temps sans informations supplémentaires telles qu’un décalage ou un fuseau horaire.

Format de sérialisation : format date-heure avec décalage étendu ISO-8601.

Il utilise DateTimeFormatter SO_LOCAL_DATE_TIME pour désérialiser et sérialiser la valeur. [En savoir plus](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Représentation littérale**

```
toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  
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

```
toDateTime("<dateTime in ISO-8601 format>")
```

```
toDateTime(<integer value of an epoch in milliseconds>)
```

**Exemple**

```
toDateTime("1977-04-22T06:00:00Z")
```

```
toDateTime("2011-12-03T15:15:30Z")
```

```
toDateTime("2011-12-03T15:15:30.123Z")
```

```
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```
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

```
toDuration("<duration in ISO-8601 format>")
```

```
toDuration(<duration in milliseconds>)
```

**Exemple**

```
toDuration("PT5S") -- parses as 5 seconds
```

```
toDuration(500) -- parses as 500ms
```

```
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## liste {#list}

**Description**

Liste d’expressions séparées par des virgules utilisant des crochets comme délimiteurs.

Le polymorphisme n’est pas pris en charge. Par conséquent, toutes les expressions contenues dans la liste doivent être du même type.

**Représentation littérale**

```
[<expression>, <expression>, ... ]
```

**Exemple**

```
["value1","value2"]
```

```
[3,5]
```

```
[toDuration(500),toDuration(800)]
```
