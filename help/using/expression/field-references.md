---
title: Références de champ
description: En savoir plus sur les références de champ dans les expressions avancées
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
source-git-commit: 8be9cd1803ab2f7093934424c36fcd7407a4a20a

---



# Références de champ {#concept_fkj_ll5_dgb}

Une référence de champ peut être jointe à un événement ou à un groupe de champs. La seule information significative est le nom du champ et son chemin.

Si vous utilisez des caractères spéciaux dans un champ, vous devez utiliser des guillemets doubles ou des guillemets simples. Voici les cas où des guillemets sont nécessaires :

* le champ commence par des caractères numériques
* le champ commence par le caractère &quot;-&quot;
* le champ contient autre chose que : _a_-_z_, _A_-_Z, 0-9, _ ,_______

Par exemple, si votre champ est de _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Dans l’expression, les champs d’événement sont référencés par &quot;@&quot; et les champs de source de données par &quot;#&quot;.

Une couleur de syntaxe permet de distinguer visuellement les champs d’événements (vert) des groupes de champs (bleu).

**Valeurs par défaut des références de champ**

Une valeur par défaut peut être associée à un nom de champ. La syntaxe est la suivante :


```
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>Le type du champ et la valeur par défaut doivent être identiques. Par exemple, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : {2} ne sera pas valide car la valeur par défaut est un entier alors que la valeur attendue doit être une chaîne.

**Référence d’un champ dans les collections**

Les éléments définis dans les collections sont référencés à l’aide des fonctions spécifiques all, first and last. For more information, see [](../expression/collection-management-functions.md).

Exemple :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Référence d&#39;un champ défini dans une carte** Pour récupérer un élément dans une carte, nous utilisons la fonction d&#39;entrée avec une clé donnée. Par exemple, elle est utilisée lors de la définition de la clé d’un événement, selon l’espace de noms sélectionné. Voir Sélection de l’espace de noms. For more information, see [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

Dans cette expression, nous obtenons l’entrée correspondant à la clé &quot;Email&quot; du champ &quot;IdentityMap&quot; d’un événement. L’entrée &quot;Email&quot; est une collection, à partir de laquelle nous prenons l’&quot;id&quot; dans le premier élément en utilisant &quot;first()&quot;. For more information, see [](../expression/collection-management-functions.md).

**Valeurs de paramètre d’une source de données (valeurs dynamiques de la source de données)**

Si vous sélectionnez un champ d’une source de données externe nécessitant l’appel d’un paramètre, un nouvel onglet s’affiche à droite pour vous permettre de spécifier ce paramètre. Voir la section [](../expression/expressionadvanced.md).

Pour des cas d’utilisation plus complexes, si vous souhaitez inclure les paramètres de la source de données dans l’expression principale, vous pouvez définir leurs valeurs à l’aide des _paramètres_ de mot-clé. Un paramètre peut être n’importe quelle expression valide, même à partir d’une autre source de données qui inclut également un autre paramètre.

>[!NOTE]
>
>Lorsque vous définissez les valeurs de paramètre dans l’expression, l’onglet de droite disparaît.

Utilisez la syntaxe suivante :

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: nom exact du premier paramètre de la source de données.
* **`<params-1-value>`**: valeur du premier paramètre. Il peut s’agir de n’importe quelle expression valide.

Exemple:

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
