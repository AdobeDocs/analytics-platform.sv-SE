---
title: CJA User Guide for Adobe Analytics users
description: Vad man ska tänka på när man flyttar data från Adobe Analytics till Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
source-git-commit: 570fb36de0ed81f001ed6115e73d1d4347f368ec
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 0%

---

# CJA User Guide for Adobe Analytics users

Ditt företag börjar anställa Customer Journey Analytics. Som användare som är bekant med Adobe Analytics har du redan fått en bra start. När du arbetar med Customer Journey Analytics kommer du att märka vissa likheter och stora skillnader. Den här sidan syftar till att förklara de saker som inte har ändrats samt några av de stora skillnaderna. Vi kommer också att berätta för er hur ni kan få mer information om nya koncept och ytterligare steg för att göra kundresan enklare och mer framgångsrik.

Flera funktioner i CJA har fått ett nytt namn och fått en ny arkitektur jämfört med traditionella Adobe Analytics för att passa in i branschens standarder. Vissa uppdaterade termer innehåller segment, virtuella rapportsviter, klassificeringar, kundattribut och behållarnamn. Välbekanta koncept som eVars och props finns inte längre, tillsammans med de begränsningar de hade.

## Vad som inte har ändrats

Mycket av det ni känner till på rapporteringssidan har inte förändrats.

* Du kan fortfarande använda [Analysis Workspace](/help/analysis-workspace/home.md) för att analysera era data. Arbetsytan fungerar på samma sätt som i traditionella Adobe Analytics.
* Du har också samma version av [Adobe Analytics dashboards](/help/mobile-app/home.md) till ditt förfogande. Kontrollpaneler (alias Dashboards) Mobile App) fungerar på samma sätt som i traditionella Adobe Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) har ett nytt gränssnitt och kan nu köras på PC, Mac och webbversionen av Excel.

När det gäller rapportering, **vad som är annorlunda** är att ni har tillgång till betydligt fler flerkanalsdata att analysera. Här är ett exempel på några visualiseringar som inkluderar datakällor för flera kanaler:

![visualiseringar med flera kanaler](assets/cross-channel.png)

## Ny arkitektur {#architecture}

Customer Journey Analytics får sina data från Adobe Experience Platform. Med Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och kanaler och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser.

