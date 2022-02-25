---
title: Customer Journey Analytics ordlista
description: Customer Journey Analytics ordlista.
exl-id: 7f8aac93-0103-4ead-b25b-3d9994a271af
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 04ceeb9e9a048a224ea957ad42bc54cbd4b3f249
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 1%

---

# Customer Journey Analytics ordlista

Vissa Customer Journey Analytics-termer skiljer sig från hur de traditionellt har använts i Adobe Analytics:

| Ny Customer Journey Analytics-term | Adobe Analytics | Beskrivning |
| --- | --- | --- |
| Sök datauppsättning | Klassificering | Använd sökning för att hämta värdet från den angivna datauppsättningen för en nyckel/matchande nyckel (i en händelsedatamängd) där det finns en 1-till-1-relation. Du kan till exempel ange&quot;tracking_code&quot; som den nyckel som matchar&quot;tracking_code&quot; i händelsedatamängden. |
| Profildatamängd | Kundattribut | Om du samlar in företagsdata i en CRM-databas (customer relationship management) kan du överföra dessa data till en profildatauppsättning i Adobe Experience Platform. När du har skapat en anslutning till datauppsättningen i Customer Journey Analytics och skapat en datavy kan du utnyttja data i Workspace. |
| Inloggningsföretag | Experience Cloud organisation | Se [Organisationer och kontolänkning](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#topic_C31CB834F109465A82ED57FF0563B3F1). |
| Ej tillämpligt | Report Suite | Rapporteringssviter i traditionell Adobe Analytics-mening finns inte längre. I stället skapar du (virtuell) [datavyer](/help/data-views/create-dataview.md) från de plattformsdatauppsättningar som du har upprättat anslutningar till. |
| Filter | Segment | Segment är nu filter. Filter i Customer Journey Analytics fungerar på samma sätt som segment. Bara terminologin har ändrats. |
| Datavy | Virtuell rapportsvit | I Adobe Analytics är ett virtuellt rapportpaket en filtrerad vy av ett överordnat rapportpaket. Den största skillnaden mellan ett virtuellt rapportpaket och en datavy i CJA är att det virtuella rapportpaketet är en delmängd av ett rapportpaket av typen&quot;bas&quot; eller&quot;överordnad&quot; och därför ärver några av dess inställningar. Eftersom det inte längre finns några överordnade rapportsviter/basrapportsviter definierar du datavyer med egna inställningar. |

## Adobe Experience Platform ordlista

Adobe Experience Platform standardiserar data och innehåll i hela företaget, vilket driver konsumentprofiler i realtid, möjliggör datavetenskap och snabbar upp innehållets hastighet för att driva upplevelsepersonalisering över hela kundresan.
Se [Adobe Experience Platform-ordlista](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html?lang=en)för mer information.
