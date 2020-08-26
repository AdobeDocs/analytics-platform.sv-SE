---
description: Projektdelning och projektroller på arbetsytan
keywords: Analysis Workspace sharing
title: Dela arbetsyteprojekt
translation-type: tm+mt
source-git-commit: afe5b341ea1b442c23561299fbffce59dae45930
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 3%

---


# Dela arbetsyteprojekt

Delning gör ett projekt tillgängligt för andra Analysis Workspace-användare i organisationen. Valfri [kuration](curate.md) du har tillämpat återspeglas när mottagarna öppnar projektet.

## Projektroller {#Roles}

Du kan lägga till mottagare i en av tre projektroller. Projektroller är kopplade till användaren och till ett specifikt projekt-ID. Projektroller är oberoende av användarbehörigheter som hanteras i [Administratörskonsol för Adobe Experience Cloud](https://docs.adobe.com/content/help/sv-SE/core-services/interface/manage-users-and-products/admin-getting-started.html).

| Roll | Projektkontroll |
|---|---|
| Kan redigera | Mottagare kan **[!UICONTROL Save]** Ändringar av ett projekt och funktioner som delägare. Denna roll är användbar om du vill hantera ett projekt tillsammans med andra kolleger. Detta omfattar redigering, borttagning och ändring av mottagarlistor för ett delat projekt. <br>Anmärkning: Analysis Workspace stöder för närvarande inte live-samarbete, så det rekommenderas att endast en användare redigerar ett projekt åt gången. Om projekt sparas samtidigt behålls den sista versionen. |
| Kan dupliceras | Mottagare kan **[!UICONTROL Save as]** och ha tillgång till vänster järnväg. Projektinteraktioner är inte begränsade i den här rollen. Den här rollen är användbar om du vill dela ett projekt med användare som förstår organisationens data och hur du använder Analysis Workspace, men du vill inte att projektet ska ändras. |
| Kan visa | Mottagarna kan inte spara som och har inte tillgång till vänster järnväg. Projektinteraktioner är också begränsade. Den här rollen är användbar om du vill dela ett projekt med användare som är mindre förtrogna med organisationens datastruktur, Analysis Workspace eller Adobe Analytics i allmänhet. Men du vill ändå att de ska konsumera data och insikter i en säker miljö.<br>Läs mer om [Kan visa projekterfarenhet](/help/analysis-workspace/curate-share/view-only-projects.md). |

>[!IMPORTANT]
> Projektmottagare som lagts till före den 18 juni 2020 har migrerats till en projektroll. Administratörsanvändare migrerade till **[!UICONTROL Can edit]** roll- och icke-administratörsanvändare migrerade till **[!UICONTROL Can duplicate]** roll. Dessa roller ger samma projekterfarenhet som tidigare. Dessutom migreras alla grupper (inklusive &quot;Alla&quot;) till **[!UICONTROL Can duplicate]** roll.

### Ingen roll tilldelad (projektlänkmottagare)

Om en mottagare inte har tilldelats en roll och tar emot en [länk](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) till projektet (**[!UICONTROL Share]>[!UICONTROL Get project link]**) placeras de som standard i en roll. Administratörer tar emot **[!UICONTROL Can edit]** och icke-administratörer tar emot **[!UICONTROL Can duplicate]**.

### Flera roller har tilldelats

Om en mottagare placeras i flera roller får han/hon alltid den högsta erfarenheten. Detta kan inträffa om en mottagare läggs till både som en enskild person och som en del av en grupp. Om t.ex. en mottagare ges **[!UICONTROL Can edit]** som individ och **[!UICONTROL Can view]** som medlem i en grupp kommer de att få en **[!UICONTROL Can edit]** projekterfarenhet.

### Administratörer och roller

Administratörer som placeras i en **[!UICONTROL Can duplicate]** eller **[!UICONTROL Can view]** Dessa begränsade erfarenheter kommer att visas när de öppnar ett projekt. Om så önskas kan en administratör öka sin roll till **[!UICONTROL Can edit]** när som helst fram **[!UICONTROL Components]>[!UICONTROL Projects]**.

## Lägg till mottagare i delat projekt {#Add}

Så här lägger du till mottagare i det delade projektet:

1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Share project]**.
Om det finns ändringar som inte har sparats uppmanas du att spara projektet först.
1. Lägg till mottagare eller grupper med mottagare.
Se hjälpikonen längst upp för beskrivningar av varje roll.
1. (Valfritt) Dela inbäddade projektkomponenter (segment, beräknade mått och datumintervall) med alla mottagare.
När komponenterna har delats visas de i listrutan Komponenter på mottagarens arbetsyta. Observera att den här inställningen inte kvarstår - det är en enstaka åtgärd vid tiden för delning.
1. (Valfritt) Ange den här sidan som landningssida för mottagare.
Den här inställningen kvarstår inte - det är en unik åtgärd vid tiden för delningen.
1. Klicka på Dela.
Du kan också klicka på **[!UICONTROL Curate and Share]** om du vill använda projektkurering automatiskt. Om ett projekt redan har delats ut, säger dessa knappar **[!UICONTROL Update]** och **[!UICONTROL Curate & Update]**. Läs mer om [projektkursion](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html).

