---
title: Vy över konverteringstrender
description: Spåra förändringar i konverteringsgraden över tid.
feature: Guided Analysis
keywords: produktanalys
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 0%

---

# Vy över konverteringstrender

The **Konverteringstrender** en visualisering av konverteringsgraden över tid. Den vågräta axeln är ett tidsintervall, medan den lodräta axeln representerar konverteringsgraden.

>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)

## Användningsexempel

Exempel:

* **Spåra optimering**: När du har identifierat viktiga flaskhalsar som du vill förbättra med [Funktion](friction.md)kan du använda den här vyn för att spåra hur optimeringarna påverkar konverteringsgraden över tid.
* **Utvärdering av A/B-tester**: Utvärdera effektiviteten i A/B-tester eller -experiment som utförs i samband med en tratt. Genom att jämföra konverteringsgraden mellan olika variationer kan ni enkelt avgöra vilka tester som ger högre konverteringsgrader, vilket leder till datadrivna beslut om vilka variationer som ska implementeras permanent.
* **Kampanjutvärdering över tid**: Mät effekten av marknadsföringskampanjer över tid. Ni kan skapa ett segment som fokuserar på användare som rör en viss kampanj och jämföra deras konverteringsgrad med andra kampanjer. Ni kan också jämföra aktuella konverteringsgrader med liknande kampanjer som körts tidigare.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Steps]**: De händelsetyper som du vill spåra. Varje stapel i diagrammet representerar ett steg. Du kan ta med upp till tio steg.
* **[!UICONTROL People]**: De segment som du vill jämföra tratten mellan. Varje markerat segment delar upp varje steg i flera staplar. Varje färg representerar ett eget segment. Du kan inkludera upp till tre segment.

## Diagraminställningar

I vyn Konverteringstrender finns följande diagraminställningar som kan justeras på menyn ovanför diagrammet:

* **[!UICONTROL Metric]**: Det mått som du vill mäta. Du kan välja sessioner och användare.
* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen är Line.
* **[!UICONTROL Conversion from]**: Anger procentberäkningen från steg till steg. Du kan använda alternativen för att beräkna konverteringen från det första steget eller föregående steg.

>[!NOTE]
>
>The **Genomsnittlig** i vyn Conversion trends skiljer sig från **Totalt** kolumn i [Bildvy](friction.md) tabell. Den första är ett medelvärde av intervallkolumnerna (till exempel medelvärdet av den dagliga konverteringsgraden), medan den andra är en aggregerad beräkning över hela datumintervallet.

## Använd tidsjämförelse

{{apply-time-comparison}}

![Tidskonverteringstrender - jämför](../assets/conversion-trends-compare.png)

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
