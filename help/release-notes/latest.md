---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 69566b840301f87a6362d6bd16b1e255a14d4e23
workflow-type: tm+mt
source-wordcount: '818'
ht-degree: 0%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (april 2024)

**Senaste uppdatering**: 17 april 2024

Versionsanteckningarna gäller den 10 april 2024 till maj 2024. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Direktuppspelningsmedia: Skicka Roku-data till Adobe Experience Platform Edge** | Nu när [installera Media Analytics med Experience Platform Edge](https://experienceleague.adobe.com/en/docs/media-analytics/using/implementation/edge-recommended/media-edge-sdk/implementation-edge)kan du använda Adobe Experience Platform Roku SDK för att skicka direktuppspelningsmediedata till Adobe Experience Platform. |  | 12 april 2024 |
| **Exponerade månadsrapporter i Reporting Activity Manager** | När du visar rapporteringsaktivitet för alla anslutningar i Reporting Activity Manager finns det nu ett diagram som visar [månatliga rapporter/förfrågningar](https://experienceleague.adobe.com/en/docs/analytics-platform/using/reporting-activity-manager/reporting-activity#view-all-report-suites) som kördes på IMS Org-nivån för både den aktuella och föregående månaden.<p>**Obs!** Data finns tillgängliga från och med mars 2024. | | 15 april 2024 |
| **Intelligenta bildtexter i mobilstyrkort** | [Intelligenta bildtexter](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions) kan hjälpa icke-analytiker att förstå sina data bättre utan hjälp av analytiker. De finns nu i Customer Journey Analytics styrkort. |  | 17 april 2024 |
| **Förbättrade behörigheter för projekt [!UICONTROL Workspace] komponenter** | Om en användare (Användare A) tidigare delade ett projekt med en annan användare (Användare B) och gav Användare B redigeringsåtkomst till projektet, skulle Användare B kunna redigera projektet. Användare B kan dock inte redigera [!UICONTROL Quick Segments] inbäddad i projektet. Begränsningen har nu tagits bort - Användare B kan redigera [!UICONTROL Quick Segments] och andra komponenter som bara är för projekt och som är inbäddade i det delade projektet. |  | 17 april 2024 |
| **Administratörer kan hantera alla platser i sin organisation** | Ett nytt alternativ på [Platssida](https://experienceleague.adobe.com/en/docs/analytics/components/locations/locations-manager) ger administratörer möjlighet att visa och hantera alla platser i organisationen. Tidigare kunde administratörer bara visa och hantera de platser som de skapade. |  | 17 april 2024 |
| **Adobe Product Analytics: Funktionsmatris** | Fatta investeringsbeslut genom att förstå vad era kärnfunktioner, er kraft, engångsfunktioner och tvivelaktiga funktioner är. [!UICONTROL Feature matrix] mäter händelser efter användningsfrekvens kontra procent aktiva användare och jämför med mediananvändning. | 17 april 2024 | 30 april 2024 |
| **Adobe Product Analytics: Förbättrade insikter i tratt** | I [Funktion](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) de skrivna insikterna har förbättrats så att de omfattar kategorier, deltoner och beskrivningar för att diagrammet och tabellen ska bli mer lättförståeliga. | 17 april 2024 | 26 april 2024 |
| **Adobe Product Analytics: Förbättrad bevarandevy** | Flera funktioner har lagts till [Kvarhållning](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/retention/retention-rates) prisvyn för att få djupare och anpassningsbara kundlojalitetsinsikter:<ul><li>Bryt länk för start- och returhändelser</li><li>Jämför flera returhändelser i en enda vy</li><li>Anpassa den kvarhållningsmodell som används med (obegränsat) på eller efter (avgränsat) och inställningarna inom hakparentes</li><li>Visa och dölja enskilda kohortrader i diagrammet</li></ul> | 24 april 2024 | 8 maj 2024 |
| **Adobe Product Analytics: Jämför händelser i ett enda trattsteg** | Du kan nu jämföra händelser i ett enda trattsteg i [Funktion](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/funnel/friction) vy. Detta är särskilt användbart när resan innehåller stegalternativ eller ett steg där ett A/B-experiment utförs. | 23 april 2024 | 3 maj 2024 |
| **B2B-schemaomvandling för person till konto** | Gör att du kan omvandla datauppsättningar för att bättre stödja personbaserade uppslag i Customer Journey Analytics B2B-rapportscenarier. Den här funktionen är tillgänglig för datauppsättningar för B2B-scheman baserat på följande klasser:<ul><li>XDM Business Account Person Relation</li><li>XDM - affärsmöjlighet, personrelation</li><li>XDM Business Marketing List-medlemmar</li><li>XDM Business Campaign-medlemmar</li></ul> | | 1 maj 2024 |
| **Upptäck Edge-robotidentifiering** | [Punktavkänning](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) gör att du kan identifiera händelser som genererats av Web SDK, Mobile SDK och Server API som om de genererats av kända spindlar och bottar. | | 1 maj 2024 |
| **Härledda fält: Funktionen Nästa eller Föregående** | Med dessa nya funktioner kan du ta ett fält som indata och sedan identifiera värdet n-previous eller n-next för att få en bättre bild av användarresan. Den här funktionen kan även kombineras med andra funktioner i [!UICONTROL Derived Fields], till exempel [!UICONTROL Concatenate]för att skapa nya dimensioner. |  | 1 maj 2024 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-319662; AN-337894; AN-338469; AN-340147; AN-340200; AN-340443; AN-341594; AN-342442; AN-342976; AN-343020; AN-343469; AN-343703; AN-343938; AN-344614; AN-3 44677;

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| **Uppdaterade länkar i användargränssnitt för datavyer och anslutningar** | Februari 15 | I början av mars planerar Adobe att uppdatera följande länkar i användargränssnittet för Customer Journey Analytics. Uppdatera bokmärkena därefter.<ul><li>**Datavyvningssida, datavyhanterare**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Skapa ny datavy**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Redigera datavy**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Ny länk](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Anslutningshanteraren**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Information om anslutningar**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Redigera anslutning**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Skapa ny anslutning**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2024](/help/release-notes/2024.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
