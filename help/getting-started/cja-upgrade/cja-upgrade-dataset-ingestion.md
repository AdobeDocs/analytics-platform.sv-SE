---
title: Övervaka datauppsättningsåtkomster vid uppgradering till Customer Journey Analytics
description: Lär dig hur du övervakar datauppsättningsåtgången när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 35fcd213-d831-4da0-b946-f6f0d8561f60
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Övervaka datauppsättningsåtkomster vid uppgradering till Customer Journey Analytics {#monitor-ingestion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataset-validate"
>title="Validera data i datauppsättningen"
>abstract="Nu när du har konfigurerat implementeringen kan du använda aktivitetshanteraren för datauppsättning för att se inkapslade och misslyckade batchar. Om du ser primärt kapslade batchar är det här steget klart. Om du i första hand ser misslyckade batchar eller inga batchar kontrollerar du att implementeringen är korrekt när du skickar data till Adobe."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

När du har konfigurerat implementeringen av Web SDK eller API måste du kontrollera status för enskilda grupper för att verifiera att data hämtas till datauppsättningen.

1. I Experience Platform-gränssnittet väljer du **[!UICONTROL Monitoring]** i den vänstra navigeringen.

   Kontrollpanelen för övervakning visas. På den här kontrollpanelen kan du visa status för inkommande data från antingen batch- eller direktuppspelningsinmatning.

   <!-- insert screenshot -->

1. Välj **[!UICONTROL Batch end-to-end]** om du vill visa en lista över batchar.

   Om inga batchar visas kontrollerar du implementeringen för att säkerställa att data skickas korrekt till Adobe.

   <!-- insert screenshot -->

1. Välj batch-ID för en given datauppsättning och validera sedan att **[!UICONTROL Success]** visas i fältet **[!UICONTROL Status]**.

   Om **[!UICONTROL Failed]** visas i fältet **[!UICONTROL Status]** kontrollerar du att implementeringen är korrekt när du skickar data till Adobe.

   Upprepa det här steget för att verifiera status för varje batch.

{{upgrade-final-step}}

