---
title: Inställningar för Persistence-komponent
description: Bestäm hur eller om dimensionsvärdena ska behållas från en händelse till nästa.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: c94e97723a4ed30e675144e02196c93016b13235
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 4%

---


# [!UICONTROL Persistence] komponentinställningar {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_persistence"
>title="Persistence"
>abstract="Konfigurera standardallokeringsmodellen som används för en dimension. Allokering tillämpas före filter i rapportering. Mer information finns i [allokeringsinställningar](/help/data-views/component-settings/persistence.md#allocation-settings), [förfalloinställningar](/help/data-views/component-settings/persistence.md#expiration-settings), [bindningsdimension](/help/data-views/component-settings/persistence.md#binding-dimension) och [bindningsmått](/help/data-views/component-settings/persistence.md#binding-metric)."

<!-- markdownlint-enable MD034 -->



[!UICONTROL Persistence] är möjligheten för ett givet dimensionsvärde att relatera till ett mått efter händelsen som det är inställt på. Den använder en kombination av allokering och förfallodatum.

![Fönstret Datavy där alternativen för persistence markeras](../assets/persistence.png)

* Med **Allokering** kan du bestämma vilket värde som ska behållas när mer än ett dimensionsobjekt kan finnas i taget i en enda kolumn.

  >[!NOTE]
  >
  >Om du har en [icke-standardattribueringsmodell](/help/data-views/component-settings/attribution.md) angiven för ett mätvärde i en rapport, ignorerar attribueringsmodellen den allokering du har angett för dimensionen för samma rapport.
  >
  >När du gör en [fullständig tabellexport](/help/analysis-workspace/export/export-cloud.md) som innehåller flera dimensioner, behåller attribueringen de allokeringsmodeller som används för varje dimension.

* Med **Förfallotid** kan du bestämma hur länge ett dimensionsobjekt kvarstår efter den händelse det är inställt på.

[!UICONTROL Persistence] är bara tillgängligt för dimensioner och är retroaktiv för de data som den tillämpas på. Det är en omedelbar dataomvandling som sker innan filtrering eller andra analysåtgärder tillämpas.

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Set persistence] | Aktivera beständighet för dimensionen. Om persistence inte är aktiverat, relaterar dimensionen endast till mått som finns i samma händelse. Den här inställningen är inaktiverad som standard. |
| [!UICONTROL Allocation] | Här kan du ange den allokeringsmodell som används för en dimension för beständighet. Alternativen är: [!UICONTROL Most recent], [!UICONTROL Original], [!UICONTROL Instance], [!UICONTROL All]. Från och med den 28 oktober 2021 läggs ett uppslagsfönster på upp till 90 dagar till i inställningen [!UICONTROL Allocation]. |
| [!UICONTROL Expiration] | Gör att du kan ange det beständiga fönstret för en dimension. Alternativ: [!UICONTROL Session] (standard), [!UICONTROL Person], [!UICONTROL Custom Time], [!UICONTROL Metric]. Du kanske måste kunna förfalla dimensionen på ett köp (till exempel interna sökvillkor eller andra användningsfall för varuexponering). Den maximala förfallotiden som du kan ange är 90 dagar. Om du väljer en allokering av [!UICONTROL All] är bara [!UICONTROL Session] eller [!UICONTROL Person] förfallodatum tillgängliga. |

{style="table-layout:auto"}

## Inställningar för [!UICONTROL Allocation]

Information om tillgängliga allokeringsinställningar.

* **[!UICONTROL Most Recent]**: Bevarar det senaste (med tidsstämpel) värdet i dimensionen. Eventuella efterföljande värden som inträffar inom dimensionens förfalloperiod ersätter det tidigare beständiga värdet. Om Behandla &#39;Inget värde&#39; som ett värde&#39; är aktiverat för den här dimensionen under [Inga värdealternativ](no-value-options.md), skriver tomma värden över tidigare beständiga värden. Ta till exempel följande tabell med [!UICONTROL Most recent]-allokering och [!UICONTROL Session]-förfallodatum:

  | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
  | --- | --- | --- | --- | --- | --- |
  | Datamängdsvärden |  | C | B |  | A |
  | Senaste allokering |  | C | B | B | A |

