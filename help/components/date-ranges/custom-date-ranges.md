---
description: Skapa anpassade datumintervall i Analysis Workspace och spara dem som tidskomponenter.
keywords: Analysis Workspace
title: Skapa anpassade datumintervall
topic: Reports and analytics
uuid: c8873d41-454d-4f22-ad1f-38cacec5a3bc
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 3%

---


# Skapa anpassade datumintervall

>[!NOTE] Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Skapa anpassade datumintervall i Analysis Workspace och spara dem som tidskomponenter.

**[!UICONTROL Components]** > **[!UICONTROL New Date Range]**

Ett datumintervall används på panelnivå. Om du vill lägga till ett datumintervall i projektet klickar du på **Paneler** > *`<select panel>`* och anger ett nytt datumintervall.

## Datumintervall för&quot;två månader sedan&quot;

I följande anpassade datumintervall visas ett datumintervall för&quot;två månader sedan&quot;, med en visualisering av Sammanfattningsändring som visar en riktningsändring.

![](assets/date-range-two-months-ago.png)

Det anpassade datumintervallet visas högst upp på [!UICONTROL Date Range] komponentpanelen i projektet:

![](assets/date-range-panel-two-months-ago.png)

Du kan dra det här anpassade datumintervallet till en kolumn tillsammans med ett anpassat, månatligt löpande datumintervall med hjälp av förinställningen Sista månaden för en jämförelse. Lägg till en visualisering av sammanfattningsändring och välj summorna från varje kolumn för att visa riktningsändring:

![](assets/date-range-two-months-table.png)

## Använd ett 7-dagars rullande datumintervall

Ett datumintervall gäller för panelnivån. Om du vill lägga till ett datumintervall i projektet klickar du på **Åtgärder** > **Lägg till panel** och anger ett nytt datumintervall.

I Date Range Builder kan du skapa ett anpassat datumintervall som visas med andra datumintervall på panelen Komponenter.

Du kan till exempel skapa ett datumintervall som anger ett 7-dagars rullande fönster som slutar för en vecka sedan:

![](assets/create_date_range.png)

Använd *`rolling daily`*.

* Startinställningarna blir *`current day minus 14 days`*.

* Slutinställningarna blir *`current day minus 7 days`*.

Datumintervallet kan vara en komponent som du drar till en frihandstabell.
