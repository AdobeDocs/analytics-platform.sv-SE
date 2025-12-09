---
title: Läs mer om publiceringsöversikten för Customer Journey Analytics Audiences
description: Läs om begreppet målgruppspublicering i Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: a8ac74b31beb3378de282ac4b0b632e0f2bd8230
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Översikt över publikpublicering

<!-- Add this when Audience Analysis releases:

>[!NOTE]
>
>Understand the difference between audience analysis and audience publishing:
>
>* **Audience analysis**: Allows you to ingest audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection. For information about audience analysis, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md)
>* **Audience publishing**: Allows you to create and publish audiences discovered in Customer Journey Analytics to Adobe Experience Platform for customer targeting and personalization. 

-->

Du kan skapa och publicera målgrupper som identifierats i Customer Journey Analytics till [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv) i Adobe Experience Platform för kundanpassning och personalisering.

<!-- add this when Audience Analysis releases: (For information about ingesting audience membership data from Experience Platform Profile datasets into a Customer Journey Analytics connection, see [Audience analysis overview](/help/connections/audience-analysis/audience-analysis-overview.md).) -->

Att publicera målgrupper är ett tydligt sätt att aktivera och vidta åtgärder för insikter som hittas i Customer Journey Analytics. Dessa åtgärder kan omfatta:

* Använda publiken för en resa i Adobe Journey Optimizer.
Mer information om hur du använder målgrupper som publicerats till Experience Platform finns i [Kom igång med målgrupper](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/audiences-profiles-identities/audiences/about-audiences) i Journey Optimizer-dokumentationen.
* Exportera målgruppen till en tredje part via ett Experience Platform-mål.
* Förbättra kundprofilen i realtid med användbara attribut som bygger på händelsebaserade data i Customer Journey Analytics.
* Allt detta med minimal fördröjning efter publikens publicering.
Mer information finns i [Fördröjningsfrågor](/help/components/audiences/publish.md#latency-considerations) i [Skapa och publicera målgrupper](/help/components/audiences/publish.md).
* Publicera engångspublikationer eller återkommande målgrupper.

De målgrupper du skapar i Customer Journey Analytics behöver inte baseras på datauppsättningar som är aktiverade för profilen. Du kan importera historiska data till Experience Platform utan att aktivera associerade datauppsättningar och scheman för profilen. Använd sedan dessa datauppsättningar för att identifiera relevanta målgrupper i Customer Journey Analytics och publicera dessa målgrupper i kundprofilen i realtid i Experience Platform för aktiveringsändamål.

## Nyckelterminologi

**Målgrupp**: En uppsättning eller lista med identiteter som har både ett namnutrymme och ett specifikt ID relaterat till det namnutrymmet. Publiken kan flyttas från Adobe Experience Platform och program som finns ovanpå det (som Customer Journey Analytics). Publiker kan innehålla blandade namnutrymmen.

**Segment**: En uppsättning regler som, när de utvärderas över en datauppsättning för en tidsperiod, skapar en delmängd av data. Ett segment kan användas för att skapa en målgrupp i kombination med andra stödtjänster. Segment definieras och underhålls i Customer Journey Analytics.

## Behörigheter

* Administratörer får automatiskt behörighet **[!UICONTROL Audience Publishing]** i Adobe Admin Console.

* Administratörer och produktprofiladministratörer kan ge enskilda användare behörighet att **[!UICONTROL Audience Creation]** och **[!UICONTROL Audience View]**. Mer information finns i [Åtkomstkontroll på användarnivå](/help/technotes/access-control.md#user-level-access).

* Administratörer behöver även behörigheten **[!UICONTROL Manage Profiles]** i Adobe Experience Platform.

## Datastyrning och samtycke

När du publicerar en målgrupp i Customer Journey Analytics registreras de etiketter och profiler för datastyrning som är kopplade till de fält som används i målgruppen.  När målgruppen aktiveras i någon av Adobe Experience App finns alla tillhörande etiketter och policyer för datastyrning tillgängliga för den målgruppen och lämplig tillsyn kan tillämpas. [Läs mer om samtycke](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=sv-SE#consent-policy).

## Nästa steg

* [Skapa och publicera målgrupper](/help/components/audiences/publish.md)
* [Hantera målgrupper](/help/components/audiences/manage.md)
