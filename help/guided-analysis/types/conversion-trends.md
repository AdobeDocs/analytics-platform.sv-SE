---
title: Konverteringstrender
description: Spåra förändringar i konverteringsgraden över tid.
feature: Guided Analysis
source-git-commit: 84ac8008e4c90250e9f626b8c4d72f20297c14ad
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Konverteringstrender

{{release-limited-testing}}

The **Konverteringstrender** en visualisering av konverteringsgraden över tid. Den vågräta axeln är ett tidsintervall, medan den lodräta axeln representerar konverteringsgraden. Exempel:

* **Spåra optimering**: När du har identifierat viktiga flaskhalsar som du vill förbättra med [Funktion](friction.md)kan du använda den här vyn för att spåra hur optimeringarna påverkar konverteringsgraden över tid.
* **Utvärdering av A/B-tester**: Utvärdera effektiviteten i A/B-tester eller -experiment som utförs i samband med en tratt. Genom att jämföra konverteringsgraden mellan olika variationer kan ni enkelt avgöra vilka tester som ger högre konverteringsgrader, vilket leder till datadrivna beslut om vilka variationer som ska implementeras permanent.
* **Kampanjutvärdering över tid**: Mät effektiviteten i marknadsföringskampanjer över tid. Ni kan skapa ett segment som fokuserar på användare som rör en viss kampanj och jämföra deras konverteringsgrad med andra kampanjer. Ni kan också jämföra aktuella konverteringsgrader med liknande kampanjer som körts tidigare.

![Konverteringstrender](../assets/conversion-trends.png)

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Steg**: De kontaktytor för händelsen som du vill spåra. Varje stapel i diagrammet representerar ett steg. Du kan ta med upp till tio steg.
* **Folk**: De segment som du vill jämföra tratten med. Varje markerat segment delar upp varje steg i flera staplar. Varje färg representerar ett eget segment. Du kan inkludera upp till tre segment.

## Diagraminställningar

I vyn Konverteringstrender finns följande diagraminställningar som kan justeras på menyn ovanför diagrammet:

* **Mått**: Det mått som du vill mäta. Du kan välja sessioner och användare.
* **Diagramtyp**: Den typ av visualisering som du vill använda. Alternativen är Line.
* **Konvertering från**: Anger procentberäkningen från steg till steg. Du kan använda alternativen för att beräkna konverteringen från det första steget eller föregående steg.

## Använd tidsjämförelse

{{apply-time-comparison}}

![Tidskonverteringstrender - jämför](../assets/conversion-trends-compare.png)

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **Intervall**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **Datum**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.