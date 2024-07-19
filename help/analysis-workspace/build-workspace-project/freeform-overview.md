---
description: Översikt över Workspace-projekt med menyrad och inställningar
keywords: Analysis Workspace
title: Projektöversikt
feature: Workspace Basics
exl-id: 2eeb615c-57a1-4469-8d4a-8a61956bd6e6
role: User
source-git-commit: 10751991e3c40cfefac7d32cea0b5cc557133232
workflow-type: tm+mt
source-wordcount: '1335'
ht-degree: 1%

---

# Projektöversikt

Med Workspace-projekt kan ni kombinera datakomponenter, tabeller och visualiseringar för att skapa analyser och dela dem med vem som helst i organisationen. Innan du startar ditt första projekt bör du lära dig hur du får tillgång till, navigerar och hanterar dina projekt.

## Projektlista {#project-list}

När du först går till **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** visas alla projekt du äger eller projekt som delas med dig på sidan. Detta är också landningssidan för Adobe Analytics, såvida du inte tidigare har angett en anpassad landningssida.

![Projektstartsida som visar projektlistan.](assets/sample-project.png)

Sidan Projekt innehåller följande information:

>[!NOTE]
>
>Vissa kolumner visas inte som standard. Klicka på ikonen **Anpassa tabell** ![Anpassa tabell](assets/projects-page-customize-columns-icon.png) om du vill anpassa de kolumner som visas.

