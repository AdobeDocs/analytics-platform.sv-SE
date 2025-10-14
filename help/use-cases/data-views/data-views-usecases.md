---
title: Datavyer - Användningsexempel
description: Läs mer om olika användningsområden som ger flexibilitet och kraft åt datavyer i Customer Journey Analytics
exl-id: 6ecbae45-9add-4554-8d83-b06ad016fea9
solution: Customer Journey Analytics
feature: Data Views
role: User
source-git-commit: 0e9dc47b80db142801a94dcbf31470d99a610949
workflow-type: tm+mt
source-wordcount: '1235'
ht-degree: 0%

---

# Datavyer använder exempel

De här användningsexemplen illustrerar flexibiliteten och kraften hos datavyer i Customer Journey Analytics.

## Använd mått för bindning

Mer information finns i [Använd bindningsmåtten](binding-dimensions-metrics.md).

## Använd sammanfattningsdata

Mer information finns i [Använda sammanfattningsdata](summary-data.md).

## Användningsexempel för BI-tillägg

Se användningsexemplen för [BI-tillägget](bi-extension-usecases.md) om hur du slutför ett antal användningsfall med Customer Journey Analytics BI-tillägget.

## Skapa ett mått från ett strängschemafält {#string}

När du skapar en datavy kan du till exempel skapa ett [!UICONTROL Orders]-mått från ett [!UICONTROL Page Title]-schemafält som är en sträng.



1. Dra **[!UICONTROL Components]** på fliken **[!UICONTROL Page Title]** till avsnittet **[!UICONTROL Metrics]** under [!UICONTROL Included components].
1. Markera måttet som du just drog in och ändra namnet till `Orders` i **[!UICONTROL Component Settings]** på
1. Öppna avsnittet **[!UICONTROL Include/Exclude Values]** och ange följande:
   1. Aktivera **[!UICONTROL Set include exclude values]**.
   1. Välj **[!UICONTROL If all criteria are met]** från **[!UICONTROL Match]**.
   1. Ange `confirmation`. Texten för **[!UICONTROL page_title]** anger att den här sidan är relaterad till att placera en order. När du har granskat alla sidrubriker där villkoren uppfylls, räknas `1` för varje instans. Resultatet är ett nytt mätvärde (inte ett beräknat mätvärde) Ett mätvärde som har inkluderade/exkluderade värden kan användas överallt där andra mätvärden kan användas. Dessa mätvärden fungerar med attribuering, segment och var du än är kan du använda standardmätvärden.

   ![Dimension till mått](../assets/string-to-metric.gif){width=100%}
1. Du kan ytterligare ange en attribueringsmodell för det här måttet, till exempel [!UICONTROL Last Touch], med [!UICONTROL Lookback window] av [!UICONTROL Session].
Du kan också skapa ytterligare [!UICONTROL Orders]-mått från samma fält och ange en annan attribueringsmodell. Till exempel [!UICONTROL First Touch] och en annan [!UICONTROL Lookback window], till exempel [!UICONTROL 30 days].

Ett annat exempel är att använda person-ID, en dimension, som ett mått för att avgöra hur många person-ID ditt företag har.

## Använd heltal som dimensioner {#integers}

Tidigare behandlades heltal automatiskt som mätvärden i Customer Journey Analytics. Nu kan numeriska värden (inklusive anpassade händelser från Adobe Analytics) behandlas som dimensioner. Här är ett exempel:



1. Dra heltalet **[!UICONTROL Duration]** till avsnittet **[!UICONTROL Dimensions]** under [!UICONTROL Included Components]:
1. Du kan nu lägga till **[!UICONTROL Value Bucketing]** för att presentera den här dimensionen på ett paketerat sätt i rapporter. Utan bucketing visas varje instans av den här dimensionen som en radartikel i Workspace-rapporter.
   ![Heltal till dimension](../assets/integer-to-dimension.gif){width=100%}


## Använd numeriska mått som mått i flödesdiagram {#numeric}

