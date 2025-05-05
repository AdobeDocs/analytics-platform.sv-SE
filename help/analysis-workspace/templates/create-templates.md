---
description: Översikt över hur du använder standardmallar i Analysis Workspace.
title: Använd mallar
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
source-git-commit: f0786cfa74453693078c7d30d647a96bf1d98d07
workflow-type: tm+mt
source-wordcount: '1688'
ht-degree: 0%

---

# Skapa och hantera mallar

Administratörer kan skapa mallar och spara dem så att andra kan använda dem i sina inloggningsföretag.

Personer i inloggningsföretaget kan använda de här företagsmallarna enligt beskrivningen i [Använd mallar](/help/analysis-workspace/templates/use-templates.md).

## Skapa en mall {#create-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="use-case-ajo-template"
>title="Använd mall i Journey Optimizer"
>abstract="När du använder den här mallen i Journey Optimizer används datavyn som är inställd som standarddatavy i Adobe Journey Optimizer, oavsett vilken datavy som är vald med den här mallen i Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Så här skapar du en ny mall som kan användas av personer i ditt inloggningsföretag:

1. I Analysis Workspace skapar du ett projekt i det läge du vill.

1. Välj [!UICONTROL **Projekt**] > **[!UICONTROL Save as template…]**.

   ![Företagsmall](assets/company-template-save.png)

1. Ange följande information i dialogrutan [!UICONTROL Save as template]:

   | Fält | Beskrivning |
   |---------|----------|
   | **[!UICONTROL Name]** | Ange ett beskrivande namn för mallen. |
   | **[!UICONTROL Description]** | Ange en kort beskrivning av mallen som beskriver dess avsedda användning. |
   | **[!UICONTROL Why use this template]** | Ge en kort förklaring för att informera personer i organisationen om hur den här mallen kan användas. Den här förklaringen visas på mallens förhandsgranskningssida. |
   | **[!UICONTROL Channels]** | Välj de kanaler som gäller för den här mallen. Du kan välja flera kanaler: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-channel]**, **[!UICONTROL Call center]** och **[!UICONTROL In-store]**.<p>De val du väljer avgör var mallen visas och vilka segment som gäller för användare som har åtkomst till den från sidan Organisationsmallar.</p> |
   | **[!UICONTROL Use cases]** | Välj de användningsfall som gäller för den här mallen. Du kan välja flera användningsfall: **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]** och **[!UICONTROL Journey Optimizer]**. <p>De val du väljer avgör mallens plats på sidan Organisationsmallar. Användarna kan navigera till mallen eller filtrera listan efter användningsfall. </p><p>**Obs!** När du väljer alternativet **[!UICONTROL Journey Optimizer]** är mallen tillgänglig för användning i Adobe Journey Optimizer. I Journey Optimizer finns en nedrullningsbar meny på sidan **[!UICONTROL Reports]** där användarna kan välja den här mallen eller standardmallen. Mer information finns i [Kom igång med den uppdaterade rapportfunktionen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) i Journey Optimizer-dokumentationen.</p><p>Tänk på följande när du väljer alternativet Journey Optimizer:</p><ul><li>Det här alternativet är bara tillgängligt om det finns Journey Optimizer-data i datavyn som du använder i Customer Journey Analytics.</li><li>När du använder den här mallen i Journey Optimizer används datavyn som är inställd som standarddatavy i Adobe Journey Optimizer, oavsett vilken datavy som är vald med den här mallen i Customer Journey Analytics. <br/>Mer information om hur du anger en datavy som standarddatavy i Journey Optimizer finns i [Kompatibilitet](/help/data-views/create-dataview.md#compatibility) i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).</li></ul> |
   | **[!UICONTROL Journey Optimizer activity type]** | Välj den Journey Optimizer-aktivitetstyp som ska associeras med den här mallen: **[!UICONTROL Campaigns]**, **[!UICONTROL Journeys]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Reports]** eller **[!UICONTROL Subscriptions]**. <p>Lämna fältet tomt om du vill att den här mallen ska kopplas till alla aktivitetstyper.</p><p>Det här fältet visas bara om **[!UICONTROL Journey Optimizer]** har valts i fältet **[!UICONTROL Use cases]**.</p> |
   | **[!UICONTROL Journey Optimizer activity]** | Välj den Journey Optimizer-aktivitet som ska associeras med den här mallen. <p>Lämna det här fältet tomt om du vill att den här mallen ska kopplas till alla aktiviteter av den valda aktivitetstypen.</p><p>Det här fältet visas bara om **[!UICONTROL Journey Optimizer]** har valts i fältet **[!UICONTROL Use cases]**.</p> |
   | **[!UICONTROL Tags]** | Ange de taggar som du vill lägga till i mallen. Användarna kan filtrera listan med mallar efter de taggar du lägger till. |

