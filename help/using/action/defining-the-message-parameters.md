---
product: adobe campaign
title: Définition des paramètres de message
description: Découvrez comment définir les paramètres de message
feature: Parcours
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: eb765d2f12ade397e124281f52213bb3e58263cb
workflow-type: ht
source-wordcount: '228'
ht-degree: 100%

---

# Définition des paramètres de message {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Dans la section **[!UICONTROL Paramètres de message]**, collez un exemple de payload JSON à envoyer au service externe.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Les noms de champ de la payload ne peuvent pas contenir de caractère &quot;.&quot; . Ils ne peuvent pas commencer par le caractère « $ ».

Vous aurez la possibilité de définir le type de paramètre (par exemple : string, integer, etc.).

Vous pourrez également préciser si le paramètre est une constante ou une variable :

* Le paramètre « Constante » signifie que la valeur du paramètre est définie dans le volet de configuration des actions par une personne ayant un rôle technique. La valeur reste identique dans tous les parcours et le marketeur ne la voit pas lors de l&#39;utilisation de l&#39;action personnalisée dans le parcours. Il peut s&#39;agir, par exemple, d&#39;un identifiant attendu par le système tiers. Dans ce cas, le champ situé à droite du bouton bascule Constante/Variable correspond à la valeur transmise.
* Le paramètre « Variable » signifie que la valeur du paramètre varie. Le marketeur qui utilise cette action personnalisée dans un parcours peut transmettre la valeur de son choix ou bien indiquer où récupérer la valeur de ce paramètre (à partir de l&#39;événement, d‘Adobe Experience Platform, etc.). Dans ce cas, le champ situé à droite du bouton bascule Constante/Variable correspond au libellé que le marketeur voit dans le parcours pour nommer ce paramètre.

![](../assets/customactionpayloadmessage2.png)
