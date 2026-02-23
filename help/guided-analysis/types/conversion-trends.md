---
title: Analys av konverteringstrender
description: Spåra förändringar i konverteringsgraden över tid.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 0%

---

# [!UICONTROL Conversion trends]-analys {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="Konverteringstrender"
>abstract="Spåra förändringar i konverteringsgrader över tid."

<!-- markdownlint-enable MD034 -->


Analysen ![Konverteringstrender](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL Conversion trends]** ger en visualisering av konverteringsgraden över tid. Den vågräta axeln är ett tidsintervall, medan den lodräta axeln representerar konverteringsgraden.


>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/conversion-trends)


## Användningsexempel

Användningsexempel för den här analysen är:

* **Spåra optimeringsaktiviteter**: När du har identifierat viktiga flaskhalsar som du vill förbättra med [Funnel](funnel.md) -analysen kan du använda den här analysen för att spåra hur dessa optimeringar påverkar konverteringsgraden över tid.
* **Utvärdering av A/B-tester**: Utvärdera effektiviteten hos A/B-tester eller -experiment som utförs i samband med en funnel. Genom att jämföra konverteringsgraden mellan olika variationer kan ni enkelt avgöra vilka tester som ger högre konverteringsgrader, vilket leder till datadrivna beslut om vilka variationer som ska implementeras permanent.
* **Kampanjutvärdering över tid**: Mät effekten av marknadsföringskampanjer över tid. Ni kan skapa ett segment som fokuserar på användare som rör en viss kampanj och jämföra deras konverteringsgrad med andra kampanjer. Ni kan också jämföra aktuella konverteringsgrader med liknande kampanjer som körts tidigare.

## Gränssnitt

I [Gränssnitt](../overview.md#interface) finns en översikt över gränssnittet för guidad analys. Följande inställningar är specifika för den här analysen:

### Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan den här analysen och [Funnel](funnel.md).
* **[!UICONTROL Steps]**: De kontaktytor för händelsen som du vill spåra. Varje stapel i diagrammet representerar ett steg. Du kan ta med upp till tio steg.
* **[!UICONTROL Counted as]**: Den beräkningsmetod som du vill använda för de markerade händelserna. Alternativen är [!UICONTROL Users] och [!UICONTROL Sessions].
* **[!UICONTROL Segments]**: Segmenten som du vill jämföra funnel med. Varje markerat segment delar upp varje steg i flera staplar. Varje färg representerar ett eget segment. Du kan inkludera upp till tre segment.

### Diagraminställningar

Analysen av [!UICONTROL Conversion trends] innehåller följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen är [!UICONTROL Line].
* **[!UICONTROL Conversion from]**: Anger procentberäkningen från steg till steg. Du kan använda alternativen för att beräkna konverteringen från [!UICONTROL First step] eller [!UICONTROL Previous step].

>[!NOTE]
>
>Kolumnen **Genomsnitt** i analystabellen för konverteringstrender skiljer sig från kolumnen **Totalt** i tabellen [Funnel analysis](funnel.md). Den första är ett medelvärde av intervallkolumnerna (till exempel medelvärdet av den dagliga konverteringsgraden), medan den andra är en aggregerad beräkning över hela datumintervallet.

### Tidsjämförelse

{{apply-time-comparison}}


### Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall, vilket påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
