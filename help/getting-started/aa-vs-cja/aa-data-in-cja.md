---
title: Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics
description: Konfigurera Adobe Analytics rapporteringsprogram för konsumtion i Adobe Experience Platform och Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 1%

---

# Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics

Adobe Analytics-kunder kan enkelt utnyttja sina rapportsviter i Adobe Experience Platform och Customer Journey Analytics med [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en). I följande diskussion beskrivs hur du gör det.

## Förberedelse

När du är redo att börja använda Adobe Analytics rapporteringsprogram i Adobe Experience Platform och Customer Journey Analytics finns det flera saker du bör tänka på när du förbereder dina data för en smidig övergång till Customer Journey Analytics. Mer information finns på följande sida:

* [Adobe Analytics till Customer Journey Analytics evolutionen](/help/getting-started/aa-to-cja.md)

## Ställ in rapportsviter för konsumtion i Adobe Experience Platform och Customer Journey Analytics

När du har förberett dina data är du redo att börja konfigurera rapportsviter för användning i Adobe Experience Platform och Customer Journey Analytics.

1. **Skapa ett dataflöde för varje rapportserie som du vill använda i Adobe Experience Platform och Customer Journey Analytics.** The [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) är det verktyg som gör att du kan [skapa en anslutning](/help/connections/create-connection.md) (alias dataflöde) mellan Adobe Analytics och Adobe Experience Platform. Du kommer att använda källkopplingen för att skapa ett dataflöde för varje rapportsvit som du vill använda i Adobe Experience Platform. Dataflödet skapar en kopia av rapportsvitens data där schemat har konverterats till  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=sv) för användning i Adobe Experience Platform, inklusive Customer Journey Analytics.<p>Varje rapportsvit som konfigurerats med ett dataflöde via källkopplingen lagras som en separat datauppsättning i Adobe Experience Platform Data Lake. 13 månaders historiska rapportsviter inkluderas automatiskt i varje dataflöde, och nya data kommer att flöda in i Adobe Experience Platform kontinuerligt. (Observera att från och med den 26 april 2023 är bakåtfyllnaden i icke-produktionssandlådor begränsad till tre månader.) Med Analytics Source Connector behöver du inte bekymra dig om att skapa schemat i förväg. Ett standardiserat schema som är specifikt för Adobe Analytics skapas automatiskt åt dig. Adobe Experience Platform [Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) kan användas för att förbättra det här schemat innan data lagras i Data Lake och görs tillgängliga för Customer Journey Analytics. Observera att vissa typer av data filtreras bort av källkopplingen och inte finns i datauppsättningen i Adobe Experience Platform Data Lake. Andra rader kan filtreras ut mellan Data Lake och Customer Journey Analytics. Se [Jämför dina Adobe Analytics-data med Customer Journey Analytics-data](/help/troubleshooting/compare.md) för mer information.
1. **Använd Data Prep för att kombinera rapportsviter i Customer Journey Analytics.** Data Prep kan användas för många typer av dataomvandling, och ett vanligt användningsområde för Adobe Analytics-data är att lösa skillnader i prop- och/eller eVar-mappningar mellan flera rapportsviter så att rapportsviterna enkelt kan kombineras inom Customer Journey Analytics. Se [kombinera rapportsviter med olika scheman](/help/use-cases/aa-data/combine-report-suites.md) för mer information.
1. **Aktivera textning** vid behov. När du kombinerar flera datauppsättningar i Customer Journey Analytics kan sammanfogningsfunktionerna hjälpa dig att matcha olika ID-namnutrymmen till ett sammanfogat ID för en enda vy av kunden över olika enheter och kanaler. Se [Översikt över titlar](../../stitching/overview.md) för mer information.
1. **Skapa en eller flera Customer Journey Analytics-anslutningar.** När datauppsättningarna för dina rapportsviter är tillgängliga i Adobe Experience Platform Data Lake kan du skapa en eller flera [Customer Journey Analytics-anslutningar](/help/connections/overview.md) för att föra in dessa datauppsättningar i Customer Journey Analytics. I en anslutning kan rapportsvitens data kombineras med andra typer av data, vilket gör att ni kan skapa en helhetsbild av kundupplevelserna.
1. **Skapa en eller flera datavyer i Customer Journey Analytics.** A [datavy](/help/data-views/data-views.md) är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en anslutning till Customer Journey Analytics ska tolkas. Datavyer har många kraftfulla [konfigurationsalternativ](/help/data-views/create-dataview.md) för att anpassa de data som presenteras för användarna i [Analysis Workspace](/help/analysis-workspace/home.md).

## Jämföra Customer Journey Analytics och Adobe Analytics

Customer Journey Analytics och Adobe Analytics har ett antal likheter. Till exempel har både Customer Journey Analytics och Adobe Analytics kraften hos Analysis Workspace för kostnadsfri tankeanalys. Eftersom Customer Journey Analytics är ett program inom Adobe Experience Platform och använder Adobe Experience Platform för dataöverföring skiljer sig Customer Journey Analytics och Adobe Analytics åt på flera viktiga sätt. Följande artiklar är användbara för att förstå skillnaderna:

* [Jämför dina Adobe Analytics-data med Customer Journey Analytics-data](/help/troubleshooting/compare.md)
* [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Jämför terminologi för analysdata som skickas via Analytics Source Connector](/help/getting-started/aa-vs-cja/terminology.md)
* [Jämför databehandling i Adobe Analytics och Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Virtual Report Suites, Data Views, Adobe Experience Platform Sandboxes och Analytics Source Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [STÖD, ECID, AACUSTOMID och Analytics Source Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
