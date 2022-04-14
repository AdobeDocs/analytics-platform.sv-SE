---
title: Infoga Marketo Engage data i AEP och rapportera i CJA
description: Learn how to bring Marketo Engage data into CJA
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
source-git-commit: ad8e3c18dbb73a064662a4543cb0e553cd52cec3
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---

# Ingest Marketo Engage data into AEP and report in CJA

Ni kan utnyttja de nya Marketo Engage-datauppsättningarna i Adobe Experience Platform (AEP) för att tillhandahålla värdefulla analyser och rapporteringslösningar till B2B-marknadsförare. Then report on these datasets in Customer Journey Analytics (CJA.)

## Steg 1: Koppla Marketo källdatafält till deras XDM-mål

Map the [Persons](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#persons) and [Activities](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#activities) objects to their respective XDM schema target fields.

## Step 2: Ingest Marketo data into AEP

Använd [Marketo Engage-kontakt](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=en) för att hämta data från Marketo till Experience Platform och hålla dessa data uppdaterade med plattformsanslutna program.

## Step 3: Set up a connection to this dataset in CJA

In order to report on Experience Platform datasets, you first have to establish a connection between datasets in Experience Platform and CJA. Find more information under [Create a connection](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en).

## Steg 4: Skapa en eller flera datavyer

A [data view](/help/data-views/data-views.md) is a container specific to Customer Journey Analytics that lets you determine how to interpret data from a connection. Här anges alla mått och mätvärden som är tillgängliga i Analysis Workspace - i det här fallet mått och mått som är specifika för Marketo. Det anger också vilka kolumner som måtten och mätvärdena hämtar data från. Data views are defined in preparation for reporting in Analysis Workspace.

## Step 5: Report in Analysis Workspace

Ett exempel du kan utforska är: Hur många webbsidesbesök av leads hade vi i april-juni 2020?

1. Öppna [Arbetsytan Analytics](/help/analysis-workspace/home.md) och skapa ett nytt projekt.
Kunder med B2B/B2P CDP kan utföra analyser i B2C-stil i CJA. B2B objects are not yet available.

1. Skapa en [filter](/help/components/filters/create-filters.md) för webbsidesvyer enligt följande - Händelsetyp = web.webpagedetails.pageViews :

   ![](assets/marketo-filter.png)

1. Dra in filtret som du skapade - webbsidesvyer i friformstabellen och dra sedan in datumintervallet för månad. Detta ger dig möjlighet att besöka webbsidor med hjälp av leads varje månad:

   ![](assets/marketo-freeform.png)

1. Or pull in the following dimensions: Person Key or Work Email Address. På så sätt kan du se vilka webbsidor varje lead besöker:

   ![](assets/marketo-freeform2.png)
