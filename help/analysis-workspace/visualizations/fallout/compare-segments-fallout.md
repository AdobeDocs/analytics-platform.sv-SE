---
description: Du kan skapa segment från en kontaktyta, lägga till segment som kontaktyta och jämföra viktiga arbetsflöden mellan olika segment i Analysis Workspace.
keywords: utfall och segment;segment i utfallsanalys;jämför segment i utfall
title: Använd segment i utfallsanalys
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# Använd segment i utfallsanalys

Du kan skapa segment från en kontaktyta, lägga till filter som kontaktyta och jämföra viktiga arbetsflöden mellan olika filter i Analysis Workspace.

>[!IMPORTANT]
>
>Filter som används som kontrollpunkter i utfall måste använda en behållare som är på en lägre nivå än den övergripande kontexten för utfallsvisualiseringen. Med en person-context Fallout måste filter som används som kontrollpunkter vara sessions- eller händelsebaserade filter. Med en bortfall för sessionskontext måste filter som används som kontrollpunkt vara händelsebaserade filter. Om du använder en ogiltig kombination är utfallet 100 %. En varning visas i Utfallsvisualiseringen när du lägger till ett inkompatibelt filter som kontaktyta. Vissa ogiltiga kombinationer av filterbehållare leder till ogiltiga utfallsdiagram, som:
>
>* Använda ett personbaserat filter som kontaktyta inuti en personsammanhangsbaserad utfallsvisualisering
>* Använda ett personbaserat filter som kontaktyta i en sessionssammanhangsbaserad utfallsvisualisering
>* Använda ett sessionsbaserat filter som kontaktyta i en sessionssammanhangsbaserad utfallsvisualisering

## Skapa ett filter från en kontaktyta

1. Skapa ett filter från en viss kontaktyta som du är särskilt intresserad av och som kan vara användbart för andra rapporter. Högerklicka på kontaktytan och välj **[!UICONTROL Create filter from touchpoint]**.

   ![Touchpoint-listrutan med Skapa segment från kontaktyta markerad.](assets/fallout-createfilter.png)

   [!UICONTROL Filter builder] öppnas och fylls i med det fördefinierade sekventiella filtret som matchar den kontaktyta du valde:

   ![Filterverktyget visar det ifyllda och förinbyggda sekventiella filtret.](assets/fallout-definefilter.png)

1. Ge filtret en titel och en beskrivning och spara den.

   Du kan nu använda det här filtret i vilket projekt som helst.

## Lägga till ett filter som kontaktyta

Om du till exempel vill se hur användarna i USA trendar och påverkar utfallet drar du bara filtret för användare i USA till utfallet:

![Filtret Användare i USA har markerats och markerats för att dras till utfallet.](assets/fallout-addfilter.png)

Du kan också skapa en OCH-kontaktyta genom att dra filtret för amerikanska användare till en annan kontrollpunkt.

## Jämför filter i utfall

Du kan jämföra ett obegränsat antal filter i Utfallsvisualiseringen.

1. Välj de filter som du vill jämföra på panelen [!UICONTROL Filter] till vänster. I exemplet har tre filter valts: *Flight Details: Page Version A*, *Flight Details: Page Version B* och *Flight Details: Page Version C*.
1. Du drar de tre filtren till filtersläppzonen högst upp i visualiseringen.


1. Valfritt: Du kan behålla *Alla besök* som standardbehållare eller ta bort behållaren.

   ![Utfall som visar alla besök tillsammans med de två filtren som drogs i föregående steg.](assets/fallout-multiplefilters.png)

1. Du kan nu jämföra utfallet för de tre filtren, till exempel var ett filter slår igenom ett annat eller andra insikter.
