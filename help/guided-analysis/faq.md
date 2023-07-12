---
title: Vanliga frågor om guidad analys
description: Vanliga frågor och svar om den guidade analysen.
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
source-git-commit: 23d3e6a9662cda932a376c09849ab078d22830dc
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---

# Vanliga frågor om guidad analys

{{release-limited-testing}}

Vanliga frågor och svar om den guidade analysen.

+++**Är guidad analys tillgänglig för alla?**

Nej. Guidad analys är ett betalt tillägg till Customer Journey Analytics. Om du vill börja använda det här tillägget kontaktar du kontoteamet på Adobe.

+++

+++**Vilka implementeringsändringar krävs för att använda den guidade analysen?**

Om du redan använder Analysis Workspace i Customer Journey Analytics behövs inga ytterligare implementeringsändringar. I den guidade analysen används samma datavyer och anslutningar som Analysis Workspace. Processen för att introducera och använda alla projekttyper är identisk för alla Customer Journey Analytics, inklusive guidad analys.

+++

+++**Hur relaterar termerna till varandra både inom och utanför den guidade analysen?**

I den guidade analysen används termer som används oftare i produktanalysbranschen. Du kan referera till den här tabellen när du växlar mellan guidad analys och Analysis Workspace.

| Guidad analysterm | Analysis Workspace |
| --- | --- |
| Händelse | Mått |
| Användare | Personer |
| Egenskap | Dimension |
| Värde | Dimension |
| Segment | Filter |

{style="table-layout:auto"}

+++

+++**Vad är det för skillnader i hur analysen av Analysis Workspace och den guidade analysen fungerar?**

Även om samma underliggande data används i Analysis Workspace- och Guidad analys är det sätt på vilket varje verktyg gör att du kan skapa frågor med dessa data annorlunda.

* **Analysis Workspace är en upplevelse som bygger på flera dimensioner.** Tabeller består vanligtvis av dimensionsobjektrader, medan kolumner vanligtvis är mått. Du kan använda filter på både rader och kolumner för att få fram önskade data.

* **Guidad analys är en händelsestyrd upplevelse.** Visualiseringar fokuserar på händelser och använder dimensioner och filter för att komplettera dessa data.

![Struktur](assets/structure.png)

Titta på följande exempel där du fokuserar på data runt hemsidan på din webbplats. Teamen ställer liknande frågor, men analysmetoden kan vara annorlunda.

* En typisk dimensionsinriktad Analysis Workspace-strategi skulle vara:&quot;Hur många sidvisningar har hemsidan fått?&quot;

  ![Dimension centrerad](assets/dimension-centered.png)

* En typisk händelsestyrd strategi för guidad analys skulle vara&quot;Hur många användare har sett hemsidan?&quot;

  ![Händelsecentrerad](assets/event-centered.png)

Dessa påståenden illustrerar två olika metoder för att uppnå samma rapport, beroende på din händelsehanteringsstrategi.

+++
