---
keywords: Analysis Workspace
title: Översikt över Analysis Workspace
description: Läs om Analysis Workspace, det främsta analysverktyget för Adobe Analytics. Använd projekt, paneler, tabeller, visualiseringar och andra komponenter för att ge liv åt data och strukturera och dela med dig av analysen.
feature: Workspace Basics
exl-id: 9075518e-54fe-49a6-9601-aa9468187b8f
solution: Customer Journey Analytics
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1355'
ht-degree: 1%

---

# Översikt över Analysis Workspace {#analysis-workspace-overview}

Med Analysis Workspace kan ni snabbt skapa analyser för att samla in insikter och sedan dela dessa insikter med andra. Med dra-och-släpp-gränssnittet i webbläsaren kan du utforma din analys, lägga till visualiseringar för att ge liv åt data, strukturera en datauppsättning samt dela och schemalägga [projekt](/help/analysis-workspace/build-workspace-project/freeform-overview.md) med vem du vill.

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Översikt över arbetsytan Analys](https://video.tv.adobe.com/v/26266/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

{{videoaa}}

>[!ENDSHADEBOX]

## Gränssnitt

Följande bild och tabell beskriver huvudelementen i Analysis Workspace användargränssnitt:

![Analysis Workspace-fönstret markerar de olika avsnitten i gränssnittet](assets/analysis-workspace-overview.png)

| Plats | Namn och funktion |
|:---------:|----------|
| A | Innehåller namnet på projektet, en menystruktur för att få åtkomst till funktioner, en knapp ![Bakåt](/help/assets/icons/ChevronLeft.svg) för att återgå till projektlistan och en **[!UICONTROL Share]**-knapp för att [dela ditt Workspace-projekt](/help/analysis-workspace/curate-share/share-projects.md). <br/>Välj namnet på ditt projekt (till exempel: Nytt projekt) när som helst för att ändra namnet. <br/>Välj ![Till skillnad](/help/assets/icons/StarOutline.svg) om du vill markera ditt projekt som ett favoritprojekt ![till förmån](/help/assets/icons/Star.svg). |
| B | **Knapppanelen:** Innehåller knappar för att komma åt [funktioner](#features) i Analysis Workspace:<ul><li>![Webbsida](/help/assets/icons/WebPage.svg) [[!UICONTROL Panels]](/help/analysis-workspace/c-panels/panels.md)</li><li>![Guidad analys](/help/assets/icons/GuidedAnalysis.svg) [[!UICONTROL Guided Analysis]](/help/guided-analysis/overview.md)</li><li>![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) [[!UICONTROL Visualizations]](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</li><li>![Kuratera](/help/assets/icons/Curate.svg) [[!UICONTROL Components]](/help/components/overview.md)</li><li>![ViewList](/help/assets/icons/ViewList.svg) [[!UICONTROL Table of contents]](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)</li><li>![Bokmärke](/help/assets/icons/Bookmark.svg) [[!UICONTROL Data Dictionary]](/help/components/data-dictionary/data-dictionary-overview.md)</li></ul> |
| C | **Vänster panel:** Det här området innehåller enskilda paneler, visualiseringar, komponenter eller listor. Innehållet beror på vilken knapp som är markerad på knapppanelen. |
| D | **Arbetsyta:** Huvudområdet där du drar innehåll från den vänstra panelen för att skapa projektet. Projektet uppdateras dynamiskt när du lägger till paneler, lägger till visualiseringar i paneler och lägger till komponenter i visualiseringar. Du kan skapa flera paneler, och i varje panel kan du skapa flera visualiseringar.<br/>Varje panel baseras på en vald datavy. Den valda datavyn avgör vilka komponenter som är tillgängliga, som mått och mått. Mer information finns i [Paneler - Datavy](/help/analysis-workspace/c-panels/panels.md#data-view). |

## Funktioner

De viktigaste funktionerna i Analysis Workspace finns på knapppanelen:

| Ikon | Funktion | Beskrivning |
|:---:|---|---|
| ![Webbsida](/help/assets/icons/WebPage.svg) | **[!UICONTROL Panels]** | [Paneler](/help/analysis-workspace/c-panels/panels.md) används för att ordna din analys i ett projekt och kan innehålla många tabeller och visualiseringar. Många av panelerna i Analysis Workspace genererar en komplett uppsättning analyser baserade på några få indata från användarna. |
| ![Guidad analys](/help/assets/icons/GuidedAnalysis.svg) | **[!UICONTROL Guided Analysis]** | [Med guidad analys](../guided-analysis/overview.md) kan du självbetjäna data och insikter av hög kvalitet om kundresan via guidade arbetsflöden. Du kan skapa en analys som ska ingå i ditt Workspace-projekt eller inkludera en befintlig analys som du sparat tidigare. |
| ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | **[!UICONTROL Visualizations]** | [Visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md), t.ex. en stapel eller ett linjediagram, kan användas för att ge data liv. På den vänstra panelen väljer du den mittersta **[!UICONTROL Visualizations]**-ikonen för att visa en fullständig lista över tillgängliga visualiseringar. |
| ![Kurva](/help/assets/icons/Curate.svg) | **[!UICONTROL Components]** | [Komponenter](/help/components/overview.md) innehåller följande element:<ul><li>![Dimensioner](/help/assets/icons/Dimensions.svg) [Dimensioner](/help/components/dimensions/overview.md)</li><li>![Händelse](/help/assets/icons/Event.svg) [Mätvärden](/help/components/apply-create-metrics.md)</li><li>![Segmentering](/help/assets/icons/Segmentation.svg) [Segment](/help/components/segments/seg-overview.md)</li><li>![Kalender](/help/assets/icons/Calendar.svg) [Datumintervall](/help/components/date-ranges/overview.md)</li></ul> |
| ![VisaLista](/help/assets/icons/ViewList.svg) | **[!UICONTROL Table of contents]** | Innehållsförteckningen organiserar alla paneler och visualiseringar som ingår i projektet i en lista som kan komprimeras, så att du snabbt kan komma åt en viss panel eller visualisering. |
| ![Bokmärke](/help/assets/icons/Bookmark.svg) | **Dataordlista** | [Dataordlistan](/help/components/data-dictionary/data-dictionary-overview.md) hjälper både användare och administratörer att hålla reda på och förstå komponenterna i sin Analytics-miljö bättre. |


## Meny

De flesta funktionerna i Analysis Workspace finns via dra-och-släpp och via snabbmenyer i paneler, visualiseringar och komponenter.

Funktionaliteten finns även via Workspace-menyn och kortkommandon eller snabbtangenter. Kortkommandon varierar beroende på vilket operativsystem webbläsaren körs på. Se tabellerna nedan för en översikt.

Observera att följande symboler kan användas på tangentbordet:

- **⇧** för **[!UICONTROL *shift *]**.
- **⌘** för **[!UICONTROL *cmd *]**(kommando).
- **⌃** för **[!UICONTROL *ctrl *]**(kontroll).
- **⌥** för **[!UICONTROL *opt *]**(alternativ).
- **⎇** för **[!UICONTROL *alt *]**(alternativ).

I tabellerna nedan finns en översikt över de tillgängliga menyerna.

| **[!UICONTROL Project]** | Genväg till Mac | Kortkommando i Windows | Beskrivning |
|---|---|---|---|
| **[!UICONTROL Create project]** | **[!UICONTROL *shift+cmd+p *]** | **[!UICONTROL *shift+Ctrl+p *]** | Skapa ett nytt projekt. |
| **[!UICONTROL Create a mobile scorecard]** | | | [Skapa ett nytt mobilstyrkort](/help/mobile-app/create-scorecard.md). |
| **[!UICONTROL Open...]** | **[!UICONTROL *cmd+o *]** | **[!UICONTROL *Ctrl+o *]** | [Öppna ett befintligt projekt](/help/analysis-workspace/build-workspace-project/save-projects.md#open-another-project). |
| **[!UICONTROL Open previous version...]** | **[!UICONTROL *opt+cmd+o *]** | **[!UICONTROL *alt+Ctrl+o *]** | [Öppna tidigare versioner av ditt projekt](/help/analysis-workspace/build-workspace-project/save-projects.md#open-previous-version). |
| **[!UICONTROL Save]** | **[!UICONTROL *cmd+s *]** | **[!UICONTROL *Ctrl+s *]** | [Spara ditt projekt](/help/analysis-workspace/build-workspace-project/save-projects.md#save-projects). |
| **[!UICONTROL Save with notes...]** | **[!UICONTROL *opt+cmd+s *]** | **[!UICONTROL *alt+Ctrl+s *]** | [Lägg till anteckningar i projektversionen som du sparar](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Save as...]** | **[!UICONTROL *shift+cmd+s *]** | **[!UICONTROL *shift+Ctrl+s *]** | [Spara projektet med ett annat namn och med annan information](/help/analysis-workspace/build-workspace-project/save-projects.md#save-project-options). |
| **[!UICONTROL Refresh project]** | **[!UICONTROL *opt+r *]** | **[!UICONTROL *alt+r *]** | Uppdatera projektet. |
| **[!UICONTROL Download CSV]** | **[!UICONTROL *shift+cmd+v *]** | **[!UICONTROL *shift+Ctrl+v *]** | Hämta projektet som en CSV-fil. |
| **[!UICONTROL Download PDF]** | **[!UICONTROL *shift+cmd+b *]** | **[!UICONTROL *shift+Ctrl+b *]** | Hämta projektet som ett PDF-dokument. |
| **[!UICONTROL Project info & settings]** | | | Definiera inställningar för dina projekt, till exempel namn, taggar, färgpalett med mera. |
| **[!UICONTROL User settings]** | | | [Konfigurera inställningar för Analysis Workspace](/help/analysis-workspace/user-preferences.md). |


| **[!UICONTROL Edit]** | Genväg till Mac | Kortkommando i Windows | Beskrivning |
|---|---|---|---|
| **[!UICONTROL Undo]** | **[!UICONTROL *cmd+z *]** | **[!UICONTROL *Ctrl+z *]** | Ångra föregående åtgärd. |
| **[!UICONTROL Redo]** | **[!UICONTROL *cmd+shift+z *]** | **[!UICONTROL *Ctrl+Skift+z *]** | Gör om föregående åtgärd. |
| **[!UICONTROL Clear all]** | **[!UICONTROL *opt+w *]** | **[!UICONTROL *alt+w *]** | Rensa alla paneler i det aktuella projektet. |

| **[!UICONTROL Insert]** | Genväg till Mac | Kortkommando i Windows | Beskrivning |
|---|---|---|---|
| **[!UICONTROL Blank panel]** | **[!UICONTROL *opt+b *]** | **[!UICONTROL *alt+b *]** | Infoga en [tom panel](/help/analysis-workspace/c-panels/blank-panel.md). |
| **[!UICONTROL Media concurrent viewers]** | **[!UICONTROL *opt+h *]** | **[!UICONTROL *alt-h *]** | Infoga en [panel för parallella medievyer](/help/analysis-workspace/c-panels/media-concurrent-viewers.md). |
| **[!UICONTROL Media playback time spent]** | **[!UICONTROL *opt+i *]** | **[!UICONTROL *alt+i *]** | Infoga en [medieuppspelningstid som har använts på panelen ](/help/analysis-workspace/c-panels/media-playback-time-spent.md). |
| **[!UICONTROL Media average minute audience]** | **[!UICONTROL *opt+m *]** | **[!UICONTROL *alt+m *]** | Infoga en [medieminarium](/help/analysis-workspace/c-panels/average-minute-audience-panel.md)-målgruppspanel. |
| **[!UICONTROL Attribution]** | **[!UICONTROL *opt+e *]** | **[!UICONTROL *alt+e *]** | Infoga en [attribueringspanel](/help/analysis-workspace/c-panels/attribution.md). |
| **[!UICONTROL Freeform]** | **[!UICONTROL *opt+a *]** | **[!UICONTROL *alt+a *]** | Infoga en [friformspanel](/help/analysis-workspace/c-panels/freeform-panel.md). |
| **[!UICONTROL Quick insights]** | **[!UICONTROL *opt+j *]** | **[!UICONTROL *alt+j *]** | Infoga en [snabbinformationspanel](/help/analysis-workspace/c-panels/quickinsight.md). |
| **[!UICONTROL Experimentation]** | **[!UICONTROL *opt+x *]** | **[!UICONTROL *alt+x *]** | Infoga en [expertpanel](/help/analysis-workspace/c-panels/experimentation.md). |
| **[!UICONTROL Freeform table]** | **[!UICONTROL *opt+1 *]** | **[!UICONTROL *alt+1 *]** | Infoga en [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)-visualisering. |
| **[!UICONTROL Line]** | **[!UICONTROL *opt+2 *]** | **[!UICONTROL *alt+2 *]** | Infoga en [Line](/help/analysis-workspace/visualizations/line.md)-visualisering. |
| **[!UICONTROL Bar]** | **[!UICONTROL *opt+3 *]** | **[!UICONTROL *alt+3 *]** | Infoga en [Bar](/help/analysis-workspace/visualizations/bar.md)-visualisering. |
| **[!UICONTROL Combo]** | **[!UICONTROL *opt+4 *]** | **[!UICONTROL *alt+4 *]** | Infoga en [kombinationsvisualisering](/help/analysis-workspace/visualizations/combo-charts.md). |


| **[!UICONTROL Components]** | Genväg till Mac | Kortkommando i Windows | Beskrivning |
|---|---|---|---|
| **[!UICONTROL Create segment...]** | **[!UICONTROL *shift+cmd+e *]** | **[!UICONTROL *shift+Ctrl+e *]** | Skapa ett nytt [segment](/help/components/segments/seg-create.md). |
| **[!UICONTROL Create metric...]** | **[!UICONTROL *shift+cmd+c *]** | **[!UICONTROL *shift+Ctrl+c *]** | Skapa ett nytt [beräknat mått](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL Create date range...]** | **[!UICONTROL *shift+cmd+d *]** | **[!UICONTROL *shift+Ctrl+d *]** | Skapa ett nytt [datumintervall](/help/components/date-ranges/overview.md). |
| **[!UICONTROL Create annotation...]** | **[!UICONTROL *shift+cmd+o *]** | **[!UICONTROL *shift+Ctrl+o *]** | Skapa en ny [anteckning](/help/components/annotations/overview.md). |
| **[!UICONTROL Create audience...]** | **[!UICONTROL *shift+cmd+u *]** | **[!UICONTROL *shift+Ctrl+u *]** | Skapa en ny [målgrupp](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL Refresh components]** | **[!UICONTROL *opt+shift+r *]** | **[!UICONTROL *alt+shift+r *]** | Uppdatera komponenterna i projektet. |

| **[!UICONTROL Share]** | Genväg till Mac | Kortkommando i Windows | Beskrivning |
|---|---|---|---|
| **[!UICONTROL Share with Workspace users]** | **[!UICONTROL *cmd+h *]** | **[!UICONTROL *ctrl+h *]** | [Dela projektet med andra Workspace-användare](/help/analysis-workspace/curate-share/share-projects.md#share-with-customer-journey-analytics-users-and-groups-in-your-organization). |
| **[!UICONTROL Share with anyone]** | **[!UICONTROL *opt+l *]** | **[!UICONTROL *alt+l *]** | [Dela en skrivskyddad version av projektet med alla](/help/analysis-workspace/curate-share/share-projects.md#share-a-link-to-a-project). |
| **[!UICONTROL Send file]** | **[!UICONTROL opt+s]** | **[!UICONTROL *alt+s *]** | [Skicka projektet som en CSV- eller PDF-fil till andra mottagare](/help/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Schedule file export]** | **[!UICONTROL *shift+opt+s *]** | **[!UICONTROL *shift+alt+s *]** | [Skicka projektet enligt ett schema som en CSV- eller PDF-fil till andra mottagare](/help/analysis-workspace/curate-share/send-schedule-files.md). |
| **[!UICONTROL Curate project data]** | **[!UICONTROL *shift+cmd+g *]** | **[!UICONTROL *shift+Ctrl+g *]** | [Kuratera projektdata](/help/analysis-workspace/curate-share/curate.md). |

| Hjälp | Beskrivning |
|---|---|
| **[!UICONTROL Videos]** | Öppna Customer Journey Analytics YouTube-kanalen på en ny flik i webbläsaren. |
| **[!UICONTROL Help documentation]** | Öppna dokumentationen (du läser just nu ...) på en ny flik i webbläsaren. |
| **[!UICONTROL Help forum]** | Öppna Adobe Analytics Experience League Community-forumet på en ny flik i webbläsaren. |
| **[!UICONTROL Hotkeys]** | Visa en översikt över de snabbtangenter (kortkommandon) som du kan använda i Workspace. |
| **[!UICONTROL Enable debugger]** | Aktivera felsökaren. Projektet läses in igen. |
| **[!UICONTROL Disable debugger]** | Inaktivera felsökaren. Projektet läses in igen. |
| **[!UICONTROL Performance]** | Visa en dialogruta med mätvärden för **[!UICONTROL Analysis Workspace performance]**. Använd **[!UICONTROL Download as CSV]** för att hämta en CSV-fil med prestandamätningar. |
| **[!UICONTROL About Workspace]** | Visa en **[!UICONTROL About Analysis Workspace]**-dialogruta med versionsinformation, funktionsåtkomstnivåer och aktiva funktionsflaggor. |

## Datakällor

Du synkroniserar visualiseringar för att kontrollera vilken datatabell eller datakälla som motsvarar en visualisering. Mer information finns i [Hantera datakällor](/help/analysis-workspace/visualizations/t-sync-visualization.md).

## Använd Analysis Workspace


Så här börjar du använda Analysis Workspace:

1. Logga in på [Adobe Experience Cloud](https://experience.adobe.com).
1. Välj **[!UICONTROL Customer Journey Analytics]** i appväljaren ![App](/help/assets/icons/Apps.svg) längst upp till höger i gränssnittet.
1. Sidan **[!UICONTROL Projects]** i Analysis Workspace visas som standard. Om ett visst projekt har valts ut åt dig eller du arbetat med det nyligen, visas det projektet som standard.

### Skapa ett projekt

En analys i Analysis Workspace kallas [projekt](/help/analysis-workspace/build-workspace-project/freeform-overview.md).

Du kan skapa ett projekt i Analysis Workspace enligt beskrivningen i [Skapa projekt](/help/analysis-workspace/build-workspace-project/create-projects.md).

Projekt kan ordnas i mappar och undermappar enligt beskrivningen i [Mappar i Analysis Workspace](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md).

### Spara och dela ett projekt

När du skapar en analys i Analysis Workspace sparas ditt arbete [automatiskt](/help/analysis-workspace/build-workspace-project/save-projects.md).

När du är klar med projektet och samlar in åtgärdbara insikter kan andra vilja förbruka projektet. Du kan dela projektet med användare och grupper i organisationen, eller till och med med med personer utanför organisationen. Mer information om hur du delar ett projekt finns i [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md).

## Ytterligare resurser {#resources}

- Sidan [Learning landing](/help/getting-started/landing.md#learning) i Customer Journey Analytics. Den här sidan är ett bra sätt att lära känna Analysis Workspace. Speciellt om Workspace Basic. I den här mallen beskrivs vanliga termer och steg för hur du skapar din första analys i Workspace
- Adobe erbjuder hundratals [självstudiekurser i Analytics-videor](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/overview).
- Information om nya funktioner finns i [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/release-notes/experience-cloud/current).

