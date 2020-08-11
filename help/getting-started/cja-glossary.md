---
title: ordlista för kundresursanalys
description: ordlista för kundens Journey Analytics.
translation-type: tm+mt
source-git-commit: 307bfae11f44d088aa8d004f1f7ddd17375f60fc
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 1%

---


# ordlista för kundresursanalys

Vissa kundens Journey Analytics-termer skiljer sig från hur de traditionellt har använts i Adobe Analytics:

| Ny kundens resesanalysterterm | Adobe Analytics-term | Beskrivning |
|---|---|---|
| Uppslagsuppsättning av datamängd | Klassificering | Använd sökning för att hämta värdet från den angivna datauppsättningen för en nyckel/matchande nyckel (i en händelsedatamängd) där det finns en 1-till-1-relation. Du kan till exempel ange &quot;trace_code&quot; som den nyckel som matchar &quot;trace_code&quot; i händelsedatamängden. |
| Profildatamängd | Kundattribut | Om du registrerar företagskunddata i en kundrelationsdatabas (CRM) kan du överföra data till en profildatamängd i Adobe Experience Platform. När du har skapat en anslutning till den datauppsättningen i Customer Journey Analytics och skapat en datavy kan du dra nytta av data på arbetsytan. |
| Inloggningsföretag | Experience Cloud-organisation | Se [Organisationer och kontokopplingar](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#topic_C31CB834F109465A82ED57FF0563B3F1). |
| Ej tillämpligt | Report Suite | Rapportsviter i traditionell Adobe Analytics-mening finns inte längre. I stället skapar du (virtuell) [datavyer](/help/data-views/create-dataview.md) från de plattformsdatauppsättningar som du upprättade anslutningar till. |
| Filter | Segment | Segment är nu filter. Filter i Customer Journey Analytics beter sig på samma sätt som segment. Endast terminologin har ändrats. |
| Datavy | Virtuellt rapportpaket | I Adobe Analytics är ett virtuellt rapportpaket en segmenterad vy av ett överordnat rapportpaket. Den största skillnaden mellan en virtuell rapportsvit och en datavyn i CJA är att den virtuella rapportssviten är en delmängd av en &quot;base&quot;- eller &quot;överordnad&quot; rapportsssvit och därmed ärver några av dess inställningar. Eftersom överordnad/basrapportsviter inte längre finns definierar du datavyer med egna inställningar. |

## ordlista för Adobe Experience Platform

I Adobe Experience Platform standardiseras data och innehåll i hela företaget, vilket ger en stark konsumentprofil i realtid, gör det möjligt att använda datavetenskap och snabbare innehållshastighet för att göra upplevelsen av anpassning under hela kundresan.
Se [Ordlistan i Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/services/acp-glossary.html)för mer information.
