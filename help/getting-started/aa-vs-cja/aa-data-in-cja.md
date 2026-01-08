---
title: Använd Adobe Analytics rapportsvitsdata i Customer Journey Analytics
description: Så här konfigurerar du Adobe Analytics rapporteringsprogram för konsumtion i Adobe Experience Platform och Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: e74bbcc385aa90ba05c628a7d37598c6692530ed
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 0%

---

# Använd Adobe Analytics rapportsviter

Adobe Analytics-kunder kan enkelt utnyttja sina rapportsviter i Experience Platform och Customer Journey Analytics med [Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html). I följande diskussion beskrivs hur du gör det.

>[!IMPORTANT]
>
>Du måste ha paketet **Select** för att kunna utföra dataanalys i flera rapportsviter. Kontakta administratören om du är osäker på vilket Customer Journey Analytics-paket du har.

## Förberedelse

När du är redo att börja använda Adobe Analytics rapporteringsprogram i Adobe Experience Platform och Customer Journey Analytics finns det flera saker du bör tänka på när du förbereder dina data för en smidig övergång till Customer Journey Analytics. Mer information finns på följande sida:

* [Adobe Analytics till Customer Journey Analytics](/help/getting-started/aa-to-cja.md)

## Skapa rapportsviter för konsumtion i Adobe Experience Platform och Customer Journey Analytics

När du har förberett dina data kan du börja konfigurera rapportsviter för användning i Adobe Experience Platform och Customer Journey Analytics.

1. **Skapa ett dataflöde för varje rapportserie som du vill använda i Adobe Experience Platform och Customer Journey Analytics.** [Analyskällans koppling ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html) är det verktyg som gör att du kan [skapa en anslutning](/help/connections/create-connection.md) (ett dataflöde) mellan Adobe Analytics och Adobe Experience Platform. Du kommer att använda källkopplingen för att skapa ett dataflöde för varje rapportsvit som du vill använda i Adobe Experience Platform. Dataflödet skapar en kopia av rapportsvitsdata där schemat har konverterats till [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html) för användning av Adobe Experience Platform-program inklusive Customer Journey Analytics.<p>Varje rapportsvit som konfigurerats med ett dataflöde via källkopplingen lagras som en separat datauppsättning i Adobe Experience Platform Data Lake. 13 månaders historiska rapportsviter inkluderas automatiskt i varje dataflöde, och nya data kommer att flöda in i Adobe Experience Platform kontinuerligt. (Observera att från och med den 26 april 2023 är bakåtfyllnaden i icke-produktionssandlådor begränsad till tre månader.) Med Analytics-källkopplingen behöver du inte bekymra dig om att skapa schemat i förväg. Ett standardiserat schema som är specifikt för Adobe Analytics skapas automatiskt åt dig. Adobe Experience Platform [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html)-verktyg kan dock användas för att förbättra det här schemat innan data lagras i Data Lake och görs tillgängliga för Customer Journey Analytics. Observera att vissa typer av data segmenteras ut av källkopplingen och inte finns med i datauppsättningen i Adobe Experience Platform Data Lake. Andra rader kan segmenteras mellan Data Lake och Customer Journey Analytics. Mer information finns i [Jämför dina Adobe Analytics-data med Customer Journey Analytics-data](/help/troubleshooting/compare.md).
1. **Använd Data Prep för att kombinera rapportsviter i Customer Journey Analytics.** Data Prep kan användas för många typer av dataomvandling, och ett vanligt användningsområde för Adobe Analytics-data är att lösa skillnader i utkast- och/eller eVar-mappningar över flera rapportsviter så att rapportsviterna enkelt kan kombineras inom Customer Journey Analytics. Mer information finns i [kombinera rapportsviter med olika scheman](/help/use-cases/aa-data/combine-report-suites.md).
1. **Aktivera namngivning** efter behov. När du kombinerar flera datauppsättningar i Customer Journey Analytics kan sammanfogningsfunktionerna hjälpa dig att matcha olika ID-namnutrymmen till ett sammanfogat ID för en enda vy av kunden över olika enheter och kanaler. Mer information finns i [Stitching overview](../../stitching/overview.md).
1. **Skapa en eller flera Customer Journey Analytics-anslutningar.** När datauppsättningarna för dina rapportsviter är tillgängliga i Adobe Experience Platform Data Lake kan du skapa en eller flera [Customer Journey Analytics-anslutningar](/help/connections/overview.md) för att hämta de datauppsättningarna till Customer Journey Analytics. I en anslutning kan rapportsvitens data kombineras med andra typer av data, vilket gör att ni kan skapa en helhetsbild av kundupplevelserna.
1. **Skapa en eller flera datavyer för Customer Journey Analytics.** En [datavy](/help/data-views/data-views.md) är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en Customer Journey Analytics-anslutning ska tolkas. Datavyer har många kraftfulla [konfigurationsalternativ](/help/data-views/create-dataview.md) för att anpassa data som visas för användarna i [Analysis Workspace](/help/analysis-workspace/home.md).

## Jämföra Customer Journey Analytics och Adobe Analytics

Customer Journey Analytics och Adobe Analytics har ett antal likheter. Till exempel har både Customer Journey Analytics och Adobe Analytics kraften hos Analysis Workspace för kostnadsfri tankeanalys. Men eftersom Customer Journey Analytics är ett program inom Adobe Experience Platform och använder Adobe Experience Platform för dataöverföring skiljer sig Customer Journey Analytics och Adobe Analytics åt på flera viktiga sätt. Följande artiklar är användbara för att förstå skillnaderna:

* [Jämför dina Adobe Analytics-data med Customer Journey Analytics-data](/help/troubleshooting/compare.md)
* [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Jämför terminologi för analysdata som skickas via Analytics-källkopplingen](/help/getting-started/aa-vs-cja/terminology.md)
* [Jämför databehandling i Adobe Analytics och Customer Journey Analytics rapporteringsfunktioner](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Virtuella rapportsviter, datavyer, Adobe Experience Platform-sandlådor och källkopplingen för Analytics](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [AAID, ECID, AACUSTOMID och Analytics-källkopplingen](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
