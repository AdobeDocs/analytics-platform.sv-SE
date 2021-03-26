---
title: Vad är en datavy i Customer Journey Analytics?
description: En datavy anger hur du vill tolka element i data i CJA-anslutningen, t.ex. mått, dimensioner, sessioner osv.
translation-type: tm+mt
source-git-commit: c1f5048e33d52a71db9811c22f49c237ac583817
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 0%

---


# Vad är en datavy?

En datavy placeras ovanpå en Customer Journey Analytics (CJA) [anslutning](/help/connections/create-connection.md). En anslutning kombinerar en eller flera datauppsättningar från Adobe Experience Platform och kopplar den till CJA. Datavyn anger hur du vill tolka element i data i anslutningen, t.ex. mått, dimensioner, sessioner osv. Datavyer definieras som förberedelser för rapportering av data i Workspace.

Om du tidigare har använt traditionell Adobe Analytics liknar datavyn en virtuell rapportsvit eftersom den är en&quot;filtrerad&quot; vy av data.

Du kan skapa olika datavyer för samma anslutning, med olika inställningar för tidsgräns för besök, attribuering osv. Du kan också skapa flera datavyer för en enskild datamängd. Du kan till exempel ha en datavy där alla dimensioner är inställda på [!UICONTROL Last Touch] och samtidigt en annan datavy (baserad på samma datamängd) med alla dimensioner inställda på [!UICONTROL First Touch].

Arbetsyteprojekt i Customer Journey Analytics baseras på datavyer.

## Nyheter i datavyer

Den senaste uppdateringen av datavyer ger dig större flexibilitet när det gäller vad du kan göra med datavyer. Med dessa förbättringar kan du **ändra schemaelementinställningarna spontant i datavyer, utan att behöva ändra schemat i Adobe Experience Platform eller implementera om CJA-miljön**.

* **Du kan ändra en komponent från ett mått till en Dimension och tvärtom**. Du kan skapa mått från strängfält eller skapa dimensioner från numeriska fält. Det gör livet enklare genom att du inte behöver skapa ett numeriskt fält i XDM-schemat för varje mätvärde du vill ha. I stället kan du skapa det spontant i dialogrutan för datavyer. Här är några exempel:
   * **Skapa en eller flera och/eller en dimension från ett enda schemafält**. Det är en en-till-många-relation. Du kan till exempel skapa en eller flera intäktsmått och/eller en eller flera intäktsdimensioner från ett enda schemafält.
   * **Använd ett strängfält som mått**: När du fyller i ett schema i Experience Platform med en datauppsättning kanske du inte vet i förväg vilka schemaelement du behöver. Du kanske inte har insett att du behöver ett mått för&quot;Fel på en sida&quot;. Därför skapade du inte ett numeriskt schemaelement med den här effekten. Genom att använda ett strängelement som mätvärden kan du nu använda datavysinställningarna för att ange att en sträng som innehåller ordet error kan användas som mätvärden.
   * **Använd ett numeriskt fält som dimension**: Om du till exempel vill hämta intäktsmåtten från dimensionen Intäkter, visar dimensionen Intäkter varje värde som en dimensionspost ($100, $175, $1,000, osv.) och antalet instanser för varje dimensionsartikel. Intäkter som mått skulle uppträda som de alltid har gjort.

* **Du kan skapa flera mätvärden med olika attribueringsmodeller eller med olika** lookback-fönster från samma schemafält.

* **Du kan redigera ID:t för en komponent**  - det används för kompatibilitet mellan datavyer. Komponent-ID är det som API:t för rapportering använder för att identifiera ett visst mått eller en viss dimension. Eftersom du godtyckligt kan skapa många mätvärden eller dimensioner från ett XDM-fält får du möjlighet att definiera ditt eget komponent-ID. Därför kan ett mätresultat som du använder i ett Workspace-projekt vara kompatibelt med alla datavyer (och API:t), även om de baseras på helt olika fält från olika anslutningar eller datavyer eller från ett annat schema i XDM.

* **Du kan ange ett eget komponentnamn som ska visas i Analysis Workspace**. Som standard ärvs det här namnet från schemats visningsnamn, men du kan nu skriva över det för den specifika datavyn. (Detta är också hur komponentkurering fungerar i virtuella rapportsviter i traditionella Adobe Analytics).

* **Du kan visa mer schemarelaterad information om komponenter** , till exempel: vilken datamängdstyp (händelse, profil, sökning) som den kommer från, vilken schematyp (sträng, heltal osv.) Den kom från. och dess schemasökväg (det XDM-fält som det baseras på).

* **Du kan tagga en** komponent så att det blir enklare att söka efter den i arbetsytan.

* **Du kan dölja en komponent i rapporter**. Vissa mått- och dimensionsinställningar i DV2 kräver ett andra mått eller en andra dimension för konfigurationen (som till exempel metrisk borttagning av dubbletter eller borttagning av dubbletter). På så sätt kan du definiera ett mått eller en dimension som kan användas i inställningarna för ett annat mått eller en annan dimension utan att exponeras direkt i rapporter (till exempel köp-ID).

* **Du kan använda formatering för ett mått** , till exempel decimal, time, percent eller currency; specificera decimaler, uppåtgående trend som grönt eller rött, och ange valutaalternativ.

* Du kan **skapa ett mått eller en dimension baserat på endast vissa av värdena i schemafältet**. Om du till exempel vill ha ett felmått kan du skapa ett mätvärde från sidnamnsfältet, men bara inkludera sidor som innehåller ordet &quot;error&quot;. Felmåttet som skapas från detta stöds av filter, kan infogas i beräknade värden och fungerar med attribuering, flöde, utfall osv.

* För dimensioner kan du **automatiskt inkludera eller exkludera endast vissa värden i ett specifikt fält**. Om en utvecklare till exempel har skickat ett felaktigt värde på `dev mistake` till ett fält kan du enkelt utesluta det från att rapportera med hjälp av en exkluderingsregel och det beter sig som om det aldrig fanns i data.

* Du kan **byta namn på dina behållare** i en datavy och låta de namnändrade behållarna visas i alla Workspace-projekt som baseras på den datavyn.

## Förutsättning

* Innan du kan skapa datavyer måste du [konfigurera en eller flera anslutningar till datauppsättningar i Experience Platform](/help/connections/create-connection.md).
* Om du vill skapa eller hantera en datavy behöver du en [uppsättning behörigheter i Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=en#admin-access-permissions).

## Visa information om en komponent

Klicka på ikonen (i) info i Workspace för att visa vilket schemafält en komponent baseras på och dess inställningar, till exempel en beskrivning.

## Datavy Settings you can override in Workspace

Vissa datavyinställningar kan åsidosättas i Analysis Workspace på projektnivå, andra kan inte det.

* Fönstret Lookback
* Måttattribut
* Om användare ser radobjektet&quot;Inget värde&quot; i en rapport eller inte

## Datavy Settings you cannot override in Workspace

* Komponenttyp
* Metrisk formatering
* Datavy name
* Dimension

## Ta bort datavyer

Om du tar bort en datavy i [!UICONTROL Customer Journey Analytics] visas ett felmeddelande om att alla arbetsyteprojekt som är beroende av den här borttagna datavyn inte längre fungerar.
