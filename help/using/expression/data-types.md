---
title: Types de données
description: En savoir plus sur les types de données dans les expressions avancées
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: ht
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: ht
source-wordcount: '675'
ht-degree: 100%

---


# Types de données {#concept_gp3_rj5_dgb}

D’un point de vue technique, une constante contient toujours un type de données. Dans une expression littérale, nous ne spécifions que la valeur. Le type de données peut être déduit de la valeur (par exemple : chaîne, entier, décimal, etc.). Pour des cas spécifiques, tels que la date et l’heure, des fonctions dédiées sont utilisées pour la représentation.

Les expressions de type de données sont représentées comme suit :

<table>
    <thead>
        <tr>
        <td>Type de données</td>
        <td>Description</td>
        <td>Représentation littérale</td>
        <td>Exemple</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>chaîne</td>
        <td><p>Séquence de caractères courante.</p><p>Pas de taille spécifique, à l’exception de la taille implicite provenant de l’environnement, comme la quantité de mémoire disponible.</p><p>Format JSON : chaîne</p><p>Format de sérialisation : UTF-8</p></td>
        <td><p>"&lt;valeur&gt;"</p><p>'&lt;valeur&gt;'</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>'hello world'</pre></p></td>
    </tr>
    <tr>
        <td>entier</td>
        <td><p>Valeur entière comprise entre -2^63 et 2^63-1.</p><p>Format JSON : nombre</p></td>
        <td>&lt;valeur entière&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>décimal</td>
        <td><p>Nombre décimal.</p><p>Représente une valeur flottante :</p>
        <p>- valeur finie positive la plus grande de type double, (2-2^-52)x2^1023</p>
        <p> - valeur normale positive la plus petite de type double, 2-1022</p>
        <p> - valeur non nulle positive la plus petite de type double, 2 p-1074</p><p>Format JSON : nombre</p><p>Format de sérialisation : utilisation de « . » comme séparateur décimal.</p></td>
        <td>&lt;valeur entière&gt;.&lt;valeur entière&gt;</td>
        <td><p><pre>3,14</pre></p></td>
    </tr>
    <tr>
        <td>booléen</td>
        <td><p>Valeur booléenne en minuscules : true ou false</p><p>Format JSON : booléen</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Représente une valeur de date et d’heure sans fuseau horaire, sous la forme année-mois-jour-heure-minute-seconde-milliseconde.</p><p>Ce type ne stocke ni ne représente un fuseau horaire.</p><p>Il s’agit plutôt d’une description de la date, telle qu’elle est utilisée pour les anniversaires, associée à l’heure locale telle qu’elle est affichée sur une horloge murale.</p><p>Il ne peut pas représenter un instant sur la ligne de temps sans informations supplémentaires telles qu’un décalage ou un fuseau horaire.</p><p>Format de sérialisation : format date-heure avec décalage étendu ISO-8601.</p><p>Il utilise DateTimeFormatter.</p><p>ISO_LOCAL_DATE_TIME pour désérialiser et sérialiser la valeur.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">En savoir plus</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly au format ISO-8601&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Constante de date et d’heure qui tient également compte du fuseau horaire.</p><p>Elle représente une valeur de date et d’heure avec un décalage par rapport à UTC. Elle peut être vue comme un point de la ligne du temps avec les informations supplémentaires du décalage. </p><p>C’est une façon de représenter un « moment » précis en un point du globe.</p><p>Format JSON : chaîne.</p><p> Elle doit être encapsulée dans une fonction toDateTime.</p><p>
        Format de sérialisation : format date-heure avec décalage étendu ISO-8601.</p><p> Elle utilise DateTimeFormatter.ISO_OFFSET_DATE_TIME pour désérialiser et sérialiser la valeur.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">En savoir plus</a>. 
        <p>Vous pouvez également transmettre un entier qui transmet une valeur d’époque.</p> <a href="https://www.epochconverter.com/">En savoir plus</a>.</p>
        <p>Le fuseau horaire peut être spécifié par un décalage ou un code de fuseau horaire (par exemple : Europe/Paris, Z ; ce qui signifie UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime au format ISO-8601&gt;")</p>
        <p>toDateTime(&lt;valeur entière d’une époque en millisecondes&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>durée</td>
        <td><p>Ce type représente une durée basée sur le temps, telle que « 34,5 secondes ».</p><p> Elle modélise une durée ou un laps de temps exprimé en millisecondes.</p><p>Les unités temporelles prises en charge sont les suivantes : millisecondes, secondes, minutes, heures, jours où un jour équivaut à 24 heures.</p><p> Les années et les mois ne sont pas pris en charge, car ils ne représentent pas un laps de temps fixe.</p><p>Format JSON : chaîne. Elle doit être encapsulée dans une fonction toDuration.</p><p>Format de sérialisation : pour désérialiser un identifiant de fuseau horaire, la fonction Java java.time est utilisée.</p><p>Duration.parse : les formats acceptés sont basés sur le format de durée ISO-8601 PnDTnHnMn.nS, avec des jours durant exactement 24 heures.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">En savoir plus</a>.</td>
        <td><p>toDuration("&lt;durée au format ISO-8601&gt;")</p><p>toDuration(&lt;durée en millisecondes&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 seconds</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>-- parses as "20.345 seconds"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> -- parses as "15 minutes"</pre></p>
        <p><pre>(where a minute is 60 seconds)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>-- parses as "10 hours"</pre></p>
        <p><pre>(where an hour is 3600 seconds)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>-- parses as "2 days"</pre></p>
        <p><pre>(where a day is </pre></p>
        <p><pre>24 hours or 86400 seconds)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>-- parses as</pre></p>
        <p><pre>"2 days, 3 hours and 4 minutes"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>-- parses as</pre></p>
        <p><pre>"-6 hours and +3 minutes"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>-- parses as</pre></p>
        <p><pre>"-6 hours and -3 minutes"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>-- parses as</pre></p>
        <p><pre>"+6 hours and -3 minutes"</pre></p></td>
    </tr>
    <tr>
        <td>liste</td>
        <td>Liste d’expressions séparées par des virgules utilisant des crochets comme délimiteurs. Le polymorphisme n’est pas pris en charge. Par conséquent, toutes les expressions contenues dans la liste doivent être du même type.</td>
        <td>[&lt;expression&gt;, &lt;expression&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
