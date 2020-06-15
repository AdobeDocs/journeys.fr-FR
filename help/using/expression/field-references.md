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
source-git-commit: 61e269bc319407f48006486b96333385ef8b9c58
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 100%

---



# Références de champ {#concept_fkj_ll5_dgb}

Il est possible d’associer une référence de champ à un événement ou à un groupe de champs. Les seules informations significatives sont le nom du champ et son chemin d’accès.

Si vous utilisez des caractères spéciaux dans un champ, vous devez avoir recours à des guillemets doubles ou des guillemets simples. Voici les cas où les guillemets sont nécessaires :

* Le champ commence par des caractères numériques.
* Le champ commence par le caractère « - ».
* Le champ contient d’autres caractères que : _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

Par exemple, si votre champ est _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Dans l’expression, les champs d’événement sont référencés par « @ » et les champs de source de données par « # ».

Une couleur de syntaxe permet de distinguer visuellement les champs d’événements (vert) des groupes de champs (bleu).

**Valeurs par défaut des références de champ**

Il est possible d’associer une valeur par défaut à un nom de champ. La syntaxe est la suivante :

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
>Le type du champ et la valeur par défaut doivent être identiques. Par exemple, @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} ne sera pas valide, car la valeur par défaut est un entier alors que la valeur attendue doit être une chaîne.

**Référence d’un champ dans les collections**

Les éléments définis dans les collections sont référencés à l’aide des fonctions spécifiques « all », « first » et « last ». Pour plus d’informations, reportez-vous à la section [](../expression/collection-management-functions.md).

Exemple :

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

**Référence d’un champ défini dans un mapping**

Pour récupérer un élément dans un mapping, il faut utiliser la fonction d’entrée avec une clé donnée. Elle est par exemple utilisée lors de la définition de la clé d’un événement, selon l’espace de noms sélectionné. Voir Sélection de l’espace de noms. Pour plus d’informations, reportez-vous à la section [](../event/selecting-the-namespace.md).

```
@{MyEvent.identityMap.entry('Email').first().id}
```

Dans cette expression, nous obtenons l’entrée correspondant à la clé « Email » du champ « IdentityMap » d’un événement. L’entrée « Email » est une collection, dans laquelle nous obtenons l’« id » dans le premier élément en utilisant « first() ». Pour plus d’informations, reportez-vous à la section [](../expression/collection-management-functions.md).

**Valeurs de paramètre d’une source de données (valeurs dynamiques de la source de données)**

Si vous sélectionnez un champ d’une source de données externe qui nécessite l’appel d’un paramètre, un nouvel onglet s’affiche à droite pour vous permettre de spécifier ce paramètre. Voir [](../expression/expressionadvanced.md).

Dans les cas d’utilisation plus complexes, si vous souhaitez inclure les paramètres de la source de données dans l’expression principale, vous pouvez définir leurs valeurs à l’aide du mot-clé _params_. Un paramètre peut être constitué de n’importe quelle expression valide, même provenant d’une autre source de données contenant également un autre paramètre.

>[!NOTE]
>
>Lorsque vous définissez les valeurs de paramètre dans l’expression, l’onglet de droite disparaît.

Utilisez la syntaxe suivante :

```
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`** : nom exact du premier paramètre de la source de données.
* **`<params-1-value>`** : valeur du premier paramètre. Il peut s’agir de n’importe quelle expression valide.

Exemple :

```
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
