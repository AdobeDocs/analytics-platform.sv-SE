---
description: Projektdelning och projektroller på arbetsytan
keywords: Analysis Workspace-delning
title: Dela projekt
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: 8cee89a8ed656ad6376e64c8327aa7c94a937ce9
workflow-type: tm+mt
source-wordcount: '1056'
ht-degree: 0%

---

# Dela projekt

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Delning gör ett projekt tillgängligt för andra Analysis Workspace-användare i organisationen. Alla [kurationer](curate.md) som du har tillämpat återspeglas när mottagarna öppnar projektet.

## Projektroller {#Roles}

Du kan lägga till mottagare i en av tre projektroller. Projektroller är knutna till användaren och ett specifikt projekt-ID. Projektroller är oberoende av användarbehörigheter som hanteras i [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

| Roll | Projektkontroll |
|---|---|
| Kan redigera | Mottagarna kan **[!UICONTROL Save]** ändra ett projekt och fungera som medägare. Den här rollen är användbar om du vill samhantera ett projekt med andra kollegor. detta inkluderar redigering, borttagning och ändring av mottagarlistor för ett delat projekt. <br>Obs! Analysis Workspace stöder för närvarande inte live-samarbete, så vi rekommenderar att endast en användare redigerar ett projekt åt gången. Om projekt sparas samtidigt behålls den senaste versionen. |
| Kan dupliceras | Mottagarna kan **[!UICONTROL Save as]** och ha tillgång till den vänstra listen. Projektinteraktioner är inte begränsade i den här rollen. Den här rollen är användbar om du vill dela ett projekt med användare som förstår organisationens data och hur du använder Analysis Workspace, men inte vill att ditt projekt ska ändras. |
| Kan visa | Mottagarna kan inte spara som och har inte åtkomst till den vänstra listen. Projektinteraktionen är också begränsad. Den här rollen är användbar om du vill dela ett projekt med användare som inte är lika bekanta med organisationens datastruktur, Analysis Workspace eller Customer Journey Analytics i allmänhet. Men ni vill ändå att de ska konsumera data och insikter i en säker miljö.<br>Läs mer om  [Can view project experience](/help/analysis-workspace/curate-share/view-only-projects.md). |

>[!IMPORTANT]
> Projektmottagare som lagts till före den 18 juni 2020 har migrerats till en projektroll. Administratörsanvändare migrerade till rollen **[!UICONTROL Can edit]** och icke-adminanvändare migrerade till rollen **[!UICONTROL Can duplicate]**. Dessa roller ger samma projekterfarenhet som tidigare. Dessutom migrerades alla grupper (inklusive&quot;Alla&quot;) till rollen **[!UICONTROL Can duplicate]**.

### Ingen roll har tilldelats (mottagare av projektlänkar)

Om en mottagare inte har tilldelats en roll och får en [länk](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) till projektet (**[!UICONTROL Share]>[!UICONTROL Get project link]**) placeras de som standard i en roll. Administratörer får **[!UICONTROL Can edit]** och icke-administratörer får **[!UICONTROL Can duplicate]**.

### Flera roller har tilldelats

Om en mottagare placeras i flera roller får de alltid den högsta upplevelsen. Detta kan inträffa om en mottagare läggs till både som individ och som en del av en grupp. Om en mottagare till exempel får rollen **[!UICONTROL Can edit]** som individ och rollen **[!UICONTROL Can view]** som medlem i en grupp får han/hon en **[!UICONTROL Can edit]**-projekterfarenhet.

### Administratörer och roller

Administratörer som placerats i en **[!UICONTROL Can duplicate]**- eller **[!UICONTROL Can view]**-roll får de begränsade upplevelserna när de öppnar ett projekt. Om du vill kan en administratör när som helst öka sin roll till **[!UICONTROL Can edit]** till **[!UICONTROL Components]>[!UICONTROL Projects]**.

## Lägg till mottagare i delat projekt {#Add}

Så här lägger du till mottagare i ditt delade projekt:

1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Share project]**.
Om det finns ändringar som inte har sparats uppmanas du att spara projektet först.
1. Lägg till mottagare eller grupper med mottagare.
Använd hjälpikonen längst upp för att få beskrivningar av de olika rollerna.
1. (Valfritt) Dela inbäddade projektkomponenter (filter, beräknade värden och datumintervall) med alla mottagare.
När komponenterna har delats visas de i listrutan Komponenter på mottagarens arbetsyta. Observera att den här inställningen inte kvarstår - det är en enkel åtgärd vid tidpunkten för delningen.
1. (Valfritt) Ange den här sidan som landningssida för mottagare.
Den här inställningen kvarstår inte - det är en enkel åtgärd vid tidpunkten för delningen.
1. Klicka på Dela.
Du kan också klicka på **[!UICONTROL Curate and Share]** om du vill använda projektkurering automatiskt. Om ett projekt redan har delats, kommer dessa knappar att säga **[!UICONTROL Update]** och **[!UICONTROL Curate & Update]**. Läs mer om [projektstrukturering](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html).

