---
description: Förteckning över kända begränsningar i Adobe Analysis Workspace och dess tillhörande komponenter
title: Kända begränsningar i Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
source-git-commit: a69f9eef39c0eceee1964a3b8741b7538b218ece
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# Kända begränsningar i Analysis Workspace

Här är en lista över kända begränsningar i Analysis Workspace och dess komponenter:

## Tabeller

* Datumjämförelsekolumner kan inte läggas till när datumintervall eller mätvärden används som rader i en tabell.
* Skapa mätvärden från markering är inaktiverat när filter används som rader i en tabell. Dessutom ska Skapa mätvärden från markering inte tillämpas på datumjusterade kolumner.
* Villkorsstyrd formatering för uppdelningsrader kan inte använda anpassade intervall.
* Tabellsummeringsrader kan inte trendas när inställningen för att beräkna summor har tillämpats (används vanligtvis för statiska radobjekt).
* [!UICONTROL Contribution Analysis] kan köras på [!UICONTROL daily] granularitet _endast_. Den kan inte köras mot [!UICONTROL hourly], [!UICONTROL weekly], etc., data.

## Visualiseringar

* Visualiseringar som utnyttjar filter, som [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort]och [!UICONTROL Histogram], kan inte acceptera beräknade värden som indata.
* [!UICONTROL Flow]: Ingångs-/avslutningsdimensioner, t.ex. [!UICONTROL Entry page], kan inte användas i Flow.
* [!UICONTROL Cohort]: Icke-heltal kan inte användas som kohortvillkor.

## Komponenter > Filter

* Vissa mått kan inte filtreras, t.ex. [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], osv.
* Ad hoc-filter skapade i [panelens dropzon](/help/analysis-workspace/c-panels/panels.md) är en typ av snabbfilter. De visas inte i den vänstra listen i Workspace eller i Filter-komponenthanteraren, såvida de inte är offentliga. Mer information finns i [Snabbfilter](/help/components/filters/quick-filters.md).

## Komponenter > Beräknade mått

* Beräknade mått kan inte användas i vissa visualiseringar. Se Visualiseringar ovan.
* Beräknade mått kan inte användas i [!UICONTROL Attribution] eftersom beräknade värden i sig kan innehålla separata attribueringsmodeller.
* Vissa komponenter och operatorer är inte tillgängliga om ett beräknat mått skapas från arbetsytan (till skillnad från om de skapas från [!UICONTROL Components > filters]). Exempel, [!UICONTROL IP Address].

## Komponenter > Datumintervall

* Anpassade datumintervall stöds inte [!UICONTROL This day last year], [!UICONTROL This day last month], osv.


## Komponenter > Rapportinställningar

* Vissa av inställningarna på [!UICONTROL Report Settings] sidan gäller inte. Analysis Workspace använder bara [!UICONTROL Language/Currency/Encoding] inställningarna längst ned: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding]och [!UICONTROL CSV Separator Character].

