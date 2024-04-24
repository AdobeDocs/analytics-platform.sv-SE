---
title: Portar för API-användning för rapportering vid migrering till Customer Journey Analytics
description: Lär dig portera API-användning från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: d26a6956-870f-44f2-9c32-f732bff17737
source-git-commit: 8b7fedb9625ba60af1fea0b1580d32d2366081b8
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Steg 7: Porten för API-användningen för rapportering vid migrering till Customer Journey Analytics

+++Expandera det här avsnittet för att se var informationen på den här sidan passar in i den större migreringsprocessen. Kontrollera att alla tidigare migreringssteg är slutförda.

Innan du fortsätter med det här avsnittet måste du först kontrollera att du har slutfört alla tidigare migreringsåtgärder.

Informationen på den här sidan omfattar steg 7, vilket framgår av tabellen nedan:

| Migreringsaktivitet | Information |
|---------|----------|
| **Steg 1: [Kom igång med migreringen](/help/getting-started/cja-migration/cja-migration-getstarted.md)** | Lär dig fördelarna med att migrera till Adobe Analytics och den grundläggande migreringsprocessen. |
| **Steg 2: [Välj migreringsväg](/help/getting-started/cja-migration/cja-migration-path.md)** | Det finns olika metoder för att migrera till Customer Journey Analytics. Välj den metod som är bäst för er organisation, beroende på er nuvarande Adobe Analytics-miljö och era långsiktiga mål. |
| **Steg 3: [Skicka data till Adobe Experience Platform](/help/getting-started/cja-migration/cja-migration-send-to-platform.md)** | Processen för att skicka data till Adobe Experience Platform varierar beroende på vilken migreringsväg du väljer i steg 2. |
| **Steg 4: [Behåll historiska data](/help/getting-started/cja-migration/cja-migration-historical-data.md)** | De flesta organisationer måste bevara sina historiska Adobe Analytics-data under en viss tid. Det finns olika alternativ för att uppnå detta. |
| **Steg 5: [Utför ytterligare implementeringsuppgifter](/help/getting-started/cja-getting-started.md)** | I nuläget i migreringsprocessen måste du utföra olika åtgärder innan du kan använda Customer Journey Analytics-miljön.<p>Dessa ytterligare uppgifter gäller migreringar från Adobe Analytics och nya implementeringar i Customer Journey Analytics.</p><p>Bland dessa uppgifter finns:</p><ul><li>Placera andra data i Experience Platform</li><li>Skapa anslutningar mellan plattformsdatauppsättningar och Customer Journey Analytics</li><li>Skapa datavyer</li><li>Portar för API-användning för rapportering</li><li>Redovisning av datafeeds och Data Warehouse</li><li>Migrera projekt och komponenter</li><li>Planera användarintroduktion</li></ul> <p>Mer information finns i [Komma igång med Customer Journey Analytics](/help/getting-started/cja-getting-started.md). |

{style="table-layout:auto"}

+++

Skicka API-användningen för rapportering från Adobe Analytics API till Customer Journey Analytics.

Rapporterings-API:t för Customer Journey Analytics har samma format, men använder en annan underdomän.

Se slutpunktshandboken för Adobe Analytics och Customer Journey Analytics.

De flesta API-anrop kan enkelt översättas från Adobe Analytics till Customer Journey Analytics.

Lägg till API:t för Customer Journey Analytics i deras API-projekt.

Lägg till IMS-organisations-ID i huvudet för deras API-anrop.

cja.adobe.io vs analytics.adobe.io

Ytterligare rubriker

## Ersätt sedan datafeeds och Data Warehouse

Bestäm hur exportalternativen i Customer Journey Analytics ska användas för att [ersätta funktionerna för dataflöden och Data Warehouse](/help/getting-started/cja-migration/cja-migration-export-options.md) du använde i Adobe Analytics.
