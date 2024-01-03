---
description: Skapa anpassade datumintervall i Analysis Workspace och spara dem som tidskomponenter.
keywords: Analysis Workspace
title: Skapa anpassade datumintervall
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Skapa anpassade datumintervall

Skapa anpassade datumintervall i Analysis Workspace och spara dem som tidskomponenter.

**[!UICONTROL Components]** > **[!UICONTROL New Date Range]**

Ett datumintervall används på panelnivå. Om du vill lägga till ett datumintervall i projektet klickar du på **Panel** > *`<select panel>`* och ange ett nytt datumintervall.

## Datumintervall för&quot;två månader sedan&quot;

I följande anpassade datumintervall visas ett datumintervall för&quot;två månader sedan&quot;, med en visualisering av Sammanfattningsändring som visar en riktningsändring.

![Date Range Builder som visar Använd rullande datum för två månader sedan](assets/date-range-two-months-ago.png)

Det anpassade datumintervallet visas högst upp i [!UICONTROL Date Range] komponentpanelen i ditt projekt:

![Panelen Datumintervallkomponent med pilen pekar på För två månader sedan.](assets/date-range-panel-two-months-ago.png)

Du kan dra det här anpassade datumintervallet till en kolumn tillsammans med ett anpassat, månatligt löpande datumintervall med hjälp av förinställningen Senaste månaden för en jämförelse. Lägg till en visualisering av sammanfattningsändring och välj summorna från varje kolumn för att visa riktningsändring:

![Ökning med 14,45%.](assets/date-range-two-months-table.png)

## Använd ett 7-dagars rullande datumintervall

Ett datumintervall gäller för panelnivån. Om du vill lägga till ett datumintervall i projektet klickar du på **Åtgärder** > **Lägg till panel** och ange ett nytt datumintervall.

I Date Range Builder kan du skapa ett anpassat datumintervall som visas med andra datumintervall på panelen Komponenter.

Du kan till exempel skapa ett datumintervall som anger ett 7-dagars rullande fönster som slutar för en vecka sedan:

![Date Range Builder med ett datumintervall som anger ett 7-dagars rullningsfönster.](assets/create_date_range.png)

Använd *`rolling daily`*.

* Startinställningarna blir *`current day minus 14 days`*.

* Slutinställningarna blir *`current day minus 7 days`*.

Det här datumintervallet kan vara en komponent som du drar till en frihandstabell.
