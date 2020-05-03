---
title: Utilisation de l’éditeur d’expression avancé
description: Découvrez comment créer des expressions avancées
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 28cb56e5f631acd8e2a49cf0bce55e7226892595

---


# Utilisation de l’éditeur d’expression avancé

L’éditeur d’expressions avancé peut être utilisé pour créer des conditions qui vous permettent de filtrer les utilisateurs dans vos voyages. Ces conditions vous permettent de cible les utilisateurs à l’heure, à la date, à l’emplacement, à la durée ou à des actions telles que l’achat ou l’abandon de paniers afin qu’ils puissent être reciblés dans le parcours.

>[!NOTE]
>
>Événements débuts avec @, sources de données avec #.

## Création de conditions sur les Événements d’expérience

L’éditeur d’expressions avancé est obligatoire pour effectuer des requêtes sur des séries temporelles, telles qu’une liste d’achats ou des clics passés sur des messages. Ces requêtes ne peuvent pas être effectuées à l’aide de l’éditeur simple.

Les événements d’expérience sont extraits d’Experience Platform sous la forme d’une collection dans l’ordre chronologique inverse. Par conséquent :

* La fonction first renvoie l’événement le plus récent.
* La fonction last renvoie l’événement le plus ancien.

Par exemple, supposons que vous vouliez cible des clients ayant abandonné leur panier au cours des 7 derniers jours pour envoyer un message lorsque le client se trouve à proximité d&#39;un magasin, avec une offre sur les articles qu&#39;il voulait et qui sont en magasin.

**Vous devez créer les conditions suivantes :**

Tout d&#39;abord, les clients cibles qui ont navigué sur la boutique en ligne mais n&#39;ont pas terminé la commande au cours des 7 derniers jours.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Cette expression recherche tous les événements de cet utilisateur spécifiés au cours des 7 derniers jours :**

Ensuite, il sélectionne tous les événements addtocart qui n’ont pas été transformés en completePurchase.

>[!NOTE]
>
>Pour insérer rapidement des champs dans l’expression, cliquez en doublon sur le champ dans le panneau de gauche de l’éditeur.

L’horodatage spécifié se comporte comme la valeur de l’heure de la date, la seconde est le nombre de jours.

    &quot;
    In( &quot;addToCart&quot;, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})EtNot(In(&quot;completePurchase&quot;), # PlatformDataSource.ExperienceEventFieldGroup.experienceevent.all(inLastDays(currentDataPackField.timestamp, 7 )).productData.productInteraction}&quot;
    
    
    
    
    
    
    
    
    
    

Cette expression renvoie une valeur booléenne.

**Maintenant, créons une expression qui vérifie que le produit est en stock**

* Dans Oracle Inventory, cette expression recherche le champ de quantité d&#39;un produit et indique qu&#39;il doit être supérieur à 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* À droite, les valeurs nécessaires sont spécifiées, ici, nous devons récupérer l&#39;emplacement du magasin, qui est mappé à partir de l&#39;emplacement du événement &quot;ArriveLumaStudio&quot; :

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Spécifiez le SKU à l’aide de la fonction `first` pour récupérer la dernière interaction &quot;addToCart&quot; :

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

De là, vous pouvez ajouter un autre chemin dans votre parcours pour les cas où le produit n’est pas en magasin et envoyer une notification avec offre d’engagement. Configurez les messages en conséquence et utilisez les données de personnalisation pour améliorer la cible des messages.

## Exemples de manipulations de chaînes avec l’éditeur d’expressions avancé

**Dans des conditions**

Cette condition récupère uniquement les événements de géofence déclenchés dans &quot;Arlington&quot; :

    &quot;
    @{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name} == &quot;Arlington&quot;
    &quot;

Explication : Il s’agit d’une comparaison de chaînes stricte (sensible à la casse), équivalente à une requête en mode simple qui utilise `equal to` avec `Is sensitive` coché.

La même requête avec `Is sensitive` non cochée génère l’expression suivante en mode avancé :

    &quot;
    égalIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    &quot;

**Dans les actions**

L’expression suivante vous permet de définir l’identifiant CRM dans un champ de personnalisation d’action :

    &quot;
    ered(@{MobileAppLaunch
    )._monorganisation
    .identification
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    ._myorganisation
    .identification
    .crmid}
    }
    ))
    
    &quot;

Explication : Cet exemple utilise `substr` et `lastIndexOf` les fonctions pour supprimer les accolades qui encadrent l’identifiant de gestion de la relation client transmis avec un événement de lancement d’application mobile.

Pour en savoir plus sur l’utilisation de l’éditeur d’expressions avancé, regardez [cette vidéo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html).
