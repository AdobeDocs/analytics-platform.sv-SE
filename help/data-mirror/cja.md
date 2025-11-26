---
title: Konfigurera Customer Journey Analytics
description: Lär dig hur du konfigurerar Customer Journey Analytics-anslutningar, datavyer och projekt för Experience Platform Data Mirror för Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f7687bba-efbe-4a2c-8ad1-cf216554a1e9
source-git-commit: b2a13524760f9d466696534bc8b9691f3b4dfb8a
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---

# Konfigurera Customer Journey Analytics

{{release-limited-testing}}

{{relational-model-based}}

Om du vill använda Experience Platform Data Mirror-funktionen för Customer Journey Analytics måste du skapa eller uppdatera anslutningar, datavyer och arbetsyteprojekt för att kunna använda relationsdata.

## Anslutningar

Lägg till de relationsdatauppsättningar som representerar data från de systemspecifika datalagerlösningarna. Dessa datauppsättningar har datatypen Relational.

När du lägger till en relationsdatauppsättning som innehåller speglade data från en inbyggd datalagerlösning är dessa data vanligtvis händelsedata. Se till att du väljer rätt inställningar för datauppsättningen. Välj till exempel rätt datamängdstyp, fält för identitet och fält för tidsstämpel.


## Datavyer

Definiera fält från relationsschemat som komponenter (mått och mått) i datavyn. Datasegmenterade fält är tillgängliga i undermappen **[!UICONTROL Adhoc & relational fields]** i mappen **[!UICONTROL Event datasets]**. Använd funktioner som [härledda fält](/help/data-views/derived-fields/derived-fields.md) eller [komponentinställningar](/help/data-views/component-settings/overview.md) för att ändra komponenterna som baseras på relationsfält.


## Workspace-projekt

Ställ in Workspace-projekt som använder mått och mått från relationsdata. Komponenter som i slutändan baseras på data i den inbyggda datalagerlösningen. Och uppdateras baserat på den dataspegelfunktion du har konfigurerat.

>[!MORELIKETHIS]
>
>[Data Mirror snabbstartsguide: Spegla och använda relaldata](relational.md)
>
