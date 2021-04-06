---
description: Använd mallar i Workspace och skapa egna mallar.
title: Mallar
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
exl-id: 464032a1-6dae-4df5-b4db-b277788e88c2
translation-type: tm+mt
source-git-commit: a0ea2be203aa2e0df7b195e259b6d98c0c027652
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 1%

---

# Mallar

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan välja om du vill skapa ett projekt från:

* **Tomt projekt (standard)**: Instruktioner finns i  [Skapa ett Analysis Workspace-projekt](/help/analysis-workspace/home.md).
* **Standardmall**: Mallarna skapas av Adobe och levereras med produkten.
* **Egen mall**: De här mallarna kan skapas, delas eller tas bort av användare med administratörsbehörighet eller av icke-administratörer, förutsatt att de har beviljats  [!UICONTROL Analysis Workspace: Save as Template] tillstånd i Admin Console. [Läs mer …](https://docs.adobe.com/content/help/en/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Skapa en anpassad mall {#create-custom-template}

Användare med administratörsbehörighet kan omvandla projekt de skapar till en egen mall. Så här:

1. Öppna projektet.
1. Gå till **[!UICONTROL Project]** > **[!UICONTROL Save As Template]**.

   ![](assets/save_project_template.png)

   Projektet sparas under det aktuella projektnamnet, följt av ordet (mall) inom parentes. Administratörer kan ändra det här namnet genom att redigera mallen.

   >[!NOTE]
   >
   >Som standard är projektmallar synliga för alla i organisationen. Du kan ordna dem genom att använda taggar. (Gå till **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]** om du vill redigera taggar och beskrivningar.)

### Åtgärder som du kan utföra på anpassade mallar

![](assets/custom_templates.png)

| Åtgärd | Beskrivning |
|--- |--- |
| Redigera mall | Låter en administratör redigera mallen genom att ändra dess datakälla, ändra komponenter, visualiseringar, datumintervall osv.  Om du vill redigera en anpassad mall, antingen<ul><li>Visa listan med egna mallar i Analysis Workspace, markera en och klicka sedan på Redigera mall, eller</li><li>Navigera till Komponenter > Projekt i Analytics och filtrera sedan efter Mallar. Klicka på namnet på mallen som du vill redigera.</li></ul>**Obs!** När du har redigerat en mall kan du välja mellan två alternativ, beroende på situationen: Spara, Spara som. Så här skiljer de sig:<ul><li>**Spara:** Uppdaterar den anpassade mallen för alla användare. När någon annan skapar ett projekt från den här anpassade mallen ser de ändringarna som du har gjort.</li><li>**Spara som:** Skapar en kopia av den anpassade mallen med dina ändringar. (Du ser att du är i redigeringsläge när menyalternativet Dela > Dela projekt är inaktiverat.)</li></ul> |
| Sök efter mallar | I dialogrutan Egna mallar klickar du på Sökmallar. |
| Sortera mallar | Du kan sortera mallar i bokstavsordning, efter relevans och efter skapandedatum.  I dialogrutan Egna mallar klickar du på Sortera:. |
| Använd taggar på mall | Öppna mallen och gå till Projekt > Projektinformation och inställningar. Klicka på Lägg till taggar. |
| Ändra mallbeskrivning | Öppna mallen och gå till Projekt > Projektinformation och inställningar. Dubbelklicka på beskrivningen och redigera den. |


## Standardmallar

När du först öppnar en arbetsyta är mallarna tillgängliga i den vänstra listen. Analysis Workspace-mallar täcker vanliga användningsområden. De grupperas efter lodrät som de tillhör och fylls i med olika dimensioner, filter, mätvärden och visualiseringar, beroende på vilken datavy du har valt.

Du kan använda de här förifyllda mallarna som de är eller anpassa dem efter dina behov (genom att till exempel lägga till eller ersätta mått eller visualiseringar) och spara dem under ett nytt namn.

>[!VIDEO](https://video.tv.adobe.com/v/23960)

*(2:46)*

Här finns tillgängliga mallar och de frågor som varje mall kan besvara.

### Utbildning

Dessa standardmallar leder dig igenom vanliga termer och steg för att skapa din första analys i Workspace. De är tillgängliga som standardmallar i det nya projektet och ersätter det exempelprojekt som finns idag för nya användare som inte har andra projekt i listan.

* **Självstudiekurs - intern sökanalys**: Självstudiekursen för intern sökning hjälper dig att förstå vad besökarna letar efter på webbplatsen eller i appen, men inte att hitta. Genom att analysera den här typen av data kan ni identifiera möjligheter till innehållsoptimering.

* **Självstudiekurs - marknadsanalys**: Den här självstudiekursen visar hur ni sammanställer en marknadsföringsanalys för era chefer, inklusive vilka anpassade mått och mätvärden som är viktiga.

### Media

* **Ljudförbrukning**: Vilket innehåll konsumeras mest och engagerar användarna?
* **Nyhet - frekvens - lojalitet**: Vilka är mina lojala läsare?


### Detaljhandel

* **Kampanjprestanda:** Vilka kampanjer genererar störst intäkter?
* **Produkter:** Vilka produkter fungerar bäst?

### Webb

* **Förvärv:** Vilka är de viktigaste trafikdrivrutinerna på min webbplats?
* **Innehållskonsumtion:** Vilka är de främsta platserna på min webbplats?
* **Kvarhållning:** Vilka typer av användare är sannolikt lojala användare på min webbplats?
* **Teknik:** Vilken teknik använder människor för att komma åt min webbplats?

