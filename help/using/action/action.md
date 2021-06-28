---
product: adobe campaign
title: À propos des actions
description: Découvrez comment configurer une action
feature: Parcours
role: Business Practitioner
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
source-git-commit: 8d10739381b4f5b09ad7070498d5f1566961c221
workflow-type: ht
source-wordcount: '316'
ht-degree: 100%

---

# À propos des actions {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="À propos des actions"
>abstract="C’est à ce niveau qu’est définie la connexion au système qui enverra les messages. Les actions définies ici seront ensuite disponibles dans la palette de gauche de votre parcours, dans la catégorie Action. "

Les actions sont des connexions par le biais desquelles vous proposez des expériences en temps réel personnalisées aux clients, telles que des notifications Push, des e-mails, des SMS ou tout autre moyen d’engagement numérique utilisé dans votre entreprise.

Les actions personnalisées vous permettent de configurer la connexion d’un système tiers pour envoyer des messages ou des appels d’API. Une action peut être configurée avec n’importe quel service de n’importe quel fournisseur qui peut être appelé via une API REST avec un payload au format JSON.

Les actions sont disponibles dans la palette gauche de votre parcours, dans la catégorie **[!UICONTROL Action]** Voir [cette page](../building-journeys/about-action-activities.md).

>[!NOTE]
>
>La configuration des actions personnalisées est toujours effectuée par un **utilisateur technique**.

Dans la liste des **Actions**, vous pouvez appuyer sur la touche c pour créer un parcours, une action, une source de données ou un événement. Pour plus d’informations sur les raccourcis dans [!DNL Journey Orchestration], voir [cette section](../about/user-interface.md#section_ksq_zr1_ffb).

Pour afficher la liste des actions ou configurer une nouvelle action, cliquez sur **[!UICONTROL Actions]** dans les menus supérieurs. La liste des actions s’affiche. Pour plus d’informations sur l’interface, voir [cette page](../about/user-interface.md)

![](../assets/custom1.png)

Si vous disposez d’Adobe Campaign Standard, vous devez configurer l’action d’usine pour pouvoir envoyer des e-mails, des notifications Push et des SMS à l’aide des fonctionnalités de message transactionnel de cette plateforme. Voir [cette page](../action/working-with-adobe-campaign.md).

Si vous disposez d’Adobe Campaign v7 ou v8, une intégration est disponible sur demande. Voir [cette page](../action/acc-action.md).

Si vous utilisez un système tiers pour envoyer des messages tels que Epsilon, Facebook, Adobe.io, Firebase, etc., vous devez ajouter et configurer une action personnalisée. Voir [cette page](../action/about-custom-action-configuration.md).

Pour plus d’informations sur la configuration d’une action pour [!DNL Journey Orchestration] et sur la façon de l’utiliser dans un parcours, regardez ce [tutoriel vidéo](https://docs.adobe.com/content/help/fr-FR/platform-learn/tutorials/journey-orchestration/configure-actions.html).
