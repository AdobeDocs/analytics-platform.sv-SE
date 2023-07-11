---
title: Nettotillväxt
description: Balansera användarvinster och -förluster.
feature: Guided Analysis
source-git-commit: 14c7aa342649afbe9923b0086947e5a0adeefff2
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---

# Nettotillväxt

{{release-limited-testing}}

The **Nettotillväxt** vytypen ger insikter om i vilken takt du förvärvar eller förlorar användare under en viss period. Den vågräta axeln är alltid en tidshalaritet, medan den lodräta axeln alltid är tillväxtmåttet.

Varje datapunkt representerar datapunktens nettotillväxt, som beräknas med följande formel:

`([New users] + [Return users]) / [Dormant users]`

Liknar [Aktiv](active.md) -vy definieras användare som följande:

* **Nytt**: Användaren var aktiv under den aktuella datapunkten och har inte visats i några tidigare datapunkter.
* **Retur**: Användaren visades inte i den omedelbart föregående datapunkten, men är inte en ny användare.
* **Vilande**: Användaren visades inte i den aktuella datapunkten, utan i den omedelbart föregående datapunkten. Vilande användare räknas inte med i det totala antalet aktiva användare.

**Upprepa** Användare är inte involverade i den här beräkningen eftersom de inte representerar någon tillväxt eller förlust.

Resultatet av den här formeln är en proportion där din användarbas växte eller krympte under datapunkten. En nettoökning av `1` motsvarar en jämvikt, produkten fick samma antal användare som den förlorade. Nettotillväxt större än `1` representerar positiv tillväxt, fler nya/återkommande användare än vilande användare. En nettotillväxt som är mindre än `1` representerar en förlust av aktiva användare, fler vilande användare än nya/återkommande användare.

Exempel:

* **Analys av kundvärvning**: Gör att ni kan bedöma hur effektiva era strategier för kundförvärv är. Genom att analysera källor till användartillväxt, t.ex. sökmotorer, kampanjer eller andra marknadsföringskanaler, kan ni identifiera de viktigaste tillväxtkällorna så att ni kan tilldela resurser i enlighet med detta.
* **Resultatutvärdering**: Gör att du kan bedöma den övergripande prestandan för din produkt när det gäller att köpa nya användare. Genom att följa tillväxttrender kan du bättre förstå om produkten lockar och behåller användare i önskad takt.
* **Kurnanalys**: Nettotillväxten innefattar attrition i sin formel (vilande användare). Du kan utvärdera den övergripande statusen för din användarbas över tiden. Om nettotillväxten är konsekvent nedan `1`, indikerar det en hög grad av attribuering, vilket uppmanar er att undersöka orsakerna bakom detta och implementera strategier för bibehållande.

[Skärmbild av användartillväxt]

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **Händelser**: Händelsen som du vill mäta. Eftersom den här vytypen är användarbaserad kan en användare peka på händelsen en gång inom det angivna datumgranulariteten för att vara i nettotillväxten. Du kan bara inkludera en händelse i en fråga.
* **Folk**: Det segment som du vill mäta. Du kan bara inkludera ett segment i en fråga.

## Datumintervall

Det önskade datumintervallet. Den här inställningen har två viktiga komponenter:

* **Intervall**: Datumgranulariteten som du vill visa data i. Giltiga alternativ är Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **Datum**: Start- och slutdatumet. Det finns förinställningar för datumintervall tillgängliga, eller så kan du använda kalenderväljaren för att ange exakt önskat datum.
