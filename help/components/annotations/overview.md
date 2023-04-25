---
title: Översikt över anteckningar
description: Så här använder du anteckningar i Workspace.
role: User, Admin
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
source-git-commit: 8e902022c07376fb3c13cad5fd5b1efa655c9424
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 0%

---

# Översikt över anteckningar

Med anteckningar kan ni effektivt kommunicera kontextuella datanunkter och insikter till organisationen. De gör att du kan koppla kalenderhändelser till specifika mått/mätvärden. Du kan anteckna ett datum eller datumintervall med kända dataproblem, allmänna helgdagar, kampanjstarter osv. Du kan sedan visa händelser grafiskt och se om kampanjer eller andra händelser har påverkat webbplatsens trafik, intäkter eller andra mätvärden.

Anta att du delar projekt med din organisation. Om ni hade ett stort trafiksprång på grund av en marknadsföringskampanj kan ni skapa en kommentar om startdatum för kampanjer och ange den som omfattning för hela rapportsviten. När användarna visar datauppsättningar som innehåller det datumet, ser de anteckningen i sina projekt, tillsammans med deras data.

![](assets/multi-day.png)

Tänk på detta:

* Anteckningar kan knytas till ett enstaka datum eller till ett datumintervall.

* De kan gälla för hela datauppsättningen eller för angivna mått, dimensioner eller segment.

* De kan gälla för det projekt i vilket de skapades (standard) eller för alla projekt.

* De kan gälla för den rapportsserie som de skapades i (standard) eller för alla rapportsviter.

## Behörigheter

Som standard kan bara administratörer skapa anteckningar. Användare har rätt att visa anteckningar på samma sätt som andra Analytics-komponenter (som segment, beräknade värden osv.).

Administratörer kan dock ge [!UICONTROL Annotation Creation] behörighet (analysverktyg) till användare via [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html).

## Aktivera eller inaktivera anteckningar {#annotations-on-off}

Anteckningar kan aktiveras och avaktiveras på flera nivåer:

* På visualiseringsnivå: [!UICONTROL Visualization] inställningar > [!UICONTROL Show annotations]

* På projektnivå: [!UICONTROL Project info & settings] > [!UICONTROL Show annotations]

* På användarnivå: [!UICONTROL Components] > [!UICONTROL User preferences] > [!UICONTROL Data] > [!UICONTROL Show annotations]

![](assets/show-ann.png)

![](assets/show-ann2.png)
