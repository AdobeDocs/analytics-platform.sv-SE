---
title: Customer Journey Analytics-ordlista
description: Customer Journey Analytics-ordlista.
translation-type: tm+mt
source-git-commit: 36fcdaff24c3055f7ce45eecb7631baa3c087bdb

---


# Customer Journey Analytics-ordlista

Vissa kundreseanalysvillkor skiljer sig från hur de traditionellt har använts i Adobe Analytics:

| Adobe Analytics-villkor | Ny term för kundreseanalys | Beskrivning |
|---|---|---|
| Klassificering | Sök datauppsättning | ... |
| Kundattribut | Profildatamängd | Om du samlar in företagsdata i en CRM-databas (customer relationship management) kan du överföra dessa data till en profildatauppsättning i Adobe Experience Platform. När du har skapat en anslutning till den datauppsättningen i kundreseanalysen och skapat en datavy kan du utnyttja data i Workspace. |
| Inloggningsföretag | Experience Cloud-organisation | Se [Organisationer och kontolänkning](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#topic_C31CB834F109465A82ED57FF0563B3F1). |
| Report Suite | Ej tillämpligt | Rapporteringssviter i traditionell Adobe Analytics-mening finns inte längre. I stället skapar du (virtuella) [datavyer](/help/data-views/create-dataview.md) från de plattformsdatauppsättningar som du har upprättat anslutningar till. |
| Segment | Filter | Segment är nu filter. Filter i kundreseanalys fungerar på samma sätt som segment. Bara terminologin har ändrats. |
| Virtuell rapportsvit | Datavy | I Adobe Analytics är en virtuell rapportsvit en segmenterad vy av en överordnad rapportsvit. Den största skillnaden mellan ett virtuellt rapportpaket och en datavy i CJA är att det virtuella rapportpaketet är en delmängd av ett rapportpaket av typen&quot;bas&quot; eller&quot;överordnad&quot; och därför ärver några av dess inställningar. Eftersom det inte längre finns några överordnade rapportsviter/basrapportsviter definierar du datavyer med egna inställningar. |

## Adobe Experience Platform - ordlista

Adobe Experience Platform standardiserar data och innehåll i hela företaget och driver konsumentprofiler i realtid, möjliggör datavetenskap och snabbar upp innehållets hastighet för att driva upplevelsepersonalisering över hela kundresan.
Mer information finns i [Adobe Experience Platform](https://www.adobe.io/apis/experienceplatform/home/services/acp-glossary.html)Glossaryy.
