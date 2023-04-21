---
title: Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics
description: Konfigurera Adobe Analytics rapporteringsprogram för förtäring i AEP och CJA
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: db5506e0-6159-4d4b-8149-e4966dab9807
source-git-commit: 41847015d581f2ee18bcaa9605bd567d5feb78d8
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 1%

---

# Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics

Adobe Analytics-kunder kan enkelt utnyttja sina rapportsviter i Adobe Experience Platform och Customer Journey Analytics med [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en). I följande diskussion beskrivs hur du gör det.

## Förberedelse

När du är redo att börja använda Adobe Analytics rapporteringsprogram i AEP och CJA finns det flera saker du bör tänka på när du förbereder dina data för en smidig övergång till Customer Journey Analytics. Mer information finns på följande sida:

* [Adobe Analytics till Customer Journey Analytics evolutionen](/help/getting-started/aa-to-cja.md)

## Ställ in rapportsviter för konsumtion i Adobe Experience Platform och CJA

När du har förberett dina data är du redo att börja konfigurera rapportsviter för användning i AEP och CJA.

1. **Skapa ett dataflöde för varje rapportserie som du vill använda i AEP och CJA.** The [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=en) är det verktyg som gör att du kan [skapa en anslutning](/help/connections/create-connection.md) (alias dataflöde) mellan Adobe Analytics och AEP. Du kommer att använda källkopplingen för att skapa ett dataflöde för varje rapportsvit som du vill använda i AEP. Dataflödet skapar en kopia av rapportsvitens data där schemat har konverterats till  [XDM](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html?lang=sv) för konsumtion i AEP-tillämpningar inklusive CJA.<p>Varje rapportsvit som konfigurerats med ett dataflöde via källkopplingen lagras som en separat datauppsättning i AEP Data Lake. 13 månaders historikrapportsvitsdata inkluderas automatiskt i varje dataflöde, och nya data flödar kontinuerligt in i AEP. (Observera att från och med den 26 april 2023 är bakåtfyllnaden i icke-produktionssandlådor begränsad till tre månader.) Med Analytics Source Connector behöver du inte bekymra dig om att skapa schemat i förväg. Ett standardiserat schema som är specifikt för Adobe Analytics skapas automatiskt åt dig. AEP [Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) kan användas för att förbättra det här schemat innan data lagras i Data Lake och görs tillgängliga för CJA. Observera att vissa typer av data filtreras bort av källkopplingen och inte kommer att finnas i datauppsättningen i AEP Data Lake. Andra rader kan filtreras ut mellan Data Lake och CJA. Se [Jämför dina Adobe Analytics-data med CJA-data](/help/troubleshooting/compare.md) för mer information.
1. **Använd Data Prep för att kombinera rapportsviter i CJA.** Data Prep kan användas för många typer av dataomvandling, och ett vanligt användningsområde för Adobe Analytics-data är att lösa skillnader i prop- och/eller eVar-mappningar mellan flera rapportsviter så att rapportsviterna enkelt kan kombineras i CJA. Se [kombinera rapportsviter med olika scheman](/help/use-cases/aa-data/combine-report-suites.md) för mer information.
1. **Aktivera flerkanalsanalys** vid behov. När du kombinerar flera datauppsättningar i CJA kan funktionerna för identitetssammanfogning i Cross-Channel Analytics hjälpa dig att matcha olika ID-namnutrymmen till ett sammanfogat ID för en enda vy av kunden över olika enheter och kanaler. Se [Översikt över flerkanalsanalys](/help/cca/overview.md) för mer information.
1. **Skapa en eller flera CJA-anslutningar.** När datauppsättningarna för dina rapportsviter är tillgängliga i AEP Data Lake kan du skapa en eller flera [CJA-anslutningar](/help/connections/overview.md) för att överföra dessa datauppsättningar till CJA. I en anslutning kan rapportsvitens data kombineras med andra typer av data, vilket gör att ni kan skapa en helhetsbild av kundupplevelserna.
1. **Skapa en eller flera CJA-datavyer.** A [datavy](/help/data-views/data-views.md) är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en CJA-anslutning ska tolkas. Datavyer har många kraftfulla [konfigurationsalternativ](/help/data-views/create-dataview.md) för att anpassa de data som presenteras för användarna i [Analysis Workspace](/help/analysis-workspace/home.md).

## Jämföra Customer Journey Analytics och Adobe Analytics

Customer Journey Analytics och Adobe Analytics har ett antal likheter. Till exempel har både CJA och Adobe Analytics kraften hos Analysis Workspace för kostnadsfri tankeanalys. Men eftersom CJA är ett program inom Adobe Experience Platform och använder AEP för dataöverföring skiljer sig CJA och Adobe Analytics åt på flera viktiga sätt. Följande artiklar är användbara för att förstå skillnaderna:

* [Jämför dina Adobe Analytics-data med CJA-data](/help/troubleshooting/compare.md)
* [Funktioner i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md)
* [Jämför terminologi för analysdata som skickas via Analytics Source Connector](/help/getting-started/aa-vs-cja/terminology.md)
* [Jämför databearbetning i Adobe Analytics- och CJA-rapporteringsfunktioner](/help/getting-started/aa-vs-cja/data-processing-comparisons.md)
* [Virtuella rapportsviter, datavyer, AEP-sandlådor och Analytics Source Connector](/help/getting-started/aa-vs-cja/vrs-dataview-sandbox-adc.md)
* [Bearbetningsregler, VISTA och klassificeringar jämfört med Data Prep](/help/getting-started/aa-vs-cja/pr-vista-dataprep.md)
* [STÖD, ECID, AACUSTOMID och Analytics Source Connector](/help/getting-started/aa-vs-cja/aaid-ecid-adc.md)
