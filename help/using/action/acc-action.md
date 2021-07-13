---
product: adobe campaign
title: À propos de l’intégration de Campaign v7/v8
description: En savoir plus sur l’intégration de Campaign v7/v8
feature: Parcours
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 100%

---

# Utilisation d’Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}

Cette intégration est disponible pour Adobe Campaign Classic v7 à partir de la version 21.1 et Adobe Campaign v8. Elle permet d’envoyer des e-mails, des notifications push et des SMS à l’aide des fonctionnalités de messagerie transactionnelle d’Adobe Campaign.

La connexion entre les instances Journey Orchestration et Campaign est configurée par Adobe au moment de l’approvisionnement.

Un cas d’utilisation complet est présenté dans cette [section](../usecase/campaign-classic-use-case.md).

Pour chaque action configurée, une activité d’action est disponible dans la palette du concepteur de parcours. Reportez-vous à cette [section](../building-journeys/using-adobe-campaign-classic.md).

## Remarques importantes

* Il n’y a pas de limitation des messages. Nous limitons le nombre de messages pouvant être envoyés à 50 000/heure en nous basant sur le contrat de niveau de service Campaign actuel. C’est la raison pour laquelle Journey Orchestration ne devrait être utilisé que dans des cas d’utilisation unitaires (des événements individuels, et non des segments).

* Vous devez configurer une action sur la zone de travail pour chaque modèle à utiliser. Vous devez configurer une action dans Journey Orchestration pour chaque modèle que vous souhaitez utiliser à partir d’Adobe Campaign.

* Nous vous recommandons d’utiliser une instance Message Center dédiée et hébergée pour cette intégration afin d’éviter d’impacter les autres opérations de Campaign en cours. Le serveur marketing peut être hébergé ou On-Premise. Le build requis est la version 21.1 Release Candidate ou ultérieure.

* Il n’existe aucune validation indiquant le caractère correct du message Campaign ou de la payload.

* Vous ne pouvez pas utiliser une action Campaign avec un événement de qualification de segment.

## Conditions préalables

Dans Campaign, vous devez créer et publier un message transactionnel et son événement associé. Reportez-vous à la [documentation d’Adobe Campaign ](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html?lang=fr#transactional-messaging).

Vous pouvez créer la payload JSON correspondant à chaque message selon le modèle ci-dessous. Il vous faudra ensuite coller cette payload lors de la configuration de l’action dans Journey Orchestration (voir ci-dessous)

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

* **channel** : le canal défini pour votre modèle transactionnel Campaign
* **eventType** : le nom interne de votre événement Campaign
* **ctx** : variable basée sur la personnalisation de votre message.

## Configuration de l’action

Dans Journey Orchestration, vous devez configurer une action par message transactionnel. Procédez de la façon suivante :

1. Créez une nouvelle action. Reportez-vous à cette [section](../action/action.md).
1. Entrez un nom et une description.
1. Dans le champ **Type d’action**, sélectionnez **Adobe Campaign Classic**.
1. Cliquez dans le champ **Payload** et collez un exemple de payload JSON correspondant au message Campaign Contactez Adobe pour obtenir cette payload.
1. Ajustez les différents champs de sorte qu’ils soient statiques ou variables selon que vous souhaitez les mapper ou non sur la zone de travail des parcours. Certains champs, tels que les paramètres de canal pour l’adresse e-mail et les champs de personnalisation (ctx), doivent probablement être définis comme des variables pour le mappage dans le contexte du parcours.
1. Cliquez sur **Enregistrer**.

![](../assets/accintegration1.png)


