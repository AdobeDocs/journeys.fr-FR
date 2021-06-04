---
product: adobe campaign
solution: Journey Orchestration
title: Utilisation des scores de fatigue
description: Découvrez comment utiliser les scores de fatigue dans les parcours
source-git-commit: c49908d36ecbc68ae11b5621305f39dd59c67871
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 3%

---


# Envoi d’un message à l’aide de Campaign {#campaign-v7-v8-use-case}

Ce cas pratique présente toutes les étapes nécessaires pour envoyer un email à l’aide de l’intégration Adobe Campaign.

Nous allons tout d’abord créer un modèle d’email transactionnel dans Campaign. Ensuite, en Journey Orchestration, nous allons créer l’événement, l’action et concevoir le parcours.

Pour en savoir plus sur l&#39;intégration de Campaign, consultez les pages suivantes :

* [Création d’une action de campagne](../action/working-with-adobe-campaign.md#using_adobe_campaign_v7_v8)
* [Utilisation de l’action dans un parcours](../building-journeys/using-adobe-campaign-actions.md).

**Adobe Campaign**

Votre instance Campaign doit être configurée pour cette intégration. La fonctionnalité de messagerie transactionnelle doit être configurée.

1. Connectez-vous à votre instance de pilotage Campaign.

1. Sous **Administration** > **Plateforme** > **Enumérations**, sélectionnez l&#39;énumération **Type d&#39;événement** (eventType). Créez un type d’événement (&quot;parcours-event&quot;, dans notre exemple). Vous devrez utiliser le nom interne du type d’événement lors de l’écriture ultérieure du fichier JSON.

   ![](../assets/accintegration-uc-1.png)

1. Déconnectez-vous et reconnectez-vous à l’instance pour que la création soit effective.

1. Sous **Message Center** > **Modèles de messages transactionnels**, créez un modèle d&#39;email basé sur le type d&#39;événement précédemment créé.

   ![](../assets/accintegration-uc-2.png)

1. Concevez votre modèle. Dans cet exemple, nous utilisons la personnalisation sur le prénom et le numéro de commande du profil. Le prénom se trouve dans la source de données Adobe Experience Platform et le numéro de commande est un champ de notre événement de Journey Orchestration. Veillez à utiliser les noms de champ corrects dans Campaign.

   ![](../assets/accintegration-uc-3.png)

1. Publiez votre modèle transactionnel.

   ![](../assets/accintegration-uc-4.png)

1. Vous devez maintenant écrire la charge utile JSON correspondant au modèle.

```
{
     "channel": "email",
     "eventType": "journey-event",
     "email": "Email address",
     "ctx": {
          "firstName": "First name", "purchaseOrderNumber": "Purchase order number"
     }
}
```

* Pour le canal, vous devez saisir &quot;email&quot;.
* Pour eventType, utilisez le nom interne du type d’événement créé précédemment.
* L’adresse électronique est une variable. Vous pouvez donc saisir n’importe quel libellé.
* Sous ctx, les champs de personnalisation sont également des variables.

**Journey Orchestration**

1. Tout d’abord, vous devez créer un événement. Veillez à inclure le champ &quot;purchaseOrderNumber&quot;.

   ![](../assets/accintegration-uc-5.png)

1. Vous devez ensuite créer, dans Journey Orchestration, une action correspondant à votre modèle Campaign. Dans la liste déroulante **Type d’action**, sélectionnez **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Cliquez sur le **champ Payload** et collez le code JSON créé précédemment.

   ![](../assets/accintegration-uc-7.png)

1. Pour l&#39;adresse email et les deux champs de personnalisation, remplacez **Constante** par **Variable**.

   ![](../assets/accintegration-uc-8.png)

1. Créez maintenant un parcours et commencez par l’événement précédemment créé.

   ![](../assets/accintegration-uc-9.png)

1. Ajoutez l’action et mappez chaque champ au champ correct dans Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Ajoutez une activité **Fin** et testez votre parcours.

   ![](../assets/accintegration-uc-11.png)

1. Vous pouvez maintenant publier votre parcours.
