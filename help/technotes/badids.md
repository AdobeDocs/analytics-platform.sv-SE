---
title: Customer Journey Analytics Bad IDs
description: Förstå felaktiga ID:n (BAVID) i Customer Journey Analytics. Lär dig hur du identifierar felaktiga ID:n i dina data, varför de påverkar rapporteringen och hur du undersöker och löser Dålig ID-exponering i dina anslutningar.
solution: Customer Journey Analytics
feature: Basics
role: Admin
source-git-commit: b7b2a1f3eb1c149caf65ab3e4321e4f4347695cc
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 0%

---


# Felaktiga ID:n

Den här artikeln innehåller kontext om felaktiga ID:n och hur du identifierar deras förekomst eller risk för förekomst i dina data med hjälp av frågetjänsten.


>[!INFO]
>
>Felaktiga ID:n kallas även BAVID:n i Customer Journey Analytics-gränssnittet (kommer från [Analytics BAVID](https://experienceleague.adobe.com/sv/docs/experience-cloud-kcs/kbarticles/ka-16444)).
>

## Definition

I Customer Journey Analytics är ett felaktigt ID en identifierare som en del av alla data som definieras i en anslutning:

* med ett specifikt ID-värde som kommer
   * från ett person-ID-fält (icke-sammansatta datauppsättningar), **eller**
   * från ett beständigt ID- eller personID-fält (sammanfogningsaktiverade datauppsättningar),

  **och**
* är på mer än en miljon (1 000 000) händelser i anslutningsdata (som räknas för alla datauppsättningar i anslutningen) inom en månad.

När ett ID-värde markeras som ett felaktigt ID tas alla framtida händelser som innehåller det ID-värdet bort från anslutningsdata och visas inte i rapporten.

### Exempel

Ett exempel på ett dåligt ID är att du har anpassade värden eller platshållarvärden i person-ID-fältet (till exempel `undefined` för anonym trafik). För en datauppsättning som har stöd för sammanslagning kan den här situationen få ännu större effekt på rapporteringsdata eftersom sammanfogningskvaliteten troligen påverkas. För att lösa detta kan du behöva rensa och återaktivera sammanfogningsinställningen, inklusive att ta bort historiska data för datauppsättningar i anslutningen.


## Mätvärden

Customer Journey Analytics Connection-gränssnittet innehåller **[!UICONTROL Bad IDs]** mätdata på flera ställen i gränssnittet.

* Du kan se **[!UICONTROL Bad IDs]** (eller **[!UICONTROL BAVIDs]**) som möjliga orsaker till att poster hoppas över i dialogrutan **[!UICONTROL Check skipped details]**. Använd **[!UICONTROL Check detail]** (om tillgängligt) under **[!UICONTROL Records skipped]** på [detaljskärmen för en anslutning](/help/connections/create-connection.md).
* För en sammanfogningsaktiverad datauppsättning visar [**[!UICONTROL Dataset preview]**](/help/stitching/use-stitching-ui.md#bad-ids) **[!UICONTROL Bad IDs]** som en del av **[!UICONTROL Stitching metrics]**. Det här måttet kan hjälpa dig att identifiera möjliga felaktiga ID-fall. Tänk dock på att detta mått beräknas baserat på en begränsad uppsättning data.

Se [Felaktig exponering för ID:n](#bad-ids-exposure) för att hjälpa dig att identifiera om det finns felaktiga ID:n för en datauppsättning som du tänker använda i en anslutning (oavsett om funktionen är aktiverad eller inte).


## Exponering

Om du vill utforska exponeringen för felaktiga ID:n för ett visst datamängdsfält bör du överväga att utföra följande fråga i Experience Platform Query Service. Kontrollera de översta returnerade ID-värdena för att se om det finns några kandidater för felaktiga ID:n. Observera att [Felaktig ID-definition](#definition) tar hänsyn till alla datauppsättningar i anslutningen.


### Identifiera (risk för) felaktiga ID:n i ett fält

Du kan använda Experience Platform Query för att identifiera den potentiella risken med felaktiga ID:n i ett fält.

Frågan nedan returnerar de första 20 ID-värdena från ett fält. I fallande ordning efter antal totala händelser. Och där varje värde identifieras inom ett visst intervall (t.ex. inom de senaste 30 dagarna).

Kör den här frågan för ett specifikt person-ID-fält som du vill analysera. För en datauppsättning som behöver sammanfogas kan du även köra frågan för ett beständigt ID-fält.

```sql
SELECT
    /* INSERT FIELD HERE */,
    COUNT(*) AS occurrences
FROM /* INSERT DATASET TABLE NAME HERE */
WHERE timestamp >= NOW() - INTERVAL '30 days' 
GROUP BY /* INSERT FIELD HERE */
ORDER BY occurrences DESC
LIMIT 20; 
```

Ersätt `INSERT FIELD HERE` i frågan beroende på vilken typ av fält du söker efter med felaktiga ID:n:

* `full.field.path.from.XDM.schema` (för strängfält definierade i XDM-schema)
* `identityMap['namespace_value'][0].id` (för fält som definieras med `namespace_value` i `identityMap`)

Kontrollera resultatet för att se om det finns problematiska ID-värden. Precis som egna värden eller platshållarvärden, eller värden med höga förekomster som får eller kan komma närmare 1 miljon inom en månad på anslutningsdatanivån.
Även om implementeringen fortfarande är i utvecklingsfasen bör du bedöma risken för att det finns felaktiga ID:n när installationen är stabil och klar för produktion.