![](assets/share-proj-modal.png)

## Dela till grupper med mottagare {#Groups}

Alla användare kan dela projekt till grupper, som är en samling mottagare. I Adobe Analytics definieras grupper efter produktprofiler i [Administratörskonsol för Adobe Experience Cloud](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

* Administratörer kan dela till valfri grupp, inklusive &quot;Alla&quot;.
* Icke-administratörer kan dela grupper som de är medlemmar i, med undantag för &quot;Alla&quot;.

## Dela en projektlänk {#Links}

Du kan hämta en länk till ett projekt under **[!UICONTROL Share]>[!UICONTROL Get project link]**. Vid klickning måste mottagarna logga in innan de landar i projektet. Om mottagaren inte har placerats i en roll får de en standardroll. Administratörer tar emot **[!UICONTROL Can edit]** och icke-administratörer tar emot **[!UICONTROL Can duplicate]**. [Läs mer](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) om att skapa delbara länkar till arbetsyteprojekt.

## Dela projekt i projektledaren {#Manager}

Projekt kan också delas från **[!UICONTROL Components]>[!UICONTROL Projects]**. Ett enda projekt kan delas enligt samma steg ovan.  Om flera projekt väljs ut för att delas ut läggs mottagarna till i den befintliga mottagarlistan för varje projekt.

Exempel:

* Projekt A delas ut till mottagare 1, 2, 3
* Projekt B delas ut till mottagare 4, 5, 6

Om du väljer Projekt A och B läggs mottagarna 4 och 7 till i resurslistorna. Den nya resurslistan för varje projekt är nu:

* Projekt A: 1, 2, 3, 4, 7
* Projekt B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Vanliga frågor och svar {#FAQs}

| Fråga | Svar |
|---|---|
| Vad händer om två redaktörer sparar ett projekt samtidigt? | Ändringarna slås inte samman och den senast sparade projektversionen behålls. Analysis Workspace stöder för närvarande inte live-samarbete. |
| Vilken projekterfarenhet ser jag som administratör? | Administratörer som placeras i en **[!UICONTROL Can duplicate]** eller **[!UICONTROL Can view]** Dessa begränsade erfarenheter kommer att visas när de öppnar ett projekt. Om så önskas kan en administratör öka sin roll till **[!UICONTROL Can edit]** när som helst fram **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Vad händer om en mottagare placeras i en roll som enskild person och en annan roll som medlem i en grupp? | Om en mottagare placeras i flera roller får han/hon alltid den högre upplevelsen. Om t.ex. en mottagare ges **[!UICONTROL Can edit]** som individ och **[!UICONTROL Can view]** som medlem i en grupp kommer de att få en **[!UICONTROL Can edit]** projekterfarenhet. |
| Vilken erfarenhet får en mottagare om de öppnar en projektlänk? | Mottagarna får den roll du placerat dem i den delade modaliteten. Om en mottagare inte har tilldelats en roll och får en länk till projektet (**[!UICONTROL Share]>[!UICONTROL Get project link]**) placeras de som standard i en roll. Administratörer tar emot **[!UICONTROL Can edit]** och icke-administratörer tar emot **[!UICONTROL Can duplicate]**. |
