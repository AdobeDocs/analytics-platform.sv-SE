---
title: Skapa ett schema för Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: c6d49ca4-3d04-4c0f-accd-8666a587109d
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Lägg till plattform som en tjänst i ditt datastream {#upgrade-addplatform-datastream}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-addplatform-datastream"
>title="Lägg till Adobe Experience Platform som en tjänst i datastream"
>abstract="En datastream behöver en eller flera tjänster att skicka data till. Konfigurera Adobe Experience Platform som en tjänst i din datastream.<br><br>Det är en enkel process att lägga till tjänster i ett datastream. Det tar bara några minuter att slutföra."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

Det bör redan finnas ett datastream innan du slutför stegen i det här avsnittet. När och hur datastream skapades beror på din Adobe Analytics-implementering, enligt följande:

* Om Adobe Analytics-implementeringen använder Web SDK eller Web SDK Extension var datastream tillgänglig för din Adobe Analytics-miljö, före uppgraderingsprocessen.

* För andra Adobe Analytics-implementeringar är det en del av uppgraderingsprocessen att skapa en datastream, vilket beskrivs i [Skapa en datastream som ska användas med Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-datastream.md).

När datastream är tillgänglig måste du lägga till Platform som en tjänst:

1. I Adobe Experience Platform-gränssnittet väljer du **[!UICONTROL Datastreams]** från [!UICONTROL DATA COLLECTION] i den vänstra listen.

1. Välj det datastream som tidigare konfigurerats. <!--true?-->

1. Välj **[!UICONTROL Add Service]**.

1. I [!UICONTROL Add Service screen]:

   1. Välj **[!UICONTROL Adobe Experience Platform]** i listan [!UICONTROL Service].

   1. Kontrollera att **[!UICONTROL Enabled]** är markerat.

   1. Välj datauppsättningen i listan [!UICONTROL Event Dataset].

      ![Datastream AEP-tjänst](./assets/datastream-aep-service.png)

   1. Lämna de andra inställningarna och välj **[!UICONTROL Save]** för att spara dataströmmen.

   Din datastream är nu konfigurerad för att vidarebefordra data som samlats in från din webbplats till din datauppsättning i Adobe Experience Platform.

   Mer information om hur du konfigurerar ett datastam och hur du hanterar känsliga data finns i [Översikt över datastreams](https://experienceleague.adobe.com/docs/experience-platform/datastreams/overview.html?lang=sv-SE).

{{upgrade-final-step}}
