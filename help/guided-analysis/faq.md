---
title: Vanliga frågor om guidad analys
description: Vanliga frågor och svar för guidad analys.
exl-id: b6f92d47-6c09-4338-9dc5-b30bbfbe9f7f
feature: Guided Analysis
keywords: produktanalys
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Vanliga frågor om guidad analys

Vanliga frågor och svar för guidad analys.

+++**Har min organisation åtkomst till guidad analys?**

Vyer med guidad analys ingår i alla Customer Journey Analytics-paket. Se avsnittet [provisionering](overview.md#provisioning) på översiktssidan om du vill veta mer om vilka vyer ditt CJA-paket låser upp.

+++

+++**Vilka implementeringsändringar krävs för att använda guidad analys?**

Om du redan använder Customer Journey Analytics idag behövs inga ytterligare implementeringsändringar. I den guidade analysen används samma [datavyer](../data-views/data-views.md) och [anslutningar](../connections/overview.md) som i andra CJA-gränssnitt som [Analysis Workspace](../analysis-workspace/home.md).

För att dina slutanvändare ska kunna bli mest framgångsrika med guidad analys rekommenderar vi att du har ett starkt händelseschema och en stark hanteringsstrategi i Adobe Experience Platform och [datavyer](../data-views/data-views.md).

+++

+++**När ska du använda guidad analys för Analysis Workspace?**

**Med hjälp av guidad analys** kan användarna snabbt få högkvalitativa insikter. Det är användbart för produktteam, användare som vill arbeta mer tillförlitligt med data och till och med analytiker som ett försprång i en djupare analys.

**[Analysis Workspace](../analysis-workspace/home.md)** är ett friare utrymme där du kan dyka längre in i data för att få fler insikter. Det är användbart för analytiker och avancerade användare som förstår data väl och vill djupdyka i det.

+++

+++**Hur skiljer sig terminologin mellan guidad analys och Analysis Workspace?**

Guidad analys och [Analysis Workspace](../analysis-workspace/home.md) anpassar sig efter de flesta nyckeltermer, med några få skillnader.

| Guidad analysterm | Analysis Workspace term |
| --- | --- |
| Händelse (ett binärt 1/0-mått) | Mått |
| Användare | Folk |
| Dimension | Dimension |
| Dimension | Dimension |
| Segment | Segment |
| Filter | Rapportfilter |
| Beräknade mått, mått | Beräknat mått |

{style="table-layout:auto"}

+++

+++**Vad är det för skillnader i hur guidad analys och Analysis Workspace-metodrapportering fungerar?**

Även om [Analysis Workspace](../analysis-workspace/home.md) och guidad analys använder samma underliggande data är det sätt på vilket varje verktyg gör att du kan skapa frågor med dessa data annorlunda.

* **Analysis Workspace är en dimensionsinriktad upplevelse.** tabeller består vanligtvis av dimensionella rader, medan kolumner vanligtvis är mått. Segment kan användas på både rader och kolumner för att få fram önskade data.

* **Guidad analys är en händelse- och användarcentrerad upplevelse.** Varje analys börjar med att välja händelser, sedan kan dimensioner och segment läggas till för att förfina händelsedata.

![Analysis Workspace och guidade analysvyer](assets/structure.png){style="border:1px solid gray"}

Titta på följande exempel där du fokuserar på data runt hemsidan på din webbplats. Teamen ställer liknande frågor, men analysmetoden kan vara annorlunda.

* En typisk dimensionsinriktad Analysis Workspace-strategi skulle vara:&quot;Vi tittar på startsidan och ser hur många sidvisningar den fått.&quot;

  ![Centrerad i Dimension](assets/dimension-centered.png){style="border:1px solid gray"}

* En typisk händelse och användarcentrerad metod för guidad analys är&quot;Hur många användare har besökt hemsidan?&quot;

  ![Händelsen centrerad](assets/event-centered.png){style="border:1px solid gray"}

+++
