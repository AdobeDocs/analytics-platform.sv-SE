---
description: Funktioner för tillgänglighetsstöd i Analysis Workspace
title: Tillgänglighet i Analysis Workspace
feature: FAQ
exl-id: 1616c625-8914-4ede-815d-e8d62e796ea5
source-git-commit: 32c507cb9de4fcd146de0e9c828c54c5f4f1a062
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 1%

---

# Tillgänglighet i Analysis Workspace

Läs mer om tillgänglighetsstöd i [!UICONTROL Analysis Workspace], det främsta analysverktyget för Customer Journey Analytics.

Med hjälpmedel avses att göra produkter användbara för personer med funktionshinder som syn-, hörsel-, kognitiv-, motor- eller andra funktionshinder. Exempel på hjälpmedelsfunktioner för programprodukter är skärmläsarstöd, textmotsvarigheter för grafik, kortkommandon, ändring av visningsfärger till hög kontrast osv.

[!UICONTROL Analysis Workspace] innehåller verktyg som gör dem tillgängliga att använda, bland annat:

## Navigera [!UICONTROL Workspace] med tangentbordet

Navigering i [!UICONTROL Analysis Workspace] fungerar top > down, and left > right. Följande navigeringselement underlättar tillgängligheten:

* The `Tab` Med tangenten kan du skapa genvägar mellan större avsnitt i arbetsytan. I den vänstra listen `Tab` Med kan du också gå från ett dragbart alternativ till nästa.
* The `left/right arrows` flytta mellan enskilda element efter `Tab` har markerat det.
* The `F6` navigerar till den första panelen i projektet och förflyttar sig mellan visualiseringarna på den panelen. Sedan flyttas den till nästa panel i projektet och upprepas.
* Vi använder fokusindikatorer så att synkade tangentbordsanvändare får en tydlig indikation på vilket gränssnittselement som för närvarande är i fokus. Indikatorn är en blå ram runt det markerade elementet.

   ![Fokusindikator](assets/focus-indicator.png)

### Tangentbordsnavigering för menyraden

1. Tabba tills du har nått menyraden.
1. Använd vänster-/högerpilstangenterna för att navigera till den meny som du vill använda.
1. Tryck `Enter` för att markera menyn och visa dess alternativ.
1. Använd upp-/nedpilarna för att navigera till det menyalternativ du vill använda.
1. Tryck `Enter` för att välja alternativet.

### Tangentbordsnavigering för dra och släpp-interaktioner

[!UICONTROL Analysis Workspace] är ett dra och släpp-användargränssnitt. Användarna kan dock lägga till komponenter med tangentbordet i stället:

1. Gå till en komponent i den vänstra listen.
1. Tryck `Enter` för att markera.
1. Använd piltangenterna för att navigera till det område där du vill släppa komponenten.
1. Tryck `Enter` för att montera komponenten.

### Kortkommandon (snabbtangenter)

[!UICONTROL Analysis Workspace] erbjuder en mängd [kortkommandon](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.html) för ett smidigare arbetsflöde. Nedan listas några vanliga genvägar för navigering, skapande av analyser och demokratisering av insikter.

#### Navigering

| Genväg | Åtgärd |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Hoppa till olika skenor: [!UICONTROL Panels], [!UICONTROL Visualizations], eller [!UICONTROL Components] |
| `[Alt + Left / Right]` | Navigera mellan paneler |
| `[Alt + M]` | Komprimera/expandera alla paneler |
| `[Alt + Ctrl + M]` | Komprimera/expandera aktiv panel |
| `[Ctrl + /]` | Sök i vänster list |

#### Analysgenerering

| Genväg | Åtgärd |
| --- | --- |
| `[Alt + 1]` | Ny frihandstabell |
| `[Ctrl + Shift + C]` | Nytt beräknat mått |
| `[Ctrl + Shift + D]` | Nytt datumintervall |
| `[Ctrl + Shift + E]` | Nytt segment |
| `[Ctrl + Z]` | Ångra |
| `[Component drag + Shift]` | Skapa ett nedrullningsbart filter |

#### Demokratisering

| Genväg | Åtgärd |
| --- | --- |
| `[Ctrl + S]` | Spara |
| `[Ctrl + Shift + G]` | Kurva |
| `[Ctrl + G]` | Dela |
| `[Alt + Shift + S]` | Schema |
| `[Alt + L]` | Hämta länk till projekt |
| `[Ctrl + Shift + B]` | Ladda ned PDF |

## Stöd för skärmläsare och skärmförstorare

En skärmläsare läser upp text som visas på datorskärmen. Den läser även information som inte är text, t.ex. knappetiketter eller bildbeskrivningar i programmet, som finns i hjälpmedelstaggar eller -attribut.

## Färgpaletter och kontrast

[!UICONTROL Analysis Workspace] eftersträvar WCAG 2.1-överensstämmelse, inklusive krav på färgkontrast.

Dessutom kan man ange en egen önskad färgpalett för ett projekt under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Projektets färgpalett](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/color-palettes.html).

## Obligatorisk fältvalidering i komponentbyggare

När du skapar en komponent valideras de obligatoriska fälten när du sparar. Om ett obligatoriskt fält inte godkänns vid valideringen visas det i rött med en felikon. En skriftlig beskrivning visas av problemet som behöver åtgärdas.

När en komponent har validerats trycker du `Save` stänger verktyget.

![Felvalidering](assets/error-validation.png)

## Stöd för hjälpmedelsfunktioner för operativsystem

Analysis Workspace har stöd för inbyggda hjälpmedelsfunktioner för MS Windows och macOS, som högkontrastläge, klisterlappar och långsamma tangenter/filtertangenter. Det innehåller även information om användargränssnittet till operativsystemet för att möjliggöra interaktion med hjälpmedelstekniker, inklusive skärmläsare som VoiceOver för macOS och NVDA i Windows.
