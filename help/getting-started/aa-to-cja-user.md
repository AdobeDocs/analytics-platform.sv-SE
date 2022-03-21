---
title: CJA User Guide for Adobe Analytics users
description: Vad man ska tänka på när man flyttar data från Adobe Analytics till Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: d31f07d8b26ea4d60481c040a0ca1ba491d4ecf0
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 0%

---


# CJA User Guide for Adobe Analytics users

>[!NOTE]
>
>Den här sidan håller på att byggas.

Grattis, ditt företag börjar arbeta med Customer Journey Analytics! Som användare som är bekant med Adobe Analytics har du redan ett försprång. När du arbetar med Customer Journey Analytics kommer du att märka några stora skillnader och vissa likheter. Den här sidan syftar till att förklara de saker som inte har ändrats samt några av de stora skillnaderna. Vi kommer också att berätta för er hur ni kan få mer information om nya koncept och ytterligare steg för att göra kundresan enklare och mer framgångsrik.

## Vad som inte har ändrats

Mycket av det ni känner till på rapporteringssidan har inte förändrats. Du kan fortfarande använda kraften i Analysis Workspace för att analysera dina data. Du har också tillgång till samma version av Adobe Analytics-kontrollpaneler. Arbetsytan och kontrollpanelerna fungerar i stort sett på samma sätt som i traditionella Adobe Analytics. Report Builder har ett nytt gränssnitt och kan nu köras på datorer, Mac-datorer och webbversionen av Excel. Medvetet om att ni har tillgång till betydligt fler flerkanalsdata som ni kan analysera är skillnaden. Här är ett exempel på några visualiseringar i flera kanaler:

![flerkanaligt](assets/cross-channel.png)

## Ny arkitektur

Customer Journey Analytics får sina data från Adobe Experience Platform. Med Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och kanaler och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser.

Kunddata på plattformen lagras som datauppsättningar, som består av ett schema och grupper med data. Mer information om plattformen finns på [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Din CJA-administratör har etablerat [anslutningar](/help/connections/create-connection.md) till datauppsättningar i Platform. De har sedan byggt [datavyer](/help/data-views/data-views.md) inom dessa anslutningar. Tänk på datavyer som liknar virtuella rapportsviter. Datavyer är grunden för rapportering i Customer Journey Analytics.

## Nya begrepp och terminologi

Flera funktioner i CJA har fått ett nytt namn och fått en ny arkitektur jämfört med traditionella Adobe Analytics för att passa in i branschens standarder. Vissa uppdaterade termer innehåller segment, virtuella rapportsviter, klassificeringar, kundattribut och behållarnamn. Välbekanta koncept som eVars och props finns inte längre, tillsammans med de begränsningar de hade.

### eVars och props

[!UICONTROL eVars], [!UICONTROL props]och [!UICONTROL events] i traditionell Adobe Analytics-mening finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden.

### Segmenten är nu &#39;Filter&#39;

[!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inget av de befintliga segmenten är kompatibelt med [!UICONTROL Customer Journey Analytics]. Dessutom har namnet&quot;segment&quot; ändrats till&quot;filter&quot;.

Du kan för närvarande inte dela/publicera [!UICONTROL filters] ([!UICONTROL segments]) från [!DNL Customer Journey Analytics] till Experience Platform Unified Profile eller andra program i Experience Cloud. Den här funktionen håller på att utvecklas.

### Beräknade värden

[!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inga befintliga beräknade värden är kompatibla med [!UICONTROL Customer Journey Analytics].

### Inställningar för session och variabel beständighet

[!UICONTROL Customer Journey Analytics] använder alla dessa inställningar vid rapporttillfället och dessa inställningar finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer!

### Virtuella rapportsviter är nu datavyer



### Klassificeringarna är nu &#39;Sök efter datauppsättningar&#39;

### Kundattribut är nu &#39;Profildatamängder&#39;


### Träffbehållare är nu Event-behållare

### Besöksbehållare är nu &#39;Sessionsbehållare&#39;

### Besöksbehållare är nu &#39;Person&#39;-behållare

### `Uniques Exceeded` begränsningar

[!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem!
