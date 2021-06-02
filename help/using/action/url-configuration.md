---
product: adobe campaign
title: Configuration d’URL
description: En savoir plus sur la configuration d’URL
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 100%

---

# Configuration d’URL {#concept_gbg_1f1_2gb}

Lors de la configuration d’une action personnalisée, vous devez définir les paramètres de **[!UICONTROL configuration d’URL]** suivants :

![](../assets/journeyurlconfiguration.png)

1. Ajoutez l’**[!UICONTROL URL]** du service externe.

   >[!NOTE]
   >
   >Nous vous recommandons vivement d’utiliser le protocole HTTPS pour des raisons de sécurité. L’utilisation des adresses Adobe qui ne sont pas publiques et des adresses IP n’est pas autorisée.

1. Sélectionnez la **[!UICONTROL Méthode]** d’appel : il peut s’agir de **[!UICONTROL POST]** ou de **[!UICONTROL PUT]**.
1. Dans la section **[!UICONTROL En-têtes]**, cliquez sur **[!UICONTROL Ajouter un champ d’en-tête]** pour définir une nouvelle paire clé/valeur. Ces en-têtes correspondent aux en-têtes HTTP de la requête adressée au service externe. Pour supprimer des paires clé/valeur, placez le curseur sur le champ **[!UICONTROL En-têtes]**, puis cliquez sur l’icône **[!UICONTROL Supprimer]**.

   Les en-têtes **[!UICONTROL Content-Type]** et **[!UICONTROL Charset]** sont définis par défaut et ne peuvent pas être supprimés ni remplacés.

   >[!NOTE]
   >
   >Les en-têtes sont validés conformément à ces [règles d’analyse](https://tools.ietf.org/html/rfc7230#section-3.2.4).
