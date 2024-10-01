---
title: Inställningar för attribueringskomponent
description: Gör att du kan ange standardattribuering för ett mätresultat.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 8f3b30ca6d20d633669d7e9180884c24e0b9a52e
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 0%

---

# Inställningar för attribueringskomponent {#attribution-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_metric_attribution"
>title="Tillskrivning"
>abstract="Konfigurera standardattribueringsmodellen som används för ett mått i rapporter."

<!-- markdownlint-enable MD034 -->


Attribution låter dig anpassa hur dimensionsposter får kredit för lyckade händelser.

![Fönstret Datavyer där attributalternativet Ange markeras ](../assets/attribution-settings.png)

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

1. Markera komponenten och expandera sedan avsnittet Attribution till höger på skärmen.

   ![Fönstret Datavyer där attributalternativet Ange markeras ](../assets/attribution-settings.png)

1. Välj [!UICONTROL **Ange attribuering**] och välj sedan attribueringsmodell i listrutan [!UICONTROL **Attributmodell**].

   Se [Attribution models](#attribution-models) om du vill veta mer om de olika attribueringsmodellerna.

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
>id="cja_dataviews_component_attribution_attributionmodels"
>title="Modell"
>abstract="Välj en attribueringsmodell för måttet."

<!-- markdownlint-enable MD034 -->

{{attribution-models-details}}


## Fönstret Lookback

{{attribution-lookback-window}}



## Attributionsexempel {#attribution-example}

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