Kunddata på plattformen lagras som datauppsättningar, som består av ett schema och grupper med data. Mer information om plattformen finns på [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Din CJA-administratör har etablerat [anslutningar](/help/connections/create-connection.md) till datauppsättningar i Platform. De har sedan byggt [datavyer](/help/data-views/data-views.md) inom dessa anslutningar. Tänk på datavyer som liknar virtuella rapportsviter. Datavyer är grunden för rapportering i Customer Journey Analytics. Begreppet rapportsvit finns inte längre.

## Anslutningar

Med en anslutning kan Analytics Admin integrera datauppsättningar från [!DNL Adobe Experience Platform] till [!UICONTROL Workspace]. För att rapportera [!DNL Experience Platform] datauppsättningar måste du först skapa en anslutning mellan datauppsättningar i [!DNL Experience Platform] och [!UICONTROL Workspace].

Här är en videoöversikt:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Rapportsviter {#report-suites}

Data från rapportsviten kan hämtas till Experience Platform via Adobe Analytics Source Connector eller Web SDK om din organisation fortfarande använder Adobe Analytics och lägger till CJA/AEP. Vanligtvis kommer du att hämta datauppsättningar som är specifika för rapportsviten med Analytics-schemat.

Rapporteringssviter är dock inte längre grunden för rapportering i CJA - [datavyer](/help/data-views/data-views.md) är. Mer information om datavyer finns i avsnittet nedan.

Befintliga implementeringar från flera datauppsättningar kan kombineras i Experience Platform. De anslutningar och datavyer som baseras på dessa datauppsättningar kan kombinera data som tidigare fanns i separata rapportsviter.

## (Virtuella) rapportsviter är nu datavyer {#data-views}

[!UICONTROL Data views] ta begreppet virtuella rapportsviter som de finns idag och utvidga det till [aktivera ytterligare kontroller av data](/help/data-views/create-dataview.md) som är tillgängliga via anslutningar. Detta gör att tidszon- och timeout-intervall för sessioner kan konfigureras. Du kan också använda attribut- och förfalloegenskaper för enskilda dimensioner dynamiskt. Observera att dessa tillämpas retroaktivt på alla data.

**Vad du behöver göra**:

* Observera att i Workspace kan du nu välja bland de datavyer som administratören har delat med dig i den rapportsvitsväljare som du är van vid:

   ![data-view-selector](assets/data-views.png)

* Bekanta dig med de många [användningsexempel runt datavyer](/help/data-views/data-views-usecases.md).

## eVars och props

[!UICONTROL eVars], [!UICONTROL props]och [!UICONTROL events] i traditionell Adobe Analytics-mening finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden.

**Vad du behöver göra**:

* Bekanta dig med de många olika sätt som dessa schemaelement kan användas för att fördjupa dig i dina data.

## Segmenten är nu &#39;Filter&#39;

[!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inget av de befintliga segmenten är kompatibelt med [!UICONTROL Customer Journey Analytics]. Dessutom har namnet&quot;segment&quot; ändrats till&quot;filter&quot;.

Du kan för närvarande inte dela/publicera [!UICONTROL filters] ([!UICONTROL segments]) från [!DNL Customer Journey Analytics] till Experience Platform Unified Profile eller andra program i Experience Cloud. Den här funktionen håller på att utvecklas.

**Vad du behöver göra**:

* Om du vill flytta befintliga Adobe Analytics-segment till Customer Journey Analytics kan du visa [den här videon](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en).
* Annars återskapar du filtren i Customer Journey Analytics.

## Beräknade värden

[!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inga befintliga beräknade värden är kompatibla med [!UICONTROL Customer Journey Analytics].

**Vad du behöver göra**:

* Om du vill flytta Adobe Analytics beräknade värden till Customer Journey Analytics kan du visa [den här videon](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en).
* Annars återskapar du de beräknade måtten i Customer Journey Analytics.

## Inställningar för session och variabel beständighet

[!UICONTROL Customer Journey Analytics] använder alla dessa inställningar vid rapporttillfället och dessa inställningar finns nu i [datavyer](/help/data-views/component-settings/persistence.md). Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer!

## Klassificeringarna är nu &#39;Sök efter datauppsättningar&#39;

Uppslagsdatauppsättningar används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn. Se [det här användningsfallet](/help/use-cases/b2b.md) till exempel.

## Kundattribut är nu &#39;Profildatamängder&#39;

Profildatauppsättningar innehåller data som tillämpas på besökare, användare eller kunder i [!UICONTROL Event] data. Du kan till exempel överföra CRM-data om dina kunder. Du kan välja vilket person-ID du vill inkludera. Varje datauppsättning som definieras i [!DNL Experience Platform] har en egen uppsättning av ett eller flera definierade person-ID, t.ex. cookie-ID, Stitched ID, User ID, Tracking Code osv.

## Identiteter

CJA utvidgar begreppet identiteter utöver ECID:n till att omfatta alla ID:n du vill använda, inklusive Kund-ID, Kakcookie-ID, Stitched ID, Användar-ID, Spårningskod osv. Använda ett gemensamt namnområdes-ID för datauppsättningar, eller använda [Flerkanalsanalys](/help/connections/cca/overview.md) hjälper till att länka samman personer över olika datauppsättningar. Alla användare som skapar ett Workspace-projekt i CJA måste förstå de ID som används i datauppsättningarna.

Här är en video som visar hur du använder identiteter i Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Namnet på behållarna har ändrats

Du anger en behållare för [varje datavy du skapar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).

* **Träffbehållare är nu Event-behållare**. The [!UICONTROL Person] behållare innehåller alla sessioner och händelser för besökare inom den angivna tidsramen.
* **Besöksbehållare är nu &#39;Sessionsbehållare&#39;**. The [!UICONTROL Session] kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session.
* **Besöksbehållare är nu [!UICONTROL Person] behållare**. The [!UICONTROL Person] behållare innehåller alla sessioner och händelser för besökare inom den angivna tidsramen.

**Vad du behöver göra**:

Du kan byta namn på alla behållare efter behov.

## `Uniques Exceeded` begränsningar

[!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem!
