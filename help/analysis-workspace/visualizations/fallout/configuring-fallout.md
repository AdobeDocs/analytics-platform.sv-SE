---
description: Lär dig hur du konfigurerar och anger kontaktytorna för att skapa en flerdimensionell fallsekvens.
title: Konfigurera en utfallsvisualisering
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 295e4c9b3b9dff5ba650456c3f62817b30fe1e3d
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Konfigurera en utfallsvisualisering {#configure-fallout-visualization}


Du kan ange **kontaktytor** om du vill skapa en flerdimensionell utfallssekvens. I många fall är en kontaktyta en sida på din webbplats. Kontaktpunkterna är dock inte begränsade till sidor. Du kan t.ex. lägga till händelser, t.ex. enheter, samt unika personer och returbesök. Du kan också lägga till dimensioner, t.ex. en kategori, webbläsartyp eller ett internt sökord.

Du kan till och med lägga till segment inom en kontaktyta. Du kanske vill jämföra segment, till exempel iOS- och Android-användare. Dra de önskade segmenten högst upp i utfallet och information om dessa segment läggs till i utfallsrapporten. Om du bara vill visa de segmenten kan du ta bort baslinjen Alla personer.

Bortfallsvisualiseringar har ingen begränsning av antalet kontaktytor som du kan lägga till eller antalet komponenter som du kan använda.

Du kan göra målningar på dimensioner, mätvärden och segment. Anta till exempel att någon tittar på `shoes, shirt` på en sida och på nästa sida tittar de på `shirt, socks`. Nästa produktflödesrapport från skor blir skjorta och strumpa, INTE skjorta.

## Använd

1. Lägg till en ![ConversionTrnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Fallout]**-visualisering. Se [Lägga till en visualisering på en panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Dra en komponent till listrutan **[!UICONTROL Add touchpoint]**.

   >[!TIP]
   >
   >Du kan lägga till en enda sida i utfallsrapporten, i stället för hela dimensionen. Klicka på högerpilen ![ChevronRight](/help/assets/icons/ChevronRight.svg) på siddimensionen för att välja en viss sida, till exempel **[!UICONTROL home]**, som ska läggas till i utfallsrapporten.

   ![Hemsidan från hemsidesdimensionen som dras till fältet Lägg till kontaktpunkt.](assets/fallout-drag.png)

1. Fortsätt lägga till kontaktytor tills sekvensen är klar.

   De cirklade siffrorna i den grå delen av fältet visar utfallet mellan kontaktytor (inte det övergripande utfallet till den punkten). De cirklade siffrorna i den gröna delen av fältet visar att det lyckades gå igenom från föregående kontaktyta till den aktuella kontaktytan.

   ![Utfallsvisualisering](assets/fallout-visualization.png)

   När du lägger till kontaktytor kan du göra något av följande:

   * Kombinera flera komponenter genom att dra en eller flera ytterligare komponenter till en enda kontaktyta.

     >[!NOTE]
     >
     >Flera segment förenas med AND, men flera objekt som dimensionsposter och mätvärden förenas med OR.

   * Ändra ordning på kontaktpunkterna genom att dra dem till en annan nivå i utfallshierarkin.

   * Kombinera två kontaktytor genom att dra en kontaktyta till en annan. Släpp kontaktytan när du ser ordet **[!UICONTROL Combine]**.

   * Begränsa enskilda kontaktytor till nästa händelse (till skillnad från *så småningom*) i banan. Under varje kontaktyta finns det en väljare med alternativen **[!UICONTROL Eventual path]** och **[!UICONTROL Next event]**, vilket visas här:

     | Alternativ | Beskrivning |
     |---|---|
     | **[!UICONTROL Eventual path]** (standard) | Personer räknas som *så småningom* landar på nästa sida i sökvägen, men inte nödvändigtvis på nästa händelse. |
     | **[!UICONTROL Next event]** | Personer räknas som kommer att landa på nästa sida i banan på nästa händelse. |

   * Håll pekaren över en kontaktyta för att se utfallet och annan information om den nivån. Informationen innehåller kontaktpunktens namn, antalet personer och antalet lyckade försök. Du kan också jämföra framgångssiffran med andra kontaktytor.

## Inställningar {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="Bortfallsbehållare"
>abstract="Välj en behållare som ska analyseras. Det här valet hjälper dig att förstå engagemang och begränsningar för analysen av den valda behållaren."

Som en del av visualiseringen är specifika inställningar tillgängliga.

| Bortfallsbehållare | Beskrivning |
|--- |--- |
| **[!UICONTROL Session]** eller **[!UICONTROL Person]** | Växla mellan [!UICONTROL Session] och [!UICONTROL Person] för att analysera personsökvägen. Standardvärdet är [!UICONTROL Person]. Dessa inställningar hjälper er att förstå personengagemang på personnivå (mellan sessioner) eller begränsa analysen till en enda session. |


## Snabbmeny

Som en del av visualiseringen finns det specifika alternativ för snabbmenyer.

### Öppna snabbmenyn

Du kommer åt snabbmenyn på något av följande sätt:

* Hovra över en kontaktyta i visualiseringen och välj sedan **[!UICONTROL Click to analyze]**.

  ![Åtkomst till snabbmenyn från hovring](assets/fallout-tooltip-analyze.png)

* Högerklicka på en kontaktyta i visualiseringen.

  ![Utfallsalternativ](assets/fallout-options.png)

### Alternativ på snabbmenyn

Följande snabbmenyalternativ är tillgängliga:

| Alternativ | Beskrivning |
|--- |--- |
| **[!UICONTROL Trend touchpoint]** | Se trenddata för en kontaktyta i ett linjediagram med vissa fördefinierade avvikelseidentifieringsdata. |
| **[!UICONTROL Trend touchpoint (%)]** | Trends the total fallout percentage. |
| **[!UICONTROL Trend all touchpoints (%)]** | Trends all the touchpoint percentage in the fallout (except **[!UICONTROL All People]**, if it is included), on the same chart. |
| **[!UICONTROL Break down fallthrough at this touchpoint]** | Se vad personer gjorde mellan två kontaktytor (den här kontaktytan och nästa kontaktyta) om de fortsatte till nästa kontaktyta. Då skapas en frihandstabell med dina mått. Du kan ersätta dimensioner och andra element i tabellen. En tabell som till exempel har etiketten **[!UICONTROL Fallthrough: All People > Page equals any of home]** och innehåller **[!UICONTROL Page]** som dimension och **[!UICONTROL People]** segmenterad av snabbsegmentet [endast för projekt](/help/components/segments/seg-quick.md) **[!UICONTROL Fallthrough: All People > Page equals any of home]** som måttenhet. Inspektera segmentet för att förstå hur grundsegmentet bestäms. |
| **[!UICONTROL Break down fallout at this touchpoint]** | Se vad de som inte klarade sig genom funnel gjorde direkt efter det valda steget. Då skapas en frihandstabell med dina mått. Du kan ersätta dimensioner och andra element i tabellen. En tabell som till exempel har etiketten **[!UICONTROL Fallout: People > Page equals any of home]** och innehåller **[!UICONTROL Page]** som dimension och **[!UICONTROL People]** segmenterad av snabbsegmentet [endast för projekt](/help/components/segments/seg-quick.md) **[!UICONTROL Fallthrough: All Visitors > Page equals any of home]** som måttenhet. Kontrollera segmentet för att förstå hur utfallssegmentet bestäms. |
| **[!UICONTROL Create segment from touchpoint]** | Skapa ett nytt segment från den markerade kontaktytan. |

>[!MORELIKETHIS]
>
>[Lägg till en visualisering på en panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Visualiseringsinställningar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Snabbmenyn Visualisering ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

