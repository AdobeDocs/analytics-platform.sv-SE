---
title: Konverteringstrender
description: Spåra förändringar i konverteringsgraden över tid.
feature: Guided Analysis
source-git-commit: 14c7aa342649afbe9923b0086947e5a0adeefff2
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 0%

---

# Konverteringstrender

{{release-limited-testing}}

The **Konverteringstrender** visningstypen ger en visualisering runt konverteringsgrader över tid. Den vågräta axeln är alltid en datumgranularitet, medan den lodräta axeln representerar konverteringsgraden. Använda den här vytypen i kombination med [Funktion](friction.md) använder du för att skapa och förfina den kanal du vill arbeta med. Du kan sedan använda den här vytypen för att visa konverteringsgrader för den tratten över tiden. Exempel:

* **Spåra optimering**: När du har identifierat viktiga flaskhalsar som du vill förbättra med [Funktion](friction.md)kan du använda den här vytypen för att spåra hur optimeringarna påverkar konverteringsgraden över tid.
* **Utvärdering av A/B-tester**: Utvärdera effektiviteten i A/B-tester eller -experiment som utförs i samband med en tratt. Genom att jämföra konverteringsgraden mellan olika variationer kan ni enkelt avgöra vilka tester som ger högre konverteringsgrader, vilket leder till datadrivna beslut om vilka variationer som ska implementeras permanent.
* **Kampanjutvärdering över tid**: Mät effektiviteten i marknadsföringskampanjer över tid. Ni kan skapa ett segment som fokuserar på användare som rör en viss kampanj och jämföra deras konverteringsgrad med andra kampanjer. Ni kan också jämföra aktuella konverteringsgrader med liknande kampanjer som körts tidigare.

[Skärmdump av tratt]

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Steg**: De beröringspunkter för händelsen som du vill spåra. Varje stapel i diagrammet representerar ett steg. Du kan ta med upp till tio steg.
* **Folk**: De segment som du vill jämföra tratten med. Varje markerat segment delar upp varje steg i flera staplar. Varje färg representerar ett eget segment. Du kan inkludera upp till tre segment.

## Diagraminställningar

Trnel har följande diagraminställningar. Du kan justera diagraminställningarna på menyn mellan vytypen och kalenderväljaren.

* **Mått**: Det mått som du vill mäta. Du kan välja sessioner och användare.
* **Diagramtyp**: Den typ av visualisering som du vill använda. Det enda alternativet är Line.
* **Konvertering från**: Anger procentberäkningen från steg till steg. Du kan använda alternativen för att beräkna konverteringen från första steget eller föregående steg.

## Använd tidsjämförelse

{{apply-time-comparison}}

## Datumintervall

Det önskade datumintervallet. Den här inställningen har två viktiga komponenter:

* **Intervall**: Datumgranulariteten som du vill visa data i. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **Datum**: Start- och slutdatumet. Det finns förinställningar för datumintervall tillgängliga, eller så kan du använda kalenderväljaren för att ange exakt önskat datum.
