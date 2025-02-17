---
product: adobe campaign
title: Définition de la clé d’événement
description: Découvrez comment définir la clé d’événement
feature: Journeys
role: User
level: Intermediate
exl-id: 79bcf562-f971-42f1-a607-94a2510c4a07
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---

# Définition de la clé d’événement {#concept_ond_hqt_52b}

La clé correspond au champ ou à la combinaison de champs faisant partie des données de payload de l&#39;événement et permettant au système d&#39;identifier la personne associée à l&#39;événement. Il peut s&#39;agir de l&#39;Experience Cloud ID, d&#39;un ID CRM ou encore d&#39;une adresse e-mail.

Si vous prévoyez d&#39;exploiter les données stockées dans la base de données de profils clients en temps réel, vous devez sélectionner, comme clé d&#39;événement, les informations que vous avez définies en tant qu&#39;identité d&#39;un profil dans le [service de profil client en temps réel](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=fr).

Le système pourra ainsi effectuer la réconciliation entre l&#39;événement et le profil de l&#39;individu. Si vous sélectionnez un schéma doté d&#39;une identité principale, les champs **[!UICONTROL Clé]** et **[!UICONTROL Espace de noms]** sont déjà renseignés. Si aucune identité n&#39;est définie, _identityMap > id_ est sélectionné comme clé principale. Vous devez ensuite sélectionner un espace de noms et la clé sera préremplie (sous le champ **[!UICONTROL Espace de noms]**) à l&#39;aide de _identityMap > id_.

Lors de la sélection de champs, les champs d&#39;identité principale sont balisés.

![](../assets/primary-identity.png)

Si vous devez utiliser une autre clé, telle qu&#39;un ID CRM ou une adresse e-mail, vous devez l&#39;ajouter manuellement :

1. Cliquez dans le champ **[!UICONTROL Clé]** ou sur l&#39;icône représentant un crayon.

   ![](../assets/journey16.png)

1. Sélectionnez le champ choisi comme clé dans la liste des champs de payload. Vous pouvez également basculer vers l&#39;éditeur d&#39;expression avancé pour créer des clés plus complexes (une concaténation de deux champs des événements, par exemple). Voir ci-dessous.

   ![](../assets/journey20.png)

Lorsque l&#39;événement est reçu, la valeur de la clé permet au système d&#39;identifier la personne qui y est associée. Associée à un espace de noms (voir [cette page](../event/selecting-the-namespace.md)), la clé peut être utilisée pour exécuter des requêtes sur Adobe Experience Platform. Voir [cette page](../building-journeys/about-orchestration-activities.md).
La clé sert également à vérifier qu&#39;une personne se trouve dans un parcours. En effet, une personne ne peut se trouver à deux endroits différents dans le même parcours. Par conséquent, le système n&#39;autorise pas qu&#39;une même clé (CRMID=3224, par exemple) se trouve à des endroits différents dans un même parcours.

Vous avez également accès aux fonctions d&#39;expression avancées (**[!UICONTROL Mode avancé]**) si vous souhaitez effectuer des manipulations supplémentaires. Ces fonctions vous permettent de manipuler les valeurs utilisées pour exécuter des requêtes spécifiques, comme modifier des formats, exécuter des concaténations de champs, prendre uniquement en compte une partie d&#39;un champ (les 10 premiers caractères, par exemple), etc. Voir [cette page](../expression/expressionadvanced.md).
