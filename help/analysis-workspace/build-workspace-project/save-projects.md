---
description: Lär dig mer om de olika alternativen för att spara automatiskt, spara som, spara som mall och öppna tidigare versioner.
title: Spara projekt
feature: Grundläggande om arbetsytan
role: User, Admin
exl-id: e8206956-6e24-4a3a-8c3f-8acf1fb9d800
source-git-commit: 734f1fe702398034090e25c251b5ff193db8381e
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 0%

---

# Spara projekt

Om du vill spara ändringarna i ett projekt går du till menyn Arbetsyta **[!UICONTROL Project]**. Arbetsytan sparar även projekt automatiskt i vissa fall.

## Spara projektalternativ {#Save}

Det finns olika åtgärder att spara som du kan utföra under menyn **[!UICONTROL Project]**, beroende på hur du vill komma åt analysen i framtiden.

| Åtgärd | Beskrivning |
|---|---| 
| **[!UICONTROL Save]** | Spara ändringar i projektet. Om projektet delas visas även ändringarna av projektmottagarna. När du sparar projektet första gången uppmanas du att ge projektet ett namn, en beskrivning (valfritt) och lägga till (valfria) taggar. |
| **[!UICONTROL Save with notes]** | Lägg till anteckningar om vad som ändrats i projektet innan projektet sparas. Anteckningar lagras med projektversionen och är tillgängliga för alla redigerare under [!UICONTROL Project] > [!UICONTROL Open previous version]. |
| **[!UICONTROL Save as]** | Skapa en kopia av projektet. Det ursprungliga projektet påverkas inte. |
| **[!UICONTROL Save as template]** | Spara projektet som en [anpassad mall](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) som blir tillgänglig för din organisation under **[!UICONTROL Project > New]** |

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

När du återgår till arbetsytan för **befintliga**-projekt visas en modal **projektåterställning**. Om du väljer Ja återställs projektet från den automatiskt sparade lokala kopian. &quot;Nej&quot; tar bort den automatiskt sparade lokala kopian och öppnar den senast sparade versionen av projektet.

![](assets/project-recovery.png)

För **nya**-projekt som aldrig har sparats går det inte att återställa ändringar som inte har sparats.

## Öppna föregående version {#previous-version}

>[!NOTE]
>
>Tidigare projektversioner är för närvarande i begränsad version.

Så här öppnar du en tidigare version av ett projekt:

1. Gå till **[!UICONTROL Project]** > **[!UICONTROL Open previous version]**

   ![](assets/previous-versions.png)

1. Granska listan över tidigare versioner.
   [!UICONTROL Timestamp] och  [!UICONTROL Editor] visas förutom  [!UICONTROL Notes] om de lades till när de  [!UICONTROL Editor] sparades. Versioner utan anteckningar lagras i 90 dagar. versioner med anteckningar lagras i ett år.
1. Välj en tidigare version och klicka på **[!UICONTROL Load]**.
Den föregående versionen läses sedan in med ett meddelande. Den tidigare versionen blir inte den aktuella sparade versionen av projektet förrän du klickar på **[!UICONTROL Save]**. Om du navigerar bort från den inlästa versionen visas den senast sparade versionen av projektet när du kommer tillbaka.
