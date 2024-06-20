---
title: Skapa hyperlänkar i en frihandstabell i Analysis Workspace
description: Lär dig skapa hyperlänkar för dimensionsobjekt i en frihandstabell i Analysis Workspace
feature: Visualizations
role: User
exl-id: 24fc2d24-b8c2-4664-8b9c-beda284f9033
source-git-commit: 0c83d64a2ab3d23f92bc804092fc507479418052
workflow-type: tm+mt
source-wordcount: '1730'
ht-degree: 0%

---

# Skapa hyperlänkar för dimensioner i en frihandstabell

Du kan skapa hyperlänkar för dimensionsobjekt för att göra dem klickbara i en frihandstabell i Analysis Workspace.

Den här funktionen är särskilt användbar när du skapar hyperlänkar för följande typer av dimensionsobjekt:

* Dimensioner som har URL-värden som du vill länka till (till exempel en sidURL-dimension)

* Dimensioner som innehåller uppdelningar som har URL-värden som du vill länka till (t.ex. en sidnamnsdimension som har en nedbrytning av sidans URL-dimension)

* Dimension av objekt eller uppdelningar som har värden som är en del av en URL som du vill länka till (t.ex. en sidnamnsdimension som är en del av en URL)

## Skapa hyperlänkar för ett eller flera dimensionsobjekt

Tänk på följande när du skapar hyperlänkar för dimensionsobjekt:

* De hyperlänkar du skapar lagras på frihandstabellen i Analysis Workspace-projektet. Hyperlänkar bevaras inte när samma dimension eller dimensionsobjekt används i en annan tabell eller i ett annat projekt.

* Om du ändrar datavyn för frihandstabellen är alla hyperlänkar som skapades för dimensioner eller dimensionsobjekt i tabellen fortfarande tillgängliga, förutsatt att dimensionen finns i datavyn.

* URL:er kontrolleras inte om de är giltiga när du skapar hyperlänken.

  Om du skapar en hyperlänk som har en ogiltig URL, eller om du skapar en hyperlänk som refererar till ett dimensionsobjekt som inte har något URL-värde (genom att referera dimensionsobjektet direkt eller med `$value` eller `$breakdown` -variabler) kommer användare som klickar på hyperlänken att se ett felmeddelande om att URL:en är ogiltig.

* Hyperlänkar som skapas för ett enskilt dimensionsobjekt åsidosätter hyperlänkar som skapas på dimensionen.

* Hyperlänkar fungerar inte i [hämtade PDF-filer](/help/analysis-workspace/export/download-send.md).

Så här skapar du hyperlänkar för ett eller flera dimensionsobjekt:

1. Gör något av följande i en frihandstabell i Analysis Workspace:

   * **Skapa en hyperlänk för ett enskilt dimensionsobjekt:** Högerklicka på dimensionsobjektet i tabellen som du vill skapa hyperlänken för och välj sedan [!UICONTROL **Skapa hyperlänk**].

     ![Skapa hyperlänk för ett enskilt dimensionsobjekt](assets/hyperlink-single-add.png)

     The [!UICONTROL **Skapa hyperlänk**] visas. Namnet på dimensionsobjektet som du skapar en hyperlänk för visas i dialogrutan.

     ![Skapa hyperlänk för en enskild objektdialogruta](assets/hyperlink-dialog-single.png)

   * **Skapa hyperlänkar för alla dimensionsobjekt i en dimensionskolumn:** Högerklicka på dimensionsnamnet i dimensionskolumnens rubrik och välj sedan [!UICONTROL **Skapa hyperlänkar för alla dimensionsobjekt**].

     ![Skapa hyperlänk för en dimension](assets/hyperlink-multiple-add.png)

     The [!UICONTROL **Skapa hyperlänkar för alla dimensionsobjekt**] visas. Namnet på dimensionen som du skapar hyperlänkar för visas i dialogrutan.

     ![Dialogrutan Skapa hyperlänkar](assets/hyperlink-dialog-multiple.png)

