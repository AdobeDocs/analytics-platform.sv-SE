---
title: Behåll historiska data vid migrering till Customer Journey Analytics
description: Lär dig hur du behåller historiska data när du migrerar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 1d17151b-3a12-468e-9a4f-9e5994599570
source-git-commit: 7bc4425f11980780ab64a201029cd63e4bd7849c
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Steg 5: Behåll historiska data vid migrering

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större migreringsprocessen. Kontrollera att alla tidigare migreringssteg är slutförda.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 4 i **migrering**, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsväg](/help/getting-started/cja-migration/cja-migration-path.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 4: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform varierar beroende på vilken migreringsväg du väljer i steg 2. |
| <span class="preview">**Steg 4: Behåll historiska data**</span> | <span class="preview">De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta.</span> |
| **Steg 5: [Utför ytterligare implementeringsuppgifter](/help/getting-started/cja-getting-started.md)** | I nuläget i migreringsprocessen måste du utföra olika åtgärder innan du kan använda Customer Journey Analytics-miljön.<p>Dessa ytterligare uppgifter gäller migreringar från Adobe Analytics och nya implementeringar i Customer Journey Analytics.</p><p>Bland dessa uppgifter finns:</p><ul><li>Placera andra data i Experience Platform</li><li>Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics</li><li>Skapa datavyer</li><li>Portar för API-användning för rapportering</li><li>Redovisning av datafeeds och Data Warehouse</li><li>Migrera projekt och komponenter</li><li>Planera användarintroduktion</li></ul> <p>Mer information finns i [Komma igång med Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Välj något av följande alternativ för att behålla historiska data när du flyttar från Adobe Analytics till Customer Journey Analytics:

>[!IMPORTANT]
>
>När du väljer hur historiska data ska sparas kontaktar du din kontorepresentant på Adobe för att fastställa prissättningen.

## Använd Analytics Source Connector

Du kan använda [Källanslutning för analyser](/help/data-ingestion/analytics.md) att bevara historiska data. Oavsett vilken migreringsväg du väljer (även om du migrerar med Web SDK) kan du använda Analytics Source Connector för att behålla historiska data från din Adobe Analytics-miljö.

Du kan använda Analytics Source Connector för att behålla historiska data genom att föra in historiska data på sin egen dedikerade plats, skilt från aktuella data.

Källkopplingen för analyser måste fungera så länge du behöver tillgång till historiska data.

<!-- Another possibility in the future: Map historical data in a way that allows you to tie it to your new data.  Possible? Explain -->

## Underhåll din befintliga Adobe Analytics-implementering

Du kan behålla din befintliga Adobe Analytics-implementering tillsammans med din nya Customer Journey Analytics-implementering under en viss tidsperiod (till exempel ett år). Tänk på följande när du väljer det här alternativet:

* Data skulle inte vara tillgängliga i Experience Platform.

* Du bör planera för att avbryta Adobe Analytics-implementeringen när du har tillräckligt med data i Customer Journey Analytics.

## Utför sedan ytterligare implementeringsuppgifter

I nuläget i migreringsprocessen måste du utföra olika implementeringsuppgifter innan du kan börja använda Customer Journey Analytics-miljön.

Dessa ytterligare uppgifter gäller migreringar från Adobe Analytics och nya implementeringar i Customer Journey Analytics.

Bland dessa uppgifter finns:

* Placera andra data i Experience Platform

* Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics

* Skapa datavyer

* Portar för API-användning för rapportering

* Redovisning av datafeeds och användningsfall för Data Warehouse

* Migrera projekt och komponenter

* Planera användarintroduktion

Om du vill ha mer information börjar du med steg 2 i [Komma igång med Customer Journey Analytics](/help/getting-started/cja-getting-started.md).
