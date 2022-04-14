---
title: Infoga B2B-data i AEP och rapportera i CJA
description: Lär dig hur du hämtar Marketo-data till CJA
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: e18de2563427941f8c227881b46f73c490be218d
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 0%

---


# Infoga Marketo B2B-data i AEP och rapportera i CJA

Ni kan utnyttja de nya Marketo B2B-datamängderna i Adobe Experience Platform (AEP) för att ge B2B-marknadsförarna värdefulla analys- och rapporteringslösningar. Rapportera sedan om dessa datauppsättningar i Customer Journey Analytics (CJA.)

## Steg 1: Koppla Marketo källdatafält till deras XDM-mål

Mappa [Personer](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#persons) och [Verksamhet](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html?lang=en#activities) till respektive målfält för XDM-schema.

## Steg 2: Infoga Marketo-data i AEP

Använd [Marketo Engage-kontakt](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html?lang=en) för att hämta in B2B-data från Marketo till Experience Platform och hålla dessa data uppdaterade med plattformsanslutna program.

## Steg 3: Konfigurera en anslutning till den här datauppsättningen i CJA

För att kunna rapportera om datauppsättningar från Experience Platform måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och CJA. Mer information finns under [Skapa en anslutning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en).

## Steg 4: Skapa en eller flera datavyer

A [datavy](/help/data-views/data-views.md) är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en anslutning ska tolkas. Här anges alla mått och mätvärden som är tillgängliga i Analysis Workspace - i det här fallet mått och mått som är specifika för Marketo. Det anger också vilka kolumner som måtten och mätvärdena hämtar data från. Datavyer definieras som förberedelser för rapportering i Analysis Workspace.

## Steg 5: Rapportera i Analysis Workspace

Ett exempel du kan utforska är: Hur många webbsidesbesök av leads hade vi i april-juni 2020?

1. Öppna [Arbetsytan Analytics](/help/analysis-workspace/home.md) och skapa ett nytt projekt.

1. Skapa en [filter](/help/components/filters/create-filters.md) för webbsidesvyer enligt följande - Händelsetyp = web.webpagedetails.pageViews :

   ![](assets/marketo-filter.png)

1. Dra in filtret som du skapade - webbsidesvyer i friformstabellen och dra sedan in datumintervallet för månad. Detta ger dig möjlighet att besöka webbsidor med hjälp av leads varje månad:

   ![](assets/marketo-freeform.png)

1. Eller dra i följande dimensioner: Personnyckel eller e-postadress till arbetet. På så sätt kan du se vilka webbsidor varje lead besöker:

   ![](assets/marketo-freeform2.png)
