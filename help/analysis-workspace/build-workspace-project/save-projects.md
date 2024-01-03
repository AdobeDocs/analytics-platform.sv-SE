---
description: Lär dig mer om de olika alternativen för att spara automatiskt, spara som, spara som mall och öppna tidigare versioner.
title: Spara projekt
feature: Workspace Basics
role: User
exl-id: d751057e-6a5f-4605-abc1-9259a1f95a28
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 0%

---

# Spara projekt

Projekt i Analysis Workspace sparas automatiskt varannan minut.

Du kan också spara projekt manuellt. Det finns andra alternativ, till exempel att lägga till taggar eller anteckningar, tillgängliga när du sparar ett projekt manuellt.

## Spara projektalternativ {#Save}

Det finns olika alternativ när du sparar ett projekt manuellt i Analysis Workspace.

Så här sparar du ett projekt manuellt:

1. Med projektet öppet i Analysis Workspace väljer du **[!UICONTROL Project]** väljer du sedan något av följande alternativ:

   | Åtgärd | Beskrivning |
   |---|---| 
   | **[!UICONTROL Save]** | Spara ändringar i projektet. Om projektet delas visas även ändringarna av projektmottagarna. När du sparar projektet första gången uppmanas du att ge projektet ett namn, en (valfri) beskrivning och lägga till (valfria) taggar. |
   | **[!UICONTROL Save with notes]** | Lägg till anteckningar om vad som ändrats i projektet innan projektet sparas. Anteckningarna lagras med projektversionen och är tillgängliga för alla redigerare under [!UICONTROL Project] > [!UICONTROL Open previous version]. |
   | **[!UICONTROL Save as]** | Skapa en kopia av projektet. Det ursprungliga projektet påverkas inte. |
   | **[!UICONTROL Save as template]** | Spara projektet som en [egen mall](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html) som blir tillgängliga för din organisation under **[!UICONTROL Project > New]** |

## Spara automatiskt {#Autosave}

Alla projekt i Analysis Workspace sparas automatiskt varannan minut på din dator. Detta inkluderar nyskapade projekt som ännu inte sparats manuellt.

* **Nya projekt:** Även om nya projekt sparas automatiskt måste du spara varje nytt projekt manuellt första gången. Analysis Workspace uppmanar dig att spara nya projekt manuellt när du växlar till ett annat projekt, stänger webbläsarfliken och så vidare.

  Om du av någon anledning oväntat förlorar åtkomsten till ett nyskapat projekt innan du sparar det manuellt, sparas en återställningsversion av ditt projekt på Analysis Workspace startsida i en mapp som kallas `Recovered Projects (Last 7 Days)`. Du måste återställa det återställda projektet och spara det manuellt på önskad plats.

  Så här återställer du ett återskapat projekt:

   1. Gå till [!UICONTROL **Återskapade projekt**] på Analysis Workspace landningssida.

      ![En lista med mappar där mappen Återskapat projekt markeras.](assets/recovered-folder.png)

   1. Öppna projektet och spara det där du vill.


* **Befintliga projekt** Om du av någon anledning lämnar ett projekt med ändringar som ännu inte har sparats automatiskt uppmanas du att spara ändringarna eller ett varningsmeddelande visas.

  Här följer några vanliga scenarier:

### Öppna ett annat projekt

Om du öppnar ytterligare ett projekt medan du arbetar med ett projekt som innehåller ändringar som ännu inte har sparats automatiskt, uppmanas du att spara det aktuella projektet innan du går.

Följande alternativ är tillgängliga:

* **Spara:** Ersätter den senaste automatiskt sparade lokala kopian av ditt projekt med dina senaste ändringar.
* **Spara som:** Sparar de senaste ändringarna som ett nytt projekt. Det ursprungliga projektet sparas endast med de senaste automatiskt sparade ändringarna.
* **Ignorera ändringar:** Ignorera de senaste ändringarna. De senaste automatiskt sparade ändringarna sparas i projektet.

![Klicka på Spara för att spara ändringar i ett projekt.](assets/existing-save.png)

### Navigera bort eller stänga en flik

Om du navigerar bort från sidan eller stänger webbläsarfliken när du visar ett projekt med ändringar som ännu inte har sparats automatiskt, visas en varning i webbläsaren om att ändringar som inte har sparats går förlorade. Du kan välja att avbryta eller avbryta.

![Klicka på Lämna om du vill lämna webbplatsen eller på Avbryt om du vill navigera utan att spara ändringarna. ](assets/browser-image.png)

### Webbläsaren kraschar eller sessionstider ut

Om webbläsaren kraschar eller om sessionen avbryts uppmanas du att återställa ändringar i projektet som ännu inte har sparats automatiskt nästa gång du öppnar Analysis Workspace.

Här följer dialogrutan Projektåterställning som visas första gången du öppnar Analysis Workspace efter en krasch eller en timeout.

Välj **Ja** om du vill återställa projektet från den senaste automatiskt sparade kopian.

Välj **Nej** om du vill ta bort den automatiskt sparade kopian och öppna den senast sparade versionen av projektet.

![Dialogrutan Projektåterställning.](assets/project-recovery.png)

För **new** projekt som aldrig har sparats går inte att återställa ändringar som inte har sparats.

## Öppna föregående version {#previous-version}

Öppna en tidigare version av ett projekt:

1. Gå till **[!UICONTROL Project]** > **[!UICONTROL Open previous version]**

   ![Listan med tidigare sparade projektversioner och alternativen för att visa alla versioner eller Endast versioner med anteckningar.](assets/previous-versions.png)

1. Granska listan över tidigare versioner.
   [!UICONTROL Timestamp] och [!UICONTROL Editor] visas utöver [!UICONTROL Notes] om de lades till när [!UICONTROL Editor] sparad. Versioner utan anteckningar lagras i 90 dagar. Versioner med anteckningar sparas i 1 år.
1. Välj en tidigare version och klicka på **[!UICONTROL Load]**.
Den föregående versionen läses sedan in med ett meddelande. Den tidigare versionen blir inte den aktuella sparade versionen av projektet förrän du klickar på **[!UICONTROL Save]**. Om du navigerar bort från den inlästa versionen visas den senast sparade versionen av projektet när du kommer tillbaka.
