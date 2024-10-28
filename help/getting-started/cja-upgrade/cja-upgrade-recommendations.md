---
title: Rekommenderad sökväg vid uppgradering från Adobe Analytics till Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 711e92db7084592dc562eda3d0dcf33bcb4a62d4
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%

---

# Uppgradera från Adobe Analytics till Customer Journey Analytics

Innan du börjar uppgradera från Adobe Analytics till Customer Journey Analytics måste du först förstå de rekommenderade uppgraderingsstegen.

Beroende på flera faktorer, t.ex. tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen inte är praktiska för din organisation. När du har förstått de rekommenderade uppgraderingsstegen fyller du i enkäten för att dynamiskt generera uppgraderingssteg som är anpassade efter organisationens unika omständigheter.

## 1. Förstå de rekommenderade uppgraderingsstegen

>[!NOTE]
>
>Uppgraderingsstegen som beskrivs i detta avsnitt är de rekommenderade uppgraderingssteg som en organisation kan använda för att uppgradera från Adobe Analytics till Customer Journey Analytics.
>
>Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen inte är praktiska för din organisation. När du har förstått de rekommenderade uppgraderingsstegen fyller du i uppgraderingsenkäten [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/) för att dynamiskt generera uppgraderingssteg som är anpassade efter organisationens unika förhållanden.

De rekommenderade stegen för uppgradering från Adobe Analytics till Customer Journey Analytics är en ny implementering av Experience Platform Web SDK, vilket är den bästa datainsamlingsmetoden för Customer Journey Analytics. I kombination med Web SDK rekommenderar Adobe också att du använder Analytics-källkopplingen för att behålla tidigare Adobe Analytics-data och för att utföra datavämningar sida vid sida.

Efter fullständig övergång till Customer Journey Analytics kan Analytics-källkopplingen stängas av och Experience Platform Web SDK kan användas exklusivt.

1. **Implementera Experience Platform Web SDK**

   En ny implementering av Experience Platform Web SDK är det bästa sättet att samla in data för Customer Journey Analytics. Det är den bästa grunden för att få ut så mycket som möjligt av Customer Journey Analytics, eftersom det är den mest kraftfulla, enkla och framtidssäkra metoden för implementering av Customer Journey Analytics.

   * Högpresterande rapportering och datatillgänglighet eftersom Adobe Experience Platform är byggt för personalisering i realtid

   * Konsolidera implementering för Adobe Experience Cloud datainsamling mellan andra Experience Cloud-produkter (AJO, RTCDP o.s.v.)

   * Inte beroende av Adobe Analytics nomenklatur (prop, eVar, event osv.)

1. **Konfigurera Adobe Analytics-källkopplingen**

   För att underlätta övergången till Experience Platform Web SDK med Customer Journey Analytics rekommenderar Adobe också att du använder Adobe Analytics källanslutning. På så sätt kan du spara historiska data och visa data från din befintliga Adobe Analytics-implementering i Customer Journey Analytics, sida vid sida med data från din nya Experience Platform Web SDK-implementering.

   Med Analytics-källkopplingen kan ni:

   * Lägg in data från Adobe Analytics historiska rapportsserie i Adobe Experience Platform och Customer Journey Analytics.

     Du kan låta Analytics-källkopplingen vara igång så länge du behöver behålla tidigare Adobe Analytics-data.

   * Visa de data som samlats in med den ursprungliga Adobe Analytics-implementeringen (antingen AppMeasurement, Analytics Extension eller Web SDK Extension) i Customer Journey Analytics. Du kan jämföra dessa data sida vid sida med den som finns i den nya Web SDK-implementeringen.

     Du kan hålla Analytics-källkontakten igång tills du känner dig bekant med skillnaderna. <!--elaborate on what those differences are? -->

   Analyskällans koppling som en fristående implementering rekommenderas inte för långtidsanvändning av Customer Journey Analytics. Detta beror på hög latens, klumpiga och komplexa scheman, beroende av Adobe Analytics nomenklatur (prop, eVar o.s.v.) och svårigheter att så småningom gå från källkopplingen till den rekommenderade Web SDK-implementeringen.

## 2. Generera uppgraderingssteg dynamiskt för organisationen

Beroende på flera faktorer, som tidslinje och resursbegränsningar, kanske de rekommenderade uppgraderingsstegen som beskrivs i [Förstå de rekommenderade uppgraderingsstegen](#1-understand-the-recommended-upgrade-steps) inte är praktiska för din organisation.

Så här visar du de dynamiskt genererade uppgraderingsstegen för organisationens unika omständigheter:

1. Fyll i uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

   När du har fyllt i enkäten får du stegvisa instruktioner som beskriver de optimala uppgraderingsstegen som är unika för din organisation. Detta är de uppgraderingssteg som bäst passar din befintliga Adobe Analytics-miljö och dina mål för Customer Journey Analytics.

1. Följ de stegvisa instruktionerna för att uppgradera till Customer Journey Analytics.

<!--

Customer Journey Analytics is the next generation of analytics. It allows multi-channel data collection (both online and offline data), combined with powerful report-time processing functionality (through the definition of components and derived fields in data views). 



When upgrading from Adobe Analytics to Customer Journey Analytics, no single set of upgrade steps exist that are optimal for every organization.

Adobe recommends using the dynamically generated upgrade steps that are unique to your organization. These upgrade steps are generated after you complete an upgrade questionnaire, which helps you understand the best way for your organization to upgrade to Customer Journey Analytics. 

Generic upgrade steps are also available.

1. **Implement the Experience Platform Web SDK**

   A new implementation of the Experience Platform Web SDK provides the best foundation to get the most out of Customer Journey Analytics. 
   
   It is the most performant, straightforward, and future-proof method for implementing Customer Journey Analytics:

   * Highly performant reporting and data availability because Adobe Experience Platform is built to power real-time personalization use cases

   * Consolidate implementation for Adobe Experience Cloud data collection between other Experience Cloud products (AJO, RTCDP, and so forth)

   * Not reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)

1. **Set up the Adobe Analytics source connector**

   The Analytics source connector is a recommended part of the piece when upgrading to Customer Journey Analytics. 

   The Analytics source connector allows you to:

   * Bring your historical Adobe Analytics report suite data into Adobe Experience Platform and Customer Journey Analytics. 
   
     You can keep the Analytics source connector running for as long as you need to retain the historical Adobe Analytics data. 
   
   * View the data collected with your original Adobe Analytics implementation (either AppMeasurement, the Analytics Extension, or the Web SDK Extension) within Customer Journey Analytics. You can compare this data side-by-side with that of your new Web SDK implementation. 
   
     You can keep the Analytics source connector running until you are familiar and comfortable with the differences. <!--elaborate on what those differences are? -->

<!--

   When you no longer need the Analytics source connector because you have enough historical data from your new implementation and you are familiar with the reporting differences in Customer Journey Analytics, you should turn off the Analytics source connector. With the Experience Platform Web SDK implementation, the Analytics source connector is not needed.  
   
   The Analytics source connector as a stand-alone implementation is not a recommended long-term method for using Customer Journey Analytics. This is because of high latency, cluttered and complex schemas, reliance on Adobe Analytics nomenclature (prop, eVar, and so forth), and difficulty in eventually moving from the source connector to the recommended Web SDK implementation. 
   
-->









