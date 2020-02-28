---
title: Modification des propriétés
description: Découvrez comment modifier des propriétés
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 76369cd714c513e0038278ad058bf1ba43fcd240

---



# Modification des propriétés {#concept_prq_wqt_52b}

Cliquez sur l’icône en forme de crayon en haut à droite pour accéder aux propriétés du parcours.

You can change the name of the journey, add a description, allow re-entrance, choose start and end dates and define a **[!UICONTROL Timeout and error]** duration if you are admin.

![](../assets/journey32.png)

## Entrée{#entrance}

Par défaut, les nouveaux parcours autorisent une rentrée. Vous pouvez désélectionner cette option pour les parcours « uniques » ; c’est le cas, par exemple, si vous souhaitez offrir un cadeau à un utilisateur qui effectue sa première visite dans la boutique. Dans ce cas, vous ne voulez pas que le client puisse effectuer une rentrée dans le parcours et bénéficier à nouveau de l’offre.

When a journey &quot;ends&quot;, it will have the status **[!UICONTROL Finished]**. Il n’est alors plus accessible aux nouveaux clients. En revanche, la procédure suit son cours normal pour les personnes qui ont déjà intégré le parcours.

## Délai dépassé et erreur dans les activités du parcours {#timeout_and_error}

Lorsque vous modifiez une action ou une activité de condition, vous pouvez définir un autre chemin en cas d’erreur ou de dépassement du délai. If the processing of the activity interrogating a third-party system exceeds the timeout duration defined in the journey&#39;s properties (**[!UICONTROL Timeout and  error]** field), the second path will be chosen to perform a potential fallback action.

Les valeurs autorisées sont comprises entre 1 et 30 secondes.

We recommend that you define a very short **[!UICONTROL Timeout and error]** value if your journey is time sensitive (example: reacting to the real-time location of a person) because you cannot delay your action for more than a few seconds. Si le facteur temps revêt une importance moindre, vous pouvez définir un délai plus long afin d’accorder davantage de temps au système appelé pour envoyer une réponse valide.

Journey Orchestration utilise également un délai d’expiration global. Pour plus d’informations, consultez la [section suivante](#global_timeout).

## Délai de parcours global {#global_timeout}

Outre le [délai d’expiration](#timeout_and_error) utilisé dans les activités de parcours, il existe un délai d’expiration global qui n’est pas affiché dans l’interface et qui ne peut pas être modifié. Cette valeur mettra fin à la progression des utilisateurs dans le parcours 30 jours après leur entrée. En d’autres termes, la durée du parcours d’un individu ne peut pas excéder 30 jours. Après cette période de 30 jours, les données le concernant sont supprimées. Les personnes qui sont encore actives dans le parcours au terme de cette période sont arrêtées et considérées comme des « erreurs » dans le cadre du reporting.

>[!NOTE]
>
>Sur le plan de la confidentialité, Journey Orchestration ne réagit pas directement aux demandes d’opt-out, de suppression ou d’accès. Cependant, le délai d’expiration global limite à 30 jours la durée d’activité d’un individu au sein d’un parcours.

Compte tenu du délai d’expiration de 30 jours, lorsque la rentrée n’est pas autorisée, nous sommes dans l’impossibilité de garantir que le blocage de rentrée fonctionnera plus de 30 jours. En effet, étant donné que nous supprimons toutes les informations sur les personnes qui ont intégré le parcours 30 jours après leur entrée, rien ne nous permet de savoir qu’une personne y a déjà accédé il y a plus de 30 jours.

## Fuseau horaire et fuseau horaire du profil {#timezone}

Les fuseaux horaires sont définis au niveau du parcours.

Vous pouvez entrer un fuseau horaire fixe ou utiliser les profils de plateforme d’expérience pour définir le fuseau horaire du voyage.

Pour plus d’informations sur la gestion des fuseaux horaires, voir [](../building-journeys/timezone-management.md).