1. Välj [!UICONTROL **Spara som mall**].

Mer information om hur användare kan skapa ett projekt baserat på en mall finns i [Skapa ett projekt baserat på en mall](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) i [Använda mallar](/help/analysis-workspace/templates/use-templates.md).

## Redigera eller ta bort en mall

Administratörer kan redigera eller ta bort företagsmallar.

1. I Analysis Workspace väljer du fliken [!UICONTROL **Workspace**] och sedan **[!UICONTROL _login_company_name _-mallar]**&#x200B;under **[!UICONTROL Templates]**&#x200B;i den vänstra listen.

1. Om du visar mallar i en kolumnvy ![kolumnvisningsikon](assets/column-view-icon.png):

   1. Gå till mallen som du vill redigera eller ta bort och välj informationsikonen bredvid mallnamnet.

      ![Information om företagsmall](assets/company-template-info.png)

   1. Välj **[!UICONTROL Preview]**.

   1. Välj ikonen Mer och välj sedan **[!UICONTROL Edit]** eller **[!UICONTROL Delete]**.

      ![Redigera eller ta bort mall](assets/company-template-edit-delete.png)

1. Om du visar mallar i en kortvy ![visas ikonen för kortvyn](assets/card-view-icon.png):

   1. Leta reda på mallen som du vill redigera eller ta bort.

      ![Vyn Företagsmallkort](assets/company-template-cards.png)

   1. Håll markören över mallen och välj sedan **[!UICONTROL Preview]**.

   1. Välj ikonen Mer och välj sedan **[!UICONTROL Edit]** eller **[!UICONTROL Delete]**.

      ![Redigera eller ta bort företagsmallkort](assets/company-template-card-edit-delete.png)

1. Om du redigerar en mall gör du önskade ändringar och väljer sedan [!UICONTROL **Projekt**] > **[!UICONTROL Save as template…]**.

   ![Företagsmall](assets/company-template-save.png)

