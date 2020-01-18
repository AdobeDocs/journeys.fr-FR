---
title: Types des données
description: En savoir plus sur les types de données dans les expressions avancées
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
source-git-commit: 4871550d1608f4ffdee3b56d38b08f808eb2281c

---


# Types des données {#concept_gp3_rj5_dgb}

Techniquement, une constante contient toujours un type de données. Dans l’expression littérale, nous spécifions uniquement la valeur. Le type de données peut être déduit de la valeur (par exemple chaîne, entier, décimal, etc.). Pour des cas spécifiques tels que l’heure de la date, nous utilisons des fonctions dédiées pour la représentation.

Voici comment les expressions de type de données sont représentées :

<table>
    <thead>
        <tr>
        <td>Type de données</td>
        <td>Description</td>
        <td>Représentation littérale</td>
        <td>Exemple </td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Séquence courante de caractères.</p><p>Il n'a pas de taille spécifique, à l'exception de la taille implicite provenant de l'environnement, comme la quantité de mémoire disponible.</p><p>Format JSON : Chaîne</p><p>Format de sérialisation : UTF-8</p></td>
        <td><p>"&lt;valeur&gt;"</p><p>'&lt;valeur&gt;'</p></td>
        <td><p><pre>"Bonjour le monde"</pre></p><p><pre>"Bonjour le monde"</pre></p></td>
    </tr>
    <tr>
        <td>integer</td>
        <td><p>Valeur entière comprise entre -2^63 et 2^63-1.</p><p>Format JSON : Nombre</p></td>
        <td>&lt;valeur entière&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>décimal</td>
        <td><p>Nombre décimal.</p><p>Il représente une valeur flottante :</p>
        <p>- valeur finale positive la plus élevée de type double (2-2^-52)x2^1023)</p>
        <p> - plus petite valeur normale positive de type double, 2-1022</p>
        <p> - plus petite valeur positive non nulle de type double, 2 p-1074</p><p>Format JSON : Nombre</p><p>Format de sérialisation : utilisation de '.' comme séparateur décimal.</p></td>
        <td>&lt;valeur entière&gt;.&lt;valeur entière&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolean</td>
        <td><p>Valeur booléenne en minuscules : true ou false</p><p>Format JSON : Booléen</p></td>
        <td><p>vrai</p><p>false</p></td>
        <td><p><pre>vrai</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Représente une heure de date sans fuseau horaire, vue sous la forme d’une année-mois-jour-heure-seconde-milliseconde.</p><p>Il ne stocke ni ne représente un fuseau horaire.</p><p>Il s’agit plutôt d’une description de la date, utilisée pour les anniversaires, associée à l’heure locale telle qu’elle est affichée sur une horloge murale.</p><p>Il ne peut pas représenter un instant sur la ligne de temps sans des informations supplémentaires telles qu’un décalage ou un fuseau horaire.</p><p>Format de sérialisation : Format date-heure de décalage étendu ISO-8601.</p><p>Il utilise DateTimeFormatter.</p><p>ISO_LOCAL_DATE_TIME pour désérialiser et sérialiser la valeur.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">En savoir plus</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly au format ISO-8601&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Constante d’heure de date qui tient également compte du fuseau horaire.</p><p>Il représente une date-heure avec un décalage par rapport à UTC. Il peut être visualisé instantanément avec les informations supplémentaires du décalage. </p><p>C'est une façon de représenter un "moment" spécifique dans un certain endroit du monde.</p><p>Format JSON : Chaîne.</p><p> Il doit être encapsulé dans une fonction toDateTime.</p><p>
        Format de sérialisation : Format date-heure de décalage étendu ISO-8601.</p><p> Il utilise DateTimeFormatter.ISO_OFFSET_DATE_TIME pour désérialiser et sérialiser la valeur.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">En savoir plus</a>. 
        <p>Vous pouvez également transmettre un entier transmettant une valeur d’époque.</p> <a href="https://www.epochconverter.com/">En savoir plus</a>.</p>
        <p>Le fuseau horaire peut être spécifié par un décalage ou un code de fuseau horaire (exemple : Europe/Paris, Z - UTC).</p></td>
        <td><p>toDateTime("&lt;dateTime au format ISO-8601&gt;")</p>
        <p>toDateTime(&lt;valeur entière d’une époque en millisecondes&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>duration</td>
        <td><p>Il représente une durée basée sur le temps, telle que "34,5 secondes".</p><p> Il modèle une quantité ou une quantité de temps en millisecondes.</p><p>Les unités temporelles prises en charge sont les suivantes : millisecondes, secondes, minutes, heures, jours où un jour équivaut à 24 heures.</p><p> Les années et les mois ne sont pas pris en charge car ils ne sont pas une durée fixe.</p><p>Format JSON : Chaîne. Il doit être encapsulé dans une fonction toDuration.</p><p>Format de sérialisation : Pour désérialiser un identifiant de fuseau horaire, il utilise la fonction java.time.</p><p>Duration.parse : les formats acceptés sont basés sur le format de durée ISO-8601 PnDTnHnMn.nS avec des jours considérés exactement 24 heures.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">En savoir plus</a>.</td>
        <td><p>toDuration("&lt;durée au format ISO-8601&gt;")</p><p>toDuration(&lt;durée en millisecondes&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 secondes</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>— analyse comme "20.345 secondes"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> — analyse comme "15 minutes"</pre></p>
        <p><pre>(où une minute est de 60 secondes)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>— analyse comme "10 heures"</pre></p>
        <p><pre>(où une heure est de 3 600 secondes)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— analyse comme "2 jours"</pre></p>
        <p><pre>(où un jour est </pre></p>
        <p><pre>24 heures ou 86 400 secondes)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>— analyse comme</pre></p>
        <p><pre>"2 jours, 3 heures et 4 minutes"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>— analyse comme</pre></p>
        <p><pre>"-6 heures et +3 minutes"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>— analyse comme</pre></p>
        <p><pre>"-6 heures et -3 minutes"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>— analyse comme</pre></p>
        <p><pre>"+6 heures et -3 minutes"</pre></p></td>
    </tr>
    <tr>
        <td>liste</td>
        <td>Liste d’expressions séparées par des virgules utilisant des crochets comme délimiteurs. Le polymorphisme n’est pas pris en charge. Par conséquent, toutes les expressions contenues dans la liste doivent avoir le même type.</td>
        <td>[&lt;expression&gt;, &lt;expression&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
