---
description: Läs mer om mätningstyp och attribuering
title: Mättyp och attribut
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 304b8d85767d89ee60a6fb37a128194f60ca89d4
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 0%

---

# Mättyp och attribut

Du kan konfigurera måtttypen och [attribueringsmodellen](#attribution-models) för ett mått i en beräknad måttdefinition.

1. Välj ![Inställning](/help/assets/icons/Setting.svg) i måttkomponenten.
1. I popup-dialogrutan:

   ![Mättyp och attribuering](assets/cm-type-alloc.png)

   * Ange **[!UICONTROL Metric type]**:

     | Mätningstyp | Definition |
     |---|---|
     | **[!UICONTROL Standard]** | Om en formel består av ett enda standardmått visas identiska data som den icke-beräknade metriska motsvarigheten. Standardvärden är användbara för att skapa beräknade värden som är specifika för varje enskilt radobjekt. <p>Till exempel tar ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** order för det specifika radobjektet och dividerar den med antalet sessioner för det specifika radobjektet. |
     | **[!UICONTROL Grand total]** | Använd **[!UICONTROL Grand total]** för rapporteringsperioden i alla radartiklar. Om en formel består av ett enda totalmått, visar det beräknade måttet samma totaltal för varje radartikel. Summavärden är användbara när du vill skapa beräknade värden som jämför med totaldata. <p>Till exempel visar ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Orders]** ![Divide](/help/assets/icons/Divide.svg) ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]** andelen order mot alla sessioner, inte bara sessionerna med det specifika radobjektet. I det här exemplet anger du **[!UICONTROL Grand Total]** för måttet ![ Event](/help/assets/icons/Event.svg) **[!UICONTROL Sessions]** i det beräknade måttet, som automatiskt förvandlar det till ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Total Sessions]**. |

   * Ange **[!UICONTROL Attribution]**.

      1. Du kan antingen:

         * Inaktivera **[!UICONTROL Use non-default attribution model]** om du vill använda standardkolumnattribueringsmodellen, som är Sista handen, med ett uppslagsfönster på 30 dagar.
         * Aktivera **[!UICONTROL Use non-default attribution model]**. I dialogrutan **[!UICONTROL Column attribution model]**

            * Välj **[!UICONTROL Model]** bland [attribueringsmodellerna](#attribution-models).
            * Välj en **[!UICONTROL Container]** bland alternativen för [container](#container).
            * Välj en **[!UICONTROL Lookback window]** bland alternativen för [uppslagsfönstret](#lookback-window). Om du väljer **[!UICONTROL Custom Time]** kan du definiera tidsperioden i **[!UICONTROL Minute(s)]** upp till **[!UICONTROL Quarter(s)]**.

      1. Välj **[!UICONTROL Apply]** om du vill använda en icke-standardattribueringsmodell. Välj Avbryt om du vill avbryta.

     Om du redan har definierat en icke-standardattribueringsmodell väljer du **[!UICONTROL Edit]** om du vill ändra urvalet.

Se [Exempel](#example) för ett exempel på hur du använder en attribueringsmodell, behållare och ett uppslagsfönster.


## Attributionsmodeller {#attribution-models}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_nondefaultattributionmodel"
>title="Använd en attribueringsmodell som inte är standard"
>abstract="Aktivera en icke-standardattribueringsmodell för det valda måttet."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modell"
>abstract="Välj en attribueringsmodell för måttet."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Senaste beröring"
>abstract="100 % av krediterna går till det sista dimensionsvärdet som en besökare kan se."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Första beröring"
>abstract="100 % av krediterna går till det första dimensionsvärdet som en besökare ser."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Linjär"
>abstract="Krediten fördelas jämnt över alla dimensionsvärden."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="deltagande"
>abstract="100 % tack för alla dimensionsvärden som ses av en besökare.<br/>Kolumnsummor är överskattade."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Samma beröring"
>abstract="Kreditering ges endast till dimensionsvärden som inträffar för samma händelse som konvertering."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Samma beröring"
>abstract="Kreditering ges endast till dimensionsvärden som inträffar för samma händelse som konvertering."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="U Shaped"
>abstract="40 % krediterar det första dimensionsvärdet, 40 % fram till det sista, 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="J-kurva"
>abstract="60 % krediterar det sista dimensionsvärdet, 20 % till det första och 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="J-kurva"
>abstract="60 % krediterar det sista dimensionsvärdet, 20 % till det första och 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="Inverterad J"
>abstract="60 % krediterar det första dimensionsvärdet, 20 % till det sista, 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="Inverterad J"
>abstract="60 % krediterar det första dimensionsvärdet, 20 % till det sista, 20 % delas av mitten."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Tidsminskning"
>abstract="Dimension-värden som ligger närmast konverteringen ger mest valuta för pengarna."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Anpassad"
>abstract="Definiera din egen positionsbaserad attribueringsvikt."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Anpassad"
>abstract="Definiera din egen positionsbaserad attribueringsvikt."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algoritmisk"
>abstract="Krediten bestäms dynamiskt utifrån en statistisk algoritm."

{{attribution-models-details}}


## Behållare {#container}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Behållare"
>abstract="Välj en behållare för att ange önskat omfång för attribueringen."

{{attribution-container}}


## Fönstret Lookback {#lookback-winwow}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Fönstret Lookback"
>abstract="Den här inställningen bestämmer fönstret för den dataattribuering som ska användas för varje konvertering."

{{attribution-lookback-window}}




## Exempel

{{attribution-example}}

>[!MORELIKETHIS]
>
>[Inställningar för attribueringskomponent](/help/data-views/component-settings/attribution.md)
>>[Deltagandemått ](participation-metric.md)
>

