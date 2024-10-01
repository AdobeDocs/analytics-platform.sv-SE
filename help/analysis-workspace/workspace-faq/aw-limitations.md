---
description: Läs om kända begränsningar i Adobe Analysis Workspace och dess tillhörande komponenter
title: Kända begränsningar i Analysis Workspace
feature: FAQ
exl-id: 334cfe24-a4b2-43be-94df-5a2df90612f0
role: User
source-git-commit: de04792035aa7c235751019ee9f9fe5b74b9b102
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# Kända begränsningar i Analysis Workspace

Här är en lista över kända begränsningar i Analysis Workspace och dess komponenter:

## Tabeller

* Datumjämförelsekolumner kan inte läggas till när datumintervall eller mätvärden används som rader i en tabell.
* Skapa mätvärden från markering är inaktiverat när filter används som rader i en tabell. Dessutom ska Skapa mätvärden från markering inte tillämpas på datumjusterade kolumner.
* Villkorsstyrd formatering för uppdelningsrader kan inte använda anpassade intervall.
* Tabellsummeringsrader kan inte trendas när inställningen för att beräkna summor har tillämpats (används vanligtvis för statiska radobjekt).

## Visualiseringar

* Visualiseringar som utnyttjar filter, som [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort] och [!UICONTROL Histogram], kan inte acceptera beräknade värden som indata.
* [!UICONTROL Flow]: Det går inte att använda in-/avslutningsdimensioner, t.ex. [!UICONTROL Entry page], i Flow.
* [!UICONTROL Cohort]: Icke-heltal kan inte användas som kohortvillkor.

## Filter

* Vissa mått och mått kan inte filtreras, som [!UICONTROL Events], [!UICONTROL Persons] osv.
* Ad hoc-filter som skapas i [panelens dropzone](/help/analysis-workspace/c-panels/panels.md) är en typ av snabbfilter. De visas inte på den vänstra panelen i Workspace eller i Filter-komponenthanteraren, såvida de inte är offentliga. Mer information finns i [Snabbfilter](/help/components/filters/quick-filters.md).

## Beräknade mätvärden

* Beräknade mått kan inte användas i vissa visualiseringar. Se [Visualiseringar](#visualizations).
* Beräknade mått kan inte användas på panelen [!UICONTROL Attribution] eftersom beräknade mått i sig kan innehålla separata attribueringsmodeller.
* Vissa komponenter och operatorer är inte tillgängliga om ett beräknat mått skapas från Workspace (till skillnad från när det skapas från [!UICONTROL Components > filters]). Exempel: [!UICONTROL IP Address].

## Datumintervall

* Anpassade datumintervall stöder inte [!UICONTROL This day last year], [!UICONTROL This day last month] osv.


## Rapportinställningar

* Vissa av inställningarna på sidan [!UICONTROL Report Settings] gäller inte. Analysis Workspace använder bara inställningarna [!UICONTROL Language/Currency/Encoding] längst ned: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] och [!UICONTROL CSV Separator Character].

