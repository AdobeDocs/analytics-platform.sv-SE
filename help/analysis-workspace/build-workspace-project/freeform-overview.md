---
description: Översikt över arbetsyteprojekt med menyrad och inställningar
keywords: Analysis Workspace
title: Översikt över projekt
feature: CJA Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 2%

---

# Översikt över projekt

Med arbetsyteprojekt kan du kombinera datakomponenter, tabeller och visualiseringar för att skapa analyser och dela dem med vem som helst i organisationen. Innan du startar ditt första projekt bör du lära dig hur du får tillgång till, navigerar och hanterar dina projekt.

## Projektlista {#project-list}

När du först besöker **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** visas alla projekt som du äger eller har delat med dig. Detta är också landningssidan för Adobe Analytics, såvida du inte tidigare har angett en anpassad landningssida.

![](assets/sample-project.png)

Sidan med projektlistan för arbetsytan innehåller följande information:

| Element | Beskrivning |
|---|---|
| [Skapa nytt projekt](/help/analysis-workspace/home.md) | Klicka på den här länken om du vill starta ett nytt projekt från grunden. |
| Hantera projekt | Om du klickar på den här länken kommer du till komponenthanteraren för projekt ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), som visar alla dina projekt i en lista och där du kan tagga, dela, ta bort, byta namn på, godkänna, kopiera och exportera projekt till CSV. |
| Ange som landningssida | Omvandlar den här sidan till startsidan för arbetsytan. |
| [Visa Tutorials](/help/analysis-workspace/home.md) | Här finns Analysis Workspace videokurser. |
| Namn | Namn på Workspace-projektet. |
| Ägare | Den person som skapade det här projektet (antingen du eller någon som delade projektet med dig). |
| Typ | Anger om det här är ett arbetsyteprojekt eller ett [Mobile Scorecard](/help/mobile-app/home.md). |
| [Projektroll](/help/analysis-workspace/curate-share/share-projects.md) | Anger din roll för projektet - ägare, redigera, duplicera, visa. |
| Taggar | Taggar som tillämpades på projektet. |
| Senast ändrad | Datum och tid när projektet senast ändrades. |
| Mina favoritprojekt | Om du vill markera ett projekt som favorit öppnar du projektet och klickar på stjärnan bredvid namnet. Den visas i den här listan nästa gång du öppnar Arbetsyta. |
| Projekt som visas ofta | Listar alla projekt som du öppnar ofta, så att de blir lätta att komma åt. |

## Menyrad {#menu-bar}

I ett projekt innehåller menyn alternativ för att hantera ditt projekt, lägga till komponenter, söka efter hjälp och mycket mer. Alla menyalternativ kan också nås via tangentbordet [genvägar](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![](assets/menu.png)

| Menyalternativ | Beskrivning |
|---|---|
| Projekt | Innehåller vanliga åtgärder för projekthantering, bland annat Ny, Öppna, Spara, Spara som och Spara som. Du kan även uppdatera hela projektet för att hämta de senaste data och definitionerna genom att klicka på Uppdatera projekt. [Hämta CSV och PDF](/help/analysis-workspace/curate-share/download-send.md) kan du exportera data från arbetsytan. **Projektinformation och inställningar** (se nedan) erbjuder många alternativ för att hantera ditt projekt. |
| Redigera | Ångra eller gör om den senaste åtgärden. Rensa alla återställer projektet till en tom startpunkt. |
| Infoga | Infoga nya paneler eller visualiseringar från den här menyn. Du kan även infoga nya paneler och visualiseringar från den vänstra listen. |
| [Komponenter](/help/components/overview.md) | Skapa nya filter, beräknade värden, datumintervall eller aviseringskomponenter från projektet. Du kan också skapa nya komponenter från den vänstra listen. Om komponentdefinitionerna nyligen har ändrats hämtas de senaste definitionerna av Uppdatera komponenter. |
| [Dela](/help/analysis-workspace/curate-share/send-schedule-files.md) | Kuratera, dela och schemalägg PDF/CSV-projekt till mottagare i organisationen. |
| Hjälp om  | Få tillgång till hjälpdokumentation, videor och analyser [Experience League community](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Hantera synligheten för arbetsytetips och [debugger](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md). Hitta information om arbetsytan och faktorer som påverkar projektet [prestanda](/help/analysis-workspace/workspace-faq/optimizing-performance.md). |
| Dela-knapp eller ägare | Om du är i en egen eller Redigera för projektet ger knappen Dela i det övre högra hörnet tillgång till ett klick för att hantera projektmottagarna. Om du har en dubblett- eller vyroll för projektet visas projektägarens namn. |

### Projektinformation och inställningar {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]** innehåller information på projektnivå om det aktiva projektet.

![](assets/projectinfo.png)

Inställningarna inkluderar:

| Inställning | Beskrivning |
|---|---|
| Projektnamn | Namnet på projektet. Du kan dubbelklicka på namnet för att redigera det. |
| Skapad av | Projektägarnamn |
| Senast ändrad | Datum för senaste ändring av projektet. |
| Taggar | Visar alla taggar som har använts i ett projekt för enklare kategorisering. |
| Beskrivning | En beskrivning är användbar för att förtydliga syftet med ett projekt. Du kan dubbelklicka på beskrivningen för att redigera den. |
| Räkna upprepade instanser i projekt | Anger om upprepade instanser räknas i rapporter. Obs! den här inställningen gäller inte för visualiseringar av flöde och utfall. |
| [Projektets färgpalett](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Du kan ändra den kategoriserade färgpaletten som används i Workspace genom att välja bland färdiga paletter som har optimerats för färgblindhet, eller genom att ange en anpassad palett. Den här funktionen påverkar många saker i Workspace, bland annat de flesta visualiseringar. |
| [Visa densitet](/help/analysis-workspace/build-workspace-project/view-density.md) | Gör att du kan se mer data på skärmen genom att minska den lodräta utfyllnaden av den vänstra listen, frihandstabeller och kohorttabeller. |

## Vänster räl {#left-rail}

Inom ett projekt [paneler](/help/analysis-workspace/c-panels/panels.md), tabeller, [visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)och [komponenter] är åtkomliga från den vänstra listen. Detta är era projektbyggstenar.

Du kan även komma åt visualiseringar och paneler via [Tom panel](/help/analysis-workspace/c-panels/blank-panel.md) också.

Komponenter (Dimensioner, Metrisk, Filter, Datumintervall) i den vänstra listen relaterar till den aktiva panelens datavy. Den aktiva panelen kommer att ha en blå ram runt sig och den aktiva datavyn kommer att visas högst upp i komponentspåret.

![](assets/left-rail.png)

## Projektarbetsyta {#canvas}

Projektarbetsytan är där du sammanför paneler, tabeller, visualiseringar och komponenter för att bygga din analys. Ett projekt kan innehålla många paneler, och varje panel kan innehålla många tabeller och visualiseringar.

Paneler är användbara när du vill ordna dina projekt efter tidsperioder, datavyer eller användningsfall för analyser. Den aktiva panelen har en blå ram runt sig och avgör vilka komponenter som är tillgängliga i den vänstra listen.

Beroende på vilken startpunkt du väljer för dina projekt har du antingen en [frihandsritbord](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) eller en [tom panel](/help/analysis-workspace/c-panels/blank-panel.md) på arbetsytan till att börja med. Det snabbaste sättet att börja analysera är att markera en eller flera komponenter och helt enkelt dra och släppa dem på arbetsytan i projektet. En datatabell återges automatiskt åt dig. [Läs mer](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) om de olika alternativen för att skapa en tabell eller utnyttja [självstudiekurs](/help/analysis-workspace/home.md) för mer vägledning om hur du skapar ditt första projekt.

![](assets/canvas.png)

## Projektledare {#manager}

Analysis Workspace-projekt kan hanteras under **Analytics > Components > Projects**. Projekthanteraren visar de objekt som en viss användare har skapat. Projektägarskap kan överföras till en ny användare under Admin > Analytics Users &amp; Assets > Transfer Assets.

I Projects Manager kan du lägga till, tagga, dela, duplicera/kopiera och mycket mer. Sök efter ett projekt i sökfältet eller med filteralternativen i den vänstra listen. Du kan filtrera efter tagg, ägare, projekttyp med mera.

![](assets/project-manager.png)

Följande är vanliga åtgärder i Projects Manager och kan utföras på ett eller flera projekt samtidigt:

| Åtgärd | Beskrivning |
|---|---|
| Lägg till | Skapa ett nytt projekt från grunden. |
| Tagga eller godkänn | Välj &quot;Tagga&quot; eller &quot;Godkänn&quot; för att ordna dina projekt och göra dem enklare att söka efter. |
| [Dela](/help/analysis-workspace/curate-share/share-projects.md) | Gör ett projekt tillgängligt för andra Analysis Workspace-användare i organisationen. |
| Ta bort | Ta bort projektet. |
| Byt namn | Redigera namnet på projektet. |
| Kopiera | Skapa en kopia av projektet. Detta skapar ett nytt projekt- och projekt-ID. Alla aktier eller tidsplaner som är knutna till det ursprungliga projektet kopieras inte. |
| Exportera till CSV | Ladda ned projektet som en CSV-fil som innehåller oformaterad text. |
