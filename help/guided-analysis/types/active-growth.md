---
title: Aktiv tillväxtvy
description: Identifiera vem som är ny, bevarad, återvändande eller vilande.
exl-id: 53ef7485-9cae-4663-bf61-4eb77c126830
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
role: User
source-git-commit: 8592d6d5d4a9d7b8ac6a40963059d386ec5ee804
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# [!UICONTROL Active growth]-vy

Vyn ![PeopleGroup](/help/assets/icons/PeopleGroup.svg) **[!UICONTROL Active growth]** ger insikter om användarnas tillväxt och förvärv under en viss period. Den vågräta axeln är ett tidsintervall, medan den lodräta axeln är ett mått på användare. Användarna är indelade i fyra kategorier:

* **[!UICONTROL New]**: Användaren var aktiv under den aktuella perioden, men inte tidigare. Se hur långt analysen ser tillbaka genom att hålla pekaren över _[!UICONTROL New users]_i diagramförklaringen. Uppslagsintervallet bestäms dynamiskt utifrån det valda datumintervallet och intervallet.
* **[!UICONTROL Repeat]**: Användaren var aktiv i den aktuella och omedelbart föregående perioden.
* **[!UICONTROL Return]**: Användaren var aktiv under den aktuella perioden och inte aktiv under den omedelbart föregående perioden, men var tidigare aktiv vid något tillfälle. Se hur långt analysen ser tillbaka genom att hålla pekaren över _[!UICONTROL Return users]_i diagramförklaringen. Uppslagsintervallet bestäms dynamiskt utifrån det valda datumintervallet och intervallet.
* **[!UICONTROL Dormant]**: Användaren var aktiv i den omedelbart föregående perioden, men är inte aktiv i den aktuella perioden. Vilande användare räknas inte med i det totala antalet aktiva användare.

Alla aktiva användare (nya + upprepning + retur) visas som en provton ovanför den vågräta axeln, medan alla vilande användare visas i orange under den vågräta axeln.

>[!VIDEO](https://video.tv.adobe.com/v/3421667/?learn=on)

## Användningsexempel

Exempel:

* **Kvarhållande och urholkning av användare:** Skapar en tydlig visualisering av perioder med hög eller låg användarlojalitet. Genom att känna igen dessa perioder av hög eller låg lojalitet kan du fatta produktbeslut för att öka kundlojaliteten eller hjälpa till att minimera bortfallet.
* **Kampanjbedömning**: Om du visar en viss kampanj kan du få en förståelse för hur mycket trafik den genererade och hur bra den hjälpte användarna att vara engagerade.
* **Livscykelanalys för användare**: Genom att analysera aktiv användartillväxt under hela användarlivscykeln kan du identifiera specifika faser där användarinteraktionen försvinner. Om det till exempel finns ett stort antal vilande användare för enskilda personer i ett introduktionsstadium kan det tyda på användarvänlighetsproblem eller ett behov av bättre produktvägledning.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan vytypen och [Nettotillväxt](net-growth.md).
* **[!UICONTROL Events]**: Den händelse som du vill mäta. Eftersom den här vytypen är användarbaserad räknas en användare som interagerar med händelsen en gång inom perioden som en aktiv användare. Du kan inkludera en händelse i en fråga.
* **[!UICONTROL Counted as]**: Den beräkningsmetod som du vill använda för de markerade händelserna. Alternativen är [!UICONTROL Number of users] och [!UICONTROL Percentage of users].
* **[!UICONTROL Segments]**: Det segment som du vill filtrera data efter. Du kan inkludera ett segment i en fråga.

## Diagraminställningar

I vyn [!UICONTROL Active] finns följande diagraminställningar som kan justeras på menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen är [!UICONTROL Stacked bar] och [!UICONTROL Stacked area].

## Tidsjämförelse

{{apply-time-comparison}}

![Aktiv tidsjämförelse](../assets/active-compare.png){style="border:1px solid gray"}

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Giltiga alternativ är Timly, Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall, vilket påverkar antalet datapunkter i diagrammet och antalet kolumner i tabellen. Om du till exempel visar en analys som sträcker sig över tre dagar med daglig granularitet visas bara tre datapunkter, medan en analys som sträcker sig över tre dagar med timgranularitet visar 72 datapunkter.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
