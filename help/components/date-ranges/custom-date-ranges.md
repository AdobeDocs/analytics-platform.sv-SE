---
description: Skapa anpassade datumintervall i Analysis Workspace och spara dem som tidskomponenter.
keywords: Analysis Workspace
title: Skapa anpassade datumintervall
feature: Calendar
exl-id: 1a7df63a-bf18-4c38-b7e2-e83c2d278544
source-git-commit: 3348117a5a6007017735a95aec26e6a8c88ad248
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 4%

---

# Skapa anpassade datumintervall

Skapa anpassade datumintervall i Analysis Workspace och spara dem som tidskomponenter.

**[!UICONTROL Components]** > **[!UICONTROL New Date Range]**

Ett datumintervall används på panelnivå. Om du vill lägga till ett datumintervall i projektet klickar du på **Paneler** > *`<select panel>`* och ange ett nytt datumintervall.

## Datumintervall för&quot;två månader sedan&quot;

I följande anpassade datumintervall visas ett datumintervall för&quot;två månader sedan&quot;, med en visualisering av Sammanfattningsändring som visar en riktningsändring.

![](assets/date-range-two-months-ago.png)

Det anpassade datumintervallet visas högst upp i [!UICONTROL Date Range] komponentpanelen i ditt projekt:

![](assets/date-range-panel-two-months-ago.png)

Du kan dra det här anpassade datumintervallet till en kolumn tillsammans med ett anpassat, månatligt löpande datumintervall med hjälp av förinställningen Sista månaden för en jämförelse. Lägg till en visualisering av sammanfattningsändring och välj summorna från varje kolumn för att visa riktningsändring:

![](assets/date-range-two-months-table.png)

## Använd ett 7-dagars rullande datumintervall

Ett datumintervall gäller för panelnivån. Om du vill lägga till ett datumintervall i projektet klickar du på **Åtgärder** > **Lägg till panel** och ange ett nytt datumintervall.

I Date Range Builder kan du skapa ett anpassat datumintervall som visas med andra datumintervall på panelen Komponenter.

Du kan till exempel skapa ett datumintervall som anger ett 7-dagars rullande fönster som slutar för en vecka sedan:

![](assets/create_date_range.png)

Använd *`rolling daily`*.

* Startinställningarna blir *`current day minus 14 days`*.

* Slutinställningarna blir *`current day minus 7 days`*.

Datumintervallet kan vara en komponent som du drar till en frihandstabell.
