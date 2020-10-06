---
description: 'null'
keywords: Analysis Workspace
title: Skapa projekt – översikt
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: ff1a11a18de0825b6338de98865e3bddeef14f39
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 7%

---


# Skapa projekt – översikt

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

Ni kan skapa ett robust Analytics-projekt baserat på valfri kombination av visualiseringar, rapportkomponenter och datatabeller. Här ingår många av tabellutvecklingsfunktionerna från Ad Hoc Analysis i Analytics.

I Analysis Workspace kan du jämföra och dela upp data på sätt som inte tidigare varit möjligt. Du kan till exempel konfigurera rankade rapporter och göra omedelbara iterativa ändringar i datafrågan, och sedan få tillgång till och ändra värdena på rapportnivå.

Frågan skickas direkt till rapportmotorn - du kan göra ändringar direkt utan att ta fram andra rapporter för att skapa en analys. Resultaten returneras omedelbart utan att webbläsaren har uppdaterats.

## Sida för projektlista för arbetsyta {#section_39AA007D7C384F4E869F842F1C7B11F8}

När du först besöker **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]** visas alla projekt som du äger eller har fått åtkomst till. Du kan ange den här sidan som din Adobe Analytics-landningssida genom att klicka på **[!UICONTROL Set as Landing Page]**. (Om du inte ser det här alternativet, som i skärmbilden nedan, är det redan din landningssida.)

![](assets/sample-project.png)

Sidan med projektlistan för arbetsytan innehåller följande information:

| Element | Beskrivning |
|---|---|
| Skapa nytt projekt | Klicka på den här länken för att [starta ett nytt projekt från grunden](/help/analysis-workspace/home.md). |
| Hantera projekt | Om du klickar på den här länken kommer du till komponenthanteraren för projekt ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), som visar alla dina projekt i en lista och där du kan tagga, dela, ta bort, byta namn på, godkänna, kopiera och exportera projekt till CSV. |
| Ange som landningssida | Omvandlar den här sidan till startsidan för arbetsytan. |
| Visa Tutorials | Tar dig till [Analysis Workspace videosjälvstudiekurser](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/analysis-workspace-introduction.html). |
| Namn | Namn på Workspace-projektet. |
| Ägare | Den person som skapade det här projektet (antingen du eller någon som delade projektet med dig). |
| Typ | Anger om det här är ett arbetsyteprojekt eller ett [Mobile Scorecard](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/mobapp/home.html). |
| Projektroll | Anger om du är ägare, om du kan redigera projektet eller om det är ett duplicerat projekt. |
| Taggar | Taggar som har tillämpats på projektet, antingen i komponenthanteraren för projekt eller under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| Senast ändrad | Datum och tid när projektet senast ändrades. |
| Mina favoritprojekt | Om du vill markera ett projekt som favorit öppnar du projektet och klickar på stjärnan bredvid namnet. Den visas i den här listan nästa gång du öppnar Arbetsyta. |
| Projekt som visas ofta | Listar alla projekt som du öppnar ofta, så att de blir lätta att komma åt. |

## Projektinformation och inställningar {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** innehåller information på projektnivå om det aktiva projektet.

| Inställning | Beskrivning |
|---|---|
| Projektnamn | Namnet på projektet. Du kan dubbelklicka på namnet för att redigera det. |
| Skapad av | Projektägarnamn |
| Senast ändrad | Datum för senaste ändring av projektet. |
| Taggar | Visar alla taggar som har använts i ett projekt för enklare kategorisering. Du kan också tagga projekt medan du sparar dem. Visa ett projekts taggar på startsidan för arbetsytan i [!UICONTROL Tags] kolumn. |
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
>Alternativ markerade med en asterisk (*) visas endast med **sparad** projekt.

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

Den vänstra listen har tre ikoner som ger dig tillgång till paneler: [Visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)och [Komponenter](/help/components/overview.md) (Dimensioner, mått, segment, dataintervall) med ett klick:

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** har lagts till i listan med paneler som är tillgängliga från den vänstra listen. Skapa en **ny kohortpanel** drar du i en tom panel och drar i en koordinattabellvisualisering.
