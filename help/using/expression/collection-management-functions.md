---
product: adobe campaign
solution: Journey Orchestration
title: Fonctions de gestion des collections
description: En savoir plus sur les types de données dans les fonctions de gestion des collections
feature: Parcours
role: Ingénieur de données
level: Expérience
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 99%

---


# Fonctions de gestion des collections {#collection-management-functions}

Le langage d’expression s’accompagne également d’un ensemble de fonctions permettant d’interroger les collections.

Ces fonctions sont expliquées ci-dessous. Dans les exemples suivants, nous allons utiliser la payload d’événement contenant une collection :

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

**La fonction « all(`<condition>`) »**

La fonction **[!UICONTROL all]** permet de définir un filtre sur une collection donnée en utilisant une expression booléenne.

```
<listExpression>.all(<condition>)
```

Par exemple, parmi tous les utilisateurs de l’application, vous pouvez extraire ceux qui utilisent IOS 13 (expression booléenne « app used == IOS 13 »). Le résultat de cette fonction est une liste filtrée contenant les éléments qui correspondent à l’expression booléenne (exemple : utilisateur 1 de l’application, utilisateur 34 de l’application, utilisateur 432 de l’application).

Dans une activité Condition de source de données, vous pouvez vérifier si le résultat de la fonction **[!UICONTROL all]** est nul ou non. Vous pouvez également combiner cette fonction **[!UICONTROL all]** à d’autres fonctions, telles que **[!UICONTROL count]**. Pour plus d’informations, voir [Activité Condition de source de données](../building-journeys/condition-activity.md#data_source_condition).

**Exemple 1 :**

Nous voulons vérifier si un utilisateur a installé une version spécifique d’une application. Pour ce faire, nous récupérons tous les jetons de notification push associés aux applications mobiles dont la version est égale à 1.0. Ensuite, nous exécutons une condition avec la fonction **[!UICONTROL count]** pour vérifier que la liste de jetons renvoyée contient au moins un élément.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Le résultat est true.

**Exemple 2 :**

Ici, nous utilisons la fonction **[!UICONTROL count]** pour vérifier s’il existe des jetons de notification push dans la collection.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

Le résultat sera true.

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

A query of experience events recorded on the Adobe Experience Platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which [!DNL Journey Orchestration] sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the Adobe Experience Platform. For example, when using the .all() syntax to query experience events from the Adobe Experience Platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>Lorsque la condition de filtrage de la fonction **all()** est vide, le filtre renvoie tous les éléments de la liste. **Cependant, pour comptabiliser le nombre d’éléments d’une collection, la fonction all n’est pas obligatoire.**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Le résultat de l’expression est **3**.

**Exemple 3 :**

Dans cet exemple, nous allons vérifier si un individu n’a reçu aucune communication au cours des dernières 24 heures. Nous allons filtrer la collection d’événements d’expérience récupérés à partir de la source de données Experience Platform, en utilisant deux expressions basées sur deux éléments de la collection. En particulier, l’horodatage de l’événement est comparé à la valeur dateTime renvoyée par la fonction **[!UICONTROL nowWithDelta]**.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Le résultat sera true si aucun événement d’expérience ne correspond aux deux conditions.

**Exemple 4 :**

Notre objectif ici est de vérifier si un individu a lancé au moins une application au cours des 7 derniers jours afin, par exemple, de déclencher une notification push l’invitant à démarrer un tutoriel.

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
>**[!UICONTROL currentEventField]** n’est disponible que lors de la manipulation de collections d’événements et **currentDataPackField**,
>lors de la manipulation de collections de sources de données. Lors du traitement de collections avec les fonctions **[!UICONTROL all]**, **[!UICONTROL first]** et **[!UICONTROL last]**, nous
>les exécutons en boucle sur chaque élément de la collection. **[!UICONTROL currentEventField]** et **currentDataPackField**
>correspondent à l’élément exécuté en boucle.

**Les fonctions « first(`<condition>`) » et « last(`<condition>`) »**

Les fonctions **[!UICONTROL first]** et **[!UICONTROL last]** activent également la définition d’un filtre sur la collection, tout en renvoyant le premier/dernier élément de la liste qui correspond au filtre.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Exemple 1 :**

Cette expression renvoie le premier jeton de notification push associé aux applications mobiles dont la version est égale à 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Le résultat est &quot;token_1&quot;.

**Exemple 2 :**

Cette expression renvoie le dernier jeton de notification push associé aux applications mobiles dont la version est égale à 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Le résultat est &quot;token_2&quot;.

>[!NOTE]
>
>Les événements d’expérience sont extraits d’Adobe Experience Platform sous la forme d’une collection dans l’ordre chronologique inverse. Par conséquent :
>* La fonction **[!UICONTROL first]** renvoie l’événement le plus récent.
>* La fonction **[!UICONTROL last]** renvoie l’événement le plus ancien.


**Exemple 3 :**

Nous vérifions si la valeur du premier événement Adobe Analytics (le plus récent), dont l’ID DMA a une valeur non nulle, est égale à 602.

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**La fonction « at(`<index>`) »**

La fonction **[!UICONTROL at]** vous permet de référencer un élément spécifique d’une collection conformément à un index.
L’index 0 est le premier de la collection.

_`<listExpression>`.at(`<index>`)_

**Exemple :**

Cette expression renvoie le deuxième jeton de notification push de la liste.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Le résultat est &quot;token_2&quot;.