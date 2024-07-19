---
description: Du kan skapa filter från en kontaktyta, lägga till filter som kontaktyta och jämföra viktiga arbetsflöden mellan olika filter i Analysis Workspace.
keywords: bortfall och filter;filter i bortfallsanalys;jämför filter i bortfall
title: Använda filter i bortfallsanalys
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 0%

---

# Använda filter i bortfallsanalys

Du kan skapa filter från en kontaktyta, lägga till filter som kontaktyta och jämföra viktiga arbetsflöden mellan olika filter i Analysis Workspace.

>[!IMPORTANT]
>
>Filter som används som kontrollpunkter i utfall måste använda en behållare som är på en lägre nivå än den övergripande kontexten för utfallsvisualiseringen. Med en person-context Fallout måste filter som används som kontrollpunkter vara besök eller händelsebaserade filter. Med en kontextutfällning måste filter som används som kontrollpunkt vara händelsebaserade filter. Om du använder en ogiltig kombination blir utfallet 100 %. Vi har lagt till en varning i utfallsvisualiseringen som visas när du lägger till ett inkompatibelt filter som kontaktyta. Vissa ogiltiga kombinationer av filterbehållare leder till ogiltiga utfallsdiagram, som:

* Använda ett personbaserat filter som kontaktyta inuti en personsammanhangsbaserad utfallsvisualisering
* Använda ett personbaserat filter som kontaktyta i en sammanhangsbaserad Fallout-visualisering
* Använda ett besöksbaserat filter som kontaktyta i en snabbutfallsvisualisering

## Skapa ett filter från en kontaktyta {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Skapa ett filter från en viss kontaktyta som du är särskilt intresserad av och som kan vara användbart för andra rapporter. Det gör du genom att högerklicka på kontaktytan och välja **[!UICONTROL Create filter from touchpoint]**.

   ![Touchpoint-listrutan med Skapa segment från kontaktyta markerad.](assets/segment-from-touchpoint.png)

   Filterverktyget öppnas och är ifyllt med det fördefinierade sekventiella filtret som matchar den kontaktyta du valde:

   ![Filterverktyget visar det ifyllda och förinbyggda sekventiella filtret.](assets/segment-builder.png)

1. Ge filtret en titel och en beskrivning och spara den.

   Du kan nu använda det här filtret i vilket projekt som helst.

## Lägga till ett filter som kontaktyta {#section_17611C1A07444BE891DC21EE8FC03EFC}

Om du till exempel vill se hur användarna i USA trendar och påverkar utfallet drar du bara filtret för användare i USA till utfallet:

![Filtret Användare i USA har markerats och markerats för att dras till utfallet.](assets/segment-touchpoint.png)

Du kan också skapa en OCH-kontaktyta genom att dra filtret för amerikanska användare till en annan kontrollpunkt.

## Jämför filter i utfall {#section_E0B761A69B1545908B52E05379277B56}

Du kan jämföra ett obegränsat antal filter i Utfallsvisualiseringen.

1. Välj de filter som du vill jämföra i fältet [!UICONTROL Filter] till vänster. I vårt exempel har vi valt två filter: Användare i USA och Användare utanför USA.
1. Dra dem till filtersläppzonen längst upp.

   ![Utfallsvisualisering med valda filter och röd pil som pekar mot filtersläppszonen.](assets/segment-drop.png)

1. Valfritt: Du kan behålla &quot;Alla besök&quot; som standardbehållare eller ta bort den.

   ![Utfall som visar alla besök tillsammans med de två filtren som drogs i föregående steg.](assets/seg-compare.png)

1. Du kan nu jämföra utfallet för de två filtren, till exempel var ett filter ligger efter ett annat eller andra insikter.