1. Ange följande information i dialogrutan [!UICONTROL Save as template]:

   | Fält | Beskrivning |
   |---------|----------|
   | **[!UICONTROL Name]** | Ange ett beskrivande namn för mallen. |
   | **[!UICONTROL Description]** | Ange en kort beskrivning av mallen som beskriver dess avsedda användning. |
   | **[!UICONTROL Why use this template]** | Ge en kort förklaring för att informera personer i organisationen om hur den här mallen kan användas. Den här förklaringen visas på mallens förhandsgranskningssida. |
   | **[!UICONTROL Channels]** | Välj de kanaler som gäller för den här mallen. Du kan välja flera kanaler: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-channel]**, **[!UICONTROL Call center]** och **[!UICONTROL In-store]**. Om inga kanaler är markerade inkluderas mallen i alla kanaler.<p>De val du väljer avgör var mallen visas och vilka filter som gäller för användare som använder den från sidan Organisationsmallar.</p> |
   | **[!UICONTROL Use cases]** | Välj de användningsfall som gäller för den här mallen. Du kan välja flera användningsfall: **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]** och **[!UICONTROL Journey Optimizer]**. <p>De val du väljer avgör mallens plats på sidan Organisationsmallar. Användarna kan navigera till mallen eller filtrera listan efter användningsfall. </p><p>**Obs!** När du väljer alternativet **[!UICONTROL Journey Optimizer]** är mallen tillgänglig för användning i Adobe Journey Optimizer. I Journey Optimizer finns en nedrullningsbar meny på sidan **[!UICONTROL Reports]** där användarna kan välja den här mallen eller standardmallen. Mer information finns i [Kom igång med den uppdaterade rapportfunktionen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) i Journey Optimizer-dokumentationen.</p><p>Tänk på följande när du väljer alternativet Journey Optimizer:</p><ul><li>Det här alternativet är bara tillgängligt om det finns Journey Optimizer-data i datavyn som du använder i Customer Journey Analytics.</li><li>När du använder den här mallen i Journey Optimizer används datavyn som är inställd som standarddatavy i Adobe Journey Optimizer, oavsett vilken datavy som är vald med den här mallen i Customer Journey Analytics. <br/>Mer information om hur du anger en datavy som standarddatavy i Journey Optimizer finns i [Kompatibilitet](/help/data-views/create-dataview.md#compatibility) i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).</li></ul> |
   | **[!UICONTROL Journey Optimizer activity type]** | Välj den Journey Optimizer-aktivitetstyp som ska associeras med den här mallen: **[!UICONTROL Campaigns]**, **[!UICONTROL Journeys]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Reports]** eller **[!UICONTROL Subscriptions]**. <p>Lämna fältet tomt om du vill att den här mallen ska kopplas till alla aktivitetstyper.</p><p>Det här fältet visas bara om **[!UICONTROL Journey Optimizer]** har valts i fältet **[!UICONTROL Use cases]**.</p> |
   | **[!UICONTROL Journey Optimizer activity]** | Välj den Journey Optimizer-aktivitet som ska associeras med den här mallen. <p>Lämna det här fältet tomt om du vill att den här mallen ska kopplas till alla aktiviteter av den valda aktivitetstypen.</p><p>Det här fältet visas bara om **[!UICONTROL Journey Optimizer]** har valts i fältet **[!UICONTROL Use cases]**.</p> |
   | **[!UICONTROL Tags]** | Ange de taggar som du vill lägga till i mallen. Användarna kan filtrera listan med mallar efter de taggar du lägger till. |

1. Välj [!UICONTROL **Spara som mall**].

## Byta namn på, tagga eller godkänna mallar

Administratörer kan byta namn på, tagga och godkänna företagsmallar.

1. I Analysis Workspace väljer du fliken [!UICONTROL **Workspace**] och sedan **[!UICONTROL Projects tab]** i den vänstra listen.

1. Markera filterikonen om du vill filtrera listan med projekt.

1. Markera **[!UICONTROL Other filters]** i filterfältet och välj sedan **[!UICONTROL Company templates]**.

   En lista över företagsmallar visas. Alla vanliga projekt visas inte, såvida de inte är fästa.

   Företagsmallar kan identifieras med hjälp av ![mallikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) som föregår mallnamnet.

   ![Visa företagsmallfilter](assets/company-templates-filter.png)

1. Klicka på ikonen **..** bredvid en mall för att visa tillgängliga alternativ.

   ![Åtgärder för företagsmallar](assets/company-templates-actions.png)

