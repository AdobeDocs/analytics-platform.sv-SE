---
description: Projektdelning och projektroller på arbetsytan
keywords: Analysis Workspace-delning
title: Dela projekt
feature: Curate and Share
exl-id: ac4ed73a-e890-46cc-be08-4ccedf66b47d
role: User
source-git-commit: 534f163230ea7cafc97948fe0e8196d1dea47fa8
workflow-type: tm+mt
source-wordcount: '1994'
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

Alla [kuration](curate.md) som du tillämpar innan delningen visas när mottagarna öppnar projektet.

Här är en videoöversikt över projektdelning:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Dela med användare och grupper i Customer Journey Analytics i din organisation {#Add}

Du kan dela ett projekt med befintliga användare eller grupper på Customer Journey Analytics i organisationen. När du delar ett projekt enligt beskrivningen i det här avsnittet måste de användare du delar med redan ha ett Customer Journey Analytics-konto.

Du kan dela en specifik roll med användare eller grupper eller dela en länk.

* [Dela en specifik projektroll](#share-a-specific-project-role)

* [Dela en länk till ett projekt](#share-a-link-to-a-project)

## Dela en specifik projektroll

När du delar en specifik projektroll med användare och grupper i organisationen bör du tänka på följande:

* Projektroller (**[!UICONTROL Edit original]**, **[!UICONTROL Edit copy]** och **[!UICONTROL Read only]**) är knutna till användaren och ett specifikt projekt-ID. Projektroller är oberoende av användarbehörigheter som hanteras i [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

* I Customer Journey Analytics definieras grupper efter produktprofiler i [Adobe Experience Cloud Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html). Administratörer kan dela till vilken grupp som helst, inklusive&quot;Alla&quot;. Icke-administratörer kan dela till alla grupper som de är medlemmar i, med undantag för&quot;Alla&quot;.

* En användare som placeras i flera roller får alltid den högsta upplevelsen. Detta kan inträffa om en användare läggs till både som en individ och som en del av en grupp. Om en användare till exempel får **[!UICONTROL Edit original]** som individ och **[!UICONTROL Read only]** som medlem i en grupp får de **[!UICONTROL Edit original]** projekterfarenhet.

* Administratörer i **[!UICONTROL Edit copy]** eller **[!UICONTROL Read only]** får de begränsade upplevelserna när de öppnar ett projekt. En administratör kan ändra sin roll till **[!UICONTROL Edit original]** genom att dela projektet med sig själva och bevilja redigeringsrollen enligt beskrivningen i följande procedur.

* Om du väljer att dela flera projekt läggs mottagarna till i den befintliga listan med mottagare för varje projekt.

  Projekt A delas till exempel redan med mottagare 1, 2 och 3, medan projekt B redan delas med mottagare 4, 5 och 6.

  Projekten A och B delas sedan med mottagarna 4 och 7. Den nya resurslistan för projekt A är nu 1, 2, 3, 4 och 7, medan den nya resurslistan för projekt B är 4, 5, 6 och 7.

Så här delar du en specifik projektroll med användare eller grupper i organisationen:

1. I Customer Journey Analytics väljer du [!UICONTROL **Arbetsyta**] tabbtangenten och sedan välja [!UICONTROL **Projekt**] till vänster.

1. Markera kryssrutan bredvid ett eller flera projekt som du vill dela och markera sedan [!UICONTROL **Dela**].

   eller

   Om du bara vill dela ett enskilt projekt kan du öppna det projekt som du vill dela och sedan välja **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**.
Om det finns ändringar som inte har sparats uppmanas du att spara projektet först.

   Dialogrutan Dela projekt visas. The [!UICONTROL **Dela via länk**] och [!UICONTROL **Inställningar**] -avsnitt i dialogrutan visas bara när du delar ett projekt.

   ![Dela projektfönstret.](assets/share-proj-modal.png)

1. Lägg till mottagare eller grupper av mottagare i något av de tillhandahållna rollfälten:

   **Redigera original:** Mottagarna kan **[!UICONTROL Save]** ändringar i ett projekt och fungerar som medägare. Den här rollen är användbar om du vill samhantera ett projekt med andra kollegor. Detta inkluderar redigering, borttagning och ändring av mottagarlistor för ett delat projekt. <br>Obs! Analysis Workspace stöder för närvarande inte live-samarbete, så vi rekommenderar att endast en användare redigerar ett projekt åt gången. Om projekt sparas samtidigt behålls den senaste versionen.

   **Redigera kopia:** Mottagarna kan **[!UICONTROL Save as]** och ha tillgång till den vänstra listen. Projektinteraktioner är inte begränsade i den här rollen. Den här rollen är användbar om du vill dela ett projekt med användare som förstår organisationens data och hur du använder Analysis Workspace, men du inte vill att ditt projekt ska ändras.

   **Skrivskyddad:** Mottagarna kan inte **[!UICONTROL Save]** eller **[!UICONTROL Save as]** och inte har tillgång till den vänstra listen. Projektinteraktionen är också begränsad. Den här rollen är användbar om du vill dela ett projekt med användare som inte är lika bekanta med organisationens datastruktur, Analysis Workspace eller Customer Journey Analytics i allmänhet. Men ni vill ändå att de ska konsumera data och insikter i en säker miljö. Läs mer om [Skrivskyddad projekterfarenhet](/help/analysis-workspace/curate-share/view-only-projects.md).

1. (Villkorligt) Om du delar ett projekt ska du välja om du vill aktivera följande alternativ när du delar projektet:

   * **Dela inbäddade projektkomponenter:** Delar filter, beräknade värden och datumintervall med alla mottagare. När komponenterna har delats visas de i listrutan Komponenter på mottagarens arbetsyta. Den här inställningen kvarstår inte - det är en engångsåtgärd vid tidpunkten för delningen.

   * **Ange som landningssida för mottagare:** Anger den här sidan som landningssida för mottagare. Den här inställningen kvarstår inte - det är en engångsåtgärd vid tidpunkten för delningen.

1. Välj **[!UICONTROL Share]**. (Om projektet redan har delats väljer du [!UICONTROL **Uppdatera**].)

   eller

   Välj **[!UICONTROL Curate and Share]** för att automatiskt lägga in projekturval. (Om projektet redan har delats väljer du **[!UICONTROL Curate & Update]**.) Läs mer om [projekturval](curate.md).

## Dela en länk till ett projekt

Tänk på följande när du delar en länk enligt beskrivningen i det här avsnittet:

* Mottagare som använder länken måste logga in på Customer Journey Analytics innan de kan komma åt projektet.

* Om en mottagare inte har tilldelats en roll och får en [link](/help/analysis-workspace/curate-share/shareable-links.md) till projektet (**[!UICONTROL Share]>[!UICONTROL Get project link]**) får de en roll som standard. Administratörer får **[!UICONTROL Edit original]** och icke-administratörer får **[!UICONTROL Edit copy]**.

Så här delar du projektlänken med användare i din organisation:

1. Spara projektet. Om det finns ändringar som inte har sparats uppmanas du att spara projektet innan du delar en länk.

1. Välj **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]** väljer **[!UICONTROL Copy]** bredvid **[!UICONTROL Share by link]** fält.

   ![Dela-projektet markerar fältet Dela efter länk.](assets/share-proj-modal.png)

1. Dela länken med användare i organisationen. Du kan till exempel klistra in den i ett e-postmeddelande, på en intern webbplats och så vidare.

## Dela ett projekt med vem som helst (ingen inloggning krävs) {#share-public-link}

Du kan bevilja [skrivskyddad åtkomst](/help/analysis-workspace/curate-share/view-only-projects.md) till Analysis Workspace-projekt för dem som inte har tillgång till Customer Journey Analytics. Detta kan omfatta:

* Personer utanför din organisation

* Personer i din organisation som inte har tillgång till Customer Journey Analytics

>[!NOTE]
>
>Tänk på följande när du delar ett Analysis Workspace-projekt med personer som inte har tillgång till Customer Journey Analytics:
>
>* Customer Journey Analytics-administratören kan inaktivera möjligheten att dela ett projekt på det här sättet enligt beskrivningen i [Inställningar](/help/analysis-workspace/user-preferences.md). Om du inte kan dela ett projekt enligt beskrivningen i det här avsnittet har Customer Journey Analytics-administratören inaktiverat den här möjligheten.
>
>* Projekt med mer än 50 utökade visualiseringar kan inte delas med personer som inte har tillgång till Customer Journey Analytics.
>
>* Användare som du delar med kan visa alla filter som använts på projektet under [kuration](curate.md).
> 
>* Användare som du delar med kan ändra projektets datumintervall. Datumintervallet som du anger för projektet visas som standard.
>
>* Ett projekt kan bli oåtkomligt om många användare försöker få åtkomst till en viss länk samtidigt. Som standard har fler än 190 personer tillgång till en enda länk var femte minut. Om din organisation når den gränsen väntar du i fem minuter och försöker sedan att få åtkomst till länken igen.
>
>* Om din organisation licensierar hälsovård kan du bara dela projekt med användare som har autentiserats antingen med enkel inloggning (SSO) eller Adobe ID. Du kan inte dela projekt med oautentiserade användare. Det är ditt ansvar att använda den här funktionen i enlighet med ditt företags interna datastyrningspolicyer och endast dela projektlänkar som innehåller personlig hälsoinformation (PHI) med användare som har rätt behörigheter.

I följande videodemonstration och medföljande dokumentation beskrivs alternativen för att dela en länk med vem som helst:

>[!VIDEO](https://video.tv.adobe.com/v/3420093/?learn=on)

Så här delar du ett Analysis Workspace-projekt med vem som helst:

1. Öppna det Analysis Workspace-projekt som du vill dela.

1. Klicka **[!UICONTROL Share]** > **[!UICONTROL Share with anyone]**.

   Om det finns ändringar som inte har sparats uppmanas du att spara projektet.

   <!-- Add screen shot of new modal -->

1. Aktivera **[!UICONTROL Link is active]** om det inte redan är aktiverat.

   Om du väljer det här alternativet skapas en länk till projektet som kan delas med alla. Du kan när som helst inaktivera åtkomsten till projektet genom att inaktivera det här alternativet.

   Ägaren till projektet är också ägare till den här länken. Länkägarskap kan endast överföras till en annan användare när projektägarskap överförs, vilket beskrivs i [Överför användarresurser eller ange förfallodatum för konton](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/user-product-management/users-assets.html?lang=en) i Analytics Admin Guide.

1. Välj om du vill aktivera följande säkerhetsalternativ (det här alternativet kan styras av Customer Journey Analytics-administratören):

   * **[!UICONTROL Require Experience Cloud authentication]:**

     När det här alternativet är aktiverat är de enda användare som har åtkomst till projektet de som kan logga in på den Adobe Experience Cloud-organisation där det projekt som du delar skapades. De användare du delar med behöver dock inte ha tillgång till Adobe Analytics.

     Customer Journey Analytics-administratörer kan konfigurera den här inställningen för företaget enligt beskrivningen i [Inställningar](/help/analysis-workspace/user-preferences.md). Följande scenarier kan visas beroende på hur administratören konfigurerade det här alternativet:

      * Om det här alternativet inte visas har Customer Journey Analytics-administratören inte aktiverat den här funktionen.

      * Om det här alternativet är aktiverat och du inte kan inaktivera det, innebär det att Customer Journey Analytics-administratören kräver Experience Cloud-autentisering för alla som använder Analysis Workspace-projekt. Detta gäller alltid för organisationer som skaffat ett vårdcertifikat.

1. Intill **[!UICONTROL Share with anyone (no login required)]** klickar du på **Kopiera länk** icon ![Ikon för att kopiera länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg)) för att kopiera länken till systemets Urklipp.

1. Dela länken med de personer som du vill ska ha tillgång till projektet. Du kan till exempel klistra in länken i ett e-postmeddelande.

   Alla som du delar länken med kan visa Analysis Workspace-projektet.

1. (Valfritt) Klicka på **Generera ny länk** icon ![Skapa länkikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) för att ta bort åtkomst från användare som tidigare har fått en länk till projektet. En ny länk skapas som du kan dela med användare som du vill ska få åtkomst till projektet.

1. Välj **[!UICONTROL Close]** för att stänga delningsdialogrutan. Ändringarna sparas automatiskt.

## Visa projekt som delas med dig

När någon delar ett projekt med dig av [dela en specifik projektroll](#share-a-specific-project-role)kan du komma åt de delade projekten från [Fliken Projekt på landningssidan för Analytics](/help/getting-started/landing.md#navigate-the-projects-tab).

När någon delar ett projekt med dig genom att dela en länk (antingen från [Dela projektflik](#share-a-link-to-a-project) eller använda en [dela med alla länkar](#share-a-project-with-anyone-no-login-required)) måste du använda länken som delades med dig för att få åtkomst till projektet. Länken kan till exempel ha delats i ett e-postmeddelande, på en intern webbplats och så vidare.

## Dela inbäddade komponenter

Här är en video om ämnet:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Vanliga frågor {#FAQs}

| Fråga | Svar |
|---|---|
| Vad händer om två redigerare sparar ett projekt samtidigt? | Ändringarna sammanfogas inte och den senast sparade projektversionen behålls. Analysis Workspace stöder för närvarande inte live-samarbete. |
| Vilken projekterfarenhet vill jag som administratör se? | Administratörer som placerats i en **[!UICONTROL Edit copy]** eller **[!UICONTROL Read only]** får de begränsade upplevelserna när de öppnar ett projekt. En administratör kan vid behov utöka sin roll till **[!UICONTROL Edit original]** när som helst till **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Vad händer om en mottagare placeras i en roll som enskild person och en annan roll som medlem i en grupp? | Om en mottagare placeras i flera roller får de alltid den högre upplevelsen. Om en mottagare får **[!UICONTROL Edit original]** som individ och **[!UICONTROL Can view]** som medlem i en grupp får de **[!UICONTROL Edit original]** projekterfarenhet. |
| Vilken upplevelse får en mottagare om de öppnar en projektlänk? | Mottagarna får rollen som du placerade dem i den delade modala rollen. Om en mottagare inte har tilldelats en roll och får en länk till projektet (**[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]** väljer **[!UICONTROL Copy]** bredvid **[!UICONTROL Share by link]** -fält) kommer de att placeras i en roll som standard. Administratörer får **[!UICONTROL Edit original]** och icke-administratörer får **[!UICONTROL Edit copy]**. |
