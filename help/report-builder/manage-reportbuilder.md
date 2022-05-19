---
title: Hantera datablock med Report Builder i Customer Journey Analytics
description: Beskriver hur du använder hanteringsfunktionen i Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 70103020-a4a9-43be-933c-bde5a6d088c8
source-git-commit: e9856269ee07b7119f75b98489b47e1f35f7cf5f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# Hantera datablock i Report Builder

Du kan visa och hantera alla datablock i en arbetsbok med hjälp av Data Block Manager. Med Data Block Manager kan du söka, filtrera och sortera efter specifika datablock. När du har markerat ett eller flera datablock kan du redigera, ta bort eller uppdatera de markerade datablocken.

![image](./assets/image52.png)

## Visa datablock

Klicka **Hantera** om du vill visa en lista över alla datablock i en arbetsbok.


![image](./assets/image53.png)

Dataslockhanteraren visar alla datablock som finns i en arbetsbok. 

![image](./assets/image52.png)

## Sortera listan över datablock

Du kan sortera data blockeringslista efter en kolumn som visas. Du kan till exempel sortera data blockeringslista efter rapportsviter, filter, datumintervall och andra variabler.

Om du vill sortera data blockeringslista klickar du på en kolumnrubrik.

![image](./assets/image54.png)

## Sök i Data Blockeringslista

Använd sökfältet för att hitta något i datablockstabellen. Du kan till exempel söka efter mätvärden i datablocken eller rapportsviten. Du kan också söka efter datum i datumintervallet, ändringsdatumet eller sista körningsdatumkolumnen.

![image](./assets/image55.png)

## Redigera datablock

Du kan redigera datavyn, datumintervallet eller de filter som används i ett eller flera datablock.

Du kan till exempel ersätta ett befintligt filter med ett nytt filter i ett eller flera datablock.

1. Markera de datablock som du vill uppdatera. Du kan markera kryssrutan på den översta nivån om du vill markera alla datablock, eller markera enskilda datablock.

   ![image](./assets/image56.png)

1. Klicka på redigeringsikonen för att visa snabbredigeringsfönstret.

   ![image](./assets/image58.png)

1. Välj en filterlänk för att uppdatera datavyer, datumintervall eller filter.

   ![image](./assets/image59.png)

## Uppdatera datablock

Klicka på uppdateringsikonen för att uppdatera datablocken i listan.

<img src="./assets/refresh-icon.png" width="15%"/>

Om du vill kontrollera om ett datablock har uppdaterats kan du visa ikonen för uppdateringsstatus. En bock i en grön cirkel <img src="./assets/refresh-success.png" width="5%"/> anger att uppdateringen av datablocket lyckades. Ett datablock som inte har uppdaterats visas med en varningsikon <img src="./assets/refresh-failure.png" width="5%"/>.  Detta gör det enkelt att identifiera om något datablock innehåller fel.


![image](./assets/image512.png)

## Ta bort ett datablock

Klicka på papperskorgsikonen för att ta bort ett markerat datablock.

## Gruppera datablock

Du kan gruppera datablock med **Gruppera efter** eller klicka på en kolumnrubrik. Om du vill sortera datablock efter kolumn klickar du på kolumnrubriken. Om du vill gruppera datablock efter grupper väljer du ett gruppnamn på menyn **Gruppera efter** nedrullningsbar meny. På skärmbilden nedan visas datablock grupperade efter ark. Här visas datablock grupperade efter Sheet1 och Sheet2.  Det här är användbart i till exempel om du vill ersätta filter. Om du har flera filter tillämpade på varje datablock är det bra att skapa en grupp som innehåller alla datablock som du vill ersätta. Sedan kan du enkelt markera och redigera alla samtidigt.

![image](./assets/group-data-blocks.png)

## Ändra vyn för Hanteraren för datablockering

Du kan ändra vilka kolumner som ska visas i fönstret Dataslockshanteraren.


Klicka på kolumnlistan <img src="./assets/image515.png" width="3%"/> -ikonen för att välja vilka kolumner som ska listas i Data Block Manager. Markera ett kolumnnamn som du vill visa kolumnen med. Avmarkera kolumnnamnet som du vill ta bort från vyn.

![bild](./assets/image516.png)
