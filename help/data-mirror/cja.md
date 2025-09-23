---
title: Konfigurera Customer Journey Analytics
description: Lär dig hur du konfigurerar Customer Journey Analytics-anslutningar, datavyer och projekt för Experience Platform Data Mirror för Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
source-git-commit: 9bd124ad651274b48052edc56bfb72358aa2d79a
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---


# Konfigurera Customer Journey Analytics

Om du vill använda funktionen Experience Platform Data Mirror för Customer Journey Analytics måste du skapa eller uppdatera anslutningar, datavyer och arbetsyteprojekt för att kunna använda modellbaserade data.

## Anslutningar

Lägg till modellbaserade datauppsättningar som representerar data från de inbyggda datalagerlösningarna i din anslutning. Dessa datauppsättningar har datatypen Model.

När du lägger till en modellbaserad datauppsättning som innehåller speglade data från en inbyggd datalagerlösning är dessa data vanligtvis händelsedata. Se till att du väljer rätt inställningar för datauppsättningen. Välj till exempel rätt datamängdstyp, fält för identitet och fält för tidsstämpel.


## Datavyer

Definiera fält från det modellbaserade schemat som komponenter (mått och mått) i datavyn. Datasegmenterade fält är tillgängliga i undermappen **[!UICONTROL Adhoc & Model-based fields]** i mappen **[!UICONTROL Event datasets]**. Använd funktioner som [härledda fält](/help/data-views/derived-fields/derived-fields.md) eller [komponentinställningar](/help/data-views/component-settings/overview.md) för att ändra komponenterna som är baserade på modellbaserade fält.


## Workspace-projekt

Ställ in Workspace-projekt som använder mått och mätvärden från era modellbaserade data. Komponenter som i slutändan baseras på data i den inbyggda datalagerlösningen. Och uppdateras baserat på den dataspegelfunktion du har konfigurerat.

>[!MORELIKETHIS]
>
>[Data Mirror snabbstartsguide: Spegla och använda modellbaserade data](data-mirror.md)
>