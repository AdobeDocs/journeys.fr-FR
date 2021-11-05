---
product: adobe campaign
title: Références de champ
description: En savoir plus sur les références de champ dans les expressions avancées
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: e4a003656058ac7ae6706e22fd5162c9e875629a
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 67%

---

# Références de champ {#concept_fkj_ll5_dgb}

Il est possible d’associer une référence de champ à un événement ou à un groupe de champs. Les seules informations significatives sont le nom du champ et son chemin d’accès.

Si vous utilisez des caractères spéciaux dans un champ, vous devez avoir recours à des guillemets doubles ou des guillemets simples. Voici les cas où les guillemets sont nécessaires :

* Le champ commence par des caractères numériques.
* Le champ commence par le caractère « - ».
* Le champ contient d’autres caractères que : _a_-_z_, _A_-_Z_, _0_-_9_, _ , _-_

Par exemple, si votre champ est _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

Dans l’expression, les champs d’événement sont référencés par « @ » et les champs de source de données par « # ».

Une couleur de syntaxe permet de distinguer visuellement les champs d’événements (vert) des groupes de champs (bleu).

## Valeurs par défaut des références de champ

Une valeur par défaut peut être associée à un nom de champ. La syntaxe se présente comme suit :

```json
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

Exemples :

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

## Référence à un champ dans les collections

Les éléments définis dans les collections sont référencés à l’aide de fonctions spécifiques. `all`, `first` et `last`. Pour plus d’informations, consultez [cette page](../expression/collection-management-functions.md).

Exemple :

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## Référence à un champ défini dans un mappage

### fonction `entry`

Pour récupérer un élément dans un mapping, il faut utiliser la fonction d’entrée avec une clé donnée. Elle est par exemple utilisée lors de la définition de la clé d’un événement, selon l’espace de noms sélectionné. Voir Sélection de l’espace de noms. Pour plus d’informations, consultez [cette page](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

Dans cette expression, nous obtenons l’entrée correspondant à la clé « E-mail » du champ « IdentityMap » d’un événement. L’entrée « E-mail » est une collection, dans laquelle nous obtenons l’« id » dans le premier élément en utilisant « first() ». Pour plus d’informations, consultez [cette page](../expression/collection-management-functions.md).

### fonction `firstEntryKey`

Pour récupérer la première clé d’entrée d’une carte, utilisez la méthode `firstEntryKey` fonction .

Cet exemple montre comment récupérer la première adresse email des abonnés d&#39;une liste spécifique :

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

Dans cet exemple, la liste des abonnements est nommée `daily-email`. Les adresses électroniques sont définies comme clés dans la variable `subscribers` map, qui est liée à la carte de la liste d’abonnements.

### fonction `keys`

Pour récupérer toutes les clés d’une carte, utilisez la variable `keys` fonction .

Cet exemple montre comment récupérer, pour un profil spécifique, toutes les adresses email associées aux abonnés d&#39;une liste spécifique :

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## Valeurs de paramètre d’une source de données (valeurs dynamiques de la source de données)

Si vous sélectionnez un champ d’une source de données externe qui nécessite l’appel d’un paramètre, un nouvel onglet s’affiche à droite pour vous permettre de spécifier ce paramètre. Voir [cette page](../expression/expressionadvanced.md).

Dans les cas d’utilisation plus complexes, si vous souhaitez inclure les paramètres de la source de données dans l’expression principale, vous pouvez définir leurs valeurs à l’aide du mot-clé _params_. Un paramètre peut être constitué de n’importe quelle expression valide, même provenant d’une autre source de données contenant également un autre paramètre.

>[!NOTE]
>
>Lorsque vous définissez les valeurs de paramètre dans l’expression, l’onglet de droite disparaît.

Utilisez la syntaxe suivante :

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`** : nom exact du premier paramètre de la source de données.
* **`<params-1-value>`** : valeur du premier paramètre. Il peut s’agir de n’importe quelle expression valide.

Exemple :

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
