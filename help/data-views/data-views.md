---
title: Översikt över datavyer
description: En datavy anger hur du vill tolka element i data i anslutningen Customer Journey Analytics, t.ex. mått, dimensioner, sessioner osv.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 0%

---

# Översikt över datavyer

En datavy är en behållare som är specifik för Customer Journey Analytics och som gör att du kan bestämma hur data ska tolkas från en [anslutning](/help/connections/create-connection.md). Här anges alla mått och mätvärden som är tillgängliga i Analysis Workspace och vilka kolumner som måtten och mätvärdena hämtar data från. Datavyer definieras som förberedelser för rapportering i Analysis Workspace.

>[!NOTE]
>
>Alla inställningar som du markerar eller ändrar i en datavy är retroaktiva och icke-förstörande. Med andra ord ändrar de inte dina underliggande data permanent.

Du kan skapa olika datavyer för samma anslutning, med mycket olika uppsättningar komponenter (mått/mått). Eller skapa datavyer med olika inställningar för tidsgräns för besök, attribuering osv. Du kan till exempel ha en datavy där alla dimensioner är inställda på [!UICONTROL Last Touch]och samtidigt en annan datavy (baserad på samma datauppsättning) med alla dimensioner inställda på [!UICONTROL First Touch].

Arbetsyteprojekt i Customer Journey Analytics baseras på datavyer.

## Funktioner för datavyer {#capabilities}

Med datavyer kan du ändra inställningar för schemaelement spontant utan att behöva ändra schemat i Adobe Experience Platform eller implementera om Customer Journey Analytics-miljön.

* **Du kan ändra en komponent från ett mått till en Dimension och tvärtom**. Du kan skapa mått från strängfält eller skapa dimensioner från numeriska fält. Det gör livet enklare eftersom du inte behöver skapa ett numeriskt fält i XDM-schemat för varje mätvärde du vill ha. I stället kan du skapa det spontant i dialogrutan för datavyer. Här är några exempel:
   * **Skapa en eller flera och/eller en dimension från ett enda schemafält**. Det är en en-till-många-relation. Du kan till exempel skapa en eller flera intäktsmått och/eller en eller flera intäktsdimensioner från ett enda schemafält.
   * **Använd ett strängfält som mått**: När du fyller i ett schema i Experience Platform med en datauppsättning kanske du inte vet i förväg vilka schemaelement du behöver. Du kanske inte har insett att du behöver ett mått för&quot;Fel på en sida&quot;. Därför skapade du inte ett numeriskt schemaelement med den här effekten. Genom att använda ett strängelement som mätvärden kan du nu använda datavysinställningarna för att ange att en sträng som innehåller ordet error kan användas som mätvärden.
   * **Använd ett numeriskt fält som dimension**: Om du till exempel vill hämta intäktsmåtten från dimensionen Intäkter, visar dimensionen Intäkter varje värde som en dimensionspost ($100, $175, $1,000, osv.) och antalet instanser för varje dimensionsartikel. Intäkter som mått skulle uppträda som de alltid har gjort.

* **Du kan skapa flera mätvärden med olika attributmodeller eller med olika uppslagsfönster** från samma schemafält.

* **Du kan redigera ID:t för en komponent** - används för kompatibilitet mellan datavyer. Komponent-ID är det som API:t för rapportering använder för att identifiera ett visst mått eller en viss dimension. Eftersom du godtyckligt kan skapa många mätvärden eller dimensioner från ett XDM-fält får du möjlighet att definiera ditt eget komponent-ID. Därför kan ett mätresultat som du använder i ett Workspace-projekt vara kompatibelt med alla datavyer (och API:t), även om de baseras på helt olika fält från olika anslutningar eller datavyer eller från ett annat schema i XDM.

* **Du kan ange ett eget komponentnamn som ska visas i Analysis Workspace**. Som standard ärvs det här namnet från schemats visningsnamn, men du kan nu skriva över det för den här specifika datavyn.

* **Du kan visa mer schemarelaterad information om komponenter** , till exempel: vilken datamängdstyp (händelse, profil, sökning) som den kommer från, vilken schematyp (sträng, heltal osv.) Den kom från. och dess schemasökväg (det XDM-fält som det baseras på).

* **Du kan lägga till märkord i en komponent** för att göra det enklare att söka i Workspace.

* **Du kan dölja en komponent i rapporter**. Vissa mått- och dimensionsinställningar kräver ett andra mått eller en andra dimension för konfiguration (som till exempel metrisk borttagning av dubbletter eller borttagning av dubbletter). På så sätt kan du definiera ett mått eller en dimension som kan användas i inställningarna för ett annat mått eller en annan dimension utan att exponeras direkt i rapporter (till exempel köp-ID).

* **Du kan använda formatering för ett mätresultat**, t.ex. visa decimal, tid, procent eller valuta, specificera decimaler, uppåtgående trend som grönt eller rött, och ange valutaalternativ.

* Du kan **skapa ett mått eller en dimension baserat på endast några av värdena i schemafältet**. Om du till exempel vill ha ett felmått kan du skapa ett mätvärde från sidnamnsfältet, men bara inkludera sidor som innehåller ordet &quot;error&quot;. Felmåttet som skapas från detta stöds av filter, kan infogas i beräknade värden och fungerar med attribuering, flöde, utfall osv.

* För dimensioner kan du **inkluderar eller exkluderar automatiskt endast vissa värden i ett specifikt fält**. Om till exempel en utvecklare har skickat ett fel värde på `dev mistake` i ett fält kan du enkelt utesluta det från rapportering med hjälp av en exkluderingsregel och det beter sig som om det aldrig fanns i data.

* Du kan **byta namn på behållare** i en datavy och låta dessa namnändrade behållare visa i ett arbetsyteprojekt som baseras på den datavyn.

## Krav för datavyer {#prerequisites}

* Innan du kan skapa datavyer måste du [konfigurera en eller flera anslutningar till datauppsättningar i Experience Platform](/help/connections/create-connection.md).
* Om du vill skapa eller hantera en datavy behöver du en [behörighetsuppsättning i Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html#admin-access-permissions).

## Datavy settings you can override in Workspace {#settings-override}

Vissa datavyinställningar kan åsidosättas i Analysis Workspace på projektnivå, andra kan inte det.

* [!UICONTROL Lookback window]
* Måttattribuering
* Om användarna ser [!UICONTROL No Value] radartikel i en rapport

## Datavy settings you cannot override in Workspace {#settings-no-override}

* [!UICONTROL Component type]
* Metrisk formatering
* Datavy name
* Dimension

## Ta bort datavyer {#delete}

Om du tar bort en datavy i [!UICONTROL Customer Journey Analytics]visas ett felmeddelande om att [!UICONTROL Workspace] projekt som är beroende av den här borttagna datavyn kommer inte längre att fungera.

## Nästa steg

* [Skapa datavyer](/help/data-views/create-dataview.md)
* [Datavyer använder exempel](/help/use-cases/data-views/data-views-usecases.md)
