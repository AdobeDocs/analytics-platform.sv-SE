---
title: Inställningar för attribueringskomponent
description: Gör att du kan ange standardattribuering för ett mätresultat.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 7d354ce65f72838c007d2b9faf02848d86fd7c0f
workflow-type: tm+mt
source-wordcount: '408'
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

## Ange en komponents standardattribueringsmodell

Du kan ange en standardattribueringsmodell för ett givet mätresultat genom att uppdatera måttets inställning i datavyn. Om du gör det åsidosätts måttets attribueringsmodell när som helst när den används i Analysis Workspace.

>[!NOTE]
>
>Tänk på följande när du aktiverar attribuering för ett mätvärde:
>
>* **När komponenten används i en rapport med *en enda dimension*:** Komponentens attribuering ignorerar allokeringsmodellen när en icke-standardattribueringsmodell används.
>
>* **När komponenten används i en rapport med *flera dimensioner*:** Komponentens attribuering behåller allokeringsmodellen när en icke-standardattribueringsmodell används.
>
>   Flera dimensioner är bara tillgängliga när [exporterar data till molnet](/help/analysis-workspace/export/export-cloud.md).
>
> Mer information om allokering finns i [Inställningar för Persistence-komponent](/help/data-views/component-settings/persistence.md).

Så här uppdaterar du en komponents standardattribueringsmodell:

1. Gå till datavyn som innehåller komponenten vars standardattribueringsmodell du vill uppdatera.

1. Markera komponenten och expandera sedan avsnittet **[!UICONTROL Attribution]** till höger på skärmen.

   ![Fönstret Datavyer där attributalternativet Ange markeras &#x200B;](../assets/attribution-settings.png)

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
