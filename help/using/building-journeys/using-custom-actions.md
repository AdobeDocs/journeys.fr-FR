---
product: adobe campaign
title: Utiliser des actions personnalisées
description: En savoir plus sur les activités d’action
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 100%

---

# Utilisation d’actions personnalisées {#section_f2c_hbg_nhb}

Le volet de configuration des activités affiche les paramètres de configuration de l’URL et les paramètres d’authentification configurés pour l’action personnalisée. [En savoir plus](../action/about-custom-action-configuration.md).

## Configuration d&#39;URL

### Chemin dynamique

Si l’URL contient un chemin dynamique, spécifiez le chemin dans le champ **[!UICONTROL Chemin]**.

>[!NOTE]
>
>Vous ne pouvez pas configurer la partie statique de l’URL dans le parcours, mais dans la configuration globale de l’action personnalisée. [En savoir plus](../action/about-custom-action-configuration.md).

Pour concaténer des champs et des chaînes de texte brut, utilisez les fonctions String ou le signe plus (+) dans l’éditeur d’expression avancé. Placez les chaînes de texte brut entre guillemets simples (’) ou entre guillemets doubles (&quot;). [En savoir plus](../expression/expressionadvanced.md).

Ce tableau présente un exemple de configuration :

| Champ | Valeur |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Chemin | `The id of marketingCampaign + '/messages'` |

L’URL concaténée se présente comme suit :

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;Identifiant de campagne\>`/messages`

![](../assets/journey-custom-action-url.png)

### En-têtes

La section **[!UICONTROL Configuration de l’URL]** affiche les champs d’en-tête dynamiques, mais pas les champs d’en-tête constants. Les champs d’en-tête dynamique sont des champs d’en-tête HTTP dont la valeur est configurée comme variable. [En savoir plus](../action/about-custom-action-configuration.md).

Si nécessaire, spécifiez la valeur des champs d’en-tête dynamique :

1. Sélectionnez l’action personnalisée dans le parcours.
1. Dans le volet de configuration, cliquez sur l’icône en forme de crayon en regard du champ d’en-tête de la section **[!UICONTROL Configuration de l’URL]**.

   ![](../assets/journey-dynamicheaderfield.png)

1. Sélectionnez un champ et cliquez sur **[!UICONTROL OK]**.

## Paramètres d’action

Dans la section **[!UICONTROL Paramètres d’action]**, vous verrez les paramètres de message définis comme _« Variable »_. Pour ces paramètres, vous pouvez définir où obtenir ces informations (événements, sources de données, par exemple), transmettre des valeurs manuellement ou utiliser l’éditeur d’expression avancé pour des cas d’utilisation avancés. Les cas d’utilisation avancés peuvent être la manipulation de données et d’autres utilisations de la fonction. [En savoir plus](../expression/expressionadvanced.md).

**Rubriques connexes**

[Configurer une action](../action/about-custom-action-configuration.md)
