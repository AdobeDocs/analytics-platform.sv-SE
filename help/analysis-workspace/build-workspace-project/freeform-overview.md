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
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

Du kan skapa ett robust analysprojekt baserat på valfri kombination av visualiseringar, rapportkomponenter och datatabeller. Den innehåller många av tabellbyggarens funktioner från Ad Hoc Analysis till Analytics.

I Analysis Workspace kan du jämföra och visa data på sätt som inte tidigare varit möjliga. Konfigurera t.ex. rankade rapporter och gör omedelbara iterativa ändringar i datafrågan, och få sedan åtkomst till och ändra värdena på rapportnivån.

Frågan går direkt till rapportmotorn. Du kan göra ändringar infogade utan att ta upp andra rapporter för att skapa analysen. Resultatet returneras omedelbart, utan att webbläsaren uppdateras.

## Projektlistsida för arbetsyta {#section_39AA007D7C384F4E869F842F1C7B11F8}

När du går till **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** visas alla projekt som du äger eller har fått åtkomst till. Du kan ange att den här sidan ska vara din Adobe Analytics-landningssida genom att klicka på **[!UICONTROL Set as Landing Page]**. (Om du inte ser det här alternativet, som i skärmbilden nedan, är det redan din landningssida.)

![](assets/sample-project.png)

Sidan med projektlista för arbetsyta innehåller följande information:

| Element | Beskrivning |
|---|---|
| Projekt [Mallar](/help/analysis-workspace/build-workspace-project/starter-projects.md) | Du kan använda de här förfyllda projektmallarna som de är eller anpassa dem efter dina behov (t.ex. genom att lägga till eller ersätta mått eller visualiseringar) och spara dem under ett nytt namn. |
| [Skapa nytt projekt](/help/analysis-workspace/home.md) | Klicka på den här länken om du vill starta ett nytt projekt från början. |
| Hantera projekt | Om du klickar på den här länken kommer du till projektkomponenthanteraren ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), som visar alla dina projekt och där du kan tagga, dela, ta bort, byta namn på, godkänna, kopiera och exportera projekt till CSV. |
| Visa självstudier | Tar er till [Video om Analysis Workspace YouTube](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS). |
| Namn | Namn på arbetsyteprojektet. |
| Skapad av | Den person som skapade projektet (antingen du eller någon som delade projektet med dig). |
| Taggar | Taggar som tillämpades på projektet, antingen i projektkomponenthanteraren eller under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| Senast ändrad | Datum och tid då projektet senast ändrades. |

## Projektinformation och inställningar {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** innehåller information på projektnivå om det aktuella aktiva projektet.

| Inställning | Beskrivning |
|---|---|
| Projektnamn | Namnet på projektet. Du kan dubbelklicka på namnet för att redigera det. |
| Skapad av | Projektägarens namn |
| Senast ändrad | Datum för senaste ändring av projektet. |
| Taggar | Visar alla taggar som används i ett projekt för enklare kategorisering. Du kan också tagga projekt samtidigt som du sparar dem. Visa ett projekts taggar på landningssidan för arbetsyta i [!UICONTROL Tags] kolumn. |
| Beskrivning | En beskrivning är användbar för att klargöra syftet med ett projekt. Du kan dubbelklicka på beskrivningen för att redigera den. |
| Räkna upprepade instanser i projekt | Anger om upprepade instanser ska räknas i rapporter. Om du har flera sekventiella värden för samma variabel kan du räkna dem som en eller som flera förekomster av variabeln. |
| Visualiseringsfärgschema | Du kan ändra färgschemat som används i arbetsytan genom att välja från en annan färgpalett eller genom att ange en egen palett. Den här funktionen påverkar många saker på arbetsytan, inklusive de flesta visualiseringar. |
| Visa densitet | Gör att du kan se mer data på skärmen genom att minska den lodräta utfyllnaden av vänster räl, frihandstabeller och kohorttabeller. |

## Menyn Projekt {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

Den övre projektmenyn ser ut så här:

![](assets/new-project-menus.png)

Undermenyerna innehåller följande alternativ.

>[!NOTE]
>
>Alternativ som markerats med en asterisk (*) visas endast med **sparad** projekt.

| Projekt | Redigera | Infoga | Komponenter | Dela | Hjälp |
|---|---|---|---|---|---|
| Ny | Ångra | Ny panel | Nytt segment | Dela projekt | Videor |
| Öppna | Rensa | Ny frihandspanel | Nytt mått | Hämta projektlänk* | Hotkey |
| Spara | Rensa alla | Ny segmentjämförelsepanel | Nytt datumintervall | Skicka filen nu* | Hjälpforum |
| Spara som* |  | Ny frihandstabell | Ny varning | Skicka fil i schema* |  |
| Ange som landningssida* |  | Ny rad | Uppdatera komponenter | Kurva projektdata |  |
| Uppdatera projekt |  | Nytt fält |  |  |  |
| Hämta CSV |  |  |  |  |  |
| Ladda ned PDF* |  |  |  |  |  |
| Projektinformation och inställningar |  |  |  |  |  |

## Vänstertåg {#section_271295C26EC840ABB2A8E7EC0498B60E}

Den vänstra rälen har tre ikoner som ger dig tillgång till paneler. [Visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)och [Komponenter](/help/components/overview.md)(Dimensioner, mått, segment, dataområden) med ett klick:

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** lades till i förteckningen över paneler som är tillgängliga från vänster räl. Så här skapar du en **ny kohortpanel**, dra i en tom panel och dra i en bild av en kohorttabell.
