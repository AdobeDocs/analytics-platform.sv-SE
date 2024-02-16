---
title: Vyn Nettotillväxt
description: Kommer du att få eller förlora användare?
feature: Guided Analysis
keywords: produktanalys
exl-id: a4f97458-9934-4a98-8005-fa1ba7831101
role: User
source-git-commit: e448f6ddbff2673abbd2920aacf41d4268f3ce07
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 0%

---

# [!UICONTROL Net growth] visa

The **[!UICONTROL Net growth]** vytypen ger insikter om i vilken takt du vinner eller förlorar användare under en viss period. Den vågräta axeln är ett tidsintervall, medan den lodräta axeln är tillväxtmåttet.

Varje datapunkt representerar nettotillväxt, som beräknas med följande formel:

`([New users] + [Return users]) / [Dormant users]`

Resultatet av den här formeln är ett förhållande. En nettoökning av `1` representerar en jämvikt, produkten har fått samma antal användare som den förlorade. En nettotillväxt som är större än `1` representerar positiv tillväxt; det fanns fler nya +-användare än vilande användare. En nettotillväxt som är mindre än `1` representerar en förlust. Det fanns fler vilande användare än nya +-användare.

Liknar [Aktiv](active.md) -vy definieras användare som följande:

* **[!UICONTROL New]**: Användaren var aktiv under den aktuella perioden, men inte tidigare. Se hur långt analysen ser tillbaka för att avgöra en ny användare genom att hålla pekaren över[!UICONTROL New users]&#39; i diagramförklaringen. Uppslagsintervallet bestäms dynamiskt utifrån det valda datumintervallet och intervallet.
* **[!UICONTROL Return]**: Användaren var aktiv under den aktuella perioden och inte aktiv under den omedelbart föregående perioden, men var tidigare aktiv vid något tillfälle. Se hur långt tillbaka analysen ser ut för att bestämma en returanvändare genom att hålla pekaren över[!UICONTROL Return users]&#39; i diagramförklaringen. Uppslagsintervallet bestäms dynamiskt utifrån det valda datumintervallet och intervallet.
* **[!UICONTROL Dormant]**: Användaren var aktiv i den omedelbart föregående perioden, men är inte aktiv i den aktuella perioden. Vilande användare räknas inte med i det totala antalet aktiva användare.

>[!NOTE]
>
>Upprepade användare tas inte med i beräkningen eftersom de inte representerar någon ökning eller förlust av användare.

>[!VIDEO](https://video.tv.adobe.com/v/3421664/?learn=on)

## Användningsexempel

Exempel:

* **Resultatutvärdering**: Gör att du kan bedöma den övergripande prestandan för din produkt när det gäller att köpa nya användare. Genom att följa tillväxttrender kan du bättre förstå om produkten lockar och behåller användare i önskad takt.
* **Analys av kundvärvning**: Gör att ni kan bedöma hur effektiva era strategier för kundvärvning är. Genom att analysera källor till användartillväxt, t.ex. sökmotorer, kampanjer eller andra marknadsföringskanaler, kan ni identifiera de viktigaste tillväxtkällorna så att ni kan tilldela resurser i enlighet med detta.
* **Kurnanalys**: Nettotillväxt inkluderar attrition i sin formel (vilande användare). Du kan utvärdera den övergripande statusen för din användarbas över tiden. Om nettotillväxten är konsekvent nedan `1`innebär det en hög grad av attribuering som kan leda till implementering av strategier för kvarhållande.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan den här vytypen och [Aktiv](active.md).
* **[!UICONTROL Events]**: Den händelse som du vill mäta. Eftersom den här vytypen är användarbaserad räknas en användare som interagerar med händelsen en gång inom perioden som en aktiv användare. Du kan inkludera en händelse i en fråga.
* **[!UICONTROL Counted as]**: Den nedräkningsmetod som du vill använda för de markerade händelserna. Alternativen inkluderar [!UICONTROL Number of users] och [!UICONTROL Percentage of users].
* **[!UICONTROL Segments]**: Det segment som du vill mäta. Du kan inkludera ett segment i en fråga.

## Tidsjämförelse

{{apply-time-comparison}}

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall som påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
