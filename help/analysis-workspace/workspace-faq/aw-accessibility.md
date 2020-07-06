---
description: Funktioner för tillgänglighetsstöd i Analysis Workspace
title: Tillgänglighet i Analysis Workspace
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 1%

---


# Tillgänglighet i Analysis Workspace

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Läs om tillgänglighetsstödet i [!UICONTROL Analysis Workspace]det främsta analysverktyget för Adobe Analytics.

Med hjälpmedel avses att göra produkter användbara för personer med funktionshinder som syn-, hörsel-, kognitiv-, motor- eller andra funktionshinder. Exempel på hjälpmedelsfunktioner för programprodukter är skärmläsarstöd, textmotsvarigheter för grafik, kortkommandon, ändring av visningsfärger till hög kontrast osv.

[!UICONTROL Analysis Workspace] innehåller verktyg som gör dem tillgängliga att använda, bland annat:

## Navigera [!UICONTROL Workspace] med tangentbordet

Navigering i [!UICONTROL Analysis Workspace] fungerar överst > nedåt och vänster > höger. Följande navigeringselement underlättar tillgängligheten:

* Med `F6` tangenten aktiveras kortkommandon för landmärken
* Tangenten rör sig `Tab` mellan enskilda element.
* Vi använder fokusindikatorer så att synkade tangentbordsanvändare får en tydlig indikation på vilket gränssnittselement som för närvarande är i fokus. Indikatorn är en blå ram runt det markerade elementet.

   ![Fokusindikator](assets/focus-indicator.png)

### Tangentbordsnavigering för dra och släpp-interaktioner

[!UICONTROL Analysis Workspace] är ett dra och släpp-användargränssnitt. Användarna kan dock lägga till komponenter med tangentbordet i stället:

1. Gå till en komponent i den vänstra listen.
1. Tryck på `Enter` för att markera.
1. Använd piltangenterna för att navigera till det område där du vill släppa komponenten.
1. Tryck för `Enter` att montera komponenten.

### Kortkommandon (snabbtangenter)

[!UICONTROL Analysis Workspace] erbjuder en mängd [kortkommandon](/help/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) för ett smidigare arbetsflöde. Nedan listas några vanliga genvägar för navigering, skapande av analyser och demokratisering av insikter.

#### Navigering

| Genväg | Åtgärd |
|---|---|
| Alt + Skift + 1 / 2 / 3 | Hoppa till olika skenor: [!UICONTROL Panels], [!UICONTROL Visualizations]eller [!UICONTROL Components] |
| Alt + Vänsterpil/Högerpil | Navigera mellan paneler |
| Alt + M | Komprimera/expandera alla paneler |
| Alt+Ctrl+M | Komprimera/expandera aktiv panel |
| Ctrl + / | Sök i vänster list |

#### Analysgenerering

| Genväg | Åtgärd |
|---|---|
| Alt+1 | Ny frihandstabell |
| Ctrl + Skift + C | Nytt beräknat mått |
| Ctrl + Skift + D | Nytt datumintervall |
| Ctrl + Skift + E | Nytt segment |
| Ctrl + Z | Ångra |
| Håll ned skift (i panelsegmentets dropzone) | Skapa ett [listrutefilter](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html) |

#### Demokratisering

| Genväg | Åtgärd |
|---|---|
| Ctrl + S | Spara |
| Ctrl + Skift + G | Kurva |
| Ctrl + G | Dela |
| Alt + Skift + S | Schema |
| Alt+L | Hämta länk till projekt |
| Ctrl + Skift + B | Ladda ned PDF |

## Stöd för skärmläsare och skärmförstorare

En skärmläsare läser upp text som visas på datorskärmen. Den läser även information som inte är text, t.ex. knappetiketter eller bildbeskrivningar i programmet, som finns i hjälpmedelstaggar eller -attribut.

## Färgpaletter och kontrast

[!UICONTROL Analysis Workspace] eftersträvar WCAG 2.1-överensstämmelse, inklusive krav på färgkontrast.

Dessutom kan användarna välja en egen färgpalett för ett projekt under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Projektfärgpalett](/help/analysis-workspace/build-workspace-project/color-palettes.md).

## Obligatorisk fältvalidering i komponentbyggare

När du skapar en komponent valideras de obligatoriska fälten när du sparar. Om ett obligatoriskt fält inte godkänns vid valideringen visas det i rött med en felikon. En skriftlig beskrivning visas av problemet som behöver åtgärdas.

När en komponent har validerats helt stängs byggaren när du trycker `Save` på.

![Felvalidering](assets/error-validation.png)

## Stöd för hjälpmedelsfunktioner för operativsystem

Analysis Workspace har stöd för inbyggda tillgänglighetsfunktioner för MS Windows och macOS, som högkontrastläge, klisterknappar och långsamma tangenter/filtertangenter. Det innehåller även information om användargränssnittet till operativsystemet för att möjliggöra interaktion med hjälpmedelstekniker, inklusive skärmläsare som VoiceOver för macOS och NVDA för Windows.