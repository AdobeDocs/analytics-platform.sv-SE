---
title: Användarhandbok för Adobe Analytics
description: Vad man ska tänka på när man flyttar data från Adobe Analytics till Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 8f64e0a31ed3bca7185674490fc36b78598f5b1c
workflow-type: tm+mt
source-wordcount: '1446'
ht-degree: 0%

---

# Användarhandbok för Adobe Analytics

Om ni börjar anställa Adobe Customer Journey Analytics kan ni märka vissa likheter och skillnader mellan Adobe Analytics och Customer Journey Analytics. På den här sidan förklaras skillnaderna så att ni kan anpassa er till det nya arbetsflödet för implementering och rapportering. Den här sidan innehåller även ytterligare resurser om nya koncept och ytterligare steg för att göra din resa som analytiker enklare och mer framgångsrik.

Flera av funktionerna i Customer Journey Analytics har bytt namn och fått en ny utformning för att passa branschens standarder. Vissa uppdaterade termer innehåller segment, virtuella rapportsviter, klassificeringar, kundattribut och behållarnamn. Begränsningarna för eVars och props finns inte längre, vilket gynnar flexibla anpassade mått och mätvärden.

## Vad som inte har ändrats

Mycket av det du är bekant med på rapporteringssidan har inte ändrats.

* Du kan fortfarande använda [Analysis Workspace](/help/analysis-workspace/home.md) för att analysera era data. Arbetsytan fungerar på samma sätt som i traditionella Adobe Analytics.
* Samma version av [Adobe Analytics dashboards](/help/mobile-app/home.md) finns och fungerar på liknande sätt mellan Customer Journey Analytics och Adobe Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) har ett nytt gränssnitt och kan köras i MS Windows, MacOS och webbversionen av Excel. (Före den här versionen av Report Builder kunde du inte använda den i Mac om du inte körde den på VMware.) Den här versionen stöder inte traditionell databegäran från AA ännu.

## Ändringar i rapportering

Ni har tillgång till betydligt fler flerkanalsdata som kan analyseras. Du kan till exempel skapa ett arbetsyteprojekt som analyserar prestanda för flera kanaler, förutsatt att dessa datauppsättningar har importerats av din organisation och ingår i datavyer som används av Customer Journey Analytics (se&quot;Ändringar i dataarkitekturen&quot; nedan).

![visualiseringar med flera kanaler](assets/cross-channel.png)

## Ändringar i dataarkitekturen {#architecture}

Customer Journey Analytics får sina data från Adobe Experience Platform. Med Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och kanaler och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser.

Kunddata i Experience Platform lagras som datauppsättningar, som består av en [schema](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html) och batchar med data. Mer information om plattformen finns på [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html).

Din Customer Journey Analytics-administratör upprättar [anslutningar](/help/connections/create-connection.md) till datauppsättningar i Experience Platform. Sedan bygger de [datavyer](/help/data-views/data-views.md) med dessa anslutningar. Datavyer liknar begreppsmässigt virtuella rapportsviter och är grunden för rapportering i Customer Journey Analytics. Eftersom Experience Platform hämtar alla data för rapportering finns inte längre rapportsviterna som databehållare.

Med en anslutning kan Analytics Admin integrera datauppsättningar från Adobe Experience Platform i Customer Journey Analytics, som ingår i följande video:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe erbjuder flera sätt att överföra data till Adobe Experience Platform, inklusive rapportsvitsdata via Analytics-källkopplingen eller Web SDK. Befintliga implementeringar från flera rapportsviter kan kombineras i Experience Platform. De anslutningar och datavyer som baseras på dessa datauppsättningar kan kombinera data som tidigare fanns i separata rapportsviter.

## Förändringar i konceptet med virtuella rapportsviter {#data-views}

[!UICONTROL Data views] ta begreppet virtuella rapportsviter som de finns idag och utvidga det till [aktivera ytterligare kontroller av data](/help/data-views/create-dataview.md) som är tillgängliga via anslutningar. Dessa ändringar gör allmänna inställningar som tidszon och tidsgränsintervall för sessioner konfigurerbara och retroaktiva. Enskilda variabelinställningar som attribuering och förfallodatum kan också anpassas på en rapport- eller datavynivå. De här inställningarna är icke-förstörande och retroaktiva.

Observera att rapportsvitens väljare i det övre hörnet nu låter dig välja bland tillgängliga datavyer:

![data-view-selector](assets/data-views.png)

Se [Använda exempel på datavyer](/help/use-cases/data-views/data-views-usecases.md) för mer information om detta koncept.

## Förändringar av begreppet eVars och Props

Begreppen [!UICONTROL eVars], [!UICONTROL props]och [!UICONTROL events] i traditionell Adobe Analytics finns inte längre i [!UICONTROL Customer Journey Analytics]. I Adobe Analytics kan eVars och props lagra beskrivningar av innehåll, kunder, kampanjer osv. och händelser räknas saker som intäkter, prenumerationer eller genererade leads. Customer Journey Analytics bevarar båda datatyperna och du kan få tillgång till dem på samma sätt - från den vänstra listen i Analysis Workspace, under Dimensioner respektive Metrisk.

