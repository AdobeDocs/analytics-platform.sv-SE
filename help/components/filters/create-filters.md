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

I Filter Builder finns en arbetsyta för att dra och släppa mått, dimensioner, filter och händelser för att filtrera besökare baserat på behållarhierarkins logik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla eller komplexa filter som identifierar besökarattribut och -åtgärder över besök och sidoträffar.

Du kan skapa snabbfilter genom att släppa valfri komponenttyp (dimension, dimensionspost, händelse, mått, segment, segmentmall, datumintervall) i filtersläppzonen överst på en panel.

Komponenttyperna konverteras automatiskt till filter. Du kan också klicka på plustecknet &quot;+&quot; i **[!UICONTROL Add Filter]** släppbox.

Kom ihåg:

* Du **inte** släppa följande komponenttyper i filterzonen: beräknade mått och dimensioner/mått från vilka du inte kan skapa filter.
* För fullständiga dimensioner och händelser skapas träfffilter för Analysis Workspace. Exempel: &quot;Träff där eVar1 finns&quot; eller &quot;hit där event1 finns&quot;.
* Om &quot;ospecificerad&quot; eller &quot;ingen&quot; släpps i filtersläppzonen konverteras det automatiskt till ett &quot;finns inte&quot;-filter så att det behandlas korrekt.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Filter som skapas på detta sätt är interna för projektet.

Du kan välja att göra dessa filter offentliga (globala) genom att följa stegen nedan:

1. Hovra över filtret i släppzonen och klicka på ikonen &quot;i&quot;.
1. Klicka på **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Andra metoder för att tillämpa filter

Det finns flera andra metoder för att tillämpa filter på ett projekt:

| Åtgärd | Beskrivning |
|--- |--- |
| Skapa filter från markering | Skapa ett textfilter. Markera rader, högerklicka på markeringen och skapa sedan ett textfilter. Det här filtret gäller bara för det öppna projektet och sparas inte som ett CJA-filter. 1 Markera rader.  2 Högerklicka på markeringen.  3 Klicka *Skapa filter från markering*. |
| Komponenter > Nytt filter | Visar Filter Builder. Se [Filter Builder](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html) för mer information om filtrering. |
| Dela > Dela projekt eller Dela > Skapa projektdata | I [Kurva och dela](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6), lär dig hur filter som du tillämpar på projektet är tillgängliga i delad analys för mottagaren. |
| Använd filter som dimensioner | Video: [Använda segment som dimensioner i analysarbetsytan](https://www.youtube.com/watch?v=WmSdReKTWto&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=39) |
