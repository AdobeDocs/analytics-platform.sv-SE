---
description: Visa endast projekt på arbetsytan
keywords: View-only projects
title: Skrivskyddade Workspace-projekt
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 3%

---


# Skrivskyddade Workspace-projekt

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan dela projekt som &quot;endast visning&quot; till mottagare via [Arbetsflöde för projektresurs](/help/analysis-workspace/curate-share/share-projects.md). Mottagare som placeras i rollen Kan visa får en mer begränsad projektupplevelse. Detta kan vara önskvärt om du delar ett projekt med användare som är mindre förtrogna med organisationens datastruktur, Analysis Workspace eller Adobe Analytics i allmänhet, men du vill ändå att de ska använda data och insikter i en säker miljö.

![](assets/view-only-project.png)

## Inaktiverade interaktioner

Inaktiverade interaktioner i ett projekt som endast är avsett för visning omfattar:

* Dold vänster räl
* Rapportpaket
* Datumintervall för panelkalenderdatum. Anmärkning: Om du vill tilldela kalenderkontroll till mottagare lägger du till i en [nedrullningsbart filter med datumintervall](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html).
* Frihandsfiltrering
* Frihandsnummer för synliga rader
* Inställningar för frihandsrad, kolumn eller visualisering
* Panelsegment
* Menyer för Redigera, Infoga och Komponent
* Arbetsytetips

## Aktiverade interaktioner

Några av de mer framträdande aktiverade interaktionerna i ett projekt med endast visning är:

| Område | Aktiverade interaktioner |
|---|---|
| Frihandsregister | <ul><li>Sidnumrering och sortering</li><li>Hovering</li><li>Cellmarkeringar som uppdaterar länkade visualiseringar</li><li>Högerklicka > Hämta visualiseringslänk</li><li>Högerklicka > Kopiera till Urklipp</li></ul> |
| Visualiseringar | <ul><li>Aktivera/inaktivera förklaring genom att klicka</li><li>Hovering</li><li>Högerklicka > Hämta visualiseringslänk</li><li>Dölj/expandera</li><li>Flöde - expandera Flödesnoder</li><li>Karta - zoom</li></ul> |
| Paneler | <ul><li>Interaktiva listrutfilter</li><li>Högerklicka > Hämta panellänk</li><li>Dölj/expandera</li></ul> |
| Projekt | <ul><li>Kontrollera alla infoikoner</li><li>Projektmeny - Nytt, Öppna, Ange som landningssida, Uppdatera, Hämta CSV/PDF, begränsad projektinformation och inställningar</li><li>Dela-menyn - Hämta projektlänk, Skicka fil nu</li><li>Hjälp-menyn - Alla åtgärder utom Tips &amp; felsökningsalternativ</li></ul> |
