---
title: Begär sammanfogning
description: Hur man begär sammanfogning
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: 9ace0679796c3a813b1fbd97c62c20faf64db211
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# Begär sammanfogning


>[!IMPORTANT]
>
>Framställning genom Adobe behövs inte längre och den här metoden är inaktuell. [Aktivera sammanslagning i anslutningsgränssnittet](use-stitching-ui.md).
>



När din organisation uppfyller alla [krav](overview.md#prerequisites) och förstår vanliga [begränsningar](overview.md#limitations) och att sammanfoga metodspecifika ([fältbaserade](fbs.md#limitations)- och [diagrambaserade](gbs.md#limitations)) begränsningar, kan du följa de här stegen för att begära och börja använda sammanfogning i Customer Journey Analytics.

## Välj alternativ

Det Customer Journey Analytics-paket som du är berättigad till avgör vilka metoder som är tillgängliga för sammanfogning, alternativ för inledande varaktighet för efterfyllning, fönster för uppspelningsfrekvens och maximalt antal datauppsättningar som tillåts för sammanfogning. Mer information finns i [Customer Journey Analytics produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html). Bestäm vilka alternativ som är tillgängliga innan du begär support.

| | Customer Journey Analytics<br/>Välj | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Tillgängliga sammanfogningsmetoder | Fältbaserad stygn | Fältbaserad häftning<br/>Diagrambaserad häftning | Fältbaserad häftning<br>Diagrambaserad häftning</li> |
| Varaktighet för engångssammanfogning av bakfyllning | 13 månader | 13 månader | 25 månader |
| Fönster för uppspelning och uppspelningsfrekvens | 1 dag, varje dag<br/>upp till 7 dagar, varje vecka | 1 dag, varje dag<br/>upp till 14 dagar, varje vecka | 1 dag, varje dag<br/>upp till 30 dagar, varje vecka |
| Högsta antal datauppsättningar som tillåts för sammanfogning | 5 | 15 | 50 |

## Begär support

1. Kontakta Adobe kundsupport med följande information:

   - En begäran om aktivering av sammanfogning.
   - Datauppsättnings-ID för den datauppsättning som du vill ändra inmatning för.
   - Kolumnnamnet (identitetssökväg och namnutrymme) för det beständiga ID:t för den önskade datauppsättningen (identifieraren som visas på varje rad).
   - Om datauppsättningen stöder `identityMap`:
      - För fältbaserad sammanfogning anger du namnutrymmet för både beständiga och person-ID:n.
      - För diagrambaserad sammanfogning anger du namnutrymmet för det beständiga ID:t och det identitetsnamnutrymme som ska användas för att fråga efter identitetsdiagrammet.
   - Om datauppsättningen inte stöder `identityMap`:
      - För fältbaserad sammanfogning är kolumnnamnet för person-ID:t för den önskade datauppsättningen (personidentifieraren, som också fungerar som en länk mellan datauppsättningar i samband med en anslutning).
      - För diagrambaserad sammanfogning används det identitetsnamnutrymme som ska användas för att fråga efter identitetsdiagrammet.
   - Du kan välja mellan uppslagsfönster och uppspelningsfrekvens. Se ditt Customer Journey Analytics-paket för de [alternativ](#options) som är tillgängliga.
   - Namn på sandlåda.


2. Adobe kundsupport arbetar tillsammans med Adobe tekniker för att knyta ihop material när du får din begäran. När den är aktiverad visas en inmatad datauppsättning som innehåller en sammanfogad ID-kolumn i Adobe Experience Platform. Adobe kundsupport kan tillhandahålla den nya datauppsättningens ID.
3. När Adobe aktiveras första gången fylls data i baklänges. Se ditt Customer Journey Analytics-paket för att se om [alternativet](#options) är tillgängligt.

4. Om du vill använda den sammanslagna datauppsättningen i en flerkanalsanalys måste du lägga till den sammanslagna datauppsättningen i en [anslutning](../connections/overview.md) i Customer Journey Analytics. Lägg sedan till andra datauppsättningar som krävs för flerkanalsanalys och välj rätt person-ID för varje datauppsättning.

5. [Skapa en datavy](/help/data-views/create-dataview.md) baserat på anslutningen.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

När datavyn har konfigurerats kan du köra Customer Journey Analytics rapportanalys i alla kanaler och på alla enheter.
