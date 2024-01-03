---
title: Så här använder du filter i Report Builder i Customer Journey Analytics
description: Beskriver hur du använder filter i Report Builder för Customer Journey Analytics
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 1f39d7f4-b508-45d8-9b97-81242c3805d3
solution: Customer Journey Analytics
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '849'
ht-degree: 0%

---

# Arbeta med filter i Report Builder

Du kan använda filter när du skapar ett nytt datablock eller när du väljer **Redigera datablock** från KOMMANDONA-panelen.

## Använda filter på ett datablock

Om du vill använda ett filter på hela datablocket dubbelklickar du på ett filter eller drar och släpper filter från komponentlistan i filteravsnittet i tabellen.

## Tillämpa filter på enskilda mätvärden

Om du vill använda filter på enskilda mätvärden drar och släpper du ett filter på ett mätvärde i tabellen. Du kan också klicka på **...** till höger om ett mätresultat i tabellrutan och välj **Filtermått**. Om du vill visa använda filter håller du pekaren över eller väljer ett mått i tabellrutan. Mätvärden med tillämpade filter visar en filterikon.

![Fliken Filter som visar mätvärden.](./assets/filter_by.png)

## Snabbredigeringsfilter

Du kan använda snabbredigeringspanelen för att lägga till, ta bort eller ersätta filter för befintliga datablock.

När du markerar ett cellintervall i kalkylbladet visas **Filter** på snabbredigeringspanelen visas en sammanfattning av de filter som används av datablocken i markeringen.

Redigera filter med hjälp av snabbredigeringspanelen

1. Markera ett cellintervall från ett eller flera datablock.

   ![Snabbredigeringsfilterpanelen med filteralternativ för datavyer, datumintervall och filter.](./assets/select_multiple_dbs.png)

1. Klicka på länken Filter för att öppna panelen Snabbredigering - filter.

   ![På panelen Filter visas fältet Lägg till filter och listorna Använda filter.](./assets/quick_edit_filters.png)

### Lägga till eller ta bort ett filter

Du kan lägga till eller ta bort filter med alternativen Lägg till/ta bort.

1. Välj **Lägg till/ta bort** på panelen Snabbredigeringsfilter.

   Alla filter som tillämpas på de markerade datablocken visas på panelen Snabbredigeringsfilter. Filter som används på alla datablock i markeringen visas under **Tillämpas på alla markerade datablock** rubrik. Filter som används på vissa, men inte alla, datablock listas under **Tillämpas på ett eller flera markerade datablock** rubrik.

   När det finns flera filter i de markerade datablocken kan du söka efter specifika filter med **Lägg till filter** sökfält.

   ![Fältet Lägg till filter.](./assets/add_filter.png)

1. Lägg till filter genom att välja filter på menyn **Lägg till filter** listrutemeny.

   Listan med sökbara filter innehåller alla filter som är tillgängliga för datavyer som finns i ett eller flera av de markerade datablocken samt alla filter som är tillgängliga globalt i organisationen.

   Om du lägger till ett filter tillämpas filtret på alla datablock i markeringen.

1. Klicka på ikonen Ta bort om du vill ta bort filter **x** till höger om filtren i **Tillämpade filter** lista.

1. Klicka **Använd** om du vill spara ändringarna och gå tillbaka till navpanelen.

   Report Builder visar ett meddelande som bekräftar de använda filterändringarna.

### Ersätta ett filter

Du kan ersätta ett befintligt filter med ett annat om du vill ändra hur data filtreras.

1. Välj **Ersätt** på panelen Snabbredigeringsfilter.

   ![Välj fliken Ersätt.](./assets/replace_filter.png)

1. Använd **Söklista** sökfält för att hitta specifika filter.

1. Välj ett eller flera filter som du vill ersätta.

1. Sök efter ett eller flera filter i fältet Ersätt med.

   Om du väljer ett filter läggs det till i **Ersätt med**... lista.

   ![Fliken Ersätt med datablocket Personer i appen markerat och listan Ersätt med uppdaterad med som visar Personer i appen ändrad.](./assets/replace_screen_new.png)

1. Klicka **Använd**.

   Report Builder uppdaterar filterlistan så att den återspeglar ersättningen.

### Definiera datablocksfilter från cell

Datablock kan referera till filter från en cell. Flera datablock kan referera till samma cell för filter, vilket gör att du enkelt kan växla filter för flera datablock samtidigt.

Använda filter från en cell

1. Navigera till Steg 2 när du skapar eller redigerar datablock. Se [Skapa ett datablock](./create-a-data-block.md).
1. Klicka på **Filter** för att definiera filter.
1. Klicka **Skapa filter från cell**.

   ![Skapa filter från cellikon.](./assets/create-filter-from-cell.png)

1. Markera cellen som du vill att datablocken ska referera till ett filter från.

1. Lägg till det filteralternativ som du vill lägga till i cellen genom att antingen dubbelklicka på filtret eller genom att dra och släppa det i avsnittet Filter som ingår.

   Obs! Endast ett alternativ kan markeras för den aktuella cellen åt gången.

   ![Filtret Lägg till från cellfönstret visar de filter som ingår.](./assets/select-filters.png)

1. Klicka **Använd** för att skapa referenscellen.

1. Från **Filter** lägger du till det nyligen skapade referenscellsfiltret i ditt datablock.

   ![Fliken Filter som visar filtret Sheet1!J1(Alla data) som har lagts till i tabellen.](./assets/reference-cell-filter.png)

1. Klicka **Slutför**.

   Nu kan andra datablock referera till den här cellen i sina filter. Om du vill använda referenscellen som ett filter för andra datablock lägger du bara till cellreferensen i filtren på fliken Filter.

#### Använd referenscellen för att ändra filter för datablock

1. Markera referenscellen i kalkylbladet.

1. Klicka på länken under **Filter från cell** på snabbredigeringsmenyn.

   ![Filter från cellänk som visar Sheet1!J1 (alla data)](./assets/filters-from-cell-link.png)

1. Välj filtret i listrutan.

   ![Listruta för filter](./assets/filter-drop-down.png)

1. Klicka **Använd**.

