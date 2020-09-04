---
title: À propos des actions
description: Découvrez comment configurer une action
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: ht
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: ht
source-wordcount: '287'
ht-degree: 100%

---


# À propos des actions {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="À propos des actions"
>abstract="C’est à ce niveau qu’est définie la connexion au système qui enverra les messages. Les actions définies ici seront ensuite disponibles dans la palette de gauche de votre parcours, dans la catégorie Action. "

Les actions sont des connexions par le biais desquelles vous proposez des expériences en temps réel personnalisées aux clients, telles que des notifications Push, des emails, des SMS ou tout autre moyen d’engagement numérique utilisé dans votre entreprise.

Les actions personnalisées vous permettent de configurer la connexion d’un système tiers pour envoyer des messages ou des appels d’API. Une action peut être configurée avec n’importe quel service de n’importe quel fournisseur qui peut être appelé via une API REST avec un payload au format JSON.

Les actions sont disponibles dans la palette de gauche de votre parcours, dans la catégorie **[!UICONTROL Action]** (voir [](../building-journeys/about-action-activities.md)).

>[!NOTE]
>
>La configuration des actions personnalisées est toujours effectuée par un **utilisateur technique**.

Dans la liste des **Actions**, vous pouvez appuyer sur la touche c pour créer un parcours, une action, une source de données ou un événement. Pour plus d’informations sur les raccourcis dans [!DNL Journey Orchestration], voir la section [](../about/user-interface.md#section_ksq_zr1_ffb).

Pour afficher la liste des actions ou configurer une nouvelle action, cliquez sur **[!UICONTROL Actions]** dans les menus supérieurs. La liste des actions s’affiche. Pour plus d’informations sur l’interface, voir [](../about/user-interface.md).

![](../assets/custom1.png)

Si vous disposez d’Adobe Campaign Standard, vous devez configurer l’action d’usine pour pouvoir envoyer des emails, des notifications Push et des SMS à l’aide des fonctionnalités de message transactionnel de cette plate-forme. Voir [](../action/working-with-adobe-campaign.md).

Si vous utilisez un système tiers pour envoyer des messages tels que Epsilon, Facebook, Adobe.io, Firebase, etc., vous devez ajouter et configurer une action personnalisée. Voir [](../action/about-custom-action-configuration.md).

Pour plus d’informations sur la configuration d’une action pour [!DNL Journey Orchestration] et sur la façon de l’utiliser dans un parcours, regardez ce [tutoriel vidéo](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html).
