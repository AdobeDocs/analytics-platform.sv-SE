---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7d915fc9b50163b7ec9c48232b99a85a3b063a77
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (juli 2024)

**Senast uppdaterad**: 17 juli 2024

Versionsanteckningarna gäller den 17 juli 2024 till augusti 2024. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md), vilket ger en mer skalbar, fasad metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Intelligenta aviseringar** | Intelligenta aviseringar finns nu i Customer Journey Analytics, så att ni kan meddelas direkt när det inträffar onormala händelser i era data.<p>Du kan ange att aviseringar ska utlösas baserat på avvikelsetrösklar, ändrade procentsatser eller specifika datapunkter. Varningar ger detaljerade kontroller som kan integreras med avvikelseidentifiering och aktiveras när du behöver dem som mest.</p><p>Processen att använda intelligenta aviseringar i Customer Journey Analytics är nästan identisk med att använda intelligenta aviseringar i Adobe Analytics. En viktig skillnad är att det inte finns timaviseringar i Customer Journey Analytics. Den här skillnaden beror på att datainmatningen för de olika typer av händelsedata som kan importeras är slutförd först efter en fördröjning, vanligtvis från 3 till 9 timmar efter datahändelsetiden.</p><p>(Uppdaterade dokumentationslänkar att följa)</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 26 juli 2024 |
| **Administratörsinställningar för att styra konton och platser som används vid export av rapporter till molnet** | En ny [&quot;Administratörsinställningar&quot;-flik i Platshanteraren ](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only) ger administratörer kontroll över om användare kan skapa och redigera konton och platser.<p>De här inställningarna gäller när användare [konfigurerar molnexportkonton](/help/components/exports/cloud-export-accounts.md) och [konfigurerar molnexportplatser](/help/components/exports/cloud-export-locations.md).</p><p>Administratörer kan också begränsa vilka typer av konton som användare kan skapa och använda. Kontotyper är bland annat Google Cloud Platform, Azure RBAC, Amazon S3, AEP Data Landing Zone, Snowflake och så vidare.</p><p>Tidigare kunde alla användare skapa, redigera och använda konton och platser för alla typer av konton.</p> | 11 juli 2024 | 19 juli 2024 |
| **Datakällor på sammanfattningsnivå** | Gör att du kan hämta in tidsseriedata som inte har något person-ID. Dessa tidsseriedata kan användas för att stödja olika användningsfall, som:<ul><li>Presentera högnivåindikatorer som en del av eller bredvid data på händelsenivå. Det kan vara något så enkelt som ett datum och ett enda mätvärde eller innehålla flera dimensioner och mätvärden, som annonsvisningar, öppning av e-post, reklamkostnader, kostnad för sålda produkter med mera.</li><li>Överföra mål eller mål på daglig, veckovis, månadsvis eller kvartalsvis basis och positionera dessa mål mot händelsenivåstatistik för att visualisera hur mätvärdena står i relation till organisationens mål eller mål.</li></ul><p>(Uppdaterade dokumentationslänkar att följa)</p> |  | 31 juli 2024 |
| **Härledda fält - Dedupliceringsfunktion** | Funktionen [Deduplicera ](/help/data-views/derived-fields/derived-fields.md#deduplicate) i härledda fält hjälper dig att förhindra att ett värde räknas flera gånger. |  | 17 juli 2024 |
| **Etablering av guidad analys för CJA-kunder** | Med hjälp av guidad analys kan användarna själva leverera högkvalitativa data och insikter om kundresan via guidade arbetsflöden som bygger på data från olika kanaler i Customer Journey Analytics. <p>Funktionsövergripande team, från marknadsföring till produkt, kan kommunicera i realtid för att använda och förstå dessa rapporter.</p><p>Upp till 11 guidade analysvyer är nu tillgängliga i CJA-paket. [Läs mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 17 juli 2024 |
| **Dela konton och platser som används för export och import** | Användarna kan nu göra de konton och platser de skapar tillgängliga för alla användare i organisationen. Endast konto- och platsägare och systemadministratörer kan redigera och ta bort konton och platser. Tidigare kunde konton och platser bara användas av den användare som skapade dem. De här inställningarna är tillgängliga när användare [konfigurerar molnexportkonton](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts) och [konfigurerar molnexportplatser](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations). | 12 juni 2024 | Mid-Juli 2024 |
| **Publiker publiceras i ett nytt&quot;Publiker&quot;-avsnitt i Experience Platform** | Publikationer som publiceras från Customer Journey Analytics är nu tillgängliga i det nya avsnittet&quot;Publiker&quot; i Adobe Experience Platform.<p>Tidigare fanns målgrupper som publicerades från Customer Journey Analytics tillgängliga i Experience Platform under segmentavsnittet.</p><p>Den här förbättringen ger följande fördelar:</p><ul><li>Publiken har inte längre en timmes fördröjning innan de visas i Experience Platform; de är tillgängliga sekunder efter att de har publicerats.</li><li>Publiker kan sorteras i Experience Platform med hjälp av kolumnen &quot;Ursprung&quot;, som visar det program som målgruppen ursprungligen publicerades från.</li><li>Med filtrerings- och sorteringsalternativen i Experience Platform kan du hitta rätt målgrupper snabbare.</li></ul> <p>(Dokumentationslänk följer)</p> |  | TBD |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-306000; AN-288748; AN-351547; AN-351110

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| Ej tillämpligt | | |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation om tilläggsprogrammet för direktuppspelad mediasamling](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
