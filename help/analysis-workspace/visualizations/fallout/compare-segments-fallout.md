---
description: Du kan skapa segment från en kontrollpunkt, lägga till segment som kontrollpunkt och jämföra nyckelarbetsflöden mellan olika segment i Analysis Workspace.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Använda segment i utfallsanalys
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 1%

---


# Tillämpa filter i utfallsanalys

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan skapa filter från en kontrollpunkt, lägga till segment som kontrollpunkt och jämföra nyckelarbetsflöden mellan olika filter i Analysis Workspace.

>[!IMPORTANT]
>
>Filter som används som kontrollpunkter i utfall måste använda en behållare som ligger på en lägre nivå än den övergripande kontexten för utfallsvisualiseringen. Med en besökarkontextutlösning måste filter som används som kontrollpunkter vara besökta eller träffbaserade filter. Med en deskontextutskrift för besök måste filter som används som kontrollpunkt vara träffbaserade segment. Om du använder en ogiltig kombination blir utfallet 100 %. Vi har lagt till en varning till Fallout-visualiseringen som visas när du lägger till ett inkompatibelt filter som en beröringspunkt. Vissa ogiltiga filterbehållarkombinationer leder till ogiltiga utfyllningsdiagram, till exempel:

* Använda ett besöksbaserat filter som en beröringspunkt inuti en besökarkontext Färdig visualisering
* Använda ett besöksbaserat filter som en beröringspunkt inuti en besökskontext Färdigställ visualisering
* Använda ett besöksbaserat filter som en beröringspunkt inuti en besökskontext Färdigställ visualisering

## Skapa ett filter från en kontrollpunkt {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Skapa ett filter från en specifik kontrollpunkt som du är särskilt intresserad av och som kan vara användbart för andra rapporter. Du gör detta genom att högerklicka på pekpunkten och välja **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Filter Builder öppnas, förfyllt med det förbyggda sekventiella filtret som matchar den touchpoint du valt:

   ![](assets/segment-builder.png)

1. Ge filtret en rubrik och beskrivning och spara det.

   Du kan nu använda det här filtret i vilket projekt som helst.

## Lägga till ett filter som en beröringspunkt {#section_17611C1A07444BE891DC21EE8FC03EFC}

Om du t.ex. vill se hur dina amerikanska användare tenderar och påverkar utfallet drar du bara filtret för amerikanska användare till utfallet:

![](assets/segment-touchpoint.png)

Du kan också skapa en OCH-pekpunkt genom att dra filtret US-användare till en annan kontrollpunkt.

## Jämför filter i utfall {#section_E0B761A69B1545908B52E05379277B56}

Du kan jämföra ett obegränsat antal filter i Fallout-visualiseringen.

1. Markera de segment som du vill jämföra från [!UICONTROL Filter] räl till vänster. I vårt exempel har vi valt ut två segment: Användare i USA och icke-amerikanska användare.
1. Dra dem till filtersläppzonen överst.

   ![](assets/segment-drop.png)

1. Valfritt: Du kan behålla &quot;Alla besök&quot; som standardbehållare eller ta bort den.

   ![](assets/seg-compare.png)

1. Du kan nu jämföra utfallet mellan de två filtren, till exempel där ett filter utför ett annat eller andra insikter.