I Customer Journey Analytics finns det ett obegränsat antal schemaelement, inklusive mått, mått och listfält. Dessa mappas till ett obegränsat antal schemaelement, inklusive mått, mått och listfält i Experience Platform. Alla inställningar för besök och attribuering som används efter bearbetning av regler i Adobe Analytics gäller nu vid frågetiden i Customer Journey Analytics.

Med den här flexibiliteten kan du råka ut för situationer där ett enda schemafält kan användas både som en dimension och ett mått för olika spårningsbehov.

## Förändringar av segmentkonceptet

Adobe har bytt namn på&quot;segment&quot;-komponenten till&quot;filter&quot; för att bättre anpassa sig till branschstandarder och ge bättre distinktion till segment i Adobe Experience Platform.

[!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser, utan använder i stället Experience Platform-schemafältnamnet som de har mappats till. Ändringen innebär att inget av de befintliga segmenten i Adobe Analytics är kompatibelt med [!UICONTROL Customer Journey Analytics]. Om du vill flytta befintliga Adobe Analytics-segment till Customer Journey Analytics ska du titta i följande video:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

Även om du inte kan dela eller publicera ännu [!UICONTROL filters] ([!UICONTROL segments]) från [!DNL Customer Journey Analytics] för Experience Platform Unified Profile håller den här funktionen på att utvecklas.

Förutom segmentändringen uppdateras även segmentbehållarna.

* **Träffbehållare är nu [!UICONTROL Event] behållare**. The [!UICONTROL Event] Med -behållare kan du dela upp personinformation baserat på enskilda händelser.
* **Besöksbehållare finns nu [!UICONTROL Session] behållare**. The [!UICONTROL Session] kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session.
* **Behållare för besökare är nu [!UICONTROL Person] behållare**. The [!UICONTROL Person] behållare innehåller alla sessioner och händelser för en person inom den angivna tidsramen.

## Förändringar av begreppet beräknade mätvärden

Beräknade mätvärden namnges på liknande sätt mellan Adobe Analytics och Customer Journey Analytics. Men [!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett Experience Platform-schemaelement. Denna grundläggande ändring innebär att inga av de befintliga beräknade mätvärdena är kompatibla med [!UICONTROL Customer Journey Analytics]. Om du vill flytta Adobe Analytics beräknade värden till Customer Journey Analytics ska du titta i följande video:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Ändringar av variabelattribuerings- och förfalloinställningar

[!UICONTROL Customer Journey Analytics] använder alla variabelinställningar, inklusive attribuering och förfallodatum, vid rapporttidpunkten. Dessa inställningar finns nu i [datavyer](/help/data-views/component-settings/persistence.md)och vissa variabelinställningar (som attribuering) kan ändras i Workspace-projekt.

Du kan ha flera versioner av samma variabel i samma datavy. Du kan t.ex. ha en spårningskoddimension som upphör efter 30 dagar och en annan som slutar i slutet av en session. Båda dessa spårningskoddimensioner använder samma källdata, men använder olika attribueringsinställningar.

Du kan också ha flera datavyer baserade på samma anslutning. Du kan till exempel ha en datavy med en sessionstimeout på 30 minuter och en annan med en sessionstimeout på 15 minuter. Båda datavyerna visas i den övre högra väljaren så att du smidigt kan växla mellan dem.

## Förändringar av begreppet klassificeringar

&quot;Klassificeringar&quot; kallas nu&quot;Sök efter datauppsättningar&quot;. Uppslagsdatauppsättningar används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. Se [Lägg till data på kontonivå som en uppslagsdatauppsättning](/help/use-cases/b2b/b2b.md) till exempel.

## Förändringar av begreppet kundattribut

&quot;Kundattribut&quot; kallas nu &quot;profildatamängder&quot;. Profildatauppsättningar innehåller data som tillämpas på dina personer, användare eller kunder i [!UICONTROL Event] data. Du kan till exempel överföra CRM-data om dina kunder. Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i [!DNL Experience Platform] har en egen uppsättning med ett eller flera person-ID definierade.

## Ändringar i hur Adobe identifierar besökare

Customer Journey Analytics utökar begreppet identiteter utöver ECID:n så att det omfattar alla ID:n du vill använda, inklusive Kund-ID, Kakcookie-ID, Stitched ID, Användar-ID, Spårningskod osv. Använda ett gemensamt namnområdes-ID för datauppsättningar, eller använda [Stitlar](../stitching/overview.md) hjälper till att länka samman personer över olika datauppsättningar. Alla användare som skapar ett Workspace-projekt i Customer Journey Analytics måste förstå de ID som används i datauppsättningarna. Se följande video som visar hur du använder identiteter i Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Förändringar av begreppet lågtrafikdimensionsobjekt

I traditionell Adobe Analytics börjar en variabel som får för många unika värden att buffra dimensionsobjekt under [!UICONTROL Low-Traffic]. Customer Journey Analytics har färre begränsningar för högkardinalfält. Tack vare förändringar i rapporteringsarkitekturen kan Analysis Workspace rapportera om många fler unika dimensionsobjekt. Se [Höga kardinaldimensioner](../components/dimensions/high-cardinality.md) om du vill ha mer information om hur Customer Journey Analytics optimerar rapporteringen för dimensioner med många unika värden.
