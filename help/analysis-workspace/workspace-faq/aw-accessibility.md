---
description: Hjälpmedelsstödfunktioner i Analysis Workspace
title: Tillgänglighet i analysarbetsytan
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 1%

---


# Tillgänglighet i analysarbetsytan

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Läs mer om hjälpmedelssupport i [!UICONTROL Analysis Workspace], förstklassiga analysverktyg för Adobe Analytics.

Med tillgänglighet avses att göra produkter användbara för personer med syn-, hörsel-, kognitiv-, motor- och andra funktionshinder. Exempel på hjälpmedelsfunktioner för programvaruprodukter är skärmläsarstöd, textmotsvarigheter för grafik, kortkommandon, byte av visningsfärger till hög kontrast och så vidare.

[!UICONTROL Analysis Workspace] innehåller vissa verktyg som gör den tillgänglig att använda, bland annat:

## Navigera [!UICONTROL Workspace] med tangentbordet

Navigering i [!UICONTROL Analysis Workspace] fungerar överst > nedåt och vänster > höger. Följande navigeringselement underlättar tillgängligheten:

* De `F6` nyckel möjliggör kortkommandon för markeringar
* De `Tab` tangenten flyttas mellan enskilda element.
* Vi använder fokusindikatorer så att synskadade tangentbordsanvändare har en tydlig indikation på vilket gränssnittselement som för närvarande är fokuserat. Indikatorn är en blå kant runt det markerade elementet.

   ![Fokusindikator](assets/focus-indicator.png)

### Navigering med tangentbord för dra- och släpp-interaktioner

[!UICONTROL Analysis Workspace] är ett dra-och-släpp-användargränssnitt. Användarna kan dock lägga till komponenter med hjälp av tangentbordet i stället för:

1. Tabb till en komponent i vänster räl.
1. Tryck `Enter` för att välja.
1. Använd piltangenterna för att navigera till det område där du vill släppa komponenten.
1. Tryck `Enter` för att placera komponenten.

### Kortkommandon (snabbtangenter)

[!UICONTROL Analysis Workspace] erbjuder en mängd [kortkommandon](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) för ett mer sömlöst arbetsflöde. Nedan listas några gemensamma genvägar för navigering, analysskapande och insiktsdemokratisering.

#### Navigering

| Genväg | Åtgärd |
|---|---|
| Alt + Skift + 1 / 2 / 3 | Hoppa till olika skenor: [!UICONTROL Panels], [!UICONTROL Visualizations]eller [!UICONTROL Components] |
| Alt + Vänster-/högerpil | Navigera mellan paneler |
| Alt + M | Dölj/expandera alla paneler |
| Alt+Ctrl+M | Dölj/expandera aktiv panel |
| Ctrl + / | Sök i vänster list |

#### Analysskapande

| Genväg | Åtgärd |
|---|---|
| Alt + 1 | Nytt frihandsregister |
| Ctrl + Skift + C | Nytt beräknat mått |
| Ctrl + Skift + D | Nytt datumintervall |
| Ctrl + Skift + E | Nytt segment |
| Ctrl + Z | Ångra |
| Håll skift (i panelsegmentets listruta) | Skapa ett [nedrullningsfilter](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) |

#### Demokratisering

| Genväg | Åtgärd |
|---|---|
| Ctrl + S | Spara |
| Ctrl + Skift + G | Curate |
| Ctrl + G | Dela |
| Alt + Skift + S | Schemalägg |
| Alt + L | Hämta länk till projekt |
| Ctrl + Skift + B | Ladda ned PDF |

## Stöd för skärmläsare och skärmförstorare

En skärmläsare läser text som visas på datorskärmen. Den läser även icke-textbaserad information, t.ex. knappetiketter eller bildbeskrivningar i programmet, som finns i hjälpmedelstaggar eller -attribut.

## Färgpaletter och kontrast

[!UICONTROL Analysis Workspace] eftersträvar överensstämmelse med WCAG 2.1, inklusive krav på färgkontrast.

Dessutom kan användarna ange sin egen föredragna färgpalett för ett projekt under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Projektfärgpalett](/help/analysis-workspace/build-workspace-project/color-palettes.md).

## Obligatorisk fältvalidering i komponentbyggare

När du skapar en komponent valideras obligatoriska fält när du sparar. Om ett obligatoriskt fält inte godkänns vid valideringen visas det med en felikon i rött. En skriftlig beskrivning visas av problemet som måste åtgärdas.

När en komponent har validerats fullständigt trycker du på `Save` Stänger byggaren.

![Felverifiering](assets/error-validation.png)

## Stöd för hjälpmedelsfunktioner för operativsystem

Analysis Workspace stöder inbyggda hjälpmedelsfunktioner för MS Windows och macOS, t.ex. högkontrastläge, klibbiga nycklar och långsamma nycklar/filternycklar. Den innehåller också information om användargränssnittet till operativsystemet för att möjliggöra interaktion med hjälpmedelstekniker, inklusive skärmläsare som VoiceOver för macOS och NVDA på Windows.