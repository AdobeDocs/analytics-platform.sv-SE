---
description: Lär dig hur du kan skapa segment från en kontaktyta, lägga till segment som kontaktyta och jämföra viktiga arbetsflöden mellan olika segment i en utfallsanalys i Analysis Workspace.
keywords: utfall och segmentering;segment i utfallsanalys;jämför segment i utfall
title: Använd segment i bortfallsanalys
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
role: User
source-git-commit: a646d1f35308dc1f1d9f06cf94835534bd8b8da6
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 0%

---

# Använd segment i utfallsanalys

Du kan skapa segment från en kontaktyta, lägga till segment som kontaktyta och jämföra viktiga arbetsflöden mellan olika segment i Analysis Workspace.

>[!IMPORTANT]
>
>Segment som används som kontrollpunkter i utfall måste använda en behållare som är på en lägre nivå än den övergripande kontexten för utfallsvisualiseringen. Med en person-context Fallout måste segment som används som kontrollpunkter vara sessions- eller händelsebaserade segment. Med en bortfall för sessionskontext måste segment som används som kontrollpunkt vara händelsebaserade segment. Om du använder en ogiltig kombination är utfallet 100 %. En varning visas i Utfallsvisualiseringen när du lägger till ett inkompatibelt segment som kontaktyta. Vissa ogiltiga kombinationer av segmentbehållare leder till ogiltiga utfallsdiagram, som:
>
>* Använda ett personbaserat segment som kontaktyta inuti en personsammanhangsbaserad Fallout-visualisering.
>* Använda ett personbaserat segment som kontaktyta i en sessionssammanhangsbaserad utfallsvisualisering.
>* Använda ett sessionsbaserat segment som kontaktyta i en sessionssammanhangsbaserad utfallsvisualisering.

<!-- Should we add B2B context here?
* [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} Usimg a B2B container based segment as a touchpoint inside a non-container based context Fallout visualization.
* -->

## Skapa ett segment från en kontaktyta

1. Skapa ett segment från en viss kontaktyta som du är särskilt intresserad av och som kan vara användbar för andra rapporter. Högerklicka på kontaktytan och välj **[!UICONTROL Create segment from touchpoint]**.

   ![Touchpoint-listrutan med Skapa segment från kontaktyta markerad.](assets/fallout-createsegment.png)

   [!UICONTROL Segment builder] öppnas och fylls i med det fördefinierade sekventiella segmentet som matchar den kontaktyta du valde:

   ![Segmentbyggaren visar det i förväg ifyllda och fördefinierade sekventiella segmentet.](assets/fallout-definesegment.png)

1. Ge segmentet en rubrik och beskrivning och spara det.

   Du kan nu använda det här segmentet i vilket projekt som helst.

## Lägga till ett segment som kontaktyta

Om du till exempel vill se hur användarna i USA trendar och påverkar utfallet drar du bara segmentet för användare i USA till utfallet:

![Det amerikanska användarsegmentet har markerats och markerats för att dras till utfallet.](assets/fallout-addfilter.png)

Du kan också skapa en OCH-kontaktyta genom att dra användarsegmentet i USA till en annan kontrollpunkt.

## Jämför segment i utfall

Du kan jämföra ett obegränsat antal segment i utfallsvisualiseringen.

1. Markera de segment som du vill jämföra på panelen [!UICONTROL Segment] till vänster. I exemplet är tre segment markerade: *Flight Details: Page Version A*, *Flight Details: Page Version B* och *Flight Details: Page Version C*.
1. Du drar de tre segmenten till segmentsläppzonen högst upp i visualiseringen.


1. Valfritt: Du kan behålla *Alla personer* som standardbehållare eller ta bort behållaren.

   ![Utfall som visar alla besök tillsammans med de två segmenten som drogs i föregående steg.](assets/fallout-multiplefilters.png)

1. Du kan nu jämföra utfallet för de tre segmenten, till exempel var ett segment presterar bättre än ett annat, eller andra insikter.
