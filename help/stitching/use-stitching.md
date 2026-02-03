---
title: Begär textning
description: Lär dig hur du begär sammanfogning.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a04c74ab-606e-45a9-a3e4-0d476c8d2426
source-git-commit: cbb18e9d0990d5df64995c2dabe8362c7c37bb45
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---

# Begär sammanfogning


>[!IMPORTANT]
>
>Framställning genom Adobe behövs inte längre och den här metoden är inaktuell. [Aktivera sammanslagning i anslutningsgränssnittet](use-stitching-ui.md).
>

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
      - För diagrambaserad sammanfogning är det identitetsnamnutrymme som du vill använda för att fråga efter identitetsdiagrammet.
   - Du kan välja mellan uppslagsfönster och uppspelningsfrekvens. Se ditt Customer Journey Analytics-paket för de [alternativ](#options) som är tillgängliga.
   - Namn på sandlåda.


2. Adobe kundsupport arbetar tillsammans med Adobe tekniker för att knyta ihop material när du får din begäran. När den är aktiverad visas en inmatad datauppsättning som innehåller en sammanfogad ID-kolumn i Adobe Experience Platform. Adobe kundsupport kan tillhandahålla den nya datauppsättningens ID.
3. När Adobe aktiveras första gången fylls data i baklänges. Se ditt Customer Journey Analytics-paket för att se om [alternativet](#options) är tillgängligt.

4. Om du vill använda den sammanslagna datauppsättningen i en flerkanalsanalys måste du lägga till den sammanslagna datauppsättningen i en [anslutning](../connections/overview.md) i Customer Journey Analytics. Lägg sedan till andra datauppsättningar som krävs för flerkanalsanalys och välj rätt person-ID för varje datauppsättning.

5. [Skapa en datavy](/help/data-views/create-dataview.md) baserat på anslutningen.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

När datavyn har konfigurerats kan du köra Customer Journey Analytics rapportanalys i alla kanaler och på alla enheter.

## Begränsningar

- Använd alla ändringar du gör i källhändelsens dataschema även i det nya sammanfogade dataschemat.

- Om du tar bort källdatauppsättningen avbryts bearbetningen av den sammanfogade datauppsättningen och tas bort av systemet.

- Dataanvändningsetiketter sprids inte automatiskt till det sammanslagna dataset-schemat. Om du har använt dataanvändningsetiketter på källdataschemat måste du använda dessa dataanvändningsetiketter manuellt på det sammanslagna dataset-schemat. Mer information finns i [Hantera dataanvändningsetiketter i Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview).
