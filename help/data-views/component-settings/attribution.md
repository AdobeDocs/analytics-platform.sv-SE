---
title: Inställningar för attribueringskomponent
description: Gör att du kan ange standardattribuering för ett mätresultat.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 2fd79da264d60bb90e1193ead2eee67602404b4c
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Inställningar för attribueringskomponent {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_attribution"
>title="Tillskrivning"
>abstract="Konfigurera standardattribueringsmodellen som används för ett mått i rapporter."

<!-- markdownlint-enable MD034 -->


Attribution låter dig anpassa hur dimensionsposter får kredit för lyckade händelser.

Exempel:

1. En person på din webbplats klickar på en betalsöklänk till en av dina produktsidor. De lägger produkten i varukorgen, men köper den inte.
2. Nästa dag ser de ett inlägg i sociala medier från en av deras vänner. De klickar på länken och slutför sedan köpet.

I vissa rapporter kanske du vill ha den beställning som är kopplad till betald sökning. I andra rapporter kanske du vill att ordern ska tillskrivas Social. Attribution låter dig styra den här aspekten av rapportering.

## Ange en komponents attribueringsmodell

Du kan ändra standardattribueringsmodellen för en viss komponent genom att uppdatera komponentens inställning i datavyn. Om du gör det åsidosätts komponentens attribueringsmodell när som helst när den används i Analysis Workspace.

>[!NOTE]
>
>Tänk på följande när du aktiverar en icke-standardattribueringsmodell för ett mätvärde:
>
>* **När du använder måttet i en rapport med *en enda dimension*:** Måttets attribuering åsidosätter den allokeringsmodell som angetts för dimensionen. Ett mätresultat med till exempel attributet &quot;first touch&quot; åsidosätter en &quot;latest&quot;-dimensionsallokering.
>
>* **När du använder måttet i en rapport med *flera dimensioner*:** Måttets attribuering tillämpas ovanpå allokeringsmodellen för varje dimension. Ett mätvärde med attributet &quot;first touch&quot; används till exempel ovanpå en &quot;latest&quot;-dimensionsallokering.
>
> Mer information om allokering finns i [Inställningar för Persistence-komponent](/help/data-views/component-settings/persistence.md).

Så här uppdaterar du en komponents standardattribueringsmodell:

1. Gå till datavyn som innehåller komponenten vars standardattribueringsmodell du vill uppdatera.

1. Markera komponenten och expandera sedan avsnittet **[!UICONTROL Attribution]** till höger på skärmen.

   ![Fönstret Datavyer där attributalternativet Ange markeras ](../assets/attribution-settings.png)

1. Välj [!UICONTROL **Ange attribuering**] och välj sedan fönstret [attribueringsmodell](#attribution-models), [container](#container) och [lookback](#lookback-window).



1. Välj [!UICONTROL **Spara och fortsätt**].

>[!TIP]
>
>Om din organisation kräver att ett mätresultat har flera attribueringsinställningar kan du göra något av följande:
>
> * Kopiera måtten i datavyn med varje önskad attribueringsinställning. Du kan inkludera samma mätvärde flera gånger i en datavy och ge varje mätvärde en egen inställning. Se till att du märker varje mätvärde på rätt sätt så att analytikerna förstår skillnaden mellan dessa mätvärden när de skapar rapporter.
>
> * Åsidosätt måttet i Analysis Workspace. I måttets [kolumninställningar](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md) väljer du **[!UICONTROL Use non-default attribution model]** om du vill ändra måttets attribueringsmodell och uppslagsfönster för den specifika rapporten.

## Attributionsmodeller {#attribution-models}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataviews_component_attribution_attributionmodels"
>title="Modell"
>abstract="Välj en attribueringsmodell för måttet."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}

## Behållare

{{attribution-container}}

## Fönstret Lookback

{{attribution-lookback-window}}

## Exempel

{{attribution-example}}
