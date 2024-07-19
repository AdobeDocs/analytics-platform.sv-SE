---
title: Behåll historiska data vid uppgradering till Customer Journey Analytics
description: Lär dig hur du behåller historiska data när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: c64f7a1676f4fd3712e618e26357f430e7d9f019
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 0%

---

# Steg 4: Behåll historiska data vid uppgradering

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större uppgraderingsprocessen. Se till att alla tidigare uppgraderingssteg är slutförda.

Innan du fortsätter med det här avsnittet bör du kontrollera att du har slutfört alla tidigare uppgraderingsuppgifter.

Informationen på den här sidan omfattar steg 4 i uppgraderingsprocessen, vilket framgår av tabellen nedan:

| Uppgradering | Information |
|---------|----------|
| **Steg 1: [Kom igång med uppgraderingen](/help/getting-started/cja-upgrade/cja-upgrade-getstarted.md)** | Läs om fördelarna med att uppgradera till Customer Journey Analytics och den grundläggande uppgraderingsprocessen. |
| **Steg 2: [Välj uppgraderingssökväg](/help/getting-started/cja-upgrade/cja-upgrade-path.md)** | Det finns olika metoder för uppgradering till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-upgrade/cja-upgrade-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform skiljer sig åt beroende på vilken uppgraderingsväg du väljer i steg 2. |
| <span class="preview">**Steg 4: Behåll historiska data**</span> | <span class="preview">De flesta organisationer måste behålla sina tidigare Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta.</span> |
| **Steg 5: [Utför ytterligare implementeringsuppgifter](/help/getting-started/cja-getting-started.md)** | I uppgraderingsprocessen måste du utföra olika uppgifter innan du kan börja använda Customer Journey Analytics-miljön.<p>Dessa ytterligare uppgifter gäller uppgraderingar från Adobe Analytics och nya implementeringar i Customer Journey Analytics.</p><p>Bland dessa uppgifter finns:</p><ul><li>Placera andra data i Experience Platform</li><li>Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics</li><li>Skapa datavyer</li><li>Portar för API-användning för rapportering</li><li>Redovisning av datafeeds och Data Warehouse</li><li>Migrera projekt och komponenter</li><li>Planera användarintroduktion</li></ul> <p>Mer information finns i [Komma igång för Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Välj något av följande alternativ för att behålla historiska data när du flyttar från Adobe Analytics till Customer Journey Analytics:

>[!IMPORTANT]
>
>När du väljer hur historiska data ska sparas kontaktar du din kontorepresentant på Adobe för att fastställa prissättningen.

## Använda Analytics Source Connector

Du kan använda [Analytics Source Connector](/help/data-ingestion/analytics.md) för att behålla historiska data. Oavsett vilken uppgraderingsväg du väljer (även om du uppgraderar med Web SDK) kan du använda Analytics Source Connector för att spara historiska data från din Adobe Analytics-miljö.

Du kan använda Analytics Source Connector för att behålla historiska data genom att föra in historiska data på sin egen dedikerade plats, skilt från aktuella data.

Analytics Source Connector måste fungera så länge du behöver tillgång till historiska data.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Underhåll din befintliga Adobe Analytics-implementering

Du kan behålla din befintliga Adobe Analytics-implementering tillsammans med din nya Customer Journey Analytics-implementering under en viss tidsperiod (till exempel ett år). Tänk på följande när du väljer det här alternativet:

* Data skulle inte vara tillgängliga i Experience Platform.

* Du bör planera för att avbryta Adobe Analytics-implementeringen när du har tillräckligt med data i Customer Journey Analytics.

## Utför sedan ytterligare implementeringsuppgifter

I uppgraderingsprocessen måste du utföra olika implementeringsuppgifter innan du kan börja använda Customer Journey Analytics-miljön.

Dessa ytterligare uppgifter gäller uppgraderingar från Adobe Analytics och nya implementeringar i Customer Journey Analytics.

Bland dessa uppgifter finns:

* Placera andra data i Experience Platform

* Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics

* Skapa datavyer

* Portar för API-användning för rapportering

* Redovisning av datafeeds och användningsfall för Data Warehouse

* Migrera projekt och komponenter

* Planera användarintroduktion

Om du vill ha mer information börjar du med steg 2 i [Komma igång för Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
