---
product: adobe campaign
title: Modification des propriétés
description: Découvrez comment modifier des propriétés
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 100%

---

# Modification des propriétés {#concept_prq_wqt_52b}

Cliquez sur l&#39;icône en forme de crayon en haut à droite pour accéder aux propriétés du parcours.

Vous pouvez modifier le nom du parcours, ajouter une description, autoriser une rentrée, choisir les dates de début et de fin, et définir une durée **[!UICONTROL Temporisation et erreur]** si vous êtes administrateur.

Pour les parcours actifs, cet écran affiche la date de publication et le nom de l’utilisateur qui a publié le parcours.

La fonction **Copier les détails techniques** permet de copier les informations techniques relatives au parcours qui seront utiles à l&#39;équipe d&#39;assistance technique pour résoudre les problèmes. Les informations suivantes sont copiées : UID JourneyVersion, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](../assets/journey32.png)

## Entrée{#entrance}

Par défaut, les nouveaux parcours autorisent une rentrée. Vous pouvez désélectionner cette option pour les parcours « uniques » ; c’est le cas, par exemple, si vous souhaitez offrir un cadeau à un utilisateur ou une utilisatrice qui effectue sa première visite dans la boutique. Dans ce cas, vous ne voulez pas que le client puisse rejoindre de nouveau le parcours et rebénéficier de l&#39;offre.

Lorsqu&#39;un parcours « prend fin », l&#39;état **[!UICONTROL Fermé (aucune entrée)]** lui est attribué. Il n&#39;est alors plus accessible aux nouveaux individus. En revanche, la procédure suit son cours normal pour les personnes qui ont déjà intégré le parcours.

Au-delà de la temporisation globale par défaut de 30 jours, le statut du parcours passe à **Terminé**. Consultez cette [section](#global_timeout).

## Temporisation et erreur dans les activités du parcours {#timeout_and_error}

Lorsque vous modifiez une action ou une activité de condition, vous pouvez définir un autre chemin en cas d&#39;erreur ou de temporisation. Si la durée de traitement de l&#39;activité qui interroge un système tiers dépasse la durée de temporisation définie dans les propriétés du parcours (champ **[!UICONTROL Temporisation et erreur]**), le deuxième chemin d&#39;accès est choisi pour effectuer une éventuelle action de remplacement.

Les valeurs autorisées sont comprises entre 1 et 30 secondes.

Nous vous recommandons de définir une valeur très basse pour **[!UICONTROL Temporisation et erreur]** si votre parcours est sensible au temps (c&#39;est le cas, par exemple, lorsqu&#39;il convient de réagir à la position en temps réel d&#39;une personne), car l&#39;action ne peut pas être différée de plus de quelques secondes. Si le facteur temps revêt une importance moindre, vous pouvez définir un délai plus long afin d’accorder davantage de temps au système appelé pour envoyer une réponse valide.

[!DNL Journey Orchestration] utilise également une temporisation globale. Pour plus d&#39;informations, consultez la [section suivante](#global_timeout).

## Temporisation de parcours globale {#global_timeout}

Outre la [temporisation](#timeout_and_error) utilisée dans les activités de parcours, il existe une temporisation globale qui n&#39;est pas affichée dans l&#39;interface et qui ne peut pas être modifiée. Cette valeur de temporisation mettra fin à la progression des individus dans le parcours 30 jours après leur entrée. En d&#39;autres termes, la durée du parcours d&#39;un individu ne peut pas excéder 30 jours. Après cette période de temporisation de 30 jours, les données le concernant sont supprimées. Les individus qui sont encore actifs dans le parcours au terme de cette période de temporisation sont arrêtés et considérés comme des « erreurs » dans le cadre du reporting.

>[!NOTE]
>
>Sur le plan de la confidentialité, [!DNL Journey Orchestration] ne réagit pas directement aux demandes d’opt-out, de suppression ou d’accès. Cependant, la temporisation globale limite à 30 jours la durée d&#39;activité d&#39;un individu au sein d&#39;un parcours.

Compte tenu de la temporisation de 30 jours, lorsque la rentrée n’est pas autorisée, nous sommes dans l’impossibilité de garantir que le blocage de rentrée fonctionnera plus de 30 jours. En effet, étant donné que nous supprimons toutes les informations sur les personnes qui ont rejoint le parcours 30 jours après leur entrée, rien ne nous permet de savoir qu&#39;une personne l&#39;a déjà rejoint il y a plus de 30 jours.

## Fuseau horaire et fuseau horaire du profil {#timezone}

Les fuseaux horaires sont définis au niveau du parcours.

Vous pouvez entrer un fuseau horaire fixe ou utiliser les profils Adobe Experience Platform pour définir le fuseau horaire du parcours.

Pour plus d&#39;informations sur la gestion des fuseaux horaires, voir [cette page](../building-journeys/timezone-management.md).
