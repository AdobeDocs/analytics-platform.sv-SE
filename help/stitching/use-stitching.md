---
title: Använd stygn
description: Hur du använder stygn
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: 7cd0bd94ec45b1570d0be765d95b25defa3e1b87
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 0%

---

# Använd stygn

När din organisation uppfyller alla [krav](#prerequisites) och förstår vanliga [begränsningar](#limitations) och begränsningar för sammanfogningsmetoder som är specifika ([fältbaserade](#limitations-1) och [diagrambaserade](#limitations-2)) kan du följa de här stegen för att börja använda sammanfogning i Customer Journey Analytics.

## Välj alternativ

Det Customer Journey Analytics-paket som du är berättigad till avgör vilka metoder som är tillgängliga för sammanfogning, alternativ för inledande varaktighet för efterfyllning, fönster för uppspelningsfrekvens och maximalt antal datauppsättningar som tillåts för sammanfogning. Mer information finns i [Customer Journey Analytics produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html). Bestäm vilka alternativ som är tillgängliga innan du begär support.

| | Customer Journey Analytics<br/>Välj | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Tillgängliga sammanfogningsmetoder | <li>Fältbaserad stygn</li> | <li>Fältbaserad stygn</li><li>Diagrambaserad utjämning</li> | <li>Fältbaserad stygn</li><li>Diagrambaserad utjämning</li> |
| Varaktighet för engångssammanfogning av bakfyllning | 13 månader | 13 månader | 25 månader |
| Fönster för uppspelning och uppspelningsfrekvens | <li>1 dag, varje dag</li><li>upp till 7 dagar, varje vecka</li> | <li>1 dag, varje dag</li><li>upp till 14 dagar, varje vecka</li> | <li>1 dag, varje dag</li><li>upp till 30 dagar, varje vecka</li> |
| Högsta antal datauppsättningar som tillåts för sammanfogning | 5 | 15 | 50 |

## Begär support

1. Kontakta Adobe kundsupport med följande information:

   - En begäran om aktivering av sammanfogning.
   - Datauppsättnings-ID för den datauppsättning som du vill ändra inmatning för.
   - Kolumnnamnet (identitetssökväg och namnutrymme) för det beständiga ID:t för den önskade datauppsättningen (identifieraren som visas på varje rad).
   - Om datauppsättningen stöder `identityMap`:
      - För fältbaserad sammanfogning anger du namnutrymmet för både beständiga och övergående ID:n.
      - För diagrambaserad sammanfogning anger du namnutrymmet för det beständiga ID:t och det identitetsnamnutrymme som ska användas för att fråga efter identitetsdiagrammet.
   - Om datauppsättningen inte stöder `identityMap`:
      - För fältbaserad sammanfogning är kolumnnamnet för det tillfälliga ID:t för den önskade datauppsättningen (personidentifieraren, som också fungerar som en länk mellan datauppsättningar i samband med en anslutning).
      - För diagrambaserad sammanfogning används det identitetsnamnutrymme som ska användas för att fråga efter identitetsdiagrammet.
   - Du kan välja mellan uppslagsfönster och uppspelningsfrekvens. Se ditt Customer Journey Analytics-paket för de [alternativ](#options) som är tillgängliga.
   - Namn på sandlåda.


2. Adobe kundsupport arbetar tillsammans med Adobe tekniker för att knyta ihop material när du får din begäran. När den är aktiverad visas en ny inmatad datauppsättning som innehåller en ny kolumn för sammanfogade ID i Adobe Experience Platform. Adobe kundsupport kan tillhandahålla den nya datauppsättningens ID.

3. När Adobe aktiveras första gången fylls data i baklänges. Se ditt Customer Journey Analytics-paket för att se om [alternativet](#options) är tillgängligt.

4. Om du vill använda den nya sammanslagna datauppsättningen i en flerkanalsanalys måste du lägga till den nya sammanslagna datauppsättningen i en [anslutning](../connections/overview.md) i Customer Journey Analytics. Lägg sedan till andra datauppsättningar som krävs för flerkanalsanalys och välj rätt person-ID för varje datauppsättning.

5. [Skapa en datavy](/help/data-views/create-dataview.md) baserat på anslutningen.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

När datavyn har konfigurerats kan du köra Customer Journey Analytics rapportanalys i alla kanaler och på alla enheter.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->
