---
description: Läs mer om mätningstyp och attribuering
title: Mättyp och attribut
feature: Calculated Metrics
exl-id: da73a9ba-542e-436c-bdb2-b629b5b6f760
source-git-commit: 2d182004b12eb44f54ec9b4b5f63cb9072594aec
workflow-type: tm+mt
source-wordcount: '967'
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

            * Välj en **[!UICONTROL Model]** från attribueringsmodellerna.
            * Välj en **[!UICONTROL Lookback window]**. Om du väljer **[!UICONTROL Custom Time]** kan du definiera tidsperioden i **[!UICONTROL Minute(s)]** upp till **[!UICONTROL Quarter(s)]**. Mer information finns i [Fönstret ](#lookback-window)

      1. Välj **[!UICONTROL Apply]** om du vill använda en icke-standardattribueringsmodell. Välj Avbryt om du vill avbryta.

     Om du redan har definierat en icke-standardattribueringsmodell väljer du **[!UICONTROL Edit]** om du vill ändra urvalet.

I [Exempel](#example) finns ett exempel på hur du använder en attribueringsmodell och ett uppslagsfönster.


## Tillskrivning {#attribution}

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


### Fönstret Lookback {#lookback-window}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Fönstret Lookback"
>abstract="Den här inställningen bestämmer fönstret för den dataattribuering som ska användas för varje konvertering."

<!-- markdownlint-enable MD034 -->

{{attribution-lookback-window}}


### Attributionsexempel {#attribution-example}

Titta på följande exempel:

1. Den 15 september kommer en person till er webbplats via en betald sökannons, sedan går han/hon iväg.
1. Den 18 september kommer personen till er webbplats igen via en länk för sociala medier som de fått från en vän. De lägger till flera artiklar i kundvagnen, men köper ingenting.
1. Den 24 september skickar marknadsföringsteamet ett e-postmeddelande med en kupong för några av artiklarna i kundvagnen. De använder kupongen, men besöker flera andra sajter för att se om det finns några andra kuponger. De hittar en till genom en displayannons och gör sedan ett köp för 50 dollar.

Beroende på ditt uppslagsfönster och din attribueringsmodell får kanalerna olika krediter. Nedan följer några exempel:

* Med **första beröring** och ett **sessionsfönster** tittar attribueringen bara på det tredje besöket. Mellan e-post och visning var e-post först, så e-post får 100 % rabatt på 50 USD.

* Attribution söker efter alla tre besök med **första beröring** och ett **fönster för personsökning**. Betalsökning var först, så den får 100 % rabatt på 50 USD.

* Med **linjär** och ett **sessionsfönster** delas krediteringen mellan e-post och visning. Båda dessa kanaler får 25 krediter.
Med **linjär** och ett **personsökningsfönster** delas krediten in i betalsökning, sociala medier, e-post och visning. Varje kanal får 12,50 dollar i rabatt för detta inköp.

* Med **J-formad** och ett **personsökningsfönster** delas krediteringen mellan betalsökningar, sociala medier, e-post och visning.

   * 60 % kredit ges för 30 dollar.
   * 20 % kredit ges till betald sökning för 10 dollar.
   * De återstående 20 % är uppdelade i sociala medier och e-post, vilket ger 5 USD till var och en.

* Med **Time Decay** och ett **Personsökningsfönster** delas krediten in i betalsökning, sociala medier, e-post och visning. Använd standardhalveringstiden på 7 dagar:

   * Mellanrum på noll dagar mellan visning och konvertering. `2^(-0/7) = 1`
   * Mellanrum på noll dagar mellan e-postens kontaktpunkt och konvertering. `2^(-0/7) = 1`
   * Ett mellanrum på sex dagar mellan social kontaktyta och konvertering. `2^(-6/7) = 0.552`
   * Mellanrum på nio dagar mellan betald sökningspunkt och konvertering. `2^(-9/7) = 0.41`
   * Normalisering av dessa värden ger följande resultat:

      * Bildskärm: 33,8 %, får 16,88 USD
      * E-post: 33,8 % får 16,88 USD
      * Socialt: 18,6 %, får 9,32 USD
      * Betalsökning: 13,8 %, får 6,92 USD

Konverteringshändelser som vanligtvis har ett heltal delas om kredit tillhör fler än en kanal. Om till exempel två kanaler bidrar till en order med en linjär attribueringsmodell får båda kanalerna 0,5 av den ordningen. Dessa partiella mätvärden summeras för alla personer och avrundas sedan till närmaste heltal för rapportering.


>[!MORELIKETHIS]
>
>[Inställningar för attribueringskomponent](/help/data-views/component-settings/attribution.md)
>[Deltagandemått ](participation-metric.md)
>

