---
product: adobe campaign
solution: Journey Orchestration
title: Envoi d'un message à l'aide de Campaign v7/v8
description: Envoi d'un message à l'aide de Campaign v7/v8
exl-id: 8832d306-5842-4be5-9fb9-509050fcbb01
source-git-commit: 3e78e429bbdfc95bfef74e0f2e2b92f8ff17cfdb
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---

# Envoi d&#39;un message à l&#39;aide de Campaign v7/v8 {#campaign-classic-use-case}

Ce cas pratique présente toutes les étapes nécessaires pour envoyer un e-mail à l&#39;aide de l&#39;intégration à Adobe Campaign Classic v7 et Adobe Campaign v8.

Nous allons tout d&#39;abord créer un modèle d&#39;e-mail transactionnel dans Campaign. Ensuite, dans Journey Orchestration, nous allons créer l’événement, l’action et concevoir le parcours.

Pour en savoir plus sur l&#39;intégration de Campaign, consultez les pages suivantes :

* [Création d&#39;une action Campaign](../action/acc-action.md)
* [Utilisation de l&#39;action dans un parcours](../building-journeys/using-adobe-campaign-classic.md).

**Adobe Campaign**

Votre instance Campaign doit être configurée pour cette intégration. La fonctionnalité de messagerie transactionnelle doit être configurée.

1. Connectez-vous à votre instance de pilotage Campaign.

1. Sous **Administration** > **Plate-forme** > **Énumérations**, sélectionnez l&#39;énumération **Type d&#39;événement** (eventType). Créez un type d&#39;événement (« journey-event », dans notre exemple). Vous devrez utiliser le nom interne du type d&#39;événement lors de l&#39;écriture ultérieure du fichier JSON.

   ![](../assets/accintegration-uc-1.png)

1. Déconnectez-vous et reconnectez-vous à l&#39;instance pour que la création prenne effet.

1. Sous **Message Center** > **Modèles de messages transactionnels**, créez un modèle d&#39;e-mail basé sur le type d&#39;événement précédemment créé.

   ![](../assets/accintegration-uc-2.png)

1. Concevez votre modèle. Dans cet exemple, nous utilisons la personnalisation sur le prénom et le numéro de commande du profil. Le prénom se trouve dans la source de données Adobe Experience Platform et le numéro de commande est un champ de notre événement Journey Orchestration. Veillez à utiliser les noms de champ corrects dans Campaign.

   ![](../assets/accintegration-uc-3.png)

1. Publiez votre modèle transactionnel.

   ![](../assets/accintegration-uc-4.png)

1. Vous devez maintenant écrire la payload JSON correspondant au modèle.

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

* Pour le canal, vous devez saisir le type &quot;e-mail&quot;.
* Pour eventType, utilisez le nom interne du type d&#39;événement créé précédemment.
* L&#39;adresse e-mail est une variable. Vous pouvez donc saisir n&#39;importe quel libellé.
* Sous ctx, les champs de personnalisation sont également des variables.

**Journey Orchestration**

1. Tout d&#39;abord, vous devez créer un événement. Veillez à inclure le champ « purchaseOrderNumber ».

   ![](../assets/accintegration-uc-5.png)

1. Vous devez ensuite créer, dans Journey Orchestration, une action correspondant à votre modèle Campaign. Dans le menu déroulant **Type d&#39;action**, sélectionnez **Adobe Campaign Classic**.

   ![](../assets/accintegration-uc-6.png)

1. Cliquez sur le **champ Payload** et collez le code JSON créé précédemment.

   ![](../assets/accintegration-uc-7.png)

1. Pour l&#39;adresse e-mail et les deux champs de personnalisation, remplacez **Constante** par **Variable**.

   ![](../assets/accintegration-uc-8.png)

1. Créez maintenant un parcours et commencez par l&#39;événement précédemment créé.

   ![](../assets/accintegration-uc-9.png)

1. Ajoutez l’action et mappez chaque champ au champ correct dans Journey Orchestration.

   ![](../assets/accintegration-uc-10.png)

1. Ajoutez une activité **Fin** et testez votre parcours.

   ![](../assets/accintegration-uc-11.png)

1. Vous pouvez maintenant publier votre parcours.