Du kan använda en numerisk dimension för att hämta mätvärden till din [!UICONTROL &#x200B; Flow]-visualisering.

1. Dra schemafältet [&#x200B; till området &#x200B;](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/create-dataview) under [!UICONTROL Marketing Channels] på fliken [!UICONTROL Metrics]Komponenter[!UICONTROL Included components] i datavyer.
2. I Workspace-rapporter visar det här flödet [!UICONTROL Marketing Channels] som flödar in i [!UICONTROL Orders]:

![Marknadskanalen flödar från e-post till Avsluta/beställ.](../assets/flow.png)

## Gör underhändelsefiltrering {#sub-event}

Den här funktionen gäller specifikt för matrisbaserade fält. Med funktionerna för att inkludera/exkludera kan du filtrera på underhändelsenivå, medan segment som byggts i segmentbyggaren bara ger dig segmentering på händelsenivå. Du kan filtrera subhändelser genom att använda Inkludera/Exkludera i datavyer och sedan referera till det nya måttet/dimensionen i ett segment på händelsenivå.

Använd till exempel funktionerna för att inkludera/exkludera i datavyer om du bara vill fokusera på produkter som genererade mer än 50 dollar för försäljning. Om du har en beställning som innehåller ett produktköp på 50 USD och ett produktköp på 25 USD tar funktionen för att inkludera/exkludera bort produktinköpet på 25 USD, inte hela beställningen.

1. Dra schemafältet [&#x200B; till området &#x200B;](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/create-dataview) under **[!UICONTROL Revenue]** på fliken **[!UICONTROL Metrics]** Komponenter[!UICONTROL Included components] i datavyer.
1. Markera måtten och konfigurera följande på höger sida:
a. Välj **[!UICONTROL Format]** under **[!UICONTROL Currency]**.
b. Välj **[!UICONTROL Currency]** under **[!UICONTROL USD]**.
c. Markera kryssrutan intill **[!UICONTROL Include/Exclude Values]** under **[!UICONTROL Set include/exclude values]**.
d. Välj **[!UICONTROL Match]** under **[!UICONTROL If all criteria are met]**.
e. Välj **[!UICONTROL Criteria]** under **[!UICONTROL is greater than or equal]**.
f. Ange `50` som värde.

Med de här nya inställningarna kan du bara visa värdefulla intäkter och filtrera bort vad som helst under 50 dollar.

## Använd inställningen [!UICONTROL No value options] {#no-value}

Företaget kan ha ägnat tid åt att utbilda dina användare så att de förväntar sig&quot;Ospecificerad&quot; för dimensioner i rapporter. Standardvärdet för dimensioner i datavyer är *Inget värde*. Du kan dock per dimension ange hur inget värde ska rapporteras. Se alternativen för **[!UICONTROL No value]** för en dimensionskomponent.

![Inga värdealternativ](../assets/no-value-options.gif){width=100%}


## Skapa flera mätvärden med olika attribueringsinställningar {#attribution}

Använd funktionen **[!UICONTROL Duplicate]** längst upp till höger för att skapa ett antal totala intäktsmått med olika attribueringsinställningar som **[!UICONTROL First Touch]**, **[!UICONTROL Last Touch]** och **[!UICONTROL Algorithmic]**.

Glöm inte att byta namn på varje mätvärde för att återspegla skillnaderna, till exempel `Total Revenue (Algorithmic)`

![Duplicerat mätvärde för olika attributinställningar](../assets/duplicate-metric-for-attribution.gif){width=100%}

Mer information om andra datavyinställningar finns i [Skapa datavyer](/help/data-views/create-dataview.md).
En konceptuell översikt över datavyer finns i [Översikt över datavyer](/help/data-views/data-views.md).

## Ny session- och retursessionsrapportering {#new-repeat}

Du kan avgöra om en session är den första sessionen någonsin för en användare eller en retursession. Baserat på det rapportfönster som du har definierat för den här datavyn och ett 13-månaders uppslagsfönster. Med den här rapporten kan du till exempel avgöra:

* Hur stor procentandel av dina beställningar kommer från nya sessioner eller retursessioner?

* För en viss marknadsföringskanal, eller för en viss kampanj, riktar ni er till förstagångsanvändare eller returanvändare? Hur påverkar detta valet konverteringsgraden?

En dimension och två mätvärden underlättar den här rapporteringen:

* [Sessionstyp](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/component-reference) - Den här dimensionen har två värden: [!UICONTROL New] och [!UICONTROL Returning]. Radobjektet [!UICONTROL New] innehåller allt beteende (d.v.s. mått mot den här dimensionen) från en session som har fastställts vara en persons definierade första session. Allt annat ingår i radobjektet [!UICONTROL Returning] (förutsatt att allt tillhör en session). Om mätvärden inte ingår i någon session hamnar de i&quot;Inte tillämpligt&quot;-haken för den här dimensionen.

* [Första sessionen](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/component-reference). Mätvärdet för förstagångssessioner definieras som en persons definierade första session i rapportfönstret.

* [Retursessioner](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-dataviews/component-reference) Måttet på retursessioner är antalet sessioner som inte var en persons första session.—>

Så här kommer du åt komponenterna:

1. Gå till datavyredigeraren.
1. Välj fliken **[!UICONTROL Components]** och välj sedan **[!UICONTROL Standard components]** i den vänstra listen.
1. Dra komponenterna **[!UICONTROL Session type]**, **[!UICONTROL First-time Sessions]** och **[!UICONTROL Return Sessions]** till datavyn.

Nya sessioner rapporteras nästan alltid korrekt. De enda undantagen är:

* När en första session ägde rum före 13-månaders uppslagsfönster. <br/>Den här sessionen ignoreras.
* När en session sträcker sig över både uppslagsfönstret och rapportfönstret.<br/>Du kan till exempel köra en rapport från 1 juni 2022 till 15 juni 2022. Fönstret för uppslag skulle sträcka sig från 1 maj 2021 till 31 maj 2022. Om en session börjar den 30 maj 2022 och slutar den 1 juni 2022, inkluderas sessionen i uppslagsfönstret. Och alla sessioner i rapportfönstret räknas som retursessioner.

## Använda funktionerna Datum och Tid {#date}

Scheman i Adobe Experience Platform innehåller fälten [!UICONTROL Date] och [!UICONTROL Date-Time]. Customer Journey Analytics datavyer har nu stöd för dessa fält. När du drar dessa fält till en datavy som en dimension kan du ange deras [format](/help/data-views/component-settings/format.md). Den här formatinställningen avgör hur fälten visas i rapporter. Exempel:

* Om du väljer **[!UICONTROL Day]** med formatet **[!UICONTROL Month, Day, Year]** för datumformatet kan ett exempel i en rapportering se ut så här: 23 augusti 2022.

* Om du väljer **[!UICONTROL Minute of Day]** med formatet **[!UICONTROL Hour:Minute]** för formatet Datum-Tid kan utdata se ut så här: 20:20.

Datum efter 1 januari 1900 (med undantag av 1 januari 1970) och datum-/tidsvärden efter 1 januari 2000 00:00:00 stöds.

### Användningsexempel för datum och tid

* Datum: Ett reseföretag samlar in avgångsdatumet för resor som ett fält i sina uppgifter. Företaget vill ha en rapport som jämför [!UICONTROL Day of Week] för alla insamlade avgångsdatum för att förstå vilka som är populärast. Företaget vill göra samma sak med [!UICONTROL Month of Year].

* Datum och tid: Ett detaljhandelsföretag samlar in tiden för var och en av sina inköp i butiken (POS). Under en viss månad skulle företaget vilja förstå de mest köpta perioderna av [!UICONTROL Hour of Day].

>[!MORELIKETHIS]
>
>[Datum och tid i inställningen för formatkomponenten](/help/data-views/component-settings/format.md)
>

