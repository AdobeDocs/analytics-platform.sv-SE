---
description: 'null'
keywords: Analysis Workspace
title: Skapa projekt – översikt
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 8%

---


# Skapa projekt – översikt

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

Du kan skapa ett robust Analytics-projekt baserat på valfri kombination av visualiseringar, rapportkomponenter och datatabeller. Här finns många tabellverktyg från Ad Hoc Analysis i Analytics.

I Analysis Workspace kan du jämföra och dela upp data på sätt som inte tidigare varit möjligt. Du kan till exempel konfigurera rankade rapporter och göra omedelbara iterativa ändringar i datafrågan, och sedan få tillgång till och ändra värdena på rapportnivå.

Frågan skickas direkt till rapportmotorn - du kan göra ändringar direkt utan att ta fram andra rapporter för att skapa en analys. Resultaten returneras omedelbart utan att webbläsaren har uppdaterats.

## Sida för projektlista för arbetsyta {#section_39AA007D7C384F4E869F842F1C7B11F8}

När du först går till **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** visas alla projekt som du äger eller har fått åtkomst till på sidan. Du kan ange den här sidan som din Adobe Analytics-landningssida genom att klicka på **[!UICONTROL Set as Landing Page]**. (Om du inte ser det här alternativet, som i skärmbilden nedan, är det redan din landningssida.)

![](assets/sample-project.png)

Sidan med projektlistan för arbetsytan innehåller följande information:

| Element | Beskrivning |
|---|---|
| Projektmallar [](/help/analysis-workspace/build-workspace-project/starter-projects.md) | Du kan använda de här förifyllda projektmallarna som de är eller anpassa dem efter dina behov (genom att till exempel lägga till eller ersätta mått eller visualiseringar) och spara dem under ett nytt namn. |
| [Skapa nytt projekt](/help/analysis-workspace/home.md) | Klicka på den här länken om du vill starta ett nytt projekt från grunden. |
| Hantera projekt | Om du klickar på den här länken kommer du till komponenthanteraren för projekt ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), som visar alla dina projekt och du kan tagga, dela, ta bort, byta namn på, godkänna, kopiera och exportera projekt till CSV. |
| Visa självstudiekurser | Tar dig till [YouTube-videor](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)i Analysis Workspace. |
| Namn | Namn på Workspace-projektet. |
| Skapad av | Den person som skapade det här projektet (antingen du eller någon som delade projektet med dig). |
| Taggar | Taggar som tillämpades på projektet, antingen i komponenthanteraren för projekt eller under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| Senast ändrad | Datum och tid när projektet senast ändrades. |

## Projektinformation och inställningar {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** innehåller information på projektnivå om det aktiva projektet.

| Inställning | Beskrivning |
|---|---|
| Projektnamn | Namnet på projektet. Du kan dubbelklicka på namnet för att redigera det. |
| Skapad av | Projektägarnamn |
| Senast ändrad | Datum för senaste ändring av projektet. |
| Taggar | Visar alla taggar som har använts i ett projekt för enklare kategorisering. Du kan också tagga projekt medan du sparar dem. Visa ett projekts taggar på startsidan för arbetsytan i [!UICONTROL Tags] kolumnen. |
| Beskrivning | En beskrivning är användbar för att förtydliga syftet med ett projekt. Du kan dubbelklicka på beskrivningen för att redigera den. |
| Räkna upprepade instanser i projekt | Anger om upprepade instanser räknas i rapporter. Om du har flera sekventiella värden för samma variabel kan du räkna dem som en eller som flera förekomster av variabeln. |
| Visualiseringsfärgschema | Du kan ändra färgschemat som används i Arbetsyta genom att välja från en annan färgpalett eller genom att ange en egen palett. Den här funktionen påverkar många saker i Workspace, bland annat de flesta visualiseringar. |
| Visa densitet | Gör att du kan se mer data på skärmen genom att minska den lodräta utfyllnaden av den vänstra listen, frihandstabeller och kohorttabeller. |

## Projekt-menyn {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

Den översta projektmenyn ser ut så här:

![](assets/new-project-menus.png)

Undermenyerna innehåller följande alternativ.

>[!NOTE]
>
>Alternativ markerade med en asterisk (*) visas bara med **sparade** projekt.

| Projekt | Redigera | Infoga | Komponenter | Dela | Hjälp |
|---|---|---|---|---|---|
| Nytt | Ångra | Ny panel | Nytt segment | Dela projekt | Videor |
| Öppna | Rensa | Ny friformspanel | Nytt mått | Hämta projektlänk* | Snabbtangenter |
| Spara | Rensa alla | Ny jämförelsepanel för segment | Nytt datumintervall | Skicka fil nu* | Hjälpforum |
| Spara som* |  | Ny friformstabell | Ny avisering | Skicka fil enligt schema* |  |
| Ange som landningssida* |  | Ny rad | Uppdatera komponenter | Kuratera projektdata |  |
| Uppdatera projekt |  | Nytt fält |  |  |  |
| Hämta CSV |  |  |  |  |  |
| Ladda ned PDF* |  |  |  |  |  |
| Projektinformation och inställningar |  |  |  |  |  |

## Vänster linje {#section_271295C26EC840ABB2A8E7EC0498B60E}

Den vänstra listen har tre ikoner som ger dig åtkomst till paneler, [visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)och [komponenter](/help/components/overview.md)(dimensioner, mått, segment, dataintervall) med ett enda klick:

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

En **[!UICONTROL Blank Panel]** har lagts till i listan med paneler som är tillgängliga från den vänstra listen. Om du vill skapa en **ny kohortpanel** drar du i en tom panel och drar i en kohorttabellvisualisering.
