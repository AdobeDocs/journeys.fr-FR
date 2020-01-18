---
title: Fonctions de gestion des collections
description: En savoir plus sur les types de données dans les fonctions de gestion des collections
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---


# Fonctions de gestion des collections {#collection-management-functions}

Le langage d’expression introduit également un ensemble de fonctions pour interroger les collections.

Ces fonctions sont expliquées ci-dessous. Dans les exemples suivants, utilisons la charge utile d’événement contenant une collection :

```
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**La fonction &quot;all(`<condition>`)&quot;**

La fonction **[!UICONTROL all]**active la définition d’un filtre sur une collection donnée en utilisant une expression booléenne.

```
<listExpression>.all(<condition>)
```

Par exemple, parmi tous les utilisateurs de l’application, vous pouvez obtenir ceux qui utilisent IOS 13 (expression booléenne &quot;app used == IOS 13&quot;). Le résultat de cette fonction est la liste filtrée contenant les éléments correspondant à l’expression booléenne (exemple : utilisateur 1 de l’application, utilisateur 34 de l’application, utilisateur 432 de l’application).

Dans une activité Condition de source de données, vous pouvez vérifier si le résultat de la fonction **[!UICONTROL all]**est nul ou non. Vous pouvez également combiner cette fonction**[!UICONTROL  all]** avec d’autres fonctions telles que **[!UICONTROL count]**. Pour plus d’informations, voir Activité[Condition de la source de](../building-journeys/condition-activity.md#data_source_condition)données.

**Exemple 1 :**

Nous voulons vérifier si un utilisateur a installé une version spécifique d’une application. Pour cela, nous obtenons tous les jetons de notification Push associés aux applications mobiles pour lesquelles la version est 1.0. Ensuite, nous exécutons une condition avec la fonction **[!UICONTROL count]**pour vérifier que la liste renvoyée de jetons contient au moins un élément.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Le résultat est vrai.

**Exemple 2 :**

Ici, nous utilisons la fonction **[!UICONTROL count]**pour vérifier s’il existe des jetons de notification Push dans la collection.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

Le résultat sera vrai.

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which Journey Orchestration sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the platform. For example, when using the .all() syntax to query experience events from the platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>Lorsque la condition de filtrage de la fonction **all()** est vide, le filtre renvoie tous les éléments de la liste. **Toutefois, pour comptabiliser le nombre d’éléments d’une collection, la fonction all n’est pas requise.**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Le résultat de l’expression est **3**.

**Exemple 3 :**

Nous vérifions ici si une personne n&#39;a reçu aucune communication au cours des dernières 24 heures. Nous filtrons la collection d’événements d’expérience récupérée à partir de la source de données ExperiencePlatform, en utilisant deux expressions basées sur deux éléments de la collection. En particulier, l’horodatage de l’événement est comparé à la dateTime renvoyée par la fonction **[!UICONTROL nowWithDelta]**.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Le résultat sera true s’il n’existe aucun événement d’expérience correspondant aux deux conditions.

**Exemple 4 :**

Ici, nous voulons vérifier si une personne a lancé au moins une application au cours des 7 derniers jours, afin par exemple de déclencher une notification Push l&#39;invitant à démarrer un tutoriel.

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```


<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]**n’est disponible que lors de la manipulation des collections d’événements et** currentDataPackField **>lors de la manipulation des collections de sources de données. Lors du traitement des collections avec**[!UICONTROL  tous]**, **[!UICONTROL d’abord]**et**[!UICONTROL  dernière]**, nous
>sur chaque élément de la collection un par un. **[!UICONTROL currentEventField]**et** currentDataPackField **>correspond à l’élément en boucle.

**Les fonctions &quot;first(`<condition>`)&quot; et &quot;last(`<condition>`)&quot;**

Les **[!UICONTROL première]**et**[!UICONTROL  dernière]** fonctions activent également la définition d’un filtre sur la collection tout en renvoyant le premier/dernier élément de la liste qui répond au filtre.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Exemple 1 :**

Cette expression renvoie le premier jeton de notification Push associé aux applications mobiles pour lesquelles la version est 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Le résultat est &quot;token_1&quot;.

**Exemple 2 :**

Cette expression renvoie le dernier jeton de notification Push associé aux applications mobiles pour lesquelles la version est 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Le résultat est &quot;token_2&quot;.

>[!NOTE]
>
>Les événements d’expérience sont récupérés à partir de la plateforme d’expérience en tant que collection dans l’ordre chronologique inverse, ce qui explique :
>* **[!UICONTROL first]**function renvoie l&#39;événement le plus récent
>* **[!UICONTROL last]**function renvoie la plus ancienne.


**Exemple 3 :**

Nous vérifions si le premier événement Adobe Analytics (le plus récent) avec une valeur non nulle pour l’ID DMA a une valeur égale à 602.

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**La fonction &quot;at(`<index>`)&quot;**

La fonction **[!UICONTROL at]**vous permet de référencer un élément spécifique d’une collection selon un index.
L’index 0 est le premier index de la collection.

_`<listExpression>`.at(`<index>`)_

**Exemple:**

Cette expression renvoie le deuxième jeton de notification Push de la liste.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Le résultat est &quot;token_2&quot;.