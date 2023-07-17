---
title: Vanliga frågor om guidad analys
description: Vanliga frågor och svar om den guidade analysen.
exl-id: 32bfce23-a59c-45cb-b1cd-82f048fb13d2
feature: Guided Analysis
source-git-commit: 2b1e0ce53016634e0cb32f9256fa48e02f2a5323
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Vanliga frågor om guidad analys

Vanliga frågor och svar om den guidade analysen.

+++**Hur kan vår organisation etableras för guidad analys?**

Guidad analys är ett betalt tillägg till Customer Journey Analytics. Om du vill börja använda det här tillägget kontaktar du kontoteamet på Adobe.

+++

+++**Vilka implementeringsändringar krävs för att använda den guidade analysen?**

Om du redan använder Customer Journey Analytics idag behövs inga ytterligare implementeringsändringar. Guidad analys använder samma [Datavyer](../data-views/data-views.md) och [Anslutningar](../connections/overview.md) som andra CJA-gränssnitt som [Analysis Workspace](../analysis-workspace/home.md).

För att dina slutanvändare ska kunna bli mest framgångsrika med guidad analys rekommenderar vi att du har ett starkt händelseschema och en hanteringsstrategi på plats i Adobe Experience Platform och [Datavyer](../data-views/data-views.md).

+++

+++**När ska du använda Guidad analys eller Analysis Workspace?**

**Guidad analys** kan hjälpa användarna att snabbt få högkvalitativa insikter. Det är användbart för produktteam, användare som vill arbeta mer tillförlitligt med data och till och med analytiker som ett försprång i en djupare analys.

**[Analysis Workspace](../analysis-workspace/home.md)** är ett friare utrymme där du kan dyka längre in i data för att få fler insikter. Det är användbart för analytiker och avancerade användare som förstår data väl och vill djupdyka i det.

+++

+++**Hur skiljer sig terminologin mellan guidad analys och Analysis Workspace?**

I den guidade analysen används termer som används oftare bland produktteamen. Du kan referera till den här tabellen när du växlar mellan guidad analys och [Analysis Workspace](../analysis-workspace/home.md).

| Guidad analysterm | Analysis Workspace |
| --- | --- |
| Händelse | Mått |
| Användare | Personer |
| Egenskap | Dimension |
| Värde | Dimension |
| Segment | Filter |

{style="table-layout:auto"}

+++

+++**Vad är det för skillnader mellan hur den guidade analysen och Analysis Workspace metodrapporter fungerar?**

while [Analysis Workspace](../analysis-workspace/home.md) och för guidad analys används samma underliggande data, vilket innebär att varje verktyg gör att du kan skapa frågor av dessa data på ett helt annat sätt.

* **Analysis Workspace är en upplevelse som bygger på flera dimensioner.** Tabeller består vanligtvis av dimensionella rader, medan kolumner vanligtvis är mått. Du kan använda filter på både rader och kolumner för att få fram önskade data.

* **Guidad analys är en händelsestyrd upplevelse.** Varje analys börjar med att välja händelser, sedan kan mått och filter läggas till för att förfina händelsedata.

![Struktur](assets/structure.png)

Titta på följande exempel där du fokuserar på data runt hemsidan på din webbplats. Teamen ställer liknande frågor, men analysmetoden kan vara annorlunda.

* En typisk dimensionsinriktad Analysis Workspace-strategi skulle vara:&quot;Vi tittar på startsidan och ser hur många sidvisningar den fått.&quot;

  ![Dimension centrerad](assets/dimension-centered.png)

* En typisk händelsestyrd strategi för guidad analys skulle vara&quot;Hur många användare har sett hemsidan?&quot;

  ![Händelsecentrerad](assets/event-centered.png)

+++
