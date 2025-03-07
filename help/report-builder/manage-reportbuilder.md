---
title: Hantera datablock med Report Builder i Customer Journey Analytics
description: Beskriver hur du använder hanteringsfunktionen i Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: bd2d45b9fc1380e36fc482ee75e1a9bbb26f6cf7
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 0%

---

# Hantera datablock i Report Builder

Du kan visa och hantera alla datablock i en arbetsbok med hjälp av Data Block Manager. Med Data Block Manager kan du söka, filtrera och sortera efter specifika datablock. När du har markerat ett eller flera datablock kan du redigera, ta bort eller uppdatera de markerade datablocken.

![Skärmen Hanteraren för datablockering.](./assets/image52.png)

## Visa datablock

Klicka på **Hantera** om du vill visa en lista över alla datablock i en arbetsbok.


![Hantera-alternativet om du vill visa en lista över alla datablock.](./assets/image53.png)

Dataslockhanteraren visar alla datablock som finns i en arbetsbok. 

![Listan med alla datablock i en arbetsbok.](./assets/image52.png)

## Sortera listan över datablock

Du kan sortera data blockeringslista efter en kolumn som visas. Du kan till exempel sortera data blockeringslista efter datavyer, segment, datumintervall och andra variabler.

Om du vill sortera data blockeringslista klickar du på en kolumnrubrik.

![Sorterar datablocken.](./assets/image54.png)

## Sök i Data Blockeringslista

Använd sökfältet för att hitta något i datablockstabellen. Du kan till exempel söka efter mått i datablocken eller datavyn. Du kan också söka efter datum i datumintervallet, ändringsdatumet eller sista körningsdatumkolumnen.

![Sökfältet används för att hitta något i datablockstabellen.](./assets/image55.png)

## Redigera datablock

Du kan redigera datavyn, datumintervallet eller de segment som används i ett eller flera datablock.

Du kan till exempel ersätta ett befintligt segment med ett nytt segment i ett eller flera datablock.

1. Markera de datablock som du vill uppdatera. Du kan markera kryssrutan på den översta nivån om du vill markera alla datablock, eller markera enskilda datablock.

   ![Ikonen för redigering av penna](./assets/image56.png)

1. Klicka på redigeringsikonen för att visa snabbredigeringsfönstret.

   ![Snabbredigeringsfönstret](./assets/image58.png)

1. Markera en segmentlänk om du vill uppdatera datavyer, datumintervall eller segment.

   ![Fältet Lägg till segment i snabbredigeringsfönstret](./assets/image59.png)

## Uppdatera datablock

Klicka på uppdateringsikonen för att uppdatera datablocken i listan.

<img src="./assets/refresh-icon.png" width="15%" alt="Ikonen Uppdatera"/>

Om du vill kontrollera om ett datablock har uppdaterats kan du visa ikonen för uppdateringsstatus.

Ett uppdaterat datablock visar en bockmarkering i en grön cirkel: <img src="./assets/refresh-success.png" width="5%" alt="Grön cirkel med bockmarkeringsikon"/>.

En varningsikon visas för ett datablock som inte har uppdaterats: <img src="./assets/refresh-failure.png" width="5%" alt="Röd triangel med utropstecken"/>.Det gör det enkelt att identifiera om några datablock innehåller fel.


![Datablockhanteraren visar uppdateringsstatus för alla listade datablock.](./assets/image512.png)

## Ta bort ett datablock

Klicka på papperskorgsikonen om du vill ta bort ett markerat datablock.

## Gruppera datablock

Du kan gruppera datablocken med listrutan **Gruppera efter** eller klicka på en kolumnrubrik. Om du vill sortera datablock efter kolumn klickar du på kolumnrubriken. Om du vill gruppera datablock efter grupper väljer du ett gruppnamn i listrutan **Gruppera efter**. På skärmbilden nedan visas datablock grupperade efter ark. Här visas datablock grupperade efter Sheet1 och Sheet2.  Detta är till exempel användbart i segmentbytet. Om du har flera segment tillämpade på varje datablock är det bra att skapa en grupp som innehåller alla datablock som du vill ersätta. Sedan kan du enkelt markera och redigera alla samtidigt.

![Datablockhanteraren visar listan Gruppera efter ark.](./assets/group-data-blocks.png)

## Ändra vyn för Hanteraren för datablockering

Du kan ändra vilka kolumner som ska visas i fönstret Dataslockshanteraren.


Klicka på kolumnlistan <img src="./assets/image515.png" width="3%" alt="Ikon för spaltlista"/>-ikonen för att välja vilka kolumner som ska listas i Dataslockhanteraren. Markera ett kolumnnamn som ska visas. Avmarkera kolumnnamnet som du vill ta bort från vyn.

![Datablockhanteraren visar kolumnlistan](./assets/image516.png)
