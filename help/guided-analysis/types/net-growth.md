---
title: Vyn Nettotillväxt
description: Kommer du att få eller förlora användare?
feature: Guided Analysis
source-git-commit: 9f176bc6bc12291dcdab80af50c32df7d8edf220
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---

# Vyn Nettotillväxt

The **Nettotillväxt** vytypen ger insikter om i vilken takt du vinner eller förlorar användare under en viss period. Den vågräta axeln är ett tidsintervall, medan den lodräta axeln är tillväxtmåttet.

Varje datapunkt representerar nettotillväxt, som beräknas med följande formel:

`([New users] + [Return users]) / [Dormant users]`

Resultatet av den här formeln är ett förhållande. En nettoökning av `1` motsvarar en jämvikt, produkten fick samma antal användare som den förlorade. Nettotillväxt större än `1` representerar positiv tillväxt, fler nya +-användare än vilande användare. En nettotillväxt som är mindre än `1` motsvarar en förlust, fler vilande användare än nya +-användare.

Liknar [Aktiv](active.md) -vy definieras användare som följande:

* **[!UICONTROL New]**: Användaren var aktiv under den aktuella perioden, men inte tidigare. Se hur långt analysen ser tillbaka för att avgöra en ny användare genom att hålla pekaren över[!UICONTROL New users]&#39; i diagramförklaringen. Uppslagsintervallet bestäms dynamiskt utifrån det valda datumintervallet och intervallet.
* **[!UICONTROL Return]**: Användaren var aktiv under den aktuella perioden och inte aktiv under den omedelbart föregående perioden, men var tidigare aktiv vid något tillfälle. Se hur långt tillbaka analysen ser ut för att bestämma en returanvändare genom att hålla pekaren över[!UICONTROL Return users]&#39; i diagramförklaringen. Uppslagsintervallet bestäms dynamiskt utifrån det valda datumintervallet och intervallet.
* **[!UICONTROL Dormant]**: Användaren var aktiv i den omedelbart föregående perioden, men är inte aktiv i den aktuella perioden. Vilande användare räknas inte med i det totala antalet aktiva användare.

>[!NOTE]
>
>Upprepade användare tas inte med i beräkningen eftersom de inte representerar någon ökning eller förlust av användare.

![Nettotillväxt](../assets/net-growth.png)

## Se hur vyn för nettotillväxt fungerar i praktiken

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)

## Användningsexempel

Exempel:

* **Resultatutvärdering**: Gör att du kan bedöma den övergripande prestandan för din produkt när det gäller att köpa nya användare. Genom att följa tillväxttrender kan du bättre förstå om produkten lockar och behåller användare i önskad takt.
* **Analys av kundvärvning**: Gör att ni kan bedöma hur effektiva era strategier för kundförvärv är. Genom att analysera källor till användartillväxt, t.ex. sökmotorer, kampanjer eller andra marknadsföringskanaler, kan ni identifiera de viktigaste tillväxtkällorna så att ni kan tilldela resurser i enlighet med detta.
* **Kurnanalys**: Nettotillväxt inkluderar attrition i sin formel (vilande användare). Du kan utvärdera den övergripande statusen för din användarbas över tiden. Om nettotillväxten är konsekvent nedan `1`innebär det en hög grad av attribuering som kan leda till implementering av strategier för kvarhållande.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Events]**: Händelsen som du vill mäta. Eftersom den här vytypen är användarbaserad räknas en användare som interagerar med händelsen en gång inom perioden som en aktiv användare. Du kan inkludera en händelse i en fråga.
* **[!UICONTROL People]**: Det segment som du vill mäta. Du kan inkludera ett segment i en fråga.

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
