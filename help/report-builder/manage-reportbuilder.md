---
title: Hantera datablock med Report Builder i Customer Journey Analytics
description: Beskriver hur du använder hanteringsfunktionen i Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: 22b06eaf9f224188699aa241de1d1daad8a14619
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Hantera datablock

Du kan visa och hantera alla datablock i en arbetsbok med [!UICONTROL Data block manager]. [!UICONTROL Data block manager] innehåller sök-, filter- och sorteringsfunktioner som gör att du kan hitta specifika datablock. När du har markerat ett eller flera datablock kan du redigera, ta bort eller uppdatera de markerade datablocken.

## Visa datablock

Om du vill visa en tabell med alla datablock i en arbetsbok väljer du ![TableManage](/help/assets/icons/TableManage.svg) **[!UICONTROL Manage]**.

![Hantera-alternativet om du vill visa en lista över alla datablock.](./assets/image53.png){zoomable="yes"}

**[!UICONTROL Data block manager]** visar en tabell med alla datablock i en arbetsbok.

![Listan med alla datablock i en arbetsbok.](./assets/image52.png){zoomable="yes"}

Du kan använda ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) för att välja vilka kolumner du vill visa.

## Sortera datablock

Du kan sortera datablockstabellen efter en kolumn som visas. Du kan till exempel sortera datablock efter datavyer, segment, datumintervall och andra variabler.

Om du vill sortera datablockstabellen väljer du en kolumnrubrik. Markera samma kolumnrubrik om du vill kasta om sorteringsordningen.


## Sök i datablock

Använd fältet ![Sök](/help/assets/icons/Search.svg) **[!UICONTROL _Sök_]** för att hitta något i datablockstabellen. Du kan till exempel söka efter mått i datablocken eller datavyn. Du kan också söka efter datum i datumintervallet, ändringsdatumet eller sista körningsdatumkolumnen.


## Redigera datablock

Du kan redigera datavyer och datumintervalldatablock. Eller segmenten som tillämpas på datablock.

Du kan till exempel ersätta ett befintligt segment med ett nytt segment i ett eller flera datablock.

1. Markera de datablock som du vill uppdatera. Du kan markera kryssrutan på den översta nivån om du vill markera alla datablock, eller markera enskilda datablock.

   ![Ikonen för redigering av penna](./assets/image56.png){zoomable="yes"}

1. Välj ![Redigera](/help/assets/icons/Edit.svg) för att visa fönstret **[!UICONTROL Quick edit]**.

   ![Snabbredigeringsfönstret](./assets/image58.png){zoomable="yes"}

1. Markera en länk om du vill uppdatera datavyer, datumintervall eller segment. I **[!UICONTROL Quick Edit]** - **[!UICONTROL Segments]** kan du lägga till, ta bort eller uppdatera segment för de markerade datablocken.

   ![Fältet Lägg till segment i snabbredigeringsfönstret](./assets/image59.png){zoomable="yes"}

## Uppdatera datablock

Välj ![Uppdatera](/help/assets/icons/Refresh.svg) om du vill uppdatera datablockstabellen.

Kontrollera om ett datablock har uppdaterats genom att visa ikonen för uppdateringsstatus:

- Ett uppdaterat datablock visar ![CheckmarkCircleGreen](/help/assets/icons/CheckmarkCircleGreen.svg).

- Ett datablock som inte kunde uppdateras visar en ![AlertRed](/help/assets/icons/AlertRed.svg).


## Ta bort datablock

Så här tar du bort ett eller flera datablock:

1. Markera ett eller flera datablock.
1. Välj ![Ta bort](/help/assets/icons/Delete.svg).
1. Välj **[!UICONTROL Delete]** i dialogrutan **[!UICONTROL Delete data block]** eller **[!UICONTROL Cancel]** om du vill avbryta borttagningen.

## Gruppera datablock

Du kan gruppera datablock med hjälp av den nedrullningsbara menyn **[!UICONTROL Group by]** eller välja en kolumnrubrik.

Om du vill sortera datablock efter kolumn markerar du kolumnrubriken. Om du vill gruppera datablock efter grupper väljer du ett gruppnamn i listrutan **[!UICONTROL Group by]**. På skärmbilden nedan visas datablock grupperade efter datavy.

Du kan använda gruppering för att snabbt markera datablock som du vill ändra ett vanligt element för, som segment.

![Datablockhanteraren visar listan Gruppera efter ark.](./assets/group-data-blocks.png){zoomable="yes"}

