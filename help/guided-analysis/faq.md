---
title: Vanliga frågor om guidad analys
description: Vanliga frågor om den guidade analysen.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: produktanalys
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Vanliga frågor om guidad analys

Vanliga frågor och svar om guidad analys.

+++**Hur kan vår organisation tillhandahållas för guidad analys?**

Guidad analys är en del av Adobe Product Analytics, ett betalt tillägg till Customer Journey Analytics. Om du vill börja använda det här tillägget kontaktar du kontoteamet på Adobe.

+++

+++**Vilka implementeringsändringar krävs för att använda guidad analys?**

Om du redan använder Customer Journey Analytics idag behövs inga ytterligare implementeringsändringar. Guidad analys använder samma [Datavyer](../data-views/data-views.md) och [Anslutningar](../connections/overview.md) som andra CJA-gränssnitt som [Analysis Workspace](../analysis-workspace/home.md).

För att dina slutanvändare ska kunna bli mest framgångsrika med guidad analys rekommenderar vi att du har ett starkt händelseschema och en hanteringsstrategi på plats i Adobe Experience Platform och [Datavyer](../data-views/data-views.md).

+++

+++**När ska du använda guidad analys eller Analysis Workspace?**

**Guidad analys** kan hjälpa användarna att snabbt få högkvalitativa insikter. Det är användbart för produktteam, användare som vill arbeta mer tillförlitligt med data och till och med analytiker som ett försprång i en djupare analys.

**[Analysis Workspace](../analysis-workspace/home.md)** är ett friare utrymme där du kan dyka längre in i data för att få fler insikter. Det är användbart för analytiker och avancerade användare som förstår data väl och vill djupdyka i det.

+++

+++**Hur jämförs terminologi mellan guidad analys och Analysis Workspace?**

I den guidade analysen används termer som används oftare bland produktteamen. Du kan referera till den här tabellen när du växlar mellan guidad analys och [Analysis Workspace](../analysis-workspace/home.md).

| Guidad analysterm | Analysis Workspace term |
| --- | --- |
| Händelse | Mått |
| Användare | Folk |
| Egenskap | Dimension |
| Värde | Dimension |
| Segment | Filter |

{style="table-layout:auto"}

+++

+++**Vad är det för skillnader mellan hur guidad analys och Analysis Workspace metodrapporter fungerar?**

while [Analysis Workspace](../analysis-workspace/home.md) och för guidad analys används samma underliggande data, på samma sätt som varje verktyg gör att du kan skapa frågor med dessa data på olika sätt.

* **Analysis Workspace är en upplevelse som bygger på flera dimensioner.** Tabeller består vanligtvis av dimensionella rader, medan kolumner vanligtvis är mätvärden. Du kan använda filter på både rader och kolumner för att få fram önskade data.

* **Guidad analys är en händelsestyrd och användarcentrerad upplevelse.** Varje analys börjar med att välja händelser, sedan kan mått och filter läggas till för att förfina händelsedata.

![Analysis Workspace och guidade analysvyer](assets/structure.png){style="border:1px solid gray"}

Titta på följande exempel där du fokuserar på data runt hemsidan på din webbplats. Teamen ställer liknande frågor, men analysmetoden kan vara annorlunda.

* En typisk dimensionsinriktad Analysis Workspace-strategi skulle vara:&quot;Vi tittar på startsidan och ser hur många sidvisningar den fått.&quot;

  ![Dimension centrerad](assets/dimension-centered.png){style="border:1px solid gray"}

* En typisk händelse och användarcentrerad metod för guidad analys är:&quot;Hur många användare har besökt vår hemsida?&quot;

  ![Händelsecentrerad](assets/event-centered.png){style="border:1px solid gray"}

+++
