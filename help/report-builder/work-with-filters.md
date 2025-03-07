---
title: Så här använder du segment i Report Builder i Customer Journey Analytics
description: Beskriver hur du använder segment i Report Builder för Customer Journey Analytics
role: User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: bd2d45b9fc1380e36fc482ee75e1a9bbb26f6cf7
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 0%

---

# Arbeta med segment i Report Builder

Du kan tillämpa segment när du skapar ett nytt datablock eller när du väljer alternativet **Redigera datablock** på kommandopanelen.

## Använda segment i ett datablock

Om du vill tillämpa ett segment på hela datablocket dubbelklickar du på ett segment eller drar och släpper segment från komponentlistan till segmentavsnittet i tabellen.

## Tillämpa segment på enskilda mätvärden

Om du vill använda segment på enskilda mätvärden drar och släpper du ett segment på ett mätvärde i tabellen. Du kan också klicka på ikonen **..** till höger om ett mått i tabellrutan och sedan välja **Segmentmått**. Om du vill visa tillämpade segment håller du pekaren över eller väljer ett mått i tabellrutan. Mätvärden med tillämpade segment visar en segmentikon.

![segmentflik som visar mått.](./assets/filter_by.png)

## Snabbredigeringssegment

Du kan använda snabbredigeringspanelen för att lägga till, ta bort eller ersätta segment för befintliga datablock.

När du markerar ett cellintervall i kalkylbladet visas en sammanfattningslista över de segment som används av datablocken i markeringen på länken **Segment** på snabbredigeringspanelen.

Redigera segment med hjälp av snabbredigeringspanelen

1. Markera ett cellintervall från ett eller flera datablock.

   ![Panelen Snabbredigering visar segmentalternativ för datavyer, datumintervall och segment.](./assets/select_multiple_dbs.png)

1. Klicka på segmentlänken för att öppna panelen Snabbredigering - Segment.

   ![segmentpanelen som visar fältet Lägg till segment och listor som används.](./assets/quick_edit_filters.png)

### Lägga till eller ta bort ett segment

Du kan lägga till eller ta bort segment med alternativen Lägg till/ta bort.

1. Välj fliken **Lägg till/ta bort** på panelen Snabbredigeringssegment.

   Alla segment som tillämpas på de markerade datablocken visas på panelen Snabbredigering. Segment som tillämpas på alla datablock i markeringen listas under rubriken **Tillämpas på alla markerade datablock**. Segment som tillämpas på vissa, men inte alla, datablock listas under rubriken **Tillämpas på 1 eller flera markerade datablock**.

   När det finns flera segment i de markerade datablocken kan du söka efter specifika segment med hjälp av sökfältet **Lägg till segment**.

   ![Fältet Lägg till segment.](./assets/add_filter.png)

1. Lägg till segment genom att välja segment i listrutan **Lägg till segment**.

   Listan med sökbara segment innehåller alla segment som är tillgängliga för datavyer som finns i ett eller flera av de markerade datablocken samt alla segment som är tillgängliga globalt i organisationen.

   Om du lägger till ett segment används segmentet på alla datablock i markeringen.

1. Om du vill ta bort segment klickar du på borttagningsikonen **x** till höger om segment i listan **Segment som används**.

1. Klicka på **Använd** om du vill spara ändringarna och återgå till hubbpanelen.

   Report Builder visar ett meddelande som bekräftar de använda segmentändringarna.

### Ersätta ett segment

Du kan ersätta ett befintligt segment med ett annat segment om du vill ändra hur data segmenteras.

1. Välj fliken **Ersätt** på panelen Snabbredigeringssegment.

   ![Välj fliken Ersätt.](./assets/replace_filter.png)

1. Använd sökfältet **Söklista** för att hitta specifika segment.

1. Välj ett eller flera segment som du vill ersätta.

1. Sök efter ett eller flera segment i fältet Ersätt med.

   Om du väljer ett segment läggs det till i listan **Ersätt med**......

   ![Fliken Ersätt med datablocket Personer i appen markerat och listan Ersätt med uppdaterad med personer i appen ändrad.](./assets/replace_screen_new.png)

1. Klicka på **Använd**.

   Report Builder uppdaterar segmentlistan så att den återspeglar ersättningen.

### Definiera datablocksegment från celler

Datablocken kan referera till segment från en cell. Flera datablock kan referera till samma cell för segment, vilket gör det enkelt att växla segment för flera datablock samtidigt.

Använda segment från en cell

1. Navigera till Steg 2 när du skapar eller redigerar datablock. Se [Skapa ett datablock](./create-a-data-block.md).
1. Klicka på fliken **Segment** för att definiera segment.
1. Klicka på **Skapa segment från cell**.

   ![Skapa segment från cellikon.](./assets/create-filter-from-cell.png)

1. Markera cellen som du vill att datablocken ska referera till ett segment från.

1. Lägg till det segment som du vill lägga till i cellen genom att antingen dubbelklicka på segmentet eller genom att dra och släppa det i segmentavsnittet Inkluderade.

   Obs! Endast ett alternativ kan markeras för den aktuella cellen åt gången.

   ![Segmentet Lägg till från cellfönstret visar de segment som ingår.](./assets/select-filters.png)

1. Klicka på **Använd** för att skapa referenscellen.

1. På fliken **Segment** lägger du till det nyligen skapade referenscellsegmentet i ditt datablock.

   ![fliken Segment med segmentet Sheet1!J1(Alla data) som har lagts till i tabellen.](./assets/reference-cell-filter.png)

1. Klicka på **Slutför**.

   Nu kan andra datablock referera till den här cellen i sina segment. Om du vill använda referenscellen som ett segment i andra datablock lägger du bara till cellreferensen i segmenten från segmentfliken.

#### Använd referenscellen för att ändra datablocksegment

1. Markera referenscellen i kalkylbladet.

1. Klicka på länken under **Segment från cell** på snabbredigeringsmenyn.

   ![segment från cellänk som visar Sheet1!J1 (alla data)](./assets/filters-from-cell-link.png)

1. Välj segmentet i listrutan.

   ![segmentlistruta](./assets/filter-drop-down.png)

1. Klicka på **Använd**.
