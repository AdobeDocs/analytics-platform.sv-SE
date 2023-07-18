---
title: Skapa ett datablock med Report Builder i Customer Journey Analytics
description: Beskriver hur du skapar ett datablock.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: f09dffe3d134c423b69f6ca75337f3aca3f51410
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# Skapa ett datablock

A *datablock* är den datatabell som skapas av en enskild databegäran. En Report Builder-arbetsbok kan innehålla flera datablock. När du skapar ett datablock konfigurerar du först datablocket och skapar sedan datablocket.

## Konfigurera datablocket

Konfigurera de inledande datablocksparametrarna för datablockets plats, datavyer och datumintervall.

1. Klicka **Skapa datablock**.

   ![](./assets/create_db.png)

1. Ange **Plats för datablock**.

   Platsalternativet för datablocket definierar den plats i kalkylbladet där rapportbyggaren lägger till data i kalkylbladet.

   Om du vill ange platsen för datablocket markerar du en enskild cell i kalkylbladet eller anger en celladress som a3, \\\$a3, a\\\$3 eller sheet1!a2. Den angivna cellen kommer att vara det övre vänstra hörnet i datablocket när data hämtas.

1. Välj **Datavyer**.

   Med alternativet Datavyer kan du välja en datavy från en nedrullningsbar meny eller referera till en datavy från en cellplats.

1. Ange **Datumintervall**.

   Med datumintervallalternativet kan du välja ett datumintervall. Datumintervall kan vara fasta eller rullande. Mer information om dataområdesalternativ finns i [Välj ett datumintervall](select-date-range.md).

1. Klicka **Nästa**.

   ![](./assets/choose_date_data_view3.png)

   När du har konfigurerat datablocket kan du välja mått, mätvärden och filter för att skapa datablocket. Flikarna Dimensioner, Metrisk och Filter visas ovanför rutan Tabellverktyg.
<!--
    ![](./assets/image9.png)
  -->


## Bygg datablocket

Om du vill skapa datablocket väljer du rapportkomponenter och anpassar sedan layouten.

1. Lägg till Dimensioner, mätvärden och filter.

   Bläddra i komponentlistorna eller använd **sök** för att hitta komponenter. Dra och släpp komponenter till tabellrutan eller dubbelklicka på ett komponentnamn i listan för att automatiskt lägga till komponenten i tabellrutan.

   Dubbelklicka på en komponent för att lägga till den i ett standardavsnitt i tabellen.

   - Dimension-komponenter läggs till i avsnittet Rad eller i kolumnavsnittet om du redan har en dimension i kolumnerna.
   - Datumkomponenter läggs till i avsnittet Kolumn.
   - Filterkomponenter läggs till i avsnittet Filter.

1. Ordna objekten i tabellrutan för att anpassa layouten för ditt datablock.

   Dra och släpp komponenter i tabellrutan för att ändra ordning på komponenterna eller högerklicka på ett komponentnamn och välj på Alternativ-menyn.

   När du lägger till komponenter i tabellen visas en förhandsvisning av datablocket på datablockets plats i kalkylbladet. Layouten för förhandsgranskningen av datablocket uppdateras automatiskt när du lägger till, flyttar eller tar bort objekt i tabellen.

   ![](./assets/image10.png)

   **Visa eller dölj rad- och kolumnrubriker**

1. Klicka på kommandot Redigera datablock i navet Report Builder.

1. Klicka på **Tabell** inställningsikon.

   ![platshållarbild](./assets/table-settings.png){width="35%"}

1. Markera eller avmarkera alternativet Visa rad- och kolumnrubriker. Rubrikerna visas som standard.

   **Dölja eller visa dimensionsetiketter och måttrubriker**

1. Klicka på ellipsikonen på dimensionerna eller kolumnrubrikerna för att visa inställningarna.

   ![platshållarbild](./assets/row-heading.png){width="35%"}

1. Klicka på Dölj eller Visa för att växla dimensionsetiketter eller kolumnrubriker. Alla etiketter visas som standard.

1. Klicka **Slutför**.

   Ett bearbetningsmeddelande visas när analysdata hämtas.

   ![](./assets/image11.png)

   Report Builder hämtar data och visar det ifyllda datablocket i kalkylbladet.

   ![](./assets/image12.png)
