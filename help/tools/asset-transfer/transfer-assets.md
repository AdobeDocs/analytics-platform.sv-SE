---
title: Överför resurser
description: Lär dig överföra komponenter från en användare till en annan
hide: true
hidefromtoc: true
source-git-commit: 1a0422144b795be7f129b13208e93f8d3645a8e7
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 1%

---


# Överför resurser

Med verktyget Resursöverföring kan du överföra ägarskap av resurser till andra användare. Assets kan innehålla komponenter som projekt, filter, datumintervall, beräknade värden, anteckningar, aviseringar och schemalagda projekt.

Assets är ofta knutet till en enskild ägare och i vissa fall, t.ex. filter och beräknade värden, kan de inte redigeras eller delas ens av administratörer. När användare lämnar organisationen eller ändrar sin roll kan det bli nödvändigt att överföra ägarskapet av dessa resurser till andra användare för att säkerställa kontinuitet och lämplig åtkomst.

## Behörigheter

Resursöverföring kräver produktadministratörsbehörighet för Customer Journey Analytics.

## Överför resurser

1. Navigera till **[!UICONTROL Tools]** > **[!UICONTROL Asset Transfer]** i CJA.

   ![Menyobjekt för resursöverföring](/help/tools/asset-transfer/assets/asset-transfer.png)

1. I dialogrutan **[!UICONTROL Users]** söker du efter och väljer den användare som du vill överföra resurser från.

   >[!IMPORTANT]
   >
   >Du kan bara göra en 1:1-överföring från en användare till en annan användare. 1:N- eller många-till-1-överföringar stöds inte.


1. När du har valt en användare visas alternativet Överför resurser längst ned på skärmen.

   ![menyalternativ](/help/tools/asset-transfer/assets/after-selection.png)

1. Klicka på **[!UICONTROL Transfer assets]**.

1. På skärmen **[!UICONTROL Transfer assets]** väljer du först mottagaren som du vill överföra resurser till.

1. Gå igenom varje komponentmapp i den vänstra navigeringen för att välja enskilda komponenter eller alla resurser i en mapp som ska överföras.

   Observera att när du överför resurser från en administratör till en icke-administratör uppgraderas inte mottagaren till en administratör.

1. Om du vill markera _alla_ resurser i en mapp markerar du kryssrutan bredvid **[!UICONTROL Name]** högst upp i tabellen.

   ![välj resurser att överföra](/help/tools/asset-transfer/assets/select-assets.png)

1. Klicka på **[!UICONTROL Transfer]** överst till höger när du har gjort alla dina val.

1. Klicka på **[!UICONTROL Confirm]** när bekräftelsemeddelandet visas.

   >[!IMPORTANT]
   >
   >Stäng inte skärmen under överföringen för att undvika att processen avbryts. Detta ger en smidig överföringsupplevelse.

## Överför resurser under uppgradering från Adobe Analytics till Customer Journey Analytics

Ett av de största användningsområdena för överföring av mediefiler är vid uppgradering från Adobe Analytics till Customer Journey Analytics.

Med funktionen [Komponentmigrering](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/component-migration) i Adobe Analytics kan du migrera administratörsägda projekt till andra administratörer. Alla komponenter som ingår i dessa projekt återskapas sedan i Customer Journey Analytics och mottagaradministratören äger alla dessa komponenter, oavsett vem som skapade dem.

Med det här verktyget kan administratörer sedan omtilldela komponenter till sina rättsinnehavare.

## Exportera till CSV

Du kan exportera en lista över resurser som överförts från en användare till en annan till en CSV-fil.

<!---## Unknown users

All previously deleted users appear under one unknown user entry, along with all their orphan components. These components can be transferred to a new recipient. This feature will be available in January.-->