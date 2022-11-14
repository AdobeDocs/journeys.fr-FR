---
product: adobe campaign
title: Gestion des fuseaux horaires
description: En savoir plus sur la gestion des fuseaux horaires
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 100%

---

# Gestion des fuseaux horaires {#timezone_management}

Vous pouvez définir un fuseau horaire dans les [propriétés](../building-journeys/changing-properties.md) de votre parcours.

Pour accéder aux propriétés, cliquez sur l&#39;icône en forme de crayon dans le coin supérieur droit de l&#39;écran.

Ce fuseau horaire sera utilisé pour chaque activité du parcours contenant un élément temporel tel que :

* [Condition de temps](../building-journeys/condition-activity.md#time_condition)
* [Condition de date](../building-journeys/condition-activity.md#date_condition)
* [Attente personnalisée](../building-journeys/wait-activity.md#custom)

Vous pouvez sélectionner un fuseau horaire ou choisir d’utiliser celui défini dans le profil utilisateur.

>[!NOTE]
>
>Le fuseau horaire de profil fonctionne avec le champ **timeZone** existant dans le groupe de champs **Détails des préférences**.

## Définition d&#39;un fuseau horaire fixe {#fixed-timezone}

Le fuseau horaire peut également être fixe. Effacez le fuseau horaire prédéfini et sélectionnez-en un dans la liste déroulante. Si vous utilisez un fuseau horaire fixe, il sera identique pour tous les individus qui participent au parcours.

Pour cela, dans **[!UICONTROL Propriétés]**, sélectionnez un fuseau horaire.

![](../assets/journey72.png)

## Utilisation de profils pour définir le fuseau horaire du parcours {#timezone-from-profiles}

Si l’événement d’entrée du parcours comporte un espace de noms, ce qui signifie que le parcours peut accéder au service de profil client en temps réel d’Adobe Experience Platform, vous pouvez utiliser le fuseau horaire défini au niveau du profil. Pour cela, dans **Propriétés**, cochez la case **Utiliser le fuseau horaire du profil dans les attentes et conditions**. Cette option n’est pas cochée par défaut.

Si un fuseau horaire a été défini pour un profil, il sera récupéré et utilisé par le parcours. Dans le cas contraire, le fuseau horaire utilisé sera celui défini dans le champ du fuseau horaire.

![](../assets/journey73.png)

## Utilisation des fuseaux horaires dans les expressions {#timezone-in-expressions}

Les dates de début et de fin d&#39;un parcours ne peuvent pas être liées à un fuseau horaire spécifique. Elles sont automatiquement associées à celui de l&#39;instance.
