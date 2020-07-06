---
description: projekt med endast visning i arbetsytan
keywords: View-only projects
title: Visa endast arbetsyteprojekt
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---


# Visa endast arbetsyteprojekt

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan dela projekt som&quot;skrivskyddade&quot; till mottagare via arbetsflödet [för](/help/analysis-workspace/curate-share/share-projects.md)projektdelning. Mottagare som placerats i rollen Kan visa får en mer begränsad projekterfarenhet. Detta kan vara önskvärt om du delar ett projekt med användare som inte är lika bekanta med organisationens datastruktur, Analysis Workspace eller Adobe Analytics i allmänhet, men ändå vill att de ska använda data och insikter i en säker miljö.

![](assets/view-only-project.png)

## Inaktiverade interaktioner

Inaktiverade interaktioner i ett projekt som endast är synligt inkluderar:

* Dolt vänster spår
* Rapportsvit
* Panelkalenderns datumintervall. Obs! Om du vill ge mottagarna kalenderkontroll lägger du till ett [nedrullningsbart filter med datumintervall](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html).
* Frihandsfiltrering
* Frihand # av synliga rader
* Inställningar för frihandsrad, kolumn eller visualisering
* Panelsegment
* Redigera, Infoga och Komponentmenyer
* Tips för arbetsyta

## Aktiverade interaktioner

Några av de mer välkända interaktionerna i ett projekt med endast visning är:

| Yta | Aktiverade interaktioner |
|---|---|
| Frihandsregister | <ul><li>Sidindelning och sortering</li><li>Hovring</li><li>Cellmarkeringar som uppdaterar länkade visualiseringar</li><li>Högerklicka > Hämta visualiseringslänk</li><li>Högerklicka > Kopiera till Urklipp</li></ul> |
| Visualiseringar | <ul><li>Klicka för att aktivera/inaktivera förklaring</li><li>Hovring</li><li>Högerklicka > Hämta visualiseringslänk</li><li>Komprimera/expandera</li><li>Flöde - expandera flödesnoder</li><li>Karta - zoom</li></ul> |
| Paneler | <ul><li>Interaktiva listrutefilter</li><li>Högerklicka > Hämta panellänk</li><li>Komprimera/expandera</li></ul> |
| Projekt | <ul><li>Inspektera alla informationsikoner</li><li>Projektmeny - Nytt, Öppna, Ange som landningssida, Uppdatera, Hämta CSV/PDF, Begränsad projektinformation och inställningar</li><li>Dela-menyn - Hämta projektlänk, Skicka fil nu</li><li>Hjälpmenyn - Alla åtgärder förutom Tips och felsökningsalternativ</li></ul> |
