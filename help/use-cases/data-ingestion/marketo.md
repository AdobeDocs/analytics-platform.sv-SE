---
title: Rapport om Marketo Engage-data
description: Lär dig hur du rapporterar Marketo Engage-data i Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
exl-id: ef8a2d08-848b-4072-b400-7b24955a085b
role: Admin
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---

# Rapport om Marketo Engage-data

Ni kan utnyttja de nya Marketo Engage-datamängderna i Adobe Experience Platform (Adobe Experience Platform) för att ge B2B-marknadsförarna värdefulla analys- och rapporteringslösningar. Rapportera sedan om dessa datauppsättningar i Adobe Customer Journey Analytics.

## Steg 1: Mappa Marketo-källdatafält till deras XDM-mål

Mappa objekten [Personer](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#persons) och [Aktiviteter](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/mapping/marketo.html#activities) till deras respektive målfält för XDM-schemat.

## Steg 2: Infoga Marketo-data i Adobe Experience Platform

Använd [Marketo Engage-anslutningen](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo.html) för att hämta data från Marketo till Experience Platform och hålla dessa data uppdaterade med plattformsanslutna program.

## Steg 3: Konfigurera en anslutning till datauppsättningen i Customer Journey Analytics

För att kunna rapportera om Experience Platform datauppsättningar måste du först upprätta en anslutning mellan datauppsättningar i Experience Platform och Customer Journey Analytics. Mer information finns i [Skapa eller redigera en anslutning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html).

## Steg 4: Skapa en eller flera datavyer

En [datavy](/help/data-views/data-views.md) är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en anslutning ska tolkas. Här anges alla mått och mätvärden som är tillgängliga i Analysis Workspace - i det här fallet mått och mått som är specifika för Marketo. Det anger också vilka kolumner som måtten och mätvärdena hämtar data från. Datavyer definieras som förberedelser för rapportering i Analysis Workspace.

## Steg 5: Rapportera i Analysis Workspace

Ett exempel du kan utforska är: Hur många webbsidesbesök av leads hade vi i april-juni 2020?

1. Öppna [Analytics Workspace](/help/analysis-workspace/home.md) och skapa ett nytt projekt.
Kunder med B2B/B2P CDP kan göra analyser i B2C-stil i Customer Journey Analytics. B2B-objekt är ännu inte tillgängliga.

1. Skapa ett [segment](/help/components/filters/create-filters.md) för webbsidesvyer enligt följande - Händelsetyp = web.webpagedetails.pageViews:

   ![Definitionsfönster med händelse- och händelsetyp](../assets/marketo-filter.png)

1. Dra in segmentet som du skapade i frihandstabellen - webbsidesvyer och dra sedan in datumintervallet för månad. Detta ger dig möjlighet att besöka webbsidor med hjälp av leads varje månad:

   ![Frihandstabell med händelser per månad.](../assets/marketo-freeform.png)

1. Eller dra in följande dimensioner: personnyckel eller e-postadress till arbetet. På så sätt kan du se vilka webbsidor varje lead besöker:

   ![Frihandstabell med händelser och workEmail.Address och Web Page Views.](../assets/marketo-freeform2.png)
