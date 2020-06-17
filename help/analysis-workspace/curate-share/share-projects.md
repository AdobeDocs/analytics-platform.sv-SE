---
description: Projektdelning och projektroller på arbetsytan
keywords: Analysis Workspace sharing
title: Dela arbetsyteprojekt
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 2%

---


# Dela arbetsyteprojekt

>[!NOTE] Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Delning gör ett projekt tillgängligt för andra Analysis Workspace-användare i organisationen. All [kuration](curate.md) du har använt återspeglas när mottagarna öppnar projektet.

## Projektroller

Du kan lägga till mottagare i en av tre projektroller. Projektroller är knutna till användaren och ett specifikt projekt-ID.

>[!NOTE]
> Projektroller är oberoende av användarbehörigheter som hanteras i Admin Console i Experience Cloud.

| Roll | Projektkontroll |
|---|---|
| Kan redigera | Mottagarna kan spara ändringar i ett projekt och fungera som medägare.<br>Den här rollen är användbar om du vill samarbeta med kollegor i ett projekt. |
| Kan dupliceras | Mottagarna kan spara som och ha tillgång till den vänstra listen. Interaktionerna är inte begränsade.<br>Den här rollen är användbar om du vill dela ett projekt med användare som förstår organisationens data och hur du använder Analysis Workspace, men inte vill att ditt sparade projekt ska ändras. |
| Kan visa | Mottagarna kan inte spara som och har inte åtkomst till den vänstra listen. Interaktionerna är också begränsade.<br>Den här rollen är användbar om du vill dela ett projekt med användare som inte är lika bekanta med organisationens datastruktur, Analysis Workspace eller Adobe Analytics i allmänhet. Men ni vill ändå att de ska konsumera data och insikter i en säker miljö.<br>Läs mer om [Can view project experience](/help/analysis-workspace/curate-share/view-only-projects.md). |

### Ingen roll har tilldelats

Om en mottagare inte har tilldelats en roll och får en länk till projektet ([!UICONTROL Share] > [!UICONTROL Get project link]) placeras de som standard i [!UICONTROL "Can view"] rollen.

### Flera roller har tilldelats

Om en mottagare placeras i flera roller får de alltid den högsta kontrollen. Detta kan inträffa om en användare läggs till både som en individ och som en del av en grupp. Om till exempel användare 1 ges Kan redigera och [!UICONTROL "Can view"] roller får de [!UICONTROL "Can edit"] kontroll över projektet.

### Administratörer och roller

Administratörer som placerats i en [!UICONTROL&quot;Kan duplicera&quot;] eller [!UICONTROL "Can view"] roll får de begränsade upplevelserna när de öppnar ett projekt. Om du vill kan en administratör när som helst utöka sin roll till [!UICONTROL "Can edit"] via [!UICONTROL Components] > [!UICONTROL Projects].

## Lägg till mottagare i delat projekt

Så här lägger du till mottagare i ditt delade projekt:

1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Share project]**.
Om det finns ändringar som inte har sparats uppmanas du att spara projektet först.
1. Lägg till mottagare eller grupper med användare.
Använd hjälpikonen längst upp för att få beskrivningar av de olika rollerna.
1. (Valfritt) Dela inbäddade projektkomponenter (segment, beräknade värden och datumintervall) med alla mottagare.
När komponenterna har delats visas de i listrutan Komponenter på mottagarens arbetsyta. Observera att den här inställningen inte kvarstår - det är en enkel åtgärd vid tidpunkten för delningen.
1. (Valfritt) Ange den här sidan som landningssida för mottagare.
Den här inställningen kvarstår inte - det är en enkel åtgärd vid tidpunkten för delningen.
1. Klicka på Dela.
Du kan också klicka **[!UICONTROL Curate and Share]** för att använda projektkurering automatiskt. Om ett projekt redan har delats upp visas **[!UICONTROL Update]** och **[!UICONTROL Curate & Update]**. Läs mer om [projektstrukturering](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/curate.html).

![](assets/share-proj-modal.png)

## Dela till grupper med mottagare

Alla användare kan dela projekt med grupper, som är en samling mottagare. I Adobe Analytics definieras grupper av produktprofiler i Adobe Experience Cloud.

* Administratörer kan dela till alla grupper, inklusive&quot;Alla&quot;.
* Icke-administratörer kan dela grupper som de är medlemmar i, med undantag för&quot;Alla&quot;.

## Dela projekt i projektledaren

Du kan även dela projekt från [!UICONTROL Components] > [!UICONTROL Projects]. Ett enskilt projekt kan delas enligt samma steg ovan.

Om du väljer att dela flera projekt läggs mottagarna till i den befintliga listan med mottagare för varje projekt. Exempel:

* Projekt A delas med användarna 1, 2, 3
* Projekt B delas med användare 4, 5, 6
* När du har valt Projekt A och B läggs användare 4 och 7 till i mottagarlistorna. Den nya mottagarlistan för varje projekt är nu:
   * Projekt A: 1, 2, 3, 4, 7
   * Projekt B: 4, 5, 6, 7
   ![](assets/mult-proj-sharing.png)
