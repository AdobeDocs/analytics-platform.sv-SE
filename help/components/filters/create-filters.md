---
title: Skapa filter
description: Förstå användargränssnittet för att skapa filter.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---


# Skapa filter

I Filter Builder finns en arbetsyta som du kan använda för att dra och släppa mätvärden, dimensioner, filter och händelser för att filtrera besökare baserat på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla eller komplexa filter som identifierar besökares attribut och åtgärder i olika besök och sidträffar.

Du kan skapa direktfilter genom att släppa valfri komponenttyp (dimension, dimensionsobjekt, händelse, mått, segment, segmentmall, datumintervall) i filtersläppzonen högst upp på en panel.

Komponenttyper konverteras automatiskt till filter. Du kan också klicka på plustecknet (+) i **[!UICONTROL Add Filter]** listrutan.

Kom ihåg:

* Du **kan inte** släppa följande komponenttyper i filterzonen: beräknade mått och mått/mätvärden som du inte kan bygga filter på.
* För fullständiga dimensioner och händelser skapar Analysis Workspace&quot;finns&quot;-träfffilter. Exempel: &quot;Tryck där eVar1 finns&quot; eller &quot;hit där event1 finns&quot;.
* Om &quot;unspecified&quot; eller &quot;none&quot; släpps i filtersläppzonen konverteras den automatiskt till filtret &quot;does not exist&quot; så att det behandlas korrekt.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Filter som skapas på det här sättet är interna för projektet.

Du kan välja att göra dessa filter offentliga (globala) genom att följa dessa steg:

1. Håll pekaren över filtret i släppzonen och klicka på ikonen i.
1. Klicka på den informationspanel som visas **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Andra metoder för att tillämpa filter

Det finns flera andra metoder för att tillämpa filter på ett projekt:

| Åtgärd | Beskrivning |
|--- |--- |
| Skapa filter från markering | Skapa ett textbundet filter. Markera rader, högerklicka på markeringen och skapa sedan ett textbundet filter. Det här filtret gäller bara för det öppna projektet och sparas inte som ett CJA-filter. 1. Markera rader.  2. Högerklicka på markeringen.  3. Klicka på *Skapa filter från markering*. |
| Komponenter > Nytt filter | Visar Filter Builder. Mer information om filtrering finns i [Filterverktyget](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html) . |
| Dela > Dela projekt eller Dela > Kuratera projektdata | I [Kuratera och dela](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6)kan du lära dig hur filter som du tillämpar på projektet är tillgängliga i en delad analys för mottagaren. |
| Använd filter som dimensioner | Video: [Använda segment som dimensioner i Analysis Workspace](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
