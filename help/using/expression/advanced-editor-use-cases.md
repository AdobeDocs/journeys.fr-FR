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
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 100%

---


# Utilisation de l’éditeur d’expression avancé

L’éditeur d’expression avancé sert à créer des conditions pour filtrer les utilisateurs dans vos parcours. Ces conditions permettent de cibler les utilisateurs en fonction de l’heure, de la date, de l’emplacement, de la durée ou des actions, notamment l’achat ou l’abandon de panier pour pouvoir les recibler dans le parcours.

>[!NOTE]
>
>Les événements commencent par le caractère @, les sources de données par #.

## Création de conditions pour les événements d’expérience

L’éditeur d’expression avancé est obligatoire pour effectuer des requêtes sur des séries temporelles, comme une liste d’achats ou des clics antérieurs sur des messages. L’éditeur simple ne permet pas d’effectuer ces requêtes.

Les événements d’expérience sont extraits d’Adobe Experience Platform sous la forme d’une collection dans l’ordre chronologique inverse. Par conséquent :

* La fonction first renvoie l’événement le plus récent.
* La fonction last renvoie l’événement le plus ancien.

Par exemple, supposons que vous vouliez cibler des clients ayant abandonné leur panier au cours des 7 derniers jours et envoyer un message lorsqu’un client se trouve à proximité d’un magasin, avec une offre sur les articles qu’il souhaitait et qui se trouvent en magasin.

**Vous devez créer les conditions suivantes :**

Tout d’abord, il s’agit de cibler les clients qui ont accédé à la boutique en ligne, mais n’ont pas finalisé la commande au cours des 7 derniers jours.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Cette expression recherche tous les événements relatifs à cet utilisateur spécifiés au cours des 7 derniers jours :**

Ensuite, il faut sélectionner tous les événements addtocart qui n’ont pas été transformés en completePurchase.

>[!NOTE]
>
>Pour insérer rapidement un champ dans l’expression, double-cliquez dessus dans le panneau de gauche de l’éditeur.

L’horodatage spécifié tient lieu de valeur de date et d’heure, et la deuxième valeur correspond au nombre de jours.

    ```
    In( “addToCart”, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    And
    Not(In( “completePurchase”, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    
    ```

Cette expression renvoie une valeur booléenne.

**Maintenant, créons une expression qui vérifie que le produit est en stock**

* Dans Inventory, cette expression recherche le champ de quantité d’un produit et indique qu’il doit être supérieur à 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* Les valeurs nécessaires sont spécifiées à droite. Ici, nous devons récupérer l’emplacement du magasin, qui est mappé à partir de l’emplacement de l’événement &quot;ArriveLumaStudio&quot; :

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Spécifiez la référence du produit (SKU) à l’aide de la fonction `first` pour récupérer la dernière interaction &quot;addToCart&quot; :

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

De là, vous pouvez ajouter un autre chemin dans votre parcours pour les cas où le produit ne se trouve pas en magasin et envoyer une notification avec une offre d’engagement. Configurez les messages en conséquence et utilisez les données de personnalisation pour améliorer le ciblage de ces messages.

## Exemples de manipulations de chaînes avec l’éditeur d’expression avancé

**Dans des conditions**

Cette condition récupère uniquement les événements de géorepérage déclenchés dans &quot;Arlington&quot; :

    ```
    @{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name} == &quot;Arlington&quot;
    ```

Explication : il s’agit d’une comparaison de chaînes stricte (sensible à la casse), équivalente à une requête en mode simple qui utilise l’opérateur `equal to` avec `Is sensitive` coché.

La même requête avec `Is sensitive` non coché génère l’expression suivante en mode avancé :

    ```
    equalIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    ```

**Dans des actions**

L’expression suivante permet de définir l’identifiant CRM dans un champ de personnalisation d’action :

    ```
    substr(@{MobileAppLaunch
    ._myorganization
    .identification
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    ._myorganization
    .identification
    .crmid}
    }
    ))
    
    ```

Explication : cet exemple utilise les fonctions `substr` et `lastIndexOf` pour supprimer les accolades qui encadrent l’identifiant CRM transmis avec un événement de lancement d’application mobile.

Pour en savoir plus sur l’utilisation de l’éditeur d’expression avancé, regardez [cette vidéo](https://docs.adobe.com/content/help/fr-FR/journey-orchestration-learn/tutorials/create-a-journey.html).
