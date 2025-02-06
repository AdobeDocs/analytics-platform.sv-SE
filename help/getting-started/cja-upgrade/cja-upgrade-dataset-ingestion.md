---
title: Övervaka datauppsättningsintag vid uppgradering till Customer Journey Analytics
description: Lär dig hur du övervakar datauppsättningsåtgången när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 3b1012a302200192fd31fd6a9ed94f96323eb595
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 0%

---

# Övervaka datauppsättningsintag vid uppgradering till Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validera data i datauppsättningen"
>abstract="Nu när du har konfigurerat implementeringen av Web SDK kan du använda aktivitetshanteraren för datauppsättning för att se inkapslade och misslyckade batchar. Om du ser primärt kapslade batchar är det här steget klart. Om du i första hand ser misslyckade batchar eller inga batchar bör du kontrollera din Web SDK-implementering för att säkerställa att data skickas korrekt till Adobe.<br><br>Om allt var korrekt och felfritt kan det här steget utföras på mindre än en dag. Om det finns flera datainsamlingsproblem kan det ta särskilt lång tid att felsöka dem."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Följ bara stegen på den här sidan när du har slutfört alla tidigare uppgraderingssteg. Du kan följa de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller följa uppgraderingsstegen som har skapats dynamiskt för din organisation med uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).
>
>När du är klar med stegen på den här sidan fortsätter du med de rekommenderade uppgraderingsstegen eller de dynamiskt genererade uppgraderingsstegen.

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

När du har konfigurerat implementeringen av Web SDK måste du kontrollera status för enskilda batchar för att verifiera att data hämtas till datauppsättningen.

1. I användargränssnittet för Experience Platform väljer du **[!UICONTROL Monitoring]** i den vänstra navigeringen.

   Kontrollpanelen för övervakning visas. På den här kontrollpanelen kan du visa status för inkommande data från antingen batch- eller direktuppspelningsinmatning.

   <!-- insert screenshot -->

1. Välj **[!UICONTROL Batch end-to-end]** om du vill visa en lista över batchar.

   Om inga grupper visas kontrollerar du att Web SDK-implementeringen är korrekt när du skickar data till Adobe.

   <!-- insert screenshot -->

1. Välj batch-ID för en given datauppsättning och validera sedan att **[!UICONTROL Success]** visas i fältet **[!UICONTROL Status]**.

   Om **[!UICONTROL Failed]** visas i fältet **[!UICONTROL Status]** kontrollerar du att Web SDK-implementeringen är korrekt när data skickas till Adobe.

   Upprepa det här steget för att verifiera status för varje batch.

1. Följ de [rekommenderade uppgraderingsstegen](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) eller de [dynamiskt genererade uppgraderingsstegen](https://gigazelle.github.io/cja-ttv/).