1. Välj **[!UICONTROL Rename]**, **[!UICONTROL Tag]** eller **[!UICONTROL Approve]**.

   Du kan också ta bort en mall eller så kan du ta bort en mall enligt beskrivningen i [Redigera eller ta bort mallar](#edit-or-delete-templates).

1. (Valfritt) Om du vill återgå till den vanliga vyn avmarkerar du **[!UICONTROL Company templates]** i filterfältet.

## Lägga till saknade komponenter i datavyn för en viss mall

Som standard kan vissa mallar från Adobe inte användas eftersom de innehåller komponenter som inte finns i datavyn.

För varje komponent som saknas finns en matchande sammanhangsetikett tillgänglig i datavyn. Du måste antingen lägga till den matchande kontextetiketten i en komponent som redan finns i datavyn, eller så måste du lägga till en ny komponent i datavyn och lägga till kontextetiketten i den.

Så här lägger du till saknade komponenter i en mall:

1. I Analysis Workspace väljer du fliken [!UICONTROL **Workspace**] och sedan **[!UICONTROL Adobe templates]** under **[!UICONTROL Templates]** i den vänstra listen.

1. Markera filterikonen om du vill filtrera listan med mallar.

1. Välj **[!UICONTROL Not ready for use]** om du vill visa mallar som kräver komponenter som inte finns i datavyn.

   ![Använd en mall som saknar komponenter](assets/template-not-ready.png)

1. Leta upp en mall som ännu inte är klar att användas med datavyn.

1. Gör något av följande:

   * **Om du visar mallar i en kolumnvy** ![ikon för kolumnvy](assets/column-view-icon.png):

      1. Gå till mallen som ännu inte är klar att användas med datavyn och välj sedan informationsikonen bredvid mallnamnet.

         ![Information om företagsmall](assets/company-template-info.png)

      1. Välj **[!UICONTROL Preview]**.

         ![Förhandsgranskningssida för mall](assets/template-preview.png)

   * **Om du visar mallar i en kortvy** ![ikonen för kortvyn](assets/card-view-icon.png):

      1. Leta reda på mallen som ännu inte är klar att användas med datavyn.

         ![Vyn Företagsmallkort](assets/company-template-cards.png)

      1. Håll markören över mallen och välj sedan **[!UICONTROL Preview]**.

         ![Förhandsgranskningssida för mall](assets/template-preview.png)

1. I avsnittet **[!UICONTROL Missing components]** visas en lista med komponenter som saknas i datavyn. Välj **[!UICONTROL Add these components to your data view]**.

   Konfigurationssidan för datavyn visas på en ny flik.

1. Välj fliken **[!UICONTROL Components]** för datavyn.

   ![Fliken Komponenter i datavy](assets/template-dataview.png)

1. Gör något av följande på fliken **[!UICONTROL Components]** för varje komponent som har listats som saknad i mallen:

   * I avsnittet **[!UICONTROL Included components]** väljer du en komponent som redan finns i datavyn som du vill använda för den komponent som saknas.

   * Lägg till en ny komponent i datavyn som du vill använda för den saknade komponenten och markera sedan komponenten.

     Om du vill lägga till en ny komponent i datavyn söker du i listan med schemafält och drar den till avsnittet **[!UICONTROL Included components]**.

1. Med komponenten markerad letar du reda på den nedrullningsbara menyn **[!UICONTROL Context labels]** i den högra kolumnen.

   ![Fliken Komponenter i datavy](assets/template-dataview-context-label.png)

1. I listrutan **[!UICONTROL Context labels]** väljer du den sammanhangsetikett som har samma namn som den komponent som saknas.

1. Välj **[!UICONTROL Save and continue]**.

1. För varje komponent som saknas upprepar du processen att lägga till den matchande kontextetiketten till en komponent i datavyn.


## Åtkomst till en företagsmall

Precis som med mallar från Adobe kan användare i organisationen komma åt mallar som administratörer skapar.

Mer information om hur du får åtkomst till en företagsmall finns i [Åtkomst till och kör en mall](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) i [Använd mallar](/help/analysis-workspace/templates/use-templates.md).

## Dölj fliken Mallar

Administratörer kan dölja fliken Mallar för alla användare i organisationen.

1. Gå till **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Preferences]** > **[!UICONTROL Company]**.
1. Välj alternativet för **[!UICONTROL Hide Templates tab]**.
