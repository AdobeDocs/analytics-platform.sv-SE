---
title: Så här skapar du ett datablock med Report Builder i Customer Journey Analytics
description: Beskriver hur du skapar ett datablock.
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 56ac1c5a6d13a972aed90cab79cbc5f794cedc9e
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# Skapa ett datablock

Ett *datablock* är den datatabell som skapas av en enskild databegäran. En Report Builder-arbetsbok kan innehålla flera datablock. När du skapar ett datablock konfigurerar du först datablocket och skapar sedan datablocket.

## Konfigurera datablocket

Konfigurera de inledande datablocksparametrarna för datablockets plats, datavyer och datumintervall.

1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL Create]**.

   ![Skärmbild med alternativet Skapa datablock.](./assets/create-datablock.png)

1. Ange **[!UICONTROL Data block location]**.

   Platsalternativet för datablocket definierar den plats i kalkylbladet där rapportbyggaren lägger till data i kalkylbladet.

   Om du vill ange platsen för datablocket markerar du en enskild cell i kalkylbladet eller anger en celladress som `a3`, `\\\$a3`, `a\\\$3` eller `sheet1!a2`. Den angivna cellen kommer att vara det övre vänstra hörnet i datablocket när data hämtas.

   Använd ![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg) om du vill välja en plats för ett datablock från den markerade cellen i kalkylbladet.

1. Välj **[!UICONTROL Data views]**.

   Med alternativet Datavyer kan du välja en datavy från en nedrullningsbar meny eller referera till en datavy från en cellplats.

   Välj ![DataViewSelector](/help/assets/icons/DataViewSelector.svg) om du vill skapa en datavy från en cell.

1. Ange **[!UICONTROL Date range]**.

   Med datumintervallalternativet kan du välja ett datumintervall. Datumintervall kan vara fasta eller rullande. Mer information om alternativ för datumintervall finns i [Välj ett datumintervall](select-date-range.md).

   Välj **[!UICONTROL Calendar]** om du vill välja ett dataintervall med ![Kalender](/help/assets/icons/Calendar.svg) eller ange ett datumintervall manuellt. Du kan också välja en förinställning i listrutan Sökförinställningar.

   Välj **[!UICONTROL From Cell]** om du vill definiera start- och slutdata baserat på en cell i det aktuella bladet.

1. Välj **Nästa**.

   ![Skärmbild som visar datumintervallalternativet och den aktiva knappen Nästa.](./assets/choose_date_data_view3.png)

   När du har konfigurerat datablocket kan du välja mått, mätvärden och segment för att skapa datablocket. Flikarna Dimensioner, Metrisk och Segment visas ovanför rutan Tabellverktyg.

## Bygg datablocket

Om du vill skapa datablocket väljer du rapportkomponenter och anpassar sedan layouten.

1. Lägg till dimensioner, mått och segment.

   Bläddra i komponentlistorna eller använd fältet **sök** för att hitta komponenter. Dra och släpp komponenter till tabellrutan eller dubbelklicka på ett komponentnamn i listan för att automatiskt lägga till komponenten i tabellrutan.

   Dubbelklicka på en komponent för att lägga till komponenten i ett standardavsnitt i tabellen.

   - Dimension-komponenter läggs till i avsnittet Rad eller i kolumnavsnittet om du redan har en dimension i kolumnerna.
   - Datumkomponenter läggs till i avsnittet Kolumn.
   - Segmentkomponenter läggs till i segmentavsnittet.

### Startdatum som Dimension

Ange startdatumet som en dimension för att tydligt identifiera startdatumet för ditt datablock. Detta är praktiskt om du har en schemalagd rapport med ett löpande datumintervall eller om du har ett okonventionellt datumintervall och du behöver inte ta hänsyn till startdatumet.

![Skärmbild som visar startdatumet i listan över dimensioner.](./assets/start-date-dimension.png)

1. Ordna objekten i tabellrutan för att anpassa layouten för ditt datablock.

   Dra och släpp komponenter i tabellrutan för att ändra ordning på komponenterna eller högerklicka på ett komponentnamn och välj på Alternativ-menyn.

   När du lägger till komponenter i tabellen visas en förhandsvisning av datablocket på datablockets plats i kalkylbladet. Layouten för förhandsgranskningen av datablocket uppdateras automatiskt när du lägger till, flyttar eller tar bort objekt i tabellen.

   ![Skärmbild som visar de tillagda komponenterna och det uppdaterade kalkylbladet.](./assets/image10.png)

### Visa eller dölj rad- och kolumnrubriker

1. Välj ikonen **[!UICONTROL Table]** ![Inställningar](/help/assets/icons/Setting.svg).

   ![Skärmbild med alternativet Tabellinställningar.](./assets/table-settings.png)

1. Markera eller avmarkera alternativet Visa rad- och kolumnrubriker. Rubrikerna visas som standard.

### Dölja eller visa dimensionsetiketter och måttrubriker

Markera ellipsikonen på dimensionerna eller kolumnrubrikerna för att visa inställningarna.

![Ellipsikonen i avsnittet Rad.](./assets/row-heading.png)

1. Välj ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]** eller ![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]** för att växla dimensionsetiketter eller kolumnrubriker. Alla etiketter visas som standard.

1. Välj **[!UICONTROL Finish]**.


Ett bearbetningsmeddelande visas när analysdata hämtas.

![Bearbetningsmeddelandet.](./assets/image11.png)

Report Builder hämtar data och visar det ifyllda datablocket i kalkylbladet.

![Det slutförda datablocket.](./assets/image12.png)
