---
title: Hantera din användning av Customer Journey Analytics
description: Beskriver hur du hanterar användningen av Customer Journey Analytics.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 5311106f486a30dbc7f06b3ef60dc7e666d2fe03
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---

# Hantera din användning av Customer Journey Analytics

>[!TIP]
>
>Använd [**[!UICONTROL Usage]**-gränssnittet](/help/connections/manage-connections.md#usage) för att** visa **hur inkapslade och rapportbara rader används i alla anslutningar i Customer Journey Analytics.



Du kan hantera din Customer Journey Analytics-användning i [**[!UICONTROL Connections]**-gränssnittet](/help/connections/create-connection.md). I det här gränssnittet kan du definiera Customer Journey Analytics datalagring som ett rullande fönster på en månad (1 månad, 3 månader, 6 månader osv.) på anslutningsnivå.

Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader.

Om du låter standardvärdet vara (omarkerat) ersätts kvarhållningsperioden av Adobe Experience Platform datalagringsinställning. Om ni har 25 månaders data i Experience Platform får Customer Journey Analytics 25 månaders data genom förifyllning. Om du raderade 10 av dessa månader i Platform behåller Customer Journey Analytics de återstående 15 månaderna.

Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för rullande datafönster för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar. Om din anslutning innehåller någon profil- eller sökdatamängd, eftersom de har förenats med händelsedatamängder, behålls data i Customer Journey Analytics baserat på dina datalagringsinställningar för händelsedatamängdens tidsstämplar.


>[!MORELIKETHIS]
>
>[Visa din Customer Journey Analytics-användning](/help/connections/manage-connections.md#usage)

