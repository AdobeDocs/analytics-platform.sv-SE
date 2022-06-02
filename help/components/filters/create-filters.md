---
title: Skapa filter
description: Förstå användargränssnittet för att skapa filter.
exl-id: b6a921d5-7dd3-4230-88b8-5f1cd313b791
source-git-commit: 7013237e11cb173d54dcbe236967b49d89810975
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Skapa filter

I Filter Builder finns en arbetsyta som du kan använda för att dra och släppa mätvärden, dimensioner, filter och händelser för att filtrera besökare baserat på behållarhierarkilogik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla eller komplexa filter som identifierar besökares attribut och åtgärder i olika besök och sidträffar.

Du kan skapa direktfilter genom att släppa valfri komponenttyp (dimension, dimensionsobjekt, händelse, mått, filter, filtermall, datumintervall) i filtersläppzonen högst upp på en panel.

Komponenttyper konverteras automatiskt till filter. Du kan också klicka på plustecknet (+) i dialogrutan **[!UICONTROL Add Filter]** drop box.

Kom ihåg:

* Du **inte** släpp följande komponenttyper i filterzonen: beräknade mått och mått/mätvärden som du inte kan bygga filter på.
* För alla dimensioner och händelser skapar Analysis Workspace&quot;exists&quot;-träfffilter. Exempel: &quot;Träffas där eVar1 finns&quot; eller &quot;hit där event1 finns&quot;.
* Om &quot;unspecified&quot; eller &quot;none&quot; släpps i filtersläppzonen konverteras den automatiskt till filtret &quot;does not exist&quot; så att det behandlas korrekt.

![](assets/segment-dropzone.png)

>[!NOTE]
>
>Filter som skapas på det här sättet är interna för projektet.

Du kan välja att göra dessa filter offentliga (globala) genom att följa dessa steg:

1. Håll pekaren över filtret i släppzonen och klicka på ikonen i.
1. Klicka på **[!UICONTROL Make public]**.

   ![](assets/segment-info.png)

## Andra metoder för att tillämpa filter

Det finns flera andra metoder för att tillämpa filter på ett projekt:

| Åtgärd | Beskrivning |
| --- | --- |
| Skapa filter från markering | Skapa ett textbundet filter. Det här filtret gäller bara för det öppna projektet och sparas inte som ett CJA-filter.<p> 1. Markera vilka tabellrader som du vill ska ingå i filtret.  2. Högerklicka på markeringen.  3. Klicka *Skapa filter från markering*. |
| Arbetsyta [!UICONTROL Components] > [!UICONTROL New Filter] | Visar Filter Builder. Se [Filter Builder](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html) för mer information om filtrering. |
| Dela > Dela projekt eller Dela > Kuratera projektdata | I [Kuratera och dela](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html#concept_4A9726927E7C44AFA260E2BB2721AFC6)Läs om hur filter som du tillämpar på projektet är tillgängliga i en delad analys för mottagaren. |
| Använd filter som dimensioner | Se videon nedan: Använda filter som Dimensioner i Analysis Workspace |

>[!VIDEO](https://video.tv.adobe.com/v/23974)
