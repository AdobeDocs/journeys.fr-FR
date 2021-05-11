---
product: adobe campaign
solution: Journey Orchestration
title: À propos de l’intégration de Campaign Classic
description: En savoir plus sur l’intégration de Campaign Classic
hide: true
hidefromtoc: true
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
translation-type: tm+mt
source-git-commit: 8ab3951f9c97a0a964f5c123978ed256d3aedc45
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 100%

---

# Intégration avec Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Cette intégration vous permet d’envoyer des e-mails, des notifications push et des SMS à l’aide des fonctionnalités de messagerie transactionnelle d’Adobe Campaign Classic.

La connexion entre les instances Journey Orchestration et Campaign Classic est configurée par Adobe au moment de l’approvisionnement.

>[!CAUTION]
>
> Cette intégration est publiée sous forme de version Beta privée. Elle n’est pas disponible pour tous les clients Journey Orchestration.

## Remarques importantes

* Il n’y a pas de limitation des messages. Nous limitons le nombre de messages pouvant être envoyés à 50 000/heure en nous basant sur le contrat de niveau de service Campaign Classic actuel. C’est la raison pour laquelle Journey Orchestration ne devrait être utilisé que dans des cas d’utilisation unitaire (des événements individuels, et non des segments).

* Vous devez configurer une action sur la zone de travail pour chaque modèle à utiliser.

* Nous vous recommandons d’utiliser une instance Message Center dédiée et hébergée pour cette intégration afin d’éviter d’impacter les autres opérations de Campaign Classic en cours. Le serveur marketing peut être hébergé ou On-Premise. Le build requis est la version 21.1 Candidate.

* Il n’existe aucune validation indiquant le caractère correct du message Campaign Classic ou de la payload.

* Vous ne pouvez pas utiliser une action Campaign Classic avec une qualification de segment.

## Conditions préalables requises

Dans Campaign Classic, vous devez créer et publier un message transactionnel et son événement associé. Reportez-vous à la [documentation d’Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=fr#transactional-messaging).

Contactez Adobe pour obtenir la payload JSON correspondant à chaque message. Il vous faudra ensuite coller cette payload lors de la configuration de l’action dans Journey Orchestration (voir ci-dessous).

Voici un exemple :

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

## Configuration de l’action

Dans Journey Orchestration, vous devez configurer une action par message transactionnel. Procédez comme suit :

1. Créez une nouvelle action. Reportez-vous à cette [section](../action/action.md).
1. Entrez un nom et une description.
1. Dans le champ **Type d’action**, sélectionnez **Adobe Campaign Classic**.
1. Cliquez dans le champ **Payload** et collez un exemple de payload JSON correspondant au message Campaign Classic. Contactez Adobe pour obtenir cette payload.
1. Ajustez les différents champs. Certains champs, tels que les paramètres de canal et les champs de personnalisation (ctx), doivent être définis comme des variables.
1. Cliquez sur **Enregistrer**.

![](../assets/accintegration1.png)

Pour chaque action configurée, une activité d’action est disponible dans la palette du concepteur de parcours.

## Ajout d’un message dans un parcours

1. Concevez votre parcours en commençant par un événement. Consultez cette [section](../building-journeys/journey.md).
1. Dans la section **Action** de la palette, sélectionnez une action Campaign Classic et ajoutez-la à votre parcours.
1. Dans les **paramètres d’action**, tous les champs attendus dans la payload du message s’affichent. Vous devez faire correspondre chacun de ces champs avec celui que vous souhaitez utiliser, et ce, depuis l’événement ou la source de données. Cette opération est similaire aux actions personnalisées. Reportez-vous à cette [section](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
