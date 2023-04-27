---
description: Projektdelning och projektroller på arbetsytan
keywords: Analysis Workspace-delning
title: Dela projekt
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
source-git-commit: 749088c6e6c100797bd9a2dd1de64d18d45108e5
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 0%

---

# Dela projekt

Du kan dela ett Analysis Workspace-projekt med följande typer av personer:

* Användare och grupper i organisationen som har tillgång till Adobe Customer Journey Analytics

   Du kan dela behörigheten Redigera, Duplicera eller Visa

* Användare och grupper i organisationen som inte har tillgång till Customer Journey Analytics

   Mottagarna har skrivskyddad åtkomst

* Personer utanför din organisation

   Mottagarna har skrivskyddad åtkomst

Alla [kuration](curate.md) används innan delningen visas när mottagarna öppnar projektet.

Här är en videoöversikt över projektdelning:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Dela med användare och grupper i Customer Journey Analytics i din organisation {#Add}

Du kan dela ett projekt med befintliga användare eller grupper på Customer Journey Analytics i organisationen. När du delar ett projekt enligt beskrivningen i det här avsnittet måste de användare du delar med redan ha ett Customer Journey Analytics-konto.

Du kan dela en specifik roll med användare eller grupper eller dela en länk.

* [Dela en specifik projektroll](#share-a-specific-project-role)

* [Dela en länk till ett projekt](#share-a-link-to-a-project)

## Dela en specifik projektroll

När du delar en specifik projektroll med användare och grupper i organisationen bör du tänka på följande:

* Projektroller (**[!UICONTROL Can edit]**, **[!UICONTROL Can duplicate]** och **[!UICONTROL Can view]**) är knutna till användaren och ett specifikt projekt-ID. Projektroller är oberoende av användarbehörigheter som hanteras i [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

* I Customer Journey Analytics definieras grupper efter produktprofiler i [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html). Administratörer kan dela till alla grupper, inklusive&quot;Alla&quot;. Icke-administratörer kan dela till alla grupper som de är medlemmar i, med undantag för&quot;Alla&quot;.

* En användare som placeras i flera roller får alltid den högsta upplevelsen. Detta kan inträffa om en användare läggs till både som en individ och som en del av en grupp. Om en användare till exempel får **[!UICONTROL Can edit]** som individ och **[!UICONTROL Can view]** som medlem i en grupp får de **[!UICONTROL Can edit]** projekterfarenhet.

* Administratörer i **[!UICONTROL Can duplicate]** eller **[!UICONTROL Can view]** får de begränsade upplevelserna när de öppnar ett projekt. En administratör kan vid behov utöka sin roll till **[!UICONTROL Can edit]** när som helst till **[!UICONTROL Components]>[!UICONTROL Projects]**.

Så här delar du en specifik projektroll med användare eller grupper i organisationen:

1. Gå till projektet som du vill dela och klicka sedan på **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**.
Om det finns ändringar som inte har sparats uppmanas du att spara projektet först.

   ![](assets/share-proj-modal.png)

   Mer information om hur du delar flera projekt samtidigt finns i [Dela projekt i projektledaren](#share-projects-in-the-project-manager).

1. Lägg till mottagare eller grupper av mottagare i något av de tillhandahållna rollfälten:

   **Kan redigera:** Mottagarna kan **[!UICONTROL Save]** ändringar i ett projekt och fungerar som medägare. Den här rollen är användbar om du vill samhantera ett projekt med andra kollegor. detta inkluderar redigering, borttagning och ändring av mottagarlistor för ett delat projekt. <br>Obs! Analysis Workspace stöder för närvarande inte live-samarbete, så vi rekommenderar att endast en användare redigerar ett projekt åt gången. Om projekt sparas samtidigt behålls den senaste versionen.

   **Kan duplicera:** Mottagarna kan **[!UICONTROL Save as]** och ha tillgång till den vänstra listen. Projektinteraktioner är inte begränsade i den här rollen. Den här rollen är användbar om du vill dela ett projekt med användare som förstår organisationens data och hur du använder Analysis Workspace, men inte vill att ditt projekt ska ändras.

   **Kan visa:** Mottagarna kan inte **[!UICONTROL Save]** eller **[!UICONTROL Save as]** och inte har tillgång till den vänstra listen. Projektinteraktionen är också begränsad. Den här rollen är användbar om du vill dela ett projekt med användare som inte är lika bekanta med organisationens datastruktur, Analysis Workspace eller Customer Journey Analytics i allmänhet. Men ni vill ändå att de ska konsumera data och insikter i en säker miljö. Läs mer om [Kan visa projekterfarenhet](/help/analysis-workspace/curate-share/view-only-projects.md).

1. Välj om du vill aktivera följande alternativ när du delar projektet:

   * **Dela inbäddade projektkomponenter:** Delar segment, beräknade värden och datumintervall med alla mottagare. När komponenterna har delats visas de i listrutan Komponenter på mottagarens arbetsyta. Den här inställningen kvarstår inte - det är en engångsåtgärd vid tidpunkten för delningen.

   * **Ange som landningssida för mottagare:** Anger den här sidan som startsida för mottagare. Den här inställningen kvarstår inte - det är en engångsåtgärd vid tidpunkten för delningen.

1. Klicka på **[!UICONTROL Share]**. (Om projektet redan har delats klickar du på [!UICONTROL **Uppdatera**].)

   eller

   Klicka **[!UICONTROL Curate and Share]** för att automatiskt lägga in projekturval. (Om projektet redan har delats klickar du på **[!UICONTROL Curate & Update]**.) Läs mer om [projekturval](curate.md).

## Dela en länk till ett projekt

Tänk på följande när du delar en länk enligt beskrivningen i det här avsnittet:

* Mottagare som använder länken måste logga in på Customer Journey Analytics innan de kan komma åt projektet.

* Om en mottagare inte har tilldelats en roll och får en [link](/help/analysis-workspace/curate-share/shareable-links.md) till projektet (**[!UICONTROL Share]>[!UICONTROL Get project link]**) får de en roll som standard. Administratörer får **[!UICONTROL Can edit]** och icke-administratörer får **[!UICONTROL Can duplicate]**.

Så här delar du projektlänken med användare i din organisation:

1. Spara projektet. Om det finns ändringar som inte har sparats uppmanas du att spara projektet innan du delar en länk.

1. Välj **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]** väljer **[!UICONTROL Copy]** bredvid **[!UICONTROL Share by link]** fält.

   ![](assets/share-proj-modal.png)

1. Dela länken med användare i organisationen. Du kan till exempel klistra in den i ett e-postmeddelande, på en intern webbplats och så vidare.

## Dela ett projekt med vem som helst (ingen inloggning krävs) {#share-public-link}

{{release-limited-testing-section}}

Du kan bevilja [skrivskyddad åtkomst](/help/analysis-workspace/curate-share/view-only-projects.md) till Analysis Workspace-projekt för dem som inte har tillgång till Customer Journey Analytics. Detta kan omfatta:

* Personer utanför din organisation

* Personer i din organisation som inte har etablerats med Customer Journey Analytics

>[!NOTE]
>
>Tänk på följande när du delar ett Analysis Workspace-projekt med personer som inte har tillgång till CJA:
>
>* CJA-administratören kan inaktivera möjligheten att dela ett projekt på det här sättet, vilket beskrivs i [Inställningar](/help/analysis-workspace/user-preferences.md). Om du inte kan dela ett projekt enligt beskrivningen i det här avsnittet har CJA-administratören inaktiverat den här möjligheten.
>
>* Projekt med mer än 50 utökade visualiseringar kan inte delas med personer som inte har tillgång till CJA.
>
>* Användare som du delar med kan visa alla filter som använts på projektet under [kuration](curate.md).
> 
>* Användare som du delar med kan ändra projektets datumintervall. Datumintervallet som du anger för projektet visas som standard.


Så här delar du ett Analysis Workspace-projekt med vem som helst:

1. Öppna det Analysis Workspace-projekt som du vill dela.

1. Klicka på **[!UICONTROL Share]** > **[!UICONTROL Share with anyone]**.

   Om det finns ändringar som inte har sparats uppmanas du att spara projektet.

   <!-- Add screen shot of new modal -->

1. Aktivera **[!UICONTROL Link is active]** om det inte redan är aktiverat.

   Om du väljer det här alternativet skapas en länk till projektet som kan delas med alla. Du kan när som helst inaktivera åtkomsten till projektet genom att inaktivera det här alternativet.

   Ägaren till projektet är också ägare till den här länken. Länkägarskap kan endast överföras till en annan användare när projektägarskap överförs, vilket beskrivs i [Överför användarresurser eller ange förfallodatum för konton](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=en) i Analytics Admin Guide.

1. Välj om du vill aktivera följande säkerhetsalternativ (det här alternativet kan styras av CJA-administratören):

   * **[!UICONTROL Require Experience Cloud authentication]:**

      När det här alternativet är aktiverat kan endast användare som kan logga in på den Adobe Experience Cloud-organisation där det projekt som du delar skapades få åtkomst till projektet.

      CJA-administratörer kan konfigurera den här inställningen för företaget enligt beskrivningen i [Inställningar](/help/analysis-workspace/user-preferences.md). Följande scenarier kan visas beroende på hur administratören konfigurerade det här alternativet:

      * Om det här alternativet inte visas har CJA-administratören inte aktiverat den här funktionen.

      * Om det här alternativet är aktiverat och nedtonat kräver CJA-administratören Experience Cloud-autentisering för alla som använder Analysis Workspace-projekt.

1. Intill **[!UICONTROL Share with anyone (no login required)]** klickar du på **Kopiera länk** icon ![Ikon för att kopiera länk](assets/copy-link-icon.png) om du vill kopiera länken till systemets Urklipp.

1. Dela länken med de personer som du vill ska ha tillgång till projektet. Du kan till exempel klistra in länken i ett e-postmeddelande.

   Alla som du delar länken med kan visa Analysis Workspace-projektet.

1. (Valfritt) Du kan klicka på **Generera ny länk** icon ![Skapa länkikon](assets/regenerate-link.png) för att ta bort åtkomst från användare som tidigare har fått en länk till projektet. En ny länk skapas som du kan dela med användare som du vill ska få åtkomst till projektet.

1. Välj **[!UICONTROL Close]** för att stänga delningsdialogrutan. Ändringarna sparas automatiskt.

## Dela projekt i projektledaren {#Manager}

Du kan även dela projekt från **[!UICONTROL Components]>[!UICONTROL Projects]**. Ett enskilt projekt kan delas enligt samma steg ovan.  Om du väljer att dela flera projekt läggs mottagarna till i den befintliga listan med mottagare för varje projekt.

Exempel:

* Projekt A delas med mottagare 1, 2, 3
* Projekt B delas med mottagare 4, 5, 6

När du har valt Projekt A och B läggs mottagarna 4 och 7 till i resurslistorna. Den nya resurslistan för varje projekt är nu:

* Projekt A: 1, 2, 3, 4, 7
* Projekt B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Dela inbäddade komponenter

Här är en video om ämnet:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Vanliga frågor {#FAQs}

| Fråga | Svar |
|---|---|
| Vad händer om två redigerare sparar ett projekt samtidigt? | Ändringarna sammanfogas inte och den senast sparade projektversionen behålls. Analysis Workspace stöder för närvarande inte live-samarbete. |
| Vilken projekterfarenhet vill jag som administratör se? | Administratörer som placerats i en **[!UICONTROL Can duplicate]** eller **[!UICONTROL Can view]** får de begränsade upplevelserna när de öppnar ett projekt. En administratör kan vid behov utöka sin roll till **[!UICONTROL Can edit]** när som helst till **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Vad händer om en mottagare placeras i en roll som enskild person och en annan roll som medlem i en grupp? | Om en mottagare placeras i flera roller får de alltid den högre upplevelsen. Om en mottagare får **[!UICONTROL Can edit]** som individ och **[!UICONTROL Can view]** som medlem i en grupp får de **[!UICONTROL Can edit]** projekterfarenhet. |
| Vilken upplevelse får en mottagare om de öppnar en projektlänk? | Mottagarna får rollen som du placerade dem i den delade modalen. Om en mottagare inte har tilldelats en roll och får en länk till projektet (**[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]** väljer **[!UICONTROL Copy]** bredvid **[!UICONTROL Share by link]** -fält) placeras de som standard i en roll. Administratörer får **[!UICONTROL Can edit]** och icke-administratörer får **[!UICONTROL Can duplicate]**. |
