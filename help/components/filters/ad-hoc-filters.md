---
description: Använd ad hoc-filter i Analysis Workspace.
title: Ad hoc-projektfilter
feature: CJA Workspace Basics
role: User, Admin
exl-id: 79513ad9-3c9d-441e-a5c5-c2b1e5cacc2e
source-git-commit: c053a1517030b68875fe7f4518dbbd473dbe1b47
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---

# Ad hoc-projektfilter

Med ad hoc-projektfilter kan du dra och släppa valfri komponent direkt i panelens släppzon för att skapa ett filter. Filtret blir ett [projektnivåfilter](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/quick-filters.html) lokalt till det aktuella projektet.

Här är en video om hur du skapar ad hoc-projektfilter:

>[!VIDEO](https://video.tv.adobe.com/v/23978/?quality=12)


1. 
   1. Släpp en komponenttyp (dimension, dimensionsobjekt, händelse, mått, segment, segmentmall, datumintervall) i filtersläppzonen högst upp på en panel. Komponenttyper konverteras automatiskt till ad hoc-filter eller [Snabbfilter](/help/components/filters/quick-filters.md) om det är kompatibelt.

   Här följer ett exempel på hur du skapar ett filter för den hänvisande domänen för Twitter:

   ![](assets/ad-hoc1.png)

   Panelen tillämpar automatiskt det här filtret och du ser resultatet direkt.

1. Du kan lägga till ett obegränsat antal filter på en panel.
1. Om du bestämmer dig för att du vill spara det här filtret kan du läsa avsnittet nedan.

Tänk på följande:

* Du **inte** släpp följande komponenttyper i filterzonen: beräknade mått och mått/mätvärden som du inte kan bygga filter på.
* För alla dimensioner och händelser skapar Analysis Workspace&quot;exists&quot;-träfffilter. Exempel: `Hit where eVar1 exists` eller `Hit where event1 exists`.
* Om &quot;unspecified&quot; eller &quot;none&quot; släpps i filtersläppzonen konverteras den automatiskt till filtret &quot;does not exist&quot; så att det behandlas korrekt vid filtrering.

## Spara ad hoc-projektfilter {#ad-hoc-save}

Du kan välja att spara dessa filter genom att följa dessa steg:

1. Håll pekaren över filtret i släppzonen och klicka på ikonen i.
1. Klicka på redigeringspennan för att gå till filterverktyget.
1. Kontrollera **[!UICONTROL Make available to all projects and add to your component list]**.
1. Klicka på **[!UICONTROL SAVE]**.

När filtret har sparats är det tillgängligt i komponentlistan till vänster och kan delas med andra användare från Filterhanteraren.

