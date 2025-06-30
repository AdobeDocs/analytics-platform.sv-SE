---
description: Förstå upplevelsen av skrivskyddade projekt i Analysis Workspace.
keywords: Skrivskyddade projekt
title: Skrivskyddade projekt
feature: Curate and Share
exl-id: 2bc26444-aeea-4695-92a5-a2b45ac18e0d
role: User
source-git-commit: 084c995658a5cf698d253f1c15229f621a8c55d5
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# Skrivskyddade projekt

Du kan dela projekt som skrivskyddade till mottagare via [delningsfunktionen](/help/analysis-workspace/curate-share/share-projects.md). Mottagare som placerats i rollen **[!UICONTROL Read only]** får en mer begränsad projekterfarenhet.

Detta kan vara önskvärt om du delar ett projekt med användare som inte är lika bekanta med organisationens datastruktur, Analysis Workspace eller Customer Journey Analytics i allmänhet, men ändå vill att de ska använda data och insikter i en säker miljö.

![Dela som skrivskyddad](assets/read-only-project-sender.png)

Interaktionen för de skrivskyddade mottagarna är begränsad.

![Dela som skrivskyddat mottaget](assets/read-only-project-receiver.png)

## Inaktiverade interaktioner

Inaktiverade interaktioner i ett projekt som endast är synligt inkluderar:

* Dold vänster panel
* Panelkalenderns datumintervall. Obs! Om du vill ge mottagarna kalenderkontroll lägger du till i ett [nedrullningsbart segment med datumintervall](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html).
* Frihandssegmentering
* Frihandsnr för synliga rader
* Inställningar för frihandsrad, kolumn eller visualisering
* Panelsegment
* Redigera, Infoga och Komponentmenyer
* Workspace tips

## Aktiverade interaktioner

Några av de mer välkända interaktionerna i ett projekt med endast visning är:

| Område | Aktiverade interaktioner |
| --- | --- |
| **Frihandstabeller** | <li>Sidindelning och sortering</li><li>Hovring</li><li>Cellmarkeringar som uppdaterar länkade visualiseringar</li><li>Från snabbmenyn > Hämta visualiseringslänk</li><li>Från snabbmenyn > Kopiera till Urklipp</li> |
| **Visualiseringar** | <li>Klicka för att aktivera/inaktivera förklaring</li><li>Hovring</li><li>Från snabbmenyn > Hämta visualiseringslänk</li><li>Komprimera/expandera</li><li>Flöde - expandera flödesnoder</li><li>Karta - zoom</li></ul> |
| **Paneler** | <li>Interaktiva nedrullningsbara segment</li><li>På snabbmenyn > Hämta panellänk</li><li>Komprimera/expandera</li> |
| **Projekt** | <li>Inspektera alla informationsikoner</li><li>Project menu - New, Open, Set as landing page, Refresh, Download CSV/PDF, limited Project Info &amp; Settings</li><li>Dela-menyn - Hämta projektlänk, Skicka fil nu</li><li>Hjälpmenyn - Alla åtgärder förutom Tips och felsökningsalternativ</li> |


## Dela med vem som helst

Om du har valt ett projekt med [Dela med vem som helst](share-projects.md#share-a-project-with-anyone-no-login-required) kan mottagaren av länken bara visa projektet och inte interagera med projektet.

![Dela med alla](assets/share-with-anyone-receiver.png)
