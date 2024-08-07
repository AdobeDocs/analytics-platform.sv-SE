---
description: Använd den centrala metriska sammanfattningen för att jämföra mätprestanda för två tidslinjer.
title: Sammanfattning av nyckelmått
feature: Visualizations
exl-id: ef606c53-b370-419a-904b-573ee6d70a8d
role: User
source-git-commit: b196b8c05ba05a3f46d71c10fdcaa2ad8ef0dcd6
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 0%

---

# Sammanfattning av nyckelmått

Med visualiseringen [!UICONTROL Key metric summary] kan du se hur ett viktigt mätresultat trendar inom en enda tidsram. Du kan också jämföra mätprestanda över två tidsramar. Det ger fördelarna med flera visualiseringar i kombination med en visualisering:

* **[!UICONTROL Line]** visualiseringar som visar hur måttet trendar för det primära datumintervallet och jämförelsedatumintervallet

* **[!UICONTROL Summary percent change]** som visar måttökning eller minskning mellan det primära datumintervallet och jämförelsedatumintervallet

* Aktuellt totalt värde ([!UICONTROL **sammanfattningsnummer**]) för måttet

## Användningsexempel

Den här visualiseringen åtgärdar ett antal vanliga användningsfall, bland annat:

* En analytiker som försöker förstå hur skapandet av nya affärsmöjligheter såg ut den här månaden jämfört med samma tidsram förra året.

* En marknadsförare som visar hur leadgenerering för en viss lead-typ har ändrats från den här månaden till den förra månaden.

* En chefer vill förstå hur nya bokningar ändrades från detta kvartal till förra kvartalet.

## Konfigurera sammanfattningen av nyckelmått

1. Dra visualiseringen **[!UICONTROL Key metric summary]** från menyn **[!UICONTROL Visualizations]** i den vänstra listen till en panel.

1. Konfigurera visualiseringen genom att välja ett mätvärde, ett primärt datumintervall och ett jämförelsedatumintervall och ett filter (om du vill):

   ![Nyckelmätningskonfiguration som visar alternativen för mått, primärt datumintervall, jämförelsedatumintervall och segment.](assets/key-metric-config.png)

   | Konfigurationsinställning | Definition |
   | --- | --- |
   | **[!UICONTROL Metric]** | Välj det mätvärde som du vill undersöka. Alla mätvärden stöds. |
   | **[!UICONTROL Primary date range]** | Det aktuella datumintervallet för frihandstabellen. |
   | **[!UICONTROL Comparison date range]** | Datumintervallet som du vill jämföra det primära datumintervallet med. |
   | **[!UICONTROL Filter (optional)]** | Alla filter som du är intresserad av för denna sammanfattning. |

   {style="table-layout:auto"}

1. Klicka på **[!UICONTROL Build]**.

<!--## How the Key Metric Summary visualization handles the comparison date range

(This will probably release in January. Per Jaden Howell)

* If the primary date range is set to the panel date range, there are 2-6 options that are considered 'relative' to the primary date range. These usually include the previous period (same amount of time immediately proceeding the primary date range), and 52 weeks prior to that date range.

* If the comparison date range is set to one of the 'relative' options, upon updating the primary date range, the comparison date range updates to the period immediate preceding the panel date range.

* If your comparison date range is *not* set to a 'relative' option, then updating the panel date range changes your primary date range, but has no effect on the comparison date range.

**Example 1**

Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a relative date range, one of: 'Previous day', 'Same day last week', 'Same day 4 weeks prior', 'Same day last month', 'Same day last year', or 'Same day 52 weeks prior'.
When I change the panel's date range to 'This month', the comparison date range will update to 'Previous month'.

**Example 2**
 
Primary date range is set to the panel's date range: 'Yesterday'
Comparison date range is set to a non-relative date range, such as 'Feb 2nd, 2022', 'Highest sales day', 'Last week', etc. 

>[!NOTE]
>
>Last week is relative to the day the project is opened on, but it is not based on the panel's date range of 'Yesterday'. In other cases, such as if the panel's date range was 'This week', it may be relative.

When you change the panel's date range to '4 days ago', the comparison date range remains at the previous selection. -->

## Visa utdata

Utdata ska se ut ungefär så här:

![Viktiga måttutdata som visar metik-, sammanfattningsändring-, sammanfattningsnummer- och linjediagram.](assets/key-metric-output.png)

Observera:

* Linjediagrammet **[!UICONTROL Previous period]** (visas alltid i grått) motsvarar **[!UICONTROL Comparison date range]** i konfigurationssteget.

* Om ett jämförelsedatumintervall inte anges under konfigurationen eller döljs i visualiseringsinställningarna, visas bara linjediagrammet för det primära datumintervallet. Sammanfattningsändringen döljs.

* Härifrån kan du hovra över linjediagrammen för att se statistik för enskilda dagar:

![Besök statistik](assets/key-metric-output2.png)

## Visualiseringsinställningar

Sammanfattningen av nyckeltal erbjuder flera flexibla inställningar för bättre rapportering och kommunikation av viktiga mätvärden. Du kommer åt inställningarna via kugghjulsikonen i det övre högra hörnet av visualiseringen.

![Sammanfattningsinställningar för nyckeltal med visningstypen Sammanfattning, allmänna alternativ och visningsalternativ.](assets/key-metric-settings.png)

| Inställning | Beskrivning |
| --- | --- |
| **[!UICONTROL Emphasize percent change]** | Visa sammanfattningsändring i framträdande fetstil i mitten av visualiseringen |
| **[!UICONTROL Emphasize number value]** | Visa sammanfattningsnummer i framträdande fetstil i mitten av visualiseringen |
| **[!UICONTROL Legend visible]** | Visa eller dölj teckenförklaringen längst ned i visualiseringen |
| **[!UICONTROL Show annotations]** | Visa eller dölj anteckningar som lagts till av en administratör |
| **[!UICONTROL Show sparklines]** | Visa eller dölj linjediagram längst ned i diagrammet. När teckenförklaringen är dold ändras den inte längre till att referera till raderna visuellt |
| **[!UICONTROL Show min and max on sparklines]** | Visa eller dölj lägsta och högsta värden i primära och jämförande raddiagram |
| **[!UICONTROL Show comparison]** | Visa eller dölj jämförelsedata. När det är dolt döljs både jämförelsetabellen och de sammanfattande ändringsobjekten. |
| **[!UICONTROL Show total number]** | Visa eller dölj sammanfattningsnummer |
| **[!UICONTROL Show raw difference]** | Visa eller dölj den obearbetade skillnaden mellan det totala värdet för måttet i det primära datumintervallet och det sekundära datumintervallet |
| **[!UICONTROL Abbreviate value]** | Förkorta talvärdena för att förenkla kommunikationen (t.ex. 20 000 -> 20 kB) |

## Redigera visualisering

När du har skapat visualiseringen kan du fortfarande redigera den ursprungliga konfigurationen.

1. Klicka på pennikonen i det övre högra hörnet av visualiseringen (bredvid inställningsikonen).

   ![Ikon för visualisering-redigering.s](assets/edit-icon.png)

   Du återgår nu till den ursprungliga konfigurationsvyn.

1. Ändra måttet, det primära datumintervallet, jämförelsedatumintervallet eller filtret.
