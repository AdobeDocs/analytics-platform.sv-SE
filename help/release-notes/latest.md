---
title: Visa versionsinformation för Customer Journey Analytics
description: Versionsinformation för senaste Customer Journey Analytics
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 20e99275a42312ed974ac4c1af28ede73180e748
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 1%

---

# Aktuell versionsinformation för Adobe Customer Journey Analytics (mars 2024)

**Senaste uppdatering**: 20 mars 2024

Versionskommentarerna gäller den 13 mars till och med april 2024. Adobe Customer Journey Analytics-releaser fungerar på en [kontinuerlig leveransmodell](releases.md) vilket ger en mer skalbar, stegvis metod för driftsättning av funktioner. Därför uppdateras versionsinformationen flera gånger i månaden. Kontrollera dem regelbundet.

## Nya eller uppdaterade funktioner

| Funktion | Beskrivning | [Startar](releases.md) | [Allmän tillgänglighet](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Ny kolumn som är tillgänglig på startsidan för projekt** | The **[!UICONTROL Last used]** -kolumnen är nu tillgänglig när du visar fliken Projekt på fliken [Customer Journey Analytics landningssida](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html). <p>Den här informationen kan hjälpa dig att avgöra om ett projekt är värdefullt för användare i organisationen genom att visa datum och tid när projektet senast öppnades. Tidigare **[!UICONTROL Last used]** kolumnen var bara tillgänglig i Beräknat mått-hanteraren, Segment-hanteraren och Alerts-hanteraren.</p> |  | 13 mars 2024 |
| **Användningsstatistik** | The [gränssnitt för användningsstatistik](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html) visar hur inkapslade och rapportbara rader används i alla anslutningar. Med det här gränssnittet kan du avgöra om din användning i Customer Journey Analytics överensstämmer med det som avtalats. |  | 13 mars 2024 |
| **Media Analytics-rapportering - genomsnittlig miniatyrpublik (AMA)** | Panelen för genomsnittlig minutpublik är nu tillgänglig i CJA. Media Analytics-kunder kan använda panelen för normal målgrupp för att bättre förstå den genomsnittliga användningen av deras innehåll. <p>Den genomsnittliga minuten-målgruppen möjliggör jämförelser av programmering oavsett längd eller genre. Dessutom kan kunderna jämföra eller lägga till den digitala genomsnittliga minuten-publiken med den linjära minuten-mätningen för tv.</p><p> Panelen ger större flexibilitet för att mäta den genomsnittliga publiken för anpassade tidsperioder samt när tidsklassificeringen har uppdaterats efter detta.</p><p>Mer information finns i [Panelen Mediegenomsnitt för miniatyrmålgrupp](/help/analysis-workspace/c-panels/average-minute-audience-panel.md).</p> |  | 12 mars 2024 |
| **B2B-schemaomvandling för person till konto** | Gör att du kan omvandla datauppsättningar för att bättre stödja personbaserade uppslag i Customer Journey Analytics B2B-rapportscenarier. Den här funktionen är tillgänglig för datauppsättningar för B2B-scheman baserat på följande klasser:<ul><li>XDM Business Account Person Relation</li><li>XDM - affärsmöjlighet, personrelation</li><li>XDM Business Marketing List-medlemmar</li><li>XDM Business Campaign-medlemmar</li></ul> | | 26 mars 2024 |
| **Användning av Report Builder ingår i kolumnen Används i i Beräknat mått-hanteraren och Filterhanteraren** | När du visar **Används i** i Beräknade mätvärden-hanteraren eller filterhanteraren är användningsdata nu tillgängliga för Report Builder.<p>Tidigare var användningsdata i filterhanteraren bara tillgängliga för aviseringar, projekt, schemalagda projekt och beräknade mätvärden. Användningsdata i hanteraren för beräknade mätvärden var endast tillgängliga för aviseringar, projekt och schemalagda projekt.</p> |  | Sent mars eller tidig april |
| **Adobe Product Analytics: Jämför händelser i ett enda trattsteg** | I vyn Funnel: Friction kan du nu jämföra händelser i ett enda tratt-steg. Detta är särskilt användbart när resan innehåller stegalternativ eller ett steg där ett A/B-experiment utförs. | 29 mars 2024 | 12 april 2024 |
| **Administratörer kan hantera alla platser och konton i sin organisation** | Ett nytt alternativ på fliken Platser (på sidan Komponenter > Exportera) gör att administratörer kan visa och hantera alla platser i organisationen. <p>Ett nytt alternativ på fliken Platskonton (på sidan Komponenter > Exportera) gör att administratörer kan visa och hantera alla konton i organisationen.</p><p>Tidigare kunde administratörer bara visa och hantera de platser och konton som de skapade.</p> | | April 2024 |
| **Publiken publiceras i ett nytt&quot;Publiker&quot;-avsnitt i Experience Platform** | Publikationer som publiceras från Customer Journey Analytics finns nu tillgängliga i det nya avsnittet Publiker i Experience Platform. Tidigare fanns målgrupper som publicerades från Customer Journey Analytics tillgängliga i Platform under segmentavsnittet. Den här förbättringen ger följande fördelar:<ul><li>Publiken har inte längre en timmes fördröjning innan de visas i Platform; de är tillgängliga sekunder efter att de publicerats.</li><li>Publiken kan sorteras i Platform med kolumnen &quot;Ursprung&quot; som visar det program som målgruppen ursprungligen publicerades från.</li><li>Filtrerings- och sorteringsalternativen i Platform gör att du snabbare kan hitta relevanta målgrupper.</li></ul>Mer information finns i avsnittet [Använda Customer Journey Analytics-målgrupper i Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#audiences-aep). |  | April 2024 |
| **Upptäck Edge-robotidentifiering** | [Punktavkänning](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) gör att du kan identifiera händelser som genererats av Web SDK, Mobile SDK och Server API som om de genererats av kända spindlar och bottar. | | 29 april 2024 |

{style="table-layout:auto"}

## Korrigeringar i Customer Journey Analytics

AN-340429; AN-341544; AN-341974; AN-342176; AN-342391

## Viktiga meddelanden för Customer Journey Analytics-administratörer

| Meddelande | Meddelande har lagts till eller uppdaterats | Beskrivning |
| --- | --- | --- |
| **Uppdaterade länkar i användargränssnitt för datavyer och anslutningar** | Februari 15 | I början av mars planerar Adobe att uppdatera följande länkar i användargränssnittet för Customer Journey Analytics. Uppdatera bokmärkena därefter.<ul><li>**Datavyvningssida, datavyhanterare**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**Skapa ny datavy**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**Redigera datavy**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [Ny länk](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**Anslutningshanteraren**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**Information om anslutningar**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**Redigera anslutning**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**Skapa ny anslutning**: [Befintlig länk](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [Ny länk](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |
| Tillägg för Adobe API-objektmedlemmar | 17 januari 2024 | Adobe kan lägga till valfria fråge- och svarsmedlemmar (namn/värde-par) i befintliga API-objekt utan föregående meddelande eller ändringar i versionshanteringen. Sådana tillägg bör vara fasta ändringar för implementeringen. Adobe rekommenderar att du läser API-dokumentationen för alla tredjepartsverktyg som du integrerar med våra API:er så att sådana tillägg ignoreras vid bearbetningen om de inte tolkas. Adobe tar inte bort parametrar eller lägger till obligatoriska parametrar utan att först skicka standardmeddelanden via versionsinformation. |

{style="table-layout:auto"}

## Relaterade resurser

* [Versionsinformation om tidigare Customer Journey Analytics för 2023](/help/release-notes/2023.md)
* [Versionsinformation för Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
* [Versionsinformation om Media Analytics](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html)
* [Versionsinformation för Adobe Experience Cloud](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)
* [Dokumentationsuppdateringar för Customer Journey Analytics](/help/release-notes/doc-changes.md)