1. Välj bland följande alternativ:

   * [!UICONTROL **Använd värdet för dimensionsobjektet som URL**]: Välj det här alternativet för dimensionsobjekt som har URL-värden, t.ex. sidans URL-dimension.

     Om du till exempel använder en sidadress där värdet för varje dimensionsobjekt är en URL, skapas en hyperlänk till URL:en om du väljer det här alternativet.

   * [!UICONTROL **Skapa en anpassad URL**]: Ange en statisk eller dynamisk anpassad URL. Välj det här alternativet om du vill skapa hyperlänkar för dimensionsobjekt som inte har URL-värden.

     Om du till exempel använder en sidnamnsdimension där värdet för varje dimensionsobjekt är namnet på en sida (och inte en fullständig URL), kan du med det här alternativet ange en hyperlänk som ska användas som länk för dimensionsobjektet.

     Om du vill skapa dynamiska URL:er för flera dimensionsobjekt kan du använda `$value` och `$breakdown` variabler i din anpassade URL. Se tabellen nedan för mer information.

     Om du vill skapa en anpassad URL-adress anger du följande information:

     | Fält | Beskrivning |
     |---------|----------|
     | [!UICONTROL **Anpassad URL**] | Ange en anpassad URL som du vill använda för hyperlänken. URL:er måste anges som kvalificerade URL:er. Till exempel: https://www.example.com<p>Den anpassade URL som du skapar kan vara statisk eller dynamisk:</p> <ul><li>**Statiska URL:er:** Om du skapar en hyperlänk för ett enskilt dimensionsobjekt kan det räcka med en statisk URL. <p>Tänk på följande exempel: Om du till exempel har ett sidobjekt kan du skapa en statisk URL som länkar användare till den specifika webbsida som du vill koppla till sidnamnet.</p><p>Anta att du vill skapa hyperlänkar för en lista med dimensionsobjekt, där alla länkar till respektive definition i dokumentationen på en intern wiki-sida.</p><p>Du kan uppnå detta genom att skapa en statisk URL för varje dimensionsobjekt. Exempel:</p><p>https://wiki.internal.company_name/page_name#item_definition</p></li><li>**Dynamiska URL-adresser:** Om du skapar en hyperlänk för flera dimensionsobjekt eller för alla dimensionsobjekt i en dimensionskolumn, är det troligtvis mer praktiskt med en dynamisk URL. <p>Om du vill göra anpassade URL-adresser dynamiska inkluderar du variabler i URL-adressen som gör att URL-adressen kan ändras dynamiskt baserat på värdet för själva dimensionen eller värdet för detaljdimensionen.</p><p>När du använder variabler är dimensionsobjekt som innehåller tecken som inte är giltiga i URL-adresser (t.ex. blanksteg) URL-kodade.</p><p>Följande variabler är tillgängliga: (**Anteckning**: Även om du kan använda dessa variabler i samma URL är det antagligen vanligare att använda dem separat.)</p> <ul><li>**`$value`:** Gör att du kan infoga värdet för dimensionsobjektet i den URL som du anger. <p>Se följande scenario som ett exempel:</p><p>Anta att du vill skapa hyperlänkar för alla sidobjekt i en friformstabell, där värdet för varje dimensionsobjekt är en del av webbsidans URL. I det här fallet kan du skapa en anpassad URL som dynamiskt justeras för varje dimensionsobjekt. </p><p>Du kan uppnå detta genom att lägga till `$value` variabel till slutet av den anpassade URL-adress som du anger. Exempel:</p> <p>https://company-name.com/browse/product#$value</p><p>När den här anpassade URL:en används för dimensionsobjekt för sidnamn vars värden är &quot;ProductY&quot; och &quot;ProductZ&quot;, skulle de genererade hyperlänkarna se ut ungefär så här: </p><p>https://company-name.com/browse/product#ProductY</p><p>och</p><p> https://company-name.com/browse/product#ProductZ </p><p>![använda värden i hyperlänkar](assets/table-hyperlinks-vaule.png)</p><p>**Tips**: Om du bara skulle lägga till `$value` i fältet Anpassad URL är det samma som att välja [!UICONTROL **Använd värdet för dimensionsartikeln**] när du skapar URL:en.</p></li><li>**`$breakdown`:** Gör att du kan infoga värdet för den uppdelade dimensionsposten i den URL du anger. Detta gör att du kan använda en dimension med ett användarvänligt namn i rapporten (till exempel en produktnamnsdimension) när du skapar hyperlänken baserat på en detaljnivådimension som kan vara mindre användarvänlig (till exempel en produkt-ID eller sidans URL-dimension).<p>När du refererar till en uppdelningsdimension är det vanligast att bara ha en uppdelningsartikel för en given dimensionsartikel. Om det finns flera uppdelningsartiklar för en given dimensionspost används värdet för den första uppdelningsartikeln i URL:en. Om inga uppdelningsobjekt visas blir URL:en ogiltig. Samma sorteringsordning tillämpas på uppdelningsobjekten som i tabellen.</p><p>Du anger uppdelningsdimension i [!UICONTROL **Uppdelningsdimension**] fält nedan.</p> <p>Titta på exempelscenariot som beskrivs för [!UICONTROL **Uppdelningsdimension**] fält nedan.</p></li></ul> |
     | [!UICONTROL **Uppdelningsdimension (valfritt)**] | Börja skriva namnet på den detaljdimension som du vill använda och välj den sedan i listrutan. <p>Om du väljer en detaljdimension i det här fältet måste du referera till den med `$breakdown` i den URL som du anger i [!UICONTROL **Anpassad URL**] fält.</p><p>Se följande scenario som ett exempel:</p><p>Anta att du vill skapa hyperlänkar för alla produktnamnsdimensionsobjekt i en friformstabell. Varje produktnamnsdimensionsobjekt innehåller en uppdelning av en produkt-ID-dimension.</p></p>I det här fallet kan du skapa hyperlänkar för varje produktnamnsdimension som dirigerar användare till produktsidan genom att använda värdet för uppdelningsdimensionen för produkt-ID. </p><p>Du kan uppnå detta genom att lägga till `$breakdown` variabeln till slutet av den anpassade URL-adress som du anger i [!UICONTROL **Anpassad URL**] fält. Exempel:</p><p>https://company-name.com/browse/product/$breakdown</p><p>När den här anpassade URL:en används för dimensionsobjekt för ditt produktnamn som har dimensionsobjekt för nedbrytning vars värden är &quot;ProductY&quot; och &quot;ProductZ&quot;, skulle de genererade hyperlänkarna se ut ungefär så här:</p><p>https://company-name.com/browse/product/ProductY</p><p>och</p><p>https://company-name.com/browse/product/ProductZ</p><p>Därefter väljer du produkt-ID-dimensionen i [!UICONTROL **Uppdelningsdimension**] fält </p><p>![använda uppdelningar i hyperlänkar](assets/table-hyperlinks-breakdown.png)</p> |