![](assets/share-proj-modal.png)

## Dela till grupper med mottagare {#Groups}

Alla användare kan dela projekt med grupper, som är en samling mottagare. I Customer Journey Analytics definieras grupper av produktprofiler i [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

* Administratörer kan dela till alla grupper, inklusive&quot;Alla&quot;.
* Icke-administratörer kan dela grupper som de är medlemmar i, med undantag för&quot;Alla&quot;.

## Dela en projektlänk {#Links}

Du kan hämta en länk till ett projekt under **[!UICONTROL Share]>[!UICONTROL Get project link]**. När man klickar på det här alternativet måste mottagarna logga in innan de landar i projektet. Om mottagaren inte har placerats i en roll får han/hon en standardroll. Administratörer får **[!UICONTROL Can edit]** och icke-administratörer får **[!UICONTROL Can duplicate]**. [Läs ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html) mer om hur du skapar delningsbara länkar till arbetsyteprojekt.

## Dela projekt i projektledaren {#Manager}

Projekt kan också delas från **[!UICONTROL Components]>[!UICONTROL Projects]**. Ett enskilt projekt kan delas enligt samma steg ovan.  Om du väljer att dela flera projekt läggs mottagarna till i den befintliga listan med mottagare för varje projekt.

Exempel:

* Projekt A delas med mottagare 1, 2, 3
* Projekt B delas med mottagare 4, 5, 6

När du har valt Projekt A och B läggs mottagarna 4 och 7 till i resurslistorna. Den nya resurslistan för varje projekt är nu:

* Projekt A: 1, 2, 3, 4, 7
* Projekt B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Vanliga frågor {#FAQs}

| Fråga | Svar |
|---|---|
| Vad händer om två redigerare sparar ett projekt samtidigt? | Ändringarna sammanfogas inte och den senast sparade projektversionen behålls. Analysis Workspace stöder för närvarande inte live-samarbete. |
| Vilken projekterfarenhet vill jag som administratör se? | Administratörer som placerats i en **[!UICONTROL Can duplicate]**- eller **[!UICONTROL Can view]**-roll får de begränsade upplevelserna när de öppnar ett projekt. Om du vill kan en administratör när som helst öka sin roll till **[!UICONTROL Can edit]** till **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Vad händer om en mottagare placeras i en roll som enskild person och en annan roll som medlem i en grupp? | Om en mottagare placeras i flera roller får de alltid den högre upplevelsen. Om en mottagare till exempel får rollen **[!UICONTROL Can edit]** som individ och rollen **[!UICONTROL Can view]** som medlem i en grupp får han/hon en **[!UICONTROL Can edit]**-projekterfarenhet. |
| Vilken upplevelse får en mottagare om de öppnar en projektlänk? | Mottagarna får rollen som du placerade dem i den delade modalen. Om en mottagare inte har tilldelats en roll och får en länk till projektet (**[!UICONTROL Share]>[!UICONTROL Get project link]**) placeras de som standard i en roll. Administratörer får **[!UICONTROL Can edit]** och icke-administratörer får **[!UICONTROL Can duplicate]**. |
