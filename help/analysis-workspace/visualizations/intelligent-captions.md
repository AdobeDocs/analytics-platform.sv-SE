---
description: Använd intelligenta bildtexter för att generera insikter på naturens språk för att snabbt identifiera trender inom visualiseringar.
title: Intelligenta bildtexter
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 6a193f2fd179809afac6808f3fb958c020f53a8d
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 0%

---

# Intelligenta bildtexter

Intelligenta bildtexter använder avancerad maskininlärning och generativ AI för att ge värdefulla insikter på naturspråket för Workspace-visualiseringar. Den första versionen innehåller automatiskt genererade insikter för visualiseringen [Line](line.md). Andra visualiseringar följer.

Intelligenta bildtexter inriktas på följande:

* Analytiker som behöver berättelser att dela med andra användare. Analytikerna behöver dessa insikter för att kunna ge sina användare kontext.
* Affärsanvändare som snabbt vill upptäcka högnivåaktiviteter.

Bildtexter är tillgängliga för alla Customer Journey Analytics-användare och kräver ingen särskild behörighet.

## Starta intelligenta bildtexter {#launch}

Om du vill starta automatiskt genererade bildtexter för en radvisualisering klickar du på ikonen **[!UICONTROL Intelligent captions]** längst upp till höger i visualiseringen.

![Startanalysfönstret som visar trenden för intelligenta bildtexter för produktvyer. ](assets/intell-caps-1.png)

Naturliga språkkunskaper genereras nu.

Kom ihåg

* Du behöver minst 3 datapunkter för att kunna generera bildtexter. Annars kan du få ett fel som **[!UICONTROL Not enough data to analyze]**.

* Bildtexter genereras varje gång underliggande markerade data ändras i tabellen som styr visualiseringen.

* Om det finns flera mätvärden i tabellen, genereras bildtexter endast för det första mätvärdet eller det mätvärde som användaren har valt.

* Om du sparar projektet vid en viss punkt och läser in det igen senare, uppdateras bildtexterna automatiskt med nya data. Detsamma gäller för schemalagda projekt och PDF-filer som exporteras från ett projekt.

Här är ett exempel på hur intelligenta bildtexter kan se ut:

![Intelligenta bildtexter för linjevisualisering, inklusive Seasonality, Min, Max, Spike och Decline.](assets/captions.png)

## Åtgärder

Du kan utföra följande åtgärder på intelligenta bildtexter:

### Kopiera till Urklipp {#copy}

Du kan kopiera bildtexterna till ett urklipp och klistra in dem i en PowerPoint eller andra verktyg. Välj ![Kopiera bildtexter till urklipp](/help/assets/icons/Copy.svg) längst upp till höger i dialogrutan med bildtexter.

### Redigera visning {#edit}

Du kan redigera visningen av bildtexter, till exempel dölja eller visa en viss kategori med insikter.

1. Välj ![Redigera visning av intelligenta bildtexter](/help/assets/icons/EditInLight.svg) i dialogrutan Intelligenta bildtexter.

1. Växla mellan ![Synlighet](/help/assets/icons/Visibility.svg) om du vill visa en specifik insikt (som **[!UICONTROL Min]**) eller ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) om du vill dölja en specifik insikt (som **[!UICONTROL Spike]**).

   ![Redigera intelligenta bildtexter](assets/edit-intelligent-captions.png)

1. Välj **[!UICONTROL Apply]**.


### Ge feedback

Du kan ge feedback på de genererade intelligenta bildtexterna.

1. Välj ![Fler åtgärder](/help/assets/icons/More.svg) i dialogrutan Intelligenta bildtexter.

1. Välj ![Bra svar](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Good response]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Bad response]** eller ![Flag](/help/assets/icons/Flag.svg) **[!UICONTROL Report]**.

1. Ange din feedback i dialogrutan **[!UICONTROL Thank you for your feedback]** och välj **[!UICONTROL Submit]** för att skicka den.

### Exportera {#export}

Du kan exportera intelligenta bildtexter som en del av PDF, förutsatt att projektet sparas med de intelligenta bildtexter som skapas.

### Växla av {#toggle}

Om du inte vill visa intelligenta bildtexter kan du inaktivera funktionen.

1. Gå till [Visualiseringsinställningar](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Avmarkera **[!UICONTROL Show intelligent captions]**.

   ![Alternativ för linjevisualisering som visar alternativet att avmarkera Visa intelligenta bildtexter.](assets/toggle-captions.png)

1. Välj **[!UICONTROL Save]** om du vill spara inställningen.


## Intelligenta bildtexter i Mobile Scorecards

Intelligenta bildtexter finns också i [mobilstyrkort](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) i Customer Journey Analytics.

## Funktionsåtkomst

Följande parametrar styr åtkomsten till intelligenta bildtexter:

* **Åtkomst till lösning**: Funktionen för intelligenta bildtexter är tillgänglig i Customer Journey Analytics, men inte i Adobe Analytics.

* **Kontraktsåtkomst**: Om du inte kan använda intelligenta bildtexter kontaktar du organisationens administratör eller Adobe-kontorepresentant. Innan du kan använda Intelligent i din organisation måste du godkänna vissa GenAI-relaterade juridiska villkor.

* **Behörigheter**: I [!UICONTROL Adobe Admin Console] avgör behörigheten [!UICONTROL Reporting Tools] **[!UICONTROL Intelligent Captions]** åtkomsten. En [produktprofiladministratör](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) måste följa de här stegen i [!UICONTROL Admin Console]:
   1. Navigera till **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**.
   1. Välj namnet på den produktprofil som du vill ge tillgång till intelligenta bildtexter för.
   1. Välj **[!UICONTROL Permissions]** i den specifika produktprofilen.
   1. Välj ![Redigera](/help/assets/icons/Edit.svg) om du vill redigera **[!UICONTROL Reporting Tools]**.
   1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) om du vill lägga till **Intelligent Captions** i **[!UICONTROL Included permission items]**.

      ![Lägg till behörighet](./assets/intelligent-captions-permissions.png)

   1. Välj **[!UICONTROL Save]** om du vill spara behörigheterna.

Mer information finns i [Åtkomstkontroll](/help/technotes/access-control.md#access-control).
