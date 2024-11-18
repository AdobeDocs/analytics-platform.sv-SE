---
title: Förstå hur Adobe Analytics implementeras och hur det påverkar din uppgradering till Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: b9cff809-6df7-4d75-9bc1-0cc12074d355
source-git-commit: 5ce69400a01566728f374d68ac08a981adfd8b6e
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 1%

---

# Förstå hur Adobe Analytics implementeras och hur det påverkar din uppgradering till Customer Journey Analytics

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i checklistan för uppgradering av [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Det finns olika sätt att implementera Adobe Analytics. När du uppgraderar till Customer Journey Analytics är inte alla uppgraderingsalternativ tillgängliga för alla Adobe Analytics-implementeringar. Den rekommenderade uppgraderingssökvägen är dock tillgänglig oavsett hur Adobe Analytics implementeras i din organisation.

Använd informationen nedan för att lära dig mer om hur Adobe Analytics implementeras och vilka uppgraderingsalternativ som finns tillgängliga för din organisation.

Kontakta din Adobe-representant om du behöver mer specifik rådgivning, vägledning eller support.

| Befintlig Adobe Analytics-implementering | Beskrivning | Tillgängliga uppgraderingssökvägar |
|---------|----------|----------|
| AppMeasurement | AppMeasurement för JavaScript har tidigare varit ett vanligt sätt att implementera Adobe Analytics.<p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med AppMeasurementet för JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/js/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Ny implementering av Experience Platform Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Analytics Source Connector</li></ul> |
| Adobe Analytics-tillägg (taggar) | <p>Taggar i Adobe Experience Platform är en tagghanteringslösning som gör att ni kan driftsätta Analytics-kod tillsammans med andra taggningskrav. Adobe erbjuder integreringar med andra lösningar och produkter och låter er driftsätta anpassad kod. Alla dessa uppgifter kan utföras utan att någon utvecklingsteam i organisationen behöver uppdatera koden på er webbplats.</p><p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Analytics-tillägget](https://experienceleague.adobe.com/en/docs/analytics/implementation/launch/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Ny implementering av Experience Platform Web SDK</li><li>Migrera Adobe Analytics till Web SDK</li><li>Analytics Source Connector</li></ul> |
| Experience Platform Web SDK (alloy.js) | Experience Platform Web SDK är den metod som rekommenderas av Adobe för att implementera Adobe Analytics. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. <p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Edge Network](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li></ul> |
| Experience Platform Web SDK-tillägg (taggar) | Experience Platform Web SDK är den metod som rekommenderas av Adobe för att implementera Adobe Analytics för webbdata. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats. <p>Mer information om implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li></ul> |
| Mobilt SDK för Experience Platform | Experience Platform Mobile SDK är den metod som Adobe rekommenderar för att implementera Adobe Analytics för mobildata. Med Adobe Experience Platform Edge Network kan du skicka data till flera produkter på en central plats.<p>Adobe Experience Platform Mobile SDK hjälper er att driva lösningar och tjänster från Adobe Experience Cloud i era mobilappar. </p><p>Mer information om den här implementeringstypen finns i [Implementera Adobe Analytics med Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/mobile-sdk/overview)</p> | <ul><li>(Rekommenderas) Ny implementering av Experience Platform Web SDK med Analytics Source Connector</li><li>Konfigurera Adobe Analytics Web SDK-implementeringen för att skicka data till plattformen</li></ul> |

{style="table-layout:auto"}
