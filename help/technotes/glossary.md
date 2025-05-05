---
title: Customer Journey Analytics ordlista
description: Customer Journey Analytics ordlista.
exl-id: 7f8aac93-0103-4ead-b25b-3d9994a271af
solution: Customer Journey Analytics
feature: Basics
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# Customer Journey Analytics ordlista

Vissa Customer Journey Analytics-termer skiljer sig från hur de traditionellt har använts i Adobe Analytics:

| Ny Customer Journey Analytics-term | Adobe Analytics term | Beskrivning |
| --- | --- | --- |
| Sök datauppsättning | Klassificering | Använd sökning för att hämta värdet från den angivna datauppsättningen för en nyckel/matchande nyckel (i en händelsedatamängd) där det finns en 1-till-1-relation. Du kan till exempel ange&quot;tracking_code&quot; som den nyckel som matchar&quot;tracking_code&quot; i händelsedatamängden. |
| Profildatamängd | Kundattribut | Om du samlar in företagsdata i en CRM-databas (customer relationship management) kan du överföra dessa data till en profildatauppsättning i Adobe Experience Platform. När du har skapat en anslutning till datauppsättningen i Customer Journey Analytics och skapat en datavy kan du utnyttja data i Workspace. |
| Experience Cloud | Inloggningsföretag | Se [Organisationer och kontolänkning](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=sv-SE#topic_C31CB834F109465A82ED57FF0563B3F1). |
| Ej tillämpligt | Report Suite | Rapporteringssviter i traditionell Adobe Analytics-mening finns inte längre. I stället skapar du (virtuella) [datavyer](/help/data-views/create-dataview.md) från de plattformsdatauppsättningar som du har upprättat anslutningar till. |
| Segment | Segment | Segment brukade vara &quot;filter&quot;. De har bytt namn till&quot;segment&quot;. |
| Datavy | Virtuell rapportsvit | I Adobe Analytics är ett virtuellt rapportpaket en filtrerad vy av ett överordnat rapportpaket. Den största skillnaden mellan ett virtuellt rapportpaket och en datavy i Customer Journey Analytics är att det virtuella rapportpaketet är en delmängd av ett rapportpaket av typen&quot;base&quot; eller&quot;parent&quot; och därför ärver några av dess inställningar. Eftersom det inte längre finns några överordnade rapportsviter/basrapportsviter definierar du datavyer med egna inställningar. |

## Adobe Experience Platform ordlista

Adobe Experience Platform standardiserar data och innehåll i hela företaget, vilket driver konsumentprofiler i realtid, möjliggör datavetenskap och snabbar upp innehållets hastighet för att driva upplevelsepersonalisering över hela kundresan.
Mer information finns i [Adobe Experience Platform-ordlistan](https://experienceleague.adobe.com/docs/experience-platform/landing/glossary.html?lang=sv-SE).
