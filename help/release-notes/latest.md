---
title: Aktuella versionsinformation för Customer Journey Analytics
description: Visa den senaste versionsinformationen om Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 5722b858e173e9704ec51afe1f0a694cf04a301f
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (juni 2025)

**Senast uppdaterad**: 18 juni 2025


Versionsinformationen omfattar releaseperioden 2 juni 2025-15 juli 2025. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace vänstra panel öppnas inte längre och stängs vid hovring** | Den vänstra panelen i Analysis Workspace används för att lägga till saker som komponenter, paneler och visualiseringar i ditt projekt. Alternativet att tillfälligt öppna den vänstra panelen genom att hålla markören över en av ikonerna längst till vänster är inte längre tillgängligt. Istället klickar du på någon av de här ikonerna för att hålla panelen öppen. Klicka sedan på samma ikon för att stänga den. |  | 2 juni 2025 <p>(Ursprungligen planerat att släppas den 29 maj 2025)</p> |
| **Customer Journey Analytics B2B edition** | Customer Journey Analytics B2B edition hjälper B2B-företag att anpassa sina marknadsförings-, sälj- och produktteam genom att tillhandahålla användbara kontoinsikter som ökar intäkterna. Med kontot som placeras i mitten av datamodellen fokuserar alla analyser på kontoresan. Genom att lägga till ett nytt lager av enheter (konton, affärsmöjligheter och inköpsgrupper) utöver personliga och tidsbaserade händelser, får ni en fullständig bild av B2B-marknadsförings- och intäktslivscykeln. [Läs mer](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 18 juni 2025 |
| **Stöd för säkra molnmål i Report Builder** | Nu kan du exportera rapporter från Report Builder till följande molnlagringsmål:<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>Tidigare kunde du dela arbetsböcker med andra användare via e-post, men du kunde inte exportera rapporter från Report Builder till molnmål.</p><p>Mer information finns i [Schemalägg arbetsböcker genom att exportera till molnmål](/help/report-builder/report-builder-export.md).</p> |  | 19 juni 2025 (original 18 juni 2025) |
| **Ny förhandsgranskning** | Förhandsgranskningspanelen, som används för att förhandsgranska segment, beräknade mätvärden och mycket mer, använder nu en horisontell fältvisualisering i stället för en donutvisualisering. |  | 18 juni 2025 |
| **Dialogrutan för ändrad attribueringsmodell** | Du kan nu definiera behållaren och tidsperioden separat i dialogrutan för attribueringsmodell. |  | Juni 18,2025 |
| **Anslutningskarta** | Det finns ett nytt [gränssnitt för anslutningskarta](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-connections/create-connection#connection-map) som visuellt visar anslutningskonfigurationen. |  | 18 juni 2025 |
| **Lägg till och visa kommentarer i Analysis Workspace-projekt** | Med en ny [kommentarsfunktion](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects) i Analysis Workspace kan du dela insikter och ställa frågor i ett Analysis Workspace-projekt. Detta kan effektivisera diskussioner om data och hålla konversationer inom ramen för de data som ska diskuteras. Du kan <ul><li>Kommentera eventuella Analysis Workspace-projekt som du har tillgång till</li><li>Kommentera en specifik punkt i en visualisering eller göra allmänna kommentarer om ett projekt</li><li>Tagga andra användare för att meddela dem om dina kommentarer</li><li>Hantera befintliga kommentarer (redigera, fästa, lösa osv.)</li></ul>Customer Journey Analytics-administratörer kan [inaktivera kommentarer på organisationsnivå](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences). Projektägare kan [inaktivera kommentarer på projektnivå](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects). | 25 juni 2025 | 11 juli 2025 <p>(Ursprungligen planerat att släppas den 29 maj 2025)</p> |
| **Stöd för Chrome-förrendering** | Styr hur datainsamlingsbibliotek fungerar när Chrome återger en sida i förväg. (Dokumentationslänk följer) |  | 30 juni 2025 |

## Korrigeringar i Customer Journey Analytics

**Varningar**: AN-379554
**Analysis Workspace**: AN-339607; AN-379222; AN-381138; AN-383291
**B2B**: AN-376028
**BI-tillägg för Tableau**: AN-377488
**Komponenter**: AN-376174
**Datavyer**: AN-379011
**Exportplatser**: AN-382191
**Fullständig tabellexport**: AN-375646; AN-376986; AN-380355; AN-381310
**Resa Canvas**: AN-375865; AN-378011
**Report Builder**: AN-369786; AN-371395; AN-372809
**Rapportering**: AN-372615; AN-378578;


## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

## Relaterade resurser

* [Tidigare versionsinformation för Customer Journey Analytics 2025](/help/release-notes/2025.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=sv-SE)
* [Versionsinformation för direktuppspelad mediainsamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=sv-SE)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=sv-SE)
* [Customer Journey Analytics dokumentationsuppdateringar](/help/release-notes/doc-changes.md)
