---
title: CJA User Guide for Adobe Analytics users
description: Vad man ska tänka på när man flyttar data från Adobe Analytics till Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13743c627ae0af608e63c39ca1f0b8c54f61bbe0
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 0%

---


# CJA User Guide for Adobe Analytics users

>[!NOTE]
>
>Den här sidan håller på att byggas.

Ditt företag börjar anställa Customer Journey Analytics. Som användare som är bekant med Adobe Analytics har du redan ett försprång. När du arbetar med Customer Journey Analytics kommer du att märka några stora skillnader och vissa likheter. Den här sidan syftar till att förklara de saker som inte har ändrats samt några av de stora skillnaderna. Vi kommer också att berätta för er hur ni kan få mer information om nya koncept och ytterligare steg för att göra kundresan enklare och mer framgångsrik.

## Vad som inte har ändrats

Mycket av det ni känner till på rapporteringssidan har inte förändrats.

* Du kan fortfarande använda [Analysis Workspace](/help/analysis-workspace/home.md) för att analysera era data. Arbetsytan fungerar på samma sätt som i traditionella Adobe Analytics.
* Du har också samma version av [Adobe Analytics dashboards](/help/mobile-app/home.md) till ditt förfogande. Kontrollpaneler (alias Dashboards) Mobile App) fungerar på samma sätt som i traditionella Adobe Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) har ett nytt gränssnitt och kan nu köras på PC, Mac och webbversionen av Excel.

När det gäller rapportering är skillnaden att ni har tillgång till betydligt fler flerkanalsdata att analysera. Här är ett exempel på några visualiseringar som inkluderar datakällor för flera kanaler:

![visualiseringar med flera kanaler](assets/cross-channel.png)

## Ny arkitektur

Customer Journey Analytics får sina data från Adobe Experience Platform. Med Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och kanaler och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser.

Kunddata på plattformen lagras som datauppsättningar, som består av ett schema och grupper med data. Mer information om plattformen finns på [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Din CJA-administratör har etablerat [anslutningar](/help/connections/create-connection.md) till datauppsättningar i Platform. De har sedan byggt [datavyer](/help/data-views/data-views.md) inom dessa anslutningar. Tänk på datavyer som liknar virtuella rapportsviter. Datavyer är grunden för rapportering i Customer Journey Analytics. Begreppet rapportsvit finns inte längre.

## Nya begrepp och terminologi

Flera funktioner i CJA har fått ett nytt namn och fått en ny arkitektur jämfört med traditionella Adobe Analytics för att passa in i branschens standarder. Vissa uppdaterade termer innehåller segment, virtuella rapportsviter, klassificeringar, kundattribut och behållarnamn. Välbekanta koncept som eVars och props finns inte längre, tillsammans med de begränsningar de hade.

## (Virtuella) rapportsviter är nu datavyer

[!UICONTROL Data views] ta begreppet virtuella rapportsviter som de finns idag och utvidga det till [aktivera ytterligare kontroller av data](/help/data-views/create-dataview.md) som är tillgängliga via anslutningar. Detta gör att tidszon- och timeout-intervall för sessioner kan konfigureras. Du kan också använda attribut- och förfalloegenskaper för enskilda dimensioner dynamiskt. Observera att dessa tillämpas retroaktivt på alla data.

**Vad du behöver göra**:

* Observera att du kan välja bland de datavyer som administratören har delat med dig i den rapportsvitsväljare som du är van vid i Workspace:

   ![data-view-selector](assets/data-views.png)

* Bekanta dig med de många [användningsexempel runt datavyer](/help/data-views/data-views-usecases.md).

## Inga fler eVars och props

[!UICONTROL eVars], [!UICONTROL props]och [!UICONTROL events] i traditionell Adobe Analytics-mening finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden. Din CJA-administratör har skapat datavyer

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


## Data för flera rapporter

Befintliga implementeringar från flera datauppsättningar kan kombineras i Experience Platform. De anslutningar och datavyer som baseras på dessa datauppsättningar kan kombinera data som tidigare fanns i separata rapportsviter.

**Vad du behöver göra**:

## Inställningar för session och variabel beständighet

[!UICONTROL Customer Journey Analytics] använder alla dessa inställningar vid rapporttillfället och dessa inställningar finns nu i [datavyer](/help/data-views/component-settings/persistence.md). Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer!

**Vad du behöver göra**:

## Klassificeringarna är nu &#39;Sök efter datauppsättningar&#39;



## Kundattribut är nu &#39;Profildatamängder&#39;


## Namnet på behållarna har ändrats

Du anger en behållare för [varje datavy du skapar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers).
* **Träffbehållare är nu Event-behållare**. The [!UICONTROL Person] behållare innehåller alla sessioner och händelser för besökare inom den angivna tidsramen.
* **Besöksbehållare är nu &#39;Sessionsbehållare&#39;**. The [!UICONTROL Session] kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session.
* **Besöksbehållare är nu [!UICONTROL Person] behållare**. The [!UICONTROL Person] behållare innehåller alla sessioner och händelser för besökare inom den angivna tidsramen.

**Vad du behöver göra**:

Du kan byta namn på alla behållare efter behov.


## `Uniques Exceeded` begränsningar

[!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem!
