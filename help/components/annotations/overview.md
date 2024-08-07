---
title: Översikt över anteckningar
description: Så här använder du anteckningar i Workspace.
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Översikt över anteckningar

Anteckningar gör att ni effektivt kan kommunicera kontextuella datanunkter och insikter till organisationen. De gör att du kan koppla kalenderhändelser till specifika mått/mätvärden. Du kan anteckna ett datum eller datumintervall med kända dataproblem, allmänna helgdagar, kampanjstarter osv. Du kan sedan visa händelser grafiskt och se om kampanjer eller andra händelser har påverkat webbplatstrafiken, användningen av mobilappar, intäkterna eller andra mätvärden.

Anta att du delar projekt med din organisation. Om trafiken har ökat mycket på grund av en marknadsföringskampanj kan du skapa en kommentar om startdatum för kampanjen och ange den som omfattning för hela datavyn. När användarna visar datauppsättningar som innehåller det datumet, ser de anteckningen i sina projekt, tillsammans med deras data.

![Linjediagram med anteckning markerad.](assets/multi-day.png)

Tänk på detta:

* Anteckningar kan knytas till ett enstaka datum eller till ett datumintervall.

* De kan användas på hela datauppsättningen eller på angivna mått, dimensioner eller filter.

* De kan gälla för det projekt i vilket de skapades (standard) eller för alla projekt.

* De kan gälla för datavyn som de skapades i (standard) eller för alla datavyer.

## Behörigheter

Som standard kan bara administratörer skapa anteckningar. Användare har rätt att visa anteckningar på samma sätt som andra Analytics-komponenter (t.ex. filter, beräknade värden).

Administratörer kan dock ge användare behörigheten [!UICONTROL Annotation Creation] (analysverktyg) via [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html).

## Aktivera eller inaktivera anteckningar {#annotations-on-off}

Anteckningar kan aktiveras och avaktiveras på flera nivåer:

* På visualiseringsnivå: [!UICONTROL Visualization] inställningar > [!UICONTROL Show annotations]

* På projektnivå: [!UICONTROL Project info & settings] > [!UICONTROL Show annotations]

* På användarnivå: [!UICONTROL Components] > [!UICONTROL User preferences] > [!UICONTROL Data] > [!UICONTROL Show annotations]

![Dialogrutan Visualiseringsinställningar med Visa anteckningar markerat](assets/show-ann.png)

![Användarinställningar markerar Visa anteckningar.](assets/show-ann2.png)
