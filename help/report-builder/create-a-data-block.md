---
title: Skapa ett datablock i Report Builder
description: Lär dig hur du skapar ett datablock.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 0%

---

# Skapa ett datablock

Ett *datablock* är den datatabell som skapas av en enskild databegäran. En Report Builder-arbetsbok kan innehålla flera datablock. När du skapar ett datablock konfigurerar du först datablocket och skapar sedan datablocket.

## Konfigurera datablocket

Konfigurera de inledande datablocksparametrarna för datablockets plats, datavyer och datumintervall.

1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Skärmbild som visar alternativet Skapa datablock](./assets/create-data-block.png){zoomable="yes"}


1. Ange **[!UICONTROL Data block location]**.

   Platsalternativet för datablocket anger den plats i kalkylbladet där Report Builder lägger till data i ditt kalkylblad.

   Om du vill ange platsen för datablocket markerar du en enskild cell i kalkylbladet eller anger en celladress, till exempel `a3`, `\\\$a3`, `a\\\$3` eller `sheet1!a2`. Den angivna cellen blir det övre vänstra hörnet i datablocket när data hämtas.

   Använd ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) om du vill välja en plats för ett datablock från den markerade cellen i kalkylbladet.

1. Välj **[!UICONTROL Data views]**.

   Med alternativet Datavyer kan du välja en datavy från en nedrullningsbar meny eller referera till en datavy från en cellplats.

   Välj ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) om du vill skapa en datavy från en cell.

1. Ange **[!UICONTROL Date range]**.

   Med alternativet **[!UICONTROL Date range]** kan du välja ett datumintervall. Datumintervall kan vara fasta eller rullande.

   Välj **[!UICONTROL Calendar]** om du vill välja ett dataintervall med ![Kalender](/help/assets/icons/Calendar.svg) eller ange ett datumintervall manuellt. Du kan också välja en förinställning i listrutan **[!UICONTROL _Sökförinställningar_]** .

   Välj **[!UICONTROL From cell]** om du vill definiera start- och slutdata baserat på en cell i det aktuella bladet.

   Mer information om alternativ för datumintervall finns i [Markera ett datumintervall](select-date-range.md).

1. Välj **[!UICONTROL Next]**.

   ![Skärmbild som visar datumintervallalternativet och den aktiva knappen Nästa.](./assets/choose_date_data_view3.png)

   När du har konfigurerat datablocket kan du välja mått, mätvärden och segment för att skapa datablocket. Flikarna **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]** och **[!UICONTROL Segments]** visas ovanför rutan **[!UICONTROL Table]**.

## Bygg datablocket

Om du vill skapa datablocket väljer du rapportkomponenter och anpassar sedan layouten.

1. Lägg till **[!UICONTROL Dimensions]**-, **[!UICONTROL Metrics]**- och **[!UICONTROL Segments]**-komponenter.

   Bläddra i komponentlistorna eller använd fältet ![Sök](/help/assets/icons/Search.svg) **[!UICONTROL _Sök efter komponenter_]** för att söka efter komponenter. Dra och släpp komponenter i rutan [!UICONTROL Table] eller dubbelmarkera ett komponentnamn i listan för att lägga till komponenten i rutan [!UICONTROL Table].

   Dubbelmarkera en komponent om du vill lägga till komponenten i ett standardavsnitt i tabellen.

   - Dimension-komponenter läggs till i avsnittet ![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]** eller i avsnittet ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]** om du redan har en dimension i kolumnerna.
   - Datumkomponenter läggs till i avsnittet ![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**.
   - Segmentkomponenter läggs till i avsnittet ![Segmentering](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** .
   - Mätkomponenter läggs till i avsnittet ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Values]** .

1. Ordna objekten i tabellrutan för att anpassa layouten för ditt datablock.

   Dra och släpp komponenter i varje lista i tabellrutan om du vill ändra ordning på komponenterna eller markera ![MoreSmall](/help/assets/icons/MoreSmall.svg) och välj ![ArrowUp](/help/assets/icons/ArrowUp.svg) Move up, ![ArrowDown](/help/assets/icons/ArrowDown.svg) Move down, med mera för att flytta komponenterna i en lista.

   När du lägger till komponenter i tabellen visas en förhandsvisning av datablocket på datablockets plats i kalkylbladet. Layouten för förhandsgranskningen av datablocket uppdateras automatiskt när du lägger till, flyttar eller tar bort objekt i tabellen.

   ![Skärmbild som visar de tillagda komponenterna och det uppdaterade kalkylbladet.](./assets/image10.png)


1. Du kan även ange **[!UICONTROL Start date]** som en dimension för att identifiera startdatumet för ditt datablock. Det kan vara bra att lägga till startdata som en dimension om du har en regelbundet schemalagd rapport med ett löpande datumintervall. Eller om du har ett okonventionellt datumintervall och du måste vara explicit angående startdatumet.

   ![Skärmbild som visar startdatumet i listan över dimensioner.](./assets/start-date-dimension.png)

1. Du kan även visa eller dölja rad- och kolumnrubriker. Så här gör du:

   1. Välj ikonen **[!UICONTROL Table]** ![Inställningar](/help/assets/icons/Setting.svg).

      ![Skärmbild med alternativet Tabellinställningar.](./assets/table-settings.png)

   1. Markera eller avmarkera alternativet för **[!UICONTROL Display row and column headers]**. Rubrikerna visas som standard.

1. Du kan även dölja eller visa dimensionsetiketter och metriska rubriker. Så här gör du:

   1. Välj ![MoreSmall](/help/assets/icons/MoreSmall.svg) på dimensionsetiketten eller kolumnrubriken för att visa snabbmenyn.

      ![Ellipsikonen i avsnittet Rad.](./assets/row-heading.png)

   1. Välj ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** eller ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** för att växla dimensionsetikett eller kolumnrubrik. Alla etiketter visas som standard.

1. Välj **[!UICONTROL Finish]** för att slutföra konfigurationen av ditt datablock.

1. Ett bearbetningsmeddelande **[!UICONTROL #BUSY]** visas när analysdata hämtas.

   ![Bearbetningsmeddelandet.](./assets/image11.png)

1. Report Builder hämtar data och visar det ifyllda datablocket i kalkylbladet.

   ![Det slutförda datablocket.](./assets/image12.png)


>[!MORELIKETHIS]
>
>[Välj en datavy](select-data-view.md)
>[Välj ett datumintervall &#x200B;](select-date-range.md)
>[Filterdimensioner &#x200B;](filter-dimensions.md)
>[Arbeta med segment &#x200B;](work-with-filters.md)
>
