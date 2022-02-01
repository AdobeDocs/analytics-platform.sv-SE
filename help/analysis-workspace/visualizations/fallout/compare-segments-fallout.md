---
description: Du kan skapa filter från en kontaktyta, lägga till filter som kontaktyta och jämföra viktiga arbetsflöden mellan olika filter i Analysis Workspace.
keywords: bortfall och filter;filter i bortfallsanalys;jämför filter i bortfall
title: Använda filter i bortfallsanalys
feature: Visualizations
exl-id: 85b1024f-acd2-43b7-b4b1-b10961ba43e8
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Använda filter i bortfallsanalys

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Funktionsuppsättningen skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan skapa filter från en kontaktyta, lägga till filter som kontaktyta och jämföra viktiga arbetsflöden mellan olika filter i Analysis Workspace.

>[!IMPORTANT]
>
>Filter som används som kontrollpunkter i utfall måste använda en behållare som är på en lägre nivå än den övergripande kontexten för utfallsvisualiseringen. Med en besökarkontext-utrullning måste filter som används som kontrollpunkter vara besök eller träffbaserade filter. Med en kontextutfällning måste filter som används som kontrollpunkt vara träffbaserade. Om du använder en ogiltig kombination blir utfallet 100 %. Vi har lagt till en varning i utfallsvisualiseringen som visas när du lägger till ett inkompatibelt filter som kontaktyta. Vissa ogiltiga kombinationer av filterbehållare leder till ogiltiga utfallsdiagram, t.ex.:

* Använda ett besöksbaserat filter som kontaktyta inuti en besökarsammanhangsbaserad utfallsvisualisering
* Använda ett besöksbaserat filter som kontaktyta i en snabbutfallsvisualisering
* Använda ett besöksbaserat filter som kontaktyta i en snabbutfallsvisualisering

## Skapa ett filter från en kontaktyta {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Skapa ett filter från en viss kontaktyta som du är särskilt intresserad av och som kan vara användbart för andra rapporter. Du gör detta genom att högerklicka på kontaktytan och välja **[!UICONTROL Create filter from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Filterverktyget öppnas och är ifyllt med det fördefinierade sekventiella filtret som matchar den kontaktyta du valde:

   ![](assets/segment-builder.png)

1. Ge filtret en titel och en beskrivning och spara den.

   Du kan nu använda det här filtret i vilket projekt som helst.

## Lägga till ett filter som kontaktyta {#section_17611C1A07444BE891DC21EE8FC03EFC}

Om du till exempel vill se hur användarna i USA trendar och påverkar utfallet drar du bara filtret för användare i USA till utfallet:

![](assets/segment-touchpoint.png)

Du kan också skapa en OCH-kontaktyta genom att dra filtret för amerikanska användare till en annan kontrollpunkt.

## Jämför filter i utfall {#section_E0B761A69B1545908B52E05379277B56}

Du kan jämföra ett obegränsat antal filter i Utfallsvisualiseringen.

1. Välj de filter som du vill jämföra i dialogrutan [!UICONTROL Filter] till vänster. I vårt exempel har vi valt två filter: Användare i USA och användare utanför USA.
1. Dra dem till filtersläppzonen längst upp.

   ![](assets/segment-drop.png)

1. Valfritt: Du kan behålla&quot;Alla besök&quot; som standardbehållare eller ta bort den.

   ![](assets/seg-compare.png)

1. Du kan nu jämföra utfallet för de två filtren, till exempel var ett filter ligger efter ett annat eller andra insikter.