* **[!UICONTROL Original]**: Visar det ursprungliga värdet med en tidsstämpel som finns i dimensionen under förfalloperiodens varaktighet. Om den här dimensionen har ett värde skrivs den inte över när ett annat värde visas för en efterföljande händelse. Ta till exempel följande tabell med [!UICONTROL Original]-allokering och [!UICONTROL Session]-förfallodatum:

  | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
  | --- | --- | --- | --- | --- | --- |
  | Datamängdsvärden |  | C | B |  | A |
  | Ursprunglig allokering |  | C | C | C | C |

* **[!UICONTROL All]**: fungerar på liknande sätt som attributmodellen [!UICONTROL Participation] för mått. Bevarar alla värden lika så att alla får full uppskattning för måttet i rapporteringen. Ta till exempel följande tabell med [!UICONTROL All]-allokering och [!UICONTROL Session]-förfallodatum:

  | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
  | --- | --- | --- | --- | --- | --- |
  | Datamängdsvärden | A | B | C |  | A |
  | Alla allokeringar | A | A,B | A,B,C | A,B,C | A,B,C |

* **[!UICONTROL First Known]** och **[!UICONTROL Last Known]**: (19 januari 2022) Dessa två allokeringsmodeller uppfyller användningsvillkoren för &quot;entry&quot; och &quot;exit&quot;-dimension. De tar det första eller sista observerade värdet för en dimension inom ett angivet beständigt omfång (session, person eller anpassad tidsperiod med uppslag) och tillämpar det på alla händelser inom det angivna omfånget. Exempel:

  | Dimension | Träff 1 | Träff 2 | Träff 3 | Träff 4 | Träff 5 |
  | --- | --- | --- | --- | --- | --- |
  | Tidsstämpel (min) | 1 | 2 | 3 | 6 | 7 |
  | Ursprungliga värden |  | C | B |  | A |
  | Första kända | C | C | C | C | C |
  | Senast känd | A | A | A | A | A |


## Inställningar för [!UICONTROL Expiration]

Information om tillgängliga förfalloinställningar.

* **Session**: Upphör att gälla efter en given session. Förfallotid som standard.
* **Personrapporteringsfönster**: Upphör att gälla i slutet av rapporteringsfönstret.
* **Fönstret Rapportering för globalt konto** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}: Upphör att gälla i slutet av rapporteringsfönstret.
* **Fönstret Kontorapportering** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}: Upphör att gälla i slutet av rapportfönstret.
* **Fönstret för säljprojektsrapportering** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}: Upphör att gälla i slutet av rapportfönstret.
* **Buying Group Reporting Window** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}: Upphör att gälla i slutet av rapporteringsfönstret.
* **Anpassad tid**: Förfaller efter en angiven tidsperiod (upp till 90 dagar). Det här förfalloalternativet är endast tillgängligt för allokeringsmodellerna Original och Senaste. När du använder tidsbaserad förfallotid beaktas värden som ligger före rapportfönstrets början (upp till 90 dagar).
* **Mått**: När det här måttet visas i en händelse upphör det beständiga värdet i dimensionen omedelbart att gälla. Du kan använda valfritt mätvärde som förfallodatum för den här dimensionen. Det här förfalloalternativet är bara tillgängligt för allokeringsinställningarna Original och Senaste.


## [!UICONTROL Binding Dimension]

En nedrullningsbar lista där du kan binda ett dimensionsvärdes beständighet till dimensionsvärden i en annan dimension. Giltiga alternativ är andra dimensioner som ingår i datavyn.

Se [Använda bindningsdimensioner och mätvärden i Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md) för exempel på hur du effektivt använder bindningsdimensioner.


>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Bindningsdimensioner](https://video.tv.adobe.com/v/342694/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## [!UICONTROL Binding Metric]

En nedrullningsbar lista där du kan välja ett mått som fungerar som en bindningsutlösare. Giltiga alternativ är mätvärden som ingår i datavyn.

Den här inställningen visas bara när Binding Dimension är lägre i objektarrayen än komponenten. När bindningsmåttet finns i en händelse kopieras dimensionsvärden från händelsenivådimensionen ned till den lägre schemanivån för bindningsdimensionen.

Se det andra exemplet under [Använda bindningsdimensioner och mätvärden i Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md) för mer information om hur du använder bindningsmått effektivt.
