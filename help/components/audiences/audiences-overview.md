---
title: Läs mer om publiceringsöversikten för Customer Journey Analytics Publikationer
description: Läs mer om begreppet målgruppspublicering i Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 1%

---

# Översikt över publikpublicering

Nu kan du skapa och publicera målgrupper som identifierats i Customer Journey Analytics till [kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv) i Adobe Experience Platform för kundanpassning och personalisering.

Att publicera målgrupper är ett tydligt sätt att aktivera och vidta åtgärder för insikter som hittas i Customer Journey Analytics. Dessa åtgärder kan omfatta:

* Använda publiken för en resa i Adobe Journey Optimizer.
* Exportera målgruppen till en tredje part via ett Experience Platform-mål.
* Förbättra kundprofilen i realtid med användbara attribut som bygger på händelsebaserade data i Customer Journey Analytics.
* Allt detta med minimal fördröjning efter publikens publicering. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)
* Publicera engångspublikationer eller återkommande målgrupper.

De målgrupper du skapar i Customer Journey Analytics behöver inte baseras på datauppsättningar som är aktiverade för profilen. Du kan importera historiska data till Experience Platform utan att aktivera associerade datauppsättningar och scheman för profilen. Använd sedan dessa datauppsättningar för att identifiera relevanta målgrupper i Customer Journey Analytics och publicera dessa målgrupper i kundprofilen i realtid i Experience Platform för aktiveringsändamål.

## Nyckelterminologi

**Målgrupp**: En uppsättning eller lista med identiteter som har både ett namnutrymme och ett specifikt ID relaterat till det namnutrymmet. Publiken är flyttbar från Adobe Experience Platform och program som finns ovanpå det (till exempel Customer Journey Analytics). Publiker kan innehålla blandade namnutrymmen.

**Filter**: En uppsättning regler som, när de utvärderas över en datauppsättning för en tidsperiod, skapar en delmängd av data. Ett filter kan användas för att skapa en målgrupp i kombination med andra stödtjänster. Filter definieras och bevaras i Customer Journey Analytics.

**Filter** kontra **segment**: Customer Journey Analytics använder inte konceptet *segment* - i stället används *filter*. Båda är en uppsättning regler som kan innehålla liknande logik, men de ger olika utdata. Ett filter används för att begränsa en datauppsättning för analysändamål. Ett segment används för att skapa en lista med identiteter som kan användas för aktivering. Segment producerar målgrupper i kundprofilen i realtid, men inte filter (enbart). Customer Journey Analytics Audience Publishing är den process genom vilken vi använder ett Customer Journey Analytics-filter för att skapa en målgrupp som kan konsumeras av kundprofilen i realtid.

## Behörigheter

* Administratörer får automatiskt behörighet **[!UICONTROL Audience Publishing]** i Adobe Admin Console.

* Administratörer och produktprofiladministratörer kan ge enskilda användare behörighet att **[!UICONTROL Audience Creation]** och **[!UICONTROL Audience View]**. Mer information finns i [Åtkomstkontroll på användarnivå](/help/technotes/access-control.md#user-level-access).

* Administratörer behöver även behörigheten **[!UICONTROL Manage Profiles]** i Adobe Experience Platform.

## Datastyrning och samtycke

När du publicerar en målgrupp i Customer Journey Analytics registreras de datastyrningsetiketter och policyer som är kopplade till de fält som används i målgruppen.  När målgruppen aktiveras i någon av Adobe Experience App finns alla tillhörande etiketter och policyer för datastyrning tillgängliga för den målgruppen och lämplig tillsyn kan tillämpas. [Läs mer om samtycke](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#consent-policy).

## Nästa steg

* [Skapa och publicera målgrupper](/help/components/audiences/publish.md)
* [Hantera målgrupper](/help/components/audiences/manage.md)
