---
description: Lista över kända begränsningar i Adobe Analysis Workspace och tillhörande komponenter
title: Kända begränsningar i Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 2%

---


# Kända begränsningar i Analysis Workspace

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Här följer en lista över kända begränsningar i Analysis Workspace och tillhörande komponenter:

## Tabeller

* Det går inte att lägga till datumjämförelskolumner när antingen datumintervall eller mått används som rader i en tabell.
* Skapa mätresultat från markering är inaktiverat när segment används som rader i en tabell. Dessutom ska Skapa mätresultat från markering inte tillämpas på datumjusterade kolumner.
* Villkorsstyrd formatering för nedbrytningsrader kan inte använda anpassade intervall.
* Det går inte att trendera tabellsummorna när du beräknar summor genom att summera radvärdesinställningen (används vanligtvis för statiska radobjekt).
* [!UICONTROL Contribution Analysis] kan köras på [!UICONTROL daily] granularitet _endast_. Det kan inte gå emot [!UICONTROL hourly], [!UICONTROL weekly]osv., uppgifter.

## Visualiseringar

* Visualiseringar som ger hävstångseffekt, t.ex. [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort]och [!UICONTROL Histogram]kan inte acceptera beräknade mått som indata.
* [!UICONTROL Flow]: Ingångs-/exitdimensioner, t.ex. [!UICONTROL Entry page]kan inte användas i Flow.
* [!UICONTROL Cohort]: Icke-heltal kan inte användas som kohortkriterier.

<!--## Panels

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.<-->

## Komponenter > Filter

* Vissa mått och mått är inte segmenterbara, t.ex. [!UICONTROL Occurrences], [!UICONTROL Unique Visitors]osv.
* Vissa komponenter och operatorer är inte tillgängliga om ett filter skapas från arbetsytan (till skillnad från att skapas från [!UICONTROL Components > Filters]). Till exempel IP-adress.

## Komponenter > Beräknade mått

* Beräknade mått kan inte användas i vissa visualiseringar. Se &quot;Visualiseringar&quot; ovan.
* Beräknade mått kan inte användas i [!UICONTROL Attribution] panelen, eftersom de beräknade måtten i sig kan innehålla separata attributmodeller.
* Vissa komponenter och operatorer är inte tillgängliga om ett beräknat mått skapas från arbetsytan (till skillnad från att skapas från [!UICONTROL Components > Segments]). Exempel, [!UICONTROL IP Address].

## Komponenter > Datumintervall

* Anpassade datumintervall stöder inte [!UICONTROL This day last year], [!UICONTROL This day last month]osv.

## Komponenter > Rapportinställningar

* Några av inställningarna på [!UICONTROL Report Settings] sidan gäller inte. Analysis Workspace använder endast [!UICONTROL Language/Currency/Encoding] inställningar längst ned: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding]och [!UICONTROL CSV Separator Character].

## Attribution IQ

* En delmängd av måtten stöds inte i [!UICONTROL Attribution IQ]. En fullständig lista finns i [FAQ för attributets IQ](../attribution/faq.md).