1. Välj [!UICONTROL **Skapa**].

   Användare som visar frihandstabellen kan se de hyperlänkade dimensionsobjekten. När du klickar på ett dimensionsobjekt dirigeras användarna till de hyperlänkade sidorna på en separat webbläsarflik.

   <!-- add screenshot of a table with hyperlinks.-->

1. [Spara projektet](/help/analysis-workspace/build-workspace-project/save-projects.md) för att spara ändringarna.

## Redigera hyperlänkar

Du kan redigera hyperlänkar som har skapats på dimensioner eller dimensionsobjekt i en frihandstabell.

1. Gör något av följande i en frihandstabell i Analysis Workspace:

   * **Redigera en hyperlänk för ett enskilt dimensionsobjekt:** Högerklicka på dimensionsobjektet i tabellen där du vill redigera hyperlänken.

     ![Redigera hyperlänk för en enskild dimensionspost](assets/hyperlink-single-edit.png)

   * **Redigera hyperlänkar för alla dimensionsobjekt i en dimensionskolumn:** Högerklicka på dimensionsnamnet i dimensionskolumnens rubrik.

     ![Redigera hyperlänk för en dimension](assets/hyperlink-dimension-edit.png)

1. Välj [!UICONTROL **Redigera hyperlänk**] från högerklicksmenyn.

   The [!UICONTROL **Redigera hyperlänkar för dimensionsobjekt**] visas.

1. Mer information om konfigurationsalternativen för att redigera hyperlänken finns i steg 3 i [Skapa hyperlänkar för ett eller flera dimensionsobjekt](#create-hyperlinks-for-one-or-more-dimension-items) markera ovan och sedan [!UICONTROL **Använd**] när uppdateringarna är klara.

1. [Spara projektet](/help/analysis-workspace/build-workspace-project/save-projects.md) för att spara ändringarna.

## Ta bort hyperlänkar

Du kan ta bort hyperlänkar som har skapats för dimensionsobjekt i en friformstabell.

>[!NOTE]
>
>Om du tar bort en dimension som innehåller hyperlänkar i en frihandstabell bevaras inte hyperlänkarna om du återställer samma dimension till frihandstabellen.

Så här tar du bort hyperlänkar från dimensionsobjekt:

1. Gör något av följande i en frihandstabell i Analysis Workspace:

   * **Ta bort en hyperlänk från ett enskilt dimensionsobjekt:** Högerklicka på dimensionsobjektet i tabellen där du vill ta bort hyperlänken.

     ![Ta bort hyperlänk från ett enskilt dimensionsobjekt](assets/hyperlink-single-remove.png)

   * **Ta bort hyperlänkar från alla dimensionsobjekt i en dimensionskolumn:** Högerklicka på dimensionsnamnet i dimensionskolumnens rubrik.

     ![Ta bort hyperlänk från en dimension](assets/hyperlink-dimension-remove.png)

1. Välj [!UICONTROL **Ta bort hyperlänk**] från högerklicksmenyn.

   Hyperlänken tas bort från den enskilda dimensionsposten (om du har valt en enskild dimensionspost) eller från alla dimensionsposter (om du har valt dimensionsnamnet i dimensionskolumnens rubrik).

1. [Spara projektet](/help/analysis-workspace/build-workspace-project/save-projects.md) för att spara ändringarna.
