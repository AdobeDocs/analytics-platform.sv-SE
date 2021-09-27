---
description: Använd ad hoc-filter i Analysis Workspace.
title: Ad hoc-projektfilter
feature: Workspace Basics
role: User, Admin
source-git-commit: 275c552b14a4c2a47e00d0600ac3eae6811beae9
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---


# Ad hoc-projektfilter

Här är en video om hur du skapar ad hoc-projektfilter:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)

Du kan skapa ad hoc-projektfilter om du snabbt vill utforska hur ett filter kan påverka ditt projekt, utan att gå till segmentbyggaren. Tänk på dessa filter som temporära filter på projektnivå. De är vanligtvis inte en del av ditt filterbibliotek som komponentfilter i den vänstra listen. Du kan dock spara dem enligt nedan.

Om du vill jämföra vad ad hoc-projektfilter kan göra med fullständiga filter på komponentnivå går du [hit](/help/components/filters/filters-overview.md).

1. Släpp en komponenttyp (dimension, dimensionsobjekt, händelse, mått, filter, filtermall, datumintervall) i filtersläppzonen högst upp på en panel. Komponenttyper konverteras automatiskt till filter.
Här följer ett exempel på hur du skapar ett filter för den hänvisande domänen för Twitter:

   ![](assets/ad-hoc1.png)

   Panelen tillämpar automatiskt det här filtret och du ser resultatet direkt.

1. Du kan lägga till ett obegränsat antal komponenter på en panel.
1. Om du bestämmer dig för att du vill spara det här filtret kan du läsa avsnittet nedan.

Tänk på följande:

* Du **kan inte** släppa följande komponenttyper i filterzonen: beräknade mått och mått/mätvärden som du inte kan bygga filter på.
* För alla dimensioner och händelser skapar Analysis Workspace&quot;exists&quot;-träfffilter. Exempel: `Hit where eVar1 exists` eller `Hit where event1 exists`.
* Om &quot;unspecified&quot; eller &quot;none&quot; släpps i filtersläppzonen konverteras den automatiskt till filtret &quot;does not exist&quot; så att det behandlas korrekt vid filtrering.

>[!NOTE]
>
>Segment som skapas på det här sättet är interna för projektet.

## Spara ad hoc-projektfilter {#ad-hoc-save}

Du kan välja att spara dessa filter genom att följa dessa steg:

1. Håll pekaren över filtret i släppzonen och klicka på ikonen i.
1. Klicka på **[!UICONTROL Save]** på informationspanelen som visas.

   ![](assets/segment-info.png)

## Vad är filter som endast är projektbaserade?

Endast projektfilter är antingen snabbfilter eller ad hoc-projektfilter för arbetsytan. När du redigerar/öppnar dem i filterverktyget visas rutan för endast projekt. Om de använder ett snabbfilter i verktyget men inte markerar kryssrutan Gör tillgänglig är det fortfarande ett projektfilter, men det kan inte längre öppnas i QS-verktyget. Om de markerar kryssrutan och SPARA är det nu ett komponentlistfilter.