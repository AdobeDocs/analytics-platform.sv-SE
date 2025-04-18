---
title: Översikt över datavyer
description: En datavy anger hur du vill tolka dataelement i Customer Journey Analytics-anslutningen, t.ex. mått, dimensioner, sessioner osv.
exl-id: f69e6e38-ac98-49a6-b0ce-f642af2932ae
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 0%

---

# Översikt över datavyer

En datavy är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en [anslutning](/help/connections/create-connection.md) ska tolkas. Här anges alla mått och mätvärden som är tillgängliga i Analysis Workspace och vilka kolumner som måtten och mätvärdena hämtar data från. Datavyer definieras som förberedelser för rapportering i Analysis Workspace.

>[!NOTE]
>
>Alla inställningar som du markerar eller ändrar i en datavy är retroaktiva och icke-förstörande. Med andra ord ändrar de inte dina underliggande data permanent.

Du kan skapa olika datavyer för samma anslutning, med mycket olika uppsättningar komponenter (mått/mått). Eller skapa datavyer med olika inställningar för tidsgräns för besök, attribuering osv. Du kan till exempel ha en datavy där alla dimensioner är inställda på [!UICONTROL Last Touch], och samtidigt en annan datavy (baserad på samma datamängd) med alla dimensioner inställda på [!UICONTROL First Touch].

Workspace-projekt i Customer Journey Analytics bygger på datavyer.

>[!IMPORTANT]
>
>Upp till 5 000 mätvärden och 5 000 dimensioner kan läggas till i en enda datavy.

## Funktioner för datavyer {#capabilities}

Med datavyer kan du ändra inställningar för schemaelement spontant utan att behöva ändra schemat i Adobe Experience Platform eller implementera om Customer Journey Analytics-miljön.

* Du kan ändra en komponent från ett mätvärde till en dimension och vice versa. Du kan skapa mätvärden från strängfält eller skapa dimensioner från numeriska fält. Den här funktionen gör livet enklare eftersom du inte behöver skapa ett numeriskt fält i XDM-schemat för varje mätvärde du vill ha. I stället kan du skapa det spontant i dialogrutan för datavyer. Här är några exempel:
   * **Skapa ett eller flera mått och/eller mått från ett enda schemafält**. Det är en en-till-många-relation. Du kan till exempel skapa en eller flera intäktsmått och/eller en eller flera intäktsdimensioner från ett enda schemafält.
   * **Använd ett strängfält som mått**: När du fyller i ett schema i Experience Platform med en datauppsättning kanske du inte vet i förväg vilka schemaelement du behöver. Du kanske inte har insett att du behövde ett mått för *Fel på en sida*. Därför skapade du inte ett numeriskt schemaelement med den här effekten. Genom att använda ett strängelement som mätvärden kan du nu använda datavysinställningarna för att ange att en sträng som innehåller ordet `error` kan användas som mätvärden när som helst.
   * **Använd ett numeriskt fält som en dimension**: Om du till exempel vill hämta intäktsmåttet från intäktsdimensionen visar intäktsdimensionen varje värde som en dimensionspost. Och antalet instanser för varje dimensionsartikel som ett mått.

* Du kan skapa flera mätvärden med olika attribueringsmodeller eller olika uppslagsfönster från samma schemafält.

* Du kan redigera ID:t för en komponent för kompatibilitet mellan data. Komponent-ID är det som API:t för rapportering använder för att identifiera ett visst mått eller en viss dimension. Eftersom du godtyckligt kan skapa många mätvärden eller dimensioner från ett XDM-fält har du möjlighet att definiera ett eget komponent-ID. Därför kan ett mätvärde som du använder i ett Workspace-projekt användas kompatibelt i datavyer (och API). Även om mätvärdena baseras på helt olika fält från olika anslutningar, datavyer eller från ett annat schema i XDM.

* Du kan ange ett eget komponentnamn som visas i Analysis Workspace. Som standard ärvs det här namnet från schemats visningsnamn, men du kan nu skriva över det för den här specifika datavyn.

* Du kan visa mer schemarelaterad information om komponenter. Till exempel:

   * vilken datamängdstyp (händelse, profil, sökning, sammanfattning) som komponenten kommer från,
   * vilken schematyp (sträng, heltal osv.) som det kommer från, och
   * schemasökvägen (XDM-fältet som den baseras på).

* Du kan tagga en komponent så att det blir enklare att söka efter den i Workspace.

* Du kan dölja en komponent i rapporter. Vissa mått- och dimensionsinställningar kräver ett andra mått eller en andra dimension för konfiguration (som till exempel metrisk borttagning av dubbletter eller borttagning av dubbletter). Genom att dölja en komponent kan du definiera en komponent som kan användas i inställningarna för en annan komponent utan att exponeras i rapporter.

* Du kan formatera ett mätresultat, till exempel visa decimal, tid, procent eller valuta, ange decimaler, visa upp trend som grön eller röd och ange valutaalternativ.

* Du kan skapa ett mått eller en dimension baserat på endast några av värdena i schemafältet. Om du till exempel vill ha ett felmått kan du skapa ett mått från sidnamnsfältet, men bara inkludera sidor som innehåller ordet `error`. Felmåttet som skapas på det här sättet stöder segment, kan infogas i beräknade värden och fungerar med attribuering, flöde, utfall osv.

* För dimensioner kan du automatiskt inkludera eller exkludera endast vissa värden i ett visst fält. Om en utvecklare till exempel har skickat fel värde på `dev mistake` till ett fält kan du enkelt utesluta det från rapportering med hjälp av en exkluderingsregel. Dimensionen fungerar som om fel värde aldrig fanns i data.

* Du kan byta namn på behållarna i en datavy och låta de namnändrade behållarna visas i alla Workspace-projekt som baseras på den datavyn.

## Krav för datavyer {#prerequisites}

* Innan du kan skapa datavyer måste du [konfigurera en eller flera anslutningar till Experience Platform datamängder](/help/connections/create-connection.md).
* Om du vill skapa eller hantera en datavy behöver du en [uppsättning behörigheter i Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-overview).
* Om du använder [Adobe Analytics-källkopplingen](/help/data-ingestion/analytics.md) eller har bakgrundskunskap om Adobe Analytics, kanske du vill förstå hur fält i dina scheman och datamängder relaterar till Adobe Analytics-motsvarigheter. Mer information finns i [Mappningar av analysfält](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/mapping/analytics).

## Datavy settings you can override in Workspace {#settings-override}

Vissa datavyinställningar kan åsidosättas i Analysis Workspace på projektnivå, andra kan inte det.

* [!UICONTROL Lookback window]
* Måttattribuering
* Om användare ser radobjektet [!UICONTROL No Value] i en rapport eller inte

## Datavyinställningar som du inte kan åsidosätta i Workspace {#settings-no-override}

* [!UICONTROL Component type]
* Metrisk formatering
* Datavy name
* Dimension-tilldelning

## Ta bort datavyer {#delete}

Om du tar bort en datavy i [!UICONTROL Customer Journey Analytics] visas ett felmeddelande om att alla [!UICONTROL Workspace]-projekt som är beroende av den här borttagna datavyn inte längre fungerar.

## Nästa steg

* [Skapa datavyer](/help/data-views/create-dataview.md)
* [Datavyer använder exempel](/help/use-cases/data-views/data-views-usecases.md)