| Element | Beskrivning |
|---|---|
| [Redigera inställningar](/help/analysis-workspace/user-preferences.md) | Hantera inställningar för Analysis Workspace och dess tillhörande komponenter för alla nya projekt eller paneler som du skapar. |
| [Skapa mapp](/help/analysis-workspace/build-workspace-project/workspace-folders/create-folders.md) | Lägg till en ny mapp eller undermapp i listan över projekt och mappar. |
| [Skapa projekt](/help/analysis-workspace/build-workspace-project/create-projects.md) | Starta ett nytt projekt från grunden. |
| Visa mer | Visar alternativ för att skapa ett tomt projekt eller ett mobilstyrkort, [visa självstudier](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html) eller [visa versionsinformation](/help/release-notes/latest.md). |
| Visa mappar och projekt | Välj om du vill visa mappstrukturen för projekt. Mer information finns i [Om mappar i Analytics](/help/analysis-workspace/build-workspace-project/workspace-folders/about-folders.md). |
| Anpassa tabell (ikon) | Här kan du anpassa informationen som visas för varje projekt på sidan Projekt. |
| Namn | Namn på Workspace-projektet. |
| Typ | Anger om det här är ett Workspace-projekt, en mapp eller ett [Mobile Scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/home.html). |
| Taggar | Taggar som tillämpades på projektet. |
| Schemalagd | Anger om projekt har schemalagts att skickas med e-post till mottagare enligt ett schema. Se [Skicka projektdata till andra](/help/analysis-workspace/export/t-schedule-report.md). |
| Delad länk (alla) | Projekt kan delas med alla - även med personer som inte har tillgång till Analysis Workspace. I den här kolumnen visas om projekt har delats på det här sättet. Mer information finns i [Dela ett projekt med vem som helst (ingen inloggning krävs)](/help/analysis-workspace/curate-share/share-projects.md#share-public-link) i [Dela projekt](/help/analysis-workspace/curate-share/share-projects.md). |
| Datavy | Datavyn som projektet är associerat med. |
| [Projektroll](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Anger din roll för projektet - ägare, redigera, duplicera, visa. |
| Ägare | Den person som skapade det här projektet (antingen du eller någon som delade projektet med dig). |
| Delas med | Användare som projektet har delats med. |
| Senast ändrad | Datum och tid när projektet senast ändrades. |
| Senast öppnad | Datum och tid när projektet senast öppnades. |
| Projekt-ID | ID för projektet. |
| Senaste datumintervall | Det längsta datumintervallet för projektet. |
| Antal frågor | Det totala antalet frågor i projektet. |
| Plats | Mappen där projektet finns. |

## Menyrad {#menu-bar}

I ett projekt innehåller menyn alternativ för att hantera ditt projekt, lägga till komponenter, söka efter hjälp och mycket mer. Du kan även komma åt alla menyalternativ via [kortkommandon](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

![Nya projektalternativ, bland annat alternativen Projekt, Redigera, Infoga, Komponenter, Dela och Hjälp.](assets/menu.png)

| Menyalternativ | Beskrivning |
|---|---|
| Projekt | Innehåller vanliga åtgärder för projekthantering, inklusive Nytt, Öppna, Spara och Spara som. Du kan även uppdatera hela projektet för att hämta de senaste data och definitionerna genom att klicka på Uppdatera projekt. Med alternativen för [Hämta projektdata](/help/analysis-workspace/export/download-send.md) kan du exportera data från Workspace. **Projektinformation och inställningar** (se nedan) innehåller många alternativ för att hantera ditt projekt. |
| Redigera | Ångra eller gör om den senaste åtgärden. Rensa alla återställer projektet till en tom startpunkt. |
| Infoga | Infoga nya paneler eller visualiseringar från den här menyn. Du kan även infoga nya paneler och visualiseringar från den vänstra listen. |
| [Komponenter](/help/components/overview.md) | Skapa nya filter, beräknade värden, datumintervall eller aviseringskomponenter från projektet. Du kan också skapa nya komponenter från den vänstra listen. Om komponentdefinitionerna nyligen har ändrats hämtas de senaste definitionerna av Uppdatera komponenter. |
| [Dela](/help/analysis-workspace/curate-share/send-schedule-files.md) | Kuratera, dela och schemalägg PDF/CSV-projekt till mottagare i organisationen. |
| Hjälp | Få tillgång till hjälpdokumentation, videoklipp och Analytics [Experience League-communityn](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community). Hantera synligheten för Workspace-tips och [felsökaren](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/reporting-tricks.md). Hitta information om Workspace och faktorer som påverkar projektet [prestanda](/help/technotes/optimizing-performance.md). |
| Dela-knapp eller ägare | Om du arbetar i en egen eller Redigera för projektet ger knappen Dela i det övre högra hörnet tillgång till ett klick för att hantera projektmottagarna. Om du har en dubblett- eller vyroll för projektet visas projektägarens namn. |

### Projektinformation och inställningar {#info-settings}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** innehåller information på projektnivå om det aktuella projektet.

![Fönstret Projektinformation och inställningar.](assets/projectinfo.png)

Inställningarna inkluderar:

| Inställning | Beskrivning |
|---|---|
| Projektnamn | Namnet på projektet. Du kan dubbelklicka på namnet för att redigera det. |
| Skapad av | Projektägarnamn |
| Senast ändrad | Datum för senaste ändring av projektet. |
| Taggar | Visar alla taggar som har använts i ett projekt för enklare kategorisering. |
| Beskrivning | En beskrivning är användbar för att förtydliga syftet med ett projekt. Du kan dubbelklicka på beskrivningen för att redigera den. |
| Räkna upprepande instanser i projekt | Anger om upprepade instanser räknas i rapporter. Obs! Den här inställningen gäller inte för visualiseringar av flöde och utfall. |
| [Projektfärgpalett](/help/analysis-workspace/build-workspace-project/color-palettes.md) | Du kan ändra den kategoriska färgpalett som används i Workspace genom att välja bland färdiga paletter som har optimerats för färgblindhet, eller genom att ange en anpassad palett. Den här funktionen påverkar många saker i Workspace, bland annat de flesta visualiseringar. |
| [Visa densitet](/help/analysis-workspace/build-workspace-project/view-density.md) | Gör att du kan se mer data på skärmen genom att minska den lodräta utfyllnaden av den vänstra listen, frihandstabeller och kohorttabeller. |

## Vänster räl {#left-rail}

I ett projekt finns det olika ikoner i den vänstra listen som representerar viktiga delar av ett projekt:

* [Paneler](/help/analysis-workspace/c-panels/panels.md) ![panelikon](assets/panels-icon.png)

* [Visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)![visualiseringsikon](assets/visualizations-icon.png)

* [Komponenter](/help/components/overview.md)![komponentikon](assets/components-icon.png)

* [Dataordlista](/help/components/data-dictionary/data-dictionary-overview.md)![ikon för dataordlista](assets/data-dictionary-icon.png)

* [Innehållsförteckning](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md) ![verktygsikon](assets/toc-icon.png)

Komponenter (Dimensioner, Metrisk, Filter, Datumintervall) i den vänstra listen relaterar till den aktiva panelens datavy. Den aktiva panelen identifieras av den blå kant som omger den och den aktiva datavyn visas högst upp i komponentspåret.

![Komponenterna som är relaterade till den aktiva paneldatavyn för datavyn för branschövergripande demodata.](assets/left-rail.png)

## Projektarbetsyta {#canvas}

Projektarbetsytan är där du sammanför paneler, tabeller, visualiseringar och komponenter för att bygga din analys. Ett projekt kan innehålla många paneler, och varje panel kan innehålla många tabeller och visualiseringar.

Paneler är användbara när du vill ordna dina projekt efter tidsperioder, datavyer eller användningsfall för analyser. Den aktiva panelen har en blå ram runt sig och avgör vilka komponenter som är tillgängliga i den vänstra listen.

Beroende på vilken startpunkt du väljer för dina projekt har du antingen en [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) eller en [tom panel](/help/analysis-workspace/c-panels/blank-panel.md) på arbetsytan som du vill börja med. Det snabbaste sättet att börja analysera är att markera en eller flera komponenter och helt enkelt dra och släppa dem på arbetsytan i projektet. En datatabell återges automatiskt åt dig. [Lär dig mer](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) om de olika alternativen för att skapa en tabell eller använd vår [självstudiekurs](/help/analysis-workspace/home.md) för mer information om hur du skapar ditt första projekt.

![En friformstabell för projektet.](assets/canvas.png)

## Projektledare {#manager}

Analysis Workspace-projekt kan hanteras under **Analys > Komponenter > Projekt**. Projekthanteraren visar de objekt som en viss användare har skapat. Du kan överföra projektägarskap till en ny användare under Admin > Analytics Users &amp; Assets > Transfer Assets.

I Projects Manager kan du lägga till, tagga, dela, duplicera/kopiera och mycket mer. Sök efter ett projekt i sökfältet eller med filteralternativen i den vänstra listen. Du kan filtrera efter tagg, ägare, projekttyp med mera.

![Sökfält för taggar i projektledaren och sökfält för titel.](assets/project-manager.png)

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
