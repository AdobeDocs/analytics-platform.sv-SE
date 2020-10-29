---
description: Lär dig mer om de olika alternativen för att spara automatiskt, spara som och spara som mall.
title: Spara projekt
translation-type: tm+mt
source-git-commit: f01585ffdc0b54d1b21b035278869e59bd4947dc
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---

# Spara projekt

Om du vill spara ändringarna i ett projekt går du till arbetsytan **[!UICONTROL Project]** -menyn. Dessutom sparar Adobe projekt automatiskt i vissa fall.

## Spara projektalternativ {#Save}

Det finns olika åtgärder att spara som du kan utföra under **[!UICONTROL Project]** -menyn, beroende på hur du vill komma åt analysen i framtiden.

| Åtgärd | Beskrivning |
|---|---| 
| **[!UICONTROL Save]** | Spara ändringar i projektet. Om projektet delas visas även ändringarna av projektmottagarna. När du sparar projektet första gången uppmanas du att ge projektet ett namn, en (valfri) beskrivning och (valfritt) att lägga till taggar. |
| **[!UICONTROL Save as]** | Skapa en kopia av projektet. Det ursprungliga projektet påverkas inte. |
| **[!UICONTROL Save as template]** | Spara projektet som en [egen mall](https://docs.adobe.com/content/help/sv-SE/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) som blir tillgängliga för din organisation under **[!UICONTROL Project > New]** |

![](assets/save-project.png)

## Spara automatiskt {#Autosave}

Befintliga projekt, dvs. projekt som har sparats minst en gång tidigare, sparas automatiskt varannan minut på den lokala datorn. Nya projekt som aldrig har sparats sparas för närvarande inte automatiskt.

Det finns några scenarier som kan leda dig bort från osparade ändringar i ett projekt, vilket resulterar i olika tillgängliga åtgärder.

### Öppna ett annat arbetsyteprojekt

I Adobe kan du spara innan du lämnar sidan. När du har lämnat ett befintligt projekt tas den automatiskt sparade lokala kopian bort.

![](assets/existing-save.png)

### Navigera bort eller stänga en flik

Webbläsaren varnar för att ändringar som inte sparats går förlorade. Du kan välja att avbryta eller avbryta.

![](assets/browser-image.png)

### Webbläsaren kraschar eller sessionstider ut

För **befintlig** projekt, när användaren återgår till arbetsytan visas en **Projektåterställning** modal. Om du väljer Ja återställs projektet från den automatiskt sparade lokala kopian. &quot;Nej&quot; tar bort den automatiskt sparade lokala kopian och öppnar den senast sparade versionen av projektet.

![](assets/project-recovery.png)

För **new** projekt som aldrig har sparats går inte att återställa ändringar som inte har sparats.