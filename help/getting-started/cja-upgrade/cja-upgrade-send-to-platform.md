---
title: Skicka data till Adobe Experience Platform vid migrering till Customer Journey Analytics
description: Skicka data till Adobe Experience Platform vid migrering till Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
exl-id: d9d7f186-9077-4372-94ad-8dd5b97779ca
source-git-commit: 765b6863cdafa06b54b76fbf0983afb4c14c21d4
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 0%

---

# Steg 3: Skicka data till Adobe Experience Platform vid uppgradering

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större uppgraderingsprocessen. Se till att alla tidigare uppgraderingssteg är slutförda.

Innan du fortsätter med det här avsnittet bör du kontrollera att du har slutfört alla tidigare uppgraderingsuppgifter.

Informationen på den här sidan omfattar steg 3 i uppgraderingsprocessen, vilket framgår av tabellen nedan:

| Uppgradering | Information |
|---------|----------|
| **Steg 1: [Kom igång med uppgraderingen](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Lär dig fördelarna med att uppgradera till Customer Journey Analytics och den grundläggande uppgraderingsprocessen. |
| **Steg 2: [Välj uppgraderingssökväg](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Det finns olika metoder för uppgradering till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| <span class="preview">**Steg 3: Skicka data till Adobe Experience Platform**</span> | <span class="preview">Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken uppgraderingssökväg du väljer i steg 2.</span> |
| **Steg 4: [Behåll historiska data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 5: [Utför ytterligare implementeringsuppgifter](/help/getting-started/cja-getting-started.md)** | I uppgraderingsprocessen måste du utföra olika uppgifter innan Customer Journey Analytics-miljön kan användas.<p>Dessa ytterligare uppgifter gäller uppgraderingar från Adobe Analytics och nya Customer Journey Analytics-implementeringar.</p><p>Bland dessa uppgifter finns:</p><ul><li>Lägg in andra data i Experience Platform</li><li>Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics</li><li>Skapa datavyer</li><li>Portar för API-användning för rapportering</li><li>Redovisning av datafeeds och Data Warehouse</li><li>Migrera projekt och komponenter</li><li>Planera användarintroduktion</li></ul> <p>Mer information finns i [Customer Journey Analytics Getting Started](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

>[!AVAILABILITY]
>
>Informationen på den här sidan ersätts med följande mer omfattande uppgraderingsinformation: <ul><li>**Rekommenderade uppgraderingssteg**<p>Mer information finns i [Rekommenderad sökväg vid uppgradering från Adobe Analytics till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).</p></li><li>**Customer Journey Analytics Upgrade Guide**<p>Det finns en ny uppgraderingsguide som dynamiskt genererar uppgraderingssteg som är skräddarsydda för just er organisation och era unika omständigheter.</p><p>Om du vill få åtkomst till guiden från Customer Journey Analytics väljer du fliken **[!UICONTROL Workspace]** och sedan **[!UICONTROL Upgrade to Customer Journey Analytics]** i den vänstra panelen. Följ instruktionerna på skärmen.</p></li></ul>

När du har [valt den uppgraderingssökväg](/help/getting-started/cja-upgrade/cja-upgrade-path.md) som passar din organisation kan du börja skicka data till Adobe Experience Platform för att göra den tillgänglig i Customer Journey Analytics.

Processen för att skicka data till Experience Platform för varje uppgraderingsväg visas nedan. Följ länkarna i tabellen för detaljerad konfigurationsinformation.

| Uppgraderingssökväg | Process för att skicka data till plattformen | Ytterligare information |
|---------|----------|----------|
| Ny implementering av Experience Platform Web SDK | <ol><li>Skapa ett XDM-schema för din organisation.<p>Samarbeta med datagruppen för att identifiera organisationens idealiska schemadesign för Customer Journey Analytics.</p></li><li>Experience Platform Web SDK.</li><li>Skicka data till plattformen.</li></ol><p>Mer information om de här stegen finns i [Importera data via Adobe Experience Platform Web SDK](/help/data-ingestion/aepwebsdk.md). | Eftersom detta är en ny implementering av Experience Platform Web SDK behövs ingen schemamappning eftersom du måste skapa schemat som ett av de första stegen under implementeringen. |
| Migrera din Adobe Analytics-implementering till Web SDK | <ol><li>Flytta Adobe Analytics-implementeringen till Experience Platform Web SDK och validera sedan att allt fungerar i Adobe Analytics.<p>Om du vill ha mer information om hur du gör det använder du följande resurser, beroende på om din nuvarande implementering är ett kodtillägg för Analytics (Analyser) eller AppMeasurement:</p><ul><li>Om du använder taggtillägget Analytics läser du [Migrera från taggtillägget Adobe Analytics till taggtillägget Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk)</li><li>Om du använder AppMeasurement läser du [Migrera från AppMeasurement till Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk)</li></ul><li>[Skapa ett XDM-schema för din organisation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Samarbeta med datagruppen för att identifiera organisationens idealiska schemadesign för Customer Journey Analytics.</p></li><li>[Använd Data Prep för att mappa alla fält i dataobjektet till ditt XDM-schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li><li>Börja skicka data till plattformen genom att [konfigurera ett datastream](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-datastream).</li></ol> |  |
| Konfigurera din befintliga Adobe Analytics Web SDK-implementering för att skicka data till plattformen | <ol><li>Börja skicka data till plattformen genom att [konfigurera ett datastream](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream).<p>Eftersom din Adobe Analytics-implementering redan använder Experience Platform Web SDK kan du ignorera de andra avsnitten i [Inkludera data via Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk).</p><p>Om du redan skickar data till Platform med din Adobe Analytics-implementering är det här steget inte obligatoriskt. Du behöver bara skapa en anslutning mellan plattformsdatauppsättningar och Customer Journey Analytics, vilket beskrivs senare i den här processen.</p></li><li>(Valfritt) [Skapa ett XDM-schema för din organisation](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk#set-up-a-schema-and-dataset).<p>Samarbeta med datagruppen för att identifiera organisationens idealiska schemadesign för Customer Journey Analytics.</p><p>Obs! Information om fördelarna med att skapa ett XDM-schema finns i [Välj ditt schema](/help/getting-started/cja-upgrade/cja-upgrade-path.md#choose-your-schema).</li><li>(Villkorligt) Om du har skapat ett XDM-schema kan du [använda Dataprep för att mappa alla fält i dataobjektet till ditt XDM-schema](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home).</li></ol> |  |
| Använda Analytics-källkopplingen | [Importera och använda data från traditionella Adobe Analytics](/help/data-ingestion/analytics.md) | Adobe Analytics-data mappas automatiskt till XDM-schemat när du använder Analytics-källkopplingen. Ytterligare mappning krävs inte. |

## Behåll sedan historiska data

Bestäm sedan hur du [ska behålla tidigare Adobe Analytics-data](/help/getting-started/cja-upgrade/cja-upgrade-historical-data.md).
