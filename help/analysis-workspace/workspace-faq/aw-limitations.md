---
description: Lista över kända begränsningar i Adobe Analysis Workspace och dess tillhörande komponenter
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
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Här är en lista över kända begränsningar i Analysis Workspace och dess tillhörande komponenter:

## Tabeller

* Datumjämförelsekolumner kan inte läggas till när datumintervall eller mätvärden används som rader i en tabell.
* Skapa mätvärden från markering är inaktiverat när segment används som rader i en tabell. Dessutom ska Skapa mätvärden från markering inte tillämpas på datumjusterade kolumner.
* Villkorsstyrd formatering för uppdelningsrader kan inte använda anpassade intervall.
* Tabellsummeringsrader kan inte trendas när inställningen för att beräkna summor har tillämpats (används vanligtvis för statiska radobjekt).
* [!UICONTROL Contribution Analysis] kan köras med [!UICONTROL daily] granularitet _endast_. Den kan inte köras mot [!UICONTROL hourly], [!UICONTROL weekly]osv., data.

## Visualiseringar

* Visualiseringar som utnyttjar segmentering, som [!UICONTROL Fallout], [!UICONTROL Flow]och [!UICONTROL Cohort][!UICONTROL Histogram], kan inte acceptera beräknade värden som indata.
* [!UICONTROL Flow]: Ingångs-/avslutningsdimensioner, t.ex. [!UICONTROL Entry page], kan inte användas i Flow.
* [!UICONTROL Cohort]: Icke-heltal kan inte användas som kohortvillkor.

<!--## Panels

* Segment Comparison: The [!UICONTROL Everyone Else] segment does not get created if a segment template is used in the initial drop zone.<-->

## Komponenter > Filter

* Vissa mätvärden och dimensioner kan inte segmenteras, t.ex. [!UICONTROL Occurrences][!UICONTROL Unique Visitors].
* Vissa komponenter och operatorer är inte tillgängliga om ett filter skapas från arbetsytan (till skillnad från att skapas från [!UICONTROL Components > Filters]). Exempel: IP-adress.

## Komponenter > Beräknade mått

* Beräknade mått kan inte användas i vissa visualiseringar. Se Visualiseringar ovan.
* Beräknade mått kan inte användas på [!UICONTROL Attribution] panelen eftersom beräknade värden i sig kan innehålla separata attribueringsmodeller.
* Vissa komponenter och operatorer är inte tillgängliga om ett beräknat mått skapas från arbetsytan (till skillnad från att skapas från [!UICONTROL Components > Segments]). Exempel, [!UICONTROL IP Address].

## Komponenter > Datumintervall

* Anpassade datumintervall har inte stöd för [!UICONTROL This day last year], [!UICONTROL This day last month]osv.

## Komponenter > Rapportinställningar

* Vissa av inställningarna på [!UICONTROL Report Settings] sidan gäller inte. I Analysis Workspace används endast [!UICONTROL Language/Currency/Encoding] inställningarna längst ned: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding]och [!UICONTROL CSV Separator Character].

## Attribution IQ

* En delmängd av mätvärden stöds inte i [!UICONTROL Attribution IQ]. En fullständig lista finns i Vanliga frågor om [attribuering](../attribution/faq.md).
