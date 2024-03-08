---
description: Beskriver vilka faktorer som påverkar konsekvensen i mätvärden och antalet målgruppsmedlemskap mellan Real-time Customer Data Platform (CDP i realtid) och Customer Journey Analytics.
title: Överensstämmelse i mätvärden och antalet målgruppsmedlemskap mellan CDP och Customer Journey Analytics i realtid
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---


# Överensstämmelse i mätvärden och antal målgruppsmedlemskap mellan CDP och Adobe Customer Journey Analytics i realtid

I verkliga scenarier kan man inte garantera enhetlighet i mätvärden och målgruppsmedlemskap i Real-time Customer Data Platform (CDP i realtid) och Customer Journey Analytics. Det här dokumentet förklarar varför.

När man jämför antalet målgruppsmedlemskap mellan CDP i realtid och Customer Journey Analytics är det viktigt att tänka på de olika syftena med dessa två verktyg. CDP använder kundprofildata i realtid för att rikta digitala upplevelser till enskilda konsumenter, medan Customer Journey Analytics är utformat för att hjälpa användare att förstå mönster inom viktiga affärsvärden och segment. Publiken kan publicera från Customer Journey Analytics till Real-time CDP och en användare av dessa verktyg kan enkelt och internt &quot;aktivera&quot; en insikt, och dra nytta av inlärningar som gjorts i Customer Journey Analytics, men dessa verktyg har ändå helt olika syften.

## Skillnader i identitetskonfigurationer

CDP och Customer Journey Analytics i realtid har inte samma definition av en person i dag. CDP i realtid är helt beroende av informationen i [Identitetsdiagram](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html) för att skapa en sammanfogad profil.

Customer Journey Analytics kan konfigureras att använda [Stitlar](../stitching/overview.md) som extraherar identifierare från datauppsättningar i datasjön och använder anpassad logik för att länka samman dem.

I framtiden kommer Customer Journey Analytics att kunna använda Identity Graph.

## Skillnader i datauppsättningskonfiguration

Du kan välja att lägga in vissa data i realtid CDP och andra data i Customer Journey Analytics. Ofta väljer kunderna att lägga in mer historiska data i Customer Journey Analytics än vad som är relevant för CDP i realtid. Andra datauppsättningar kan vara mer relevanta för CDP i realtid än för Customer Journey Analytics.

## Skillnader i bearbetningskonfigurationen

Customer Journey Analytics tillåter omfattande dataändringar vid frågetillfället, som att kombinera fält, dela upp fält och andra ändringar som inkluderar/exkluderar, delsträngar, deduplicering av värde, sessionisering och filtrering på radnivå.

CDP erbjuder en annan uppsättning datahanteringsverktyg i realtid. Gäller [sammanfogningsprinciper](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html) fastställa vilka data som ska prioriteras och vilka data som ska kombineras för att skapa en enhetlig bild av en person.

## Skillnader i TTL (Time to Live) och dataöverföring

Även om datauppsättningarna i realtid CDP och Customer Journey Analytics är desamma, kan CDP i realtid bara behålla ett mycket begränsat historikfönster. Däremot har Customer Journey Analytics sannolikt många års data. Dessutom:

* Customer Journey Analytics och CDP-kunder i realtid kan ange anpassade kvarhållningsfönster för data, oberoende av varandra.

* CDP och Customer Journey Analytics i realtid har olika logik för datainhämtning. Customer Journey Analytics ignorerar poster utan ett person-ID eller tidsstämpel och har strikta gränser för hur många poster en enskild profil/person kan ha.

* CDP-kunder i realtid får 7 dagars tillgång till data i sjön, främst för att underlätta datainhämtning i profiler och för ad hoc-frågor.

* Det finns inga TTL-värden för data i sjön för Customer Journey Analytics-kunder. Customer Journey Analytics-användare kan dock själva ange ett anpassat kvarhållningsfönster i Customer Journey Analytics när de skapar en anslutning.

* Profilarkivet i realtid CDP tillåter kundkonfigurerbara TTL:er. Kunderna kan ändra denna TTL till det de behöver för att hålla sig inom sina licensrättigheter.

## Skillnader i fördröjning för dataöverföring

Customer Journey Analytics har ännu inte realtidsfunktionerna i CDP i realtid och därför innehåller Customer Journey Analytics-rapportering viss fördröjning innan data är tillgängliga för rapportering eller målgruppsgenerering. CDP bearbetar data i realtid via olika system med olika fördröjning.
