---
description: Lär dig mer om de olika alternativen för att spara automatiskt, spara som, spara som mall och öppna tidigare versioner.
title: Spara projekt
feature: CJA Workspace Basics
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---

# Spara projekt

Om du vill spara ändringarna i ett projekt går du till arbetsytan **[!UICONTROL Project]** -menyn. Arbetsytan sparar även projekt automatiskt i vissa fall.

## Spara projektalternativ {#Save}

Det finns olika åtgärder att spara som du kan utföra under **[!UICONTROL Project]** -menyn, beroende på hur du vill komma åt analysen i framtiden.

| Åtgärd | Beskrivning |
|---|---|
| **[!UICONTROL Save]** | Spara ändringar i projektet. Om projektet delas visas även ändringarna av projektmottagarna. När du sparar projektet första gången uppmanas du att ge projektet ett namn, en beskrivning (valfritt) och lägga till (valfria) taggar. |
| **[!UICONTROL Save with notes]** | Lägg till anteckningar om vad som ändrats i projektet innan projektet sparas. Anteckningarna lagras med projektversionen och är tillgängliga för alla redigerare under [!UICONTROL Project] > [!UICONTROL Open previous version]. |
| **[!UICONTROL Save as]** | Skapa en kopia av projektet. Det ursprungliga projektet påverkas inte. |
| **[!UICONTROL Save as template]** | Spara projektet som en [egen mall](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) som blir tillgängliga för din organisation under **[!UICONTROL Project > New]** |

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

För **befintlig** projekt, när du återgår till arbetsytan visas en **Projektåterställning** modal. Om du väljer Ja återställs projektet från den automatiskt sparade lokala kopian. &quot;Nej&quot; tar bort den automatiskt sparade lokala kopian och öppnar den senast sparade versionen av projektet.

![](assets/project-recovery.png)

För **new** projekt som aldrig har sparats går inte att återställa ändringar som inte har sparats.

## Öppna föregående version {#previous-version}

>[!NOTE]
>
>Tidigare projektversioner är för närvarande i begränsad version.

Så här öppnar du en tidigare version av ett projekt:

1. Gå till **[!UICONTROL Project]** > **[!UICONTROL Open previous version]**

   ![](assets/previous-versions.png)

1. Granska listan över tidigare versioner.
   [!UICONTROL Timestamp] och [!UICONTROL Editor] visas utöver [!UICONTROL Notes] om de lades till när [!UICONTROL Editor] sparad. Versioner utan anteckningar lagras i 90 dagar. versioner med anteckningar lagras i ett år.
1. Välj en tidigare version och klicka på **[!UICONTROL Load]**.
Den föregående versionen läses sedan in med ett meddelande. Den tidigare versionen blir inte den aktuella sparade versionen av projektet förrän du klickar på **[!UICONTROL Save]**. Om du navigerar bort från den inlästa versionen visas den senast sparade versionen av projektet när du kommer tillbaka.
