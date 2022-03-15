---
title: CJA User Guide for Adobe Analytics users
description: Vad man ska tänka på när man flyttar data från Adobe Analytics till Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: eeb56599c81dd9cd20bf91c864aa57a783ef13fd
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 0%

---


# CJA User Guide for Adobe Analytics users

Grattis! Ditt företag har flyttat åtminstone en del av sina data till Customer Journey Analytics! När du börjar arbeta med Customer Journey Analytics kommer du att märka några stora skillnader och vissa likheter. Den här sidan syftar till att förklara de saker som inte har ändrats samt några av de stora skillnaderna.

Vi kommer också att berätta för er hur ni kan få mer information om nya koncept och ytterligare steg för att göra kundresan enklare och mer framgångsrik.

## Vad som inte har ändrats

Mycket av det ni känner till på rapporteringssidan har inte förändrats. Du kan fortfarande använda kraften i Analysis Workspace för att analysera dina data, plus Adobe Analytics dashboards och en ny version av Report Builder. Arbetsytan och kontrollpanelerna fungerar i stort sett på samma sätt som i traditionella Adobe Analytics. Report Builder har ett nytt gränssnitt och kan nu köras på datorer, Mac-datorer och webbversionen av Excel. Medvetet om att ni har tillgång till betydligt fler flerkanalsdata som ni kan analysera är skillnaden. Här är ett exempel på en arbetsyta

## Ny arkitektur

Arkitekturellt får Customer Journey Analytics data från Adobe Experience Platform. Med Experience Platform kan ni centralisera och standardisera kunddata och innehåll från alla system och kanaler och använda datavetenskap och maskininlärning för att förbättra utformningen och leveransen av personaliserade upplevelser.

Kunddata på plattformen lagras som datauppsättningar, som består av ett schema och grupper med data. Mer information om plattformen finns på [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

CJA-administratören upprättar anslutningar till data i plattformen och skapar datavyer inom dessa anslutningar. Tänk på datavyer som liknar virtuella rapportsviter. Datavyer är grunden för rapportering i Customer Journey Analytics.

## Nya begrepp och terminologi

Flera funktioner i CJA har fått ett nytt namn och fått en ny arkitektur jämfört med traditionella Adobe Analytics för att passa in i branschens standarder. Vissa uppdaterade termer innehåller segment, virtuella rapportsviter, klassificeringar, kundattribut och behållarnamn. Välbekanta koncept som eVars och props finns inte längre, tillsammans med de begränsningar de hade.

### Segmenten är nu &#39;Filter&#39;


### Virtuella rapportsviter är nu datavyer


### Klassificeringarna är nu &#39;Sök efter datauppsättningar&#39;

### Kundattribut är nu &#39;Profildatamängder&#39;


### Träffbehållare är nu Event-behållare

### Besöksbehållare är nu &#39;Sessionsbehållare&#39;

### Besöksbehållare är nu &#39;Person&#39;-behållare

## Frågor och svar om Adobe Analytics-komponenter

| Fråga | Svar |
| --- | --- |
| Kan jag dela/publicera [!UICONTROL filters] ([!UICONTROL segments]) från [!DNL Customer Journey Analytics] till Experience Platform Unified Profile eller andra program från Experience Cloud? | Inte ännu, men vi arbetar aktivt för att leverera den här funktionen. |
| Vad hände med min gamla [!UICONTROL eVar] inställning? | [!UICONTROL eVars], [!UICONTROL props]och [!UICONTROL events] i traditionell Adobe Analytics-mening finns inte längre i [!UICONTROL Customer Journey Analytics]. Du har ett obegränsat antal schemaelement (mått, mått, listfält). Alla attribueringsinställningar som du använde under datainsamlingsprocessen tillämpas nu vid frågetiden. |
| Var finns alla inställningar för session och variabel beständighet nu? | [!UICONTROL Customer Journey Analytics] använder alla dessa inställningar vid rapporttillfället och dessa inställningar finns nu i datavyer. Ändringarna av de här inställningarna är nu retroaktiva och du kan ha flera versioner genom att använda flera datavyer! |
| Vad händer med våra befintliga segment/beräknade värden? | [!UICONTROL Customer Journey Analytics] använder inte längre eVars, props eller händelser och använder i stället ett AEP-schema. Detta innebär att inget av de befintliga segmenten eller beräkningstalen är kompatibelt med [!UICONTROL Customer Journey Analytics]. |
| Hur [!UICONTROL Customer Journey Analytics] handtag `Uniques Exceeded` begränsningar? | [!UICONTROL Customer Journey Analytics] har inga unika värdebegränsningar, så du behöver inte bekymra dig om dem! |
| Om jag är en befintlig [!DNL Data Workbench] kund, kan jag gå över till [!UICONTROL Customer Journey Analytics] just nu? | Det beror på ditt användningssätt - samarbeta med ditt Adobe-kontoteam. Dina nuvarande användningsexempel kanske redan passar Customer Journey Analytics! |
