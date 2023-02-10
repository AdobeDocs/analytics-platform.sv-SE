---
description: Beskriver vilka faktorer som påverkar konsekvensen i mätvärden och antalet målgruppsmedlemskap mellan Real-time Customer Data Platform (CDP i realtid) och CJA.
title: Överensstämmelse i mätvärden och antal målgruppsmedlemskap mellan CDP och CJA i realtid
role: Admin
feature: CJA Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 34ee7954329d7dc8520031a977bb83d6e1bf3d3d
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# Överensstämmelse i mätvärden och antal målgruppsmedlemskap mellan CDP och CJA i realtid

I verkliga scenarier kan man inte garantera enhetlighet i mätvärden och målgruppsmedlemskap i Real-time Customer Data Platform (CDP i realtid) och Customer Journey Analytics (CJA). Det här dokumentet förklarar varför.

När man jämför antalet målgruppsmedlemskap mellan CDP och CJA i realtid är det viktigt att tänka på de olika syftena med dessa två verktyg. CDP använder kundprofildata i realtid för att rikta digitala upplevelser till enskilda konsumenter, medan CJA är utformat för att hjälpa användarna att förstå mönster i viktiga affärsvärden och segment. Publiken kan publicera från CJA till CDP i realtid, men en användare av dessa verktyg kan enkelt och internt&quot;aktivera&quot; en insikt och dra nytta av CJA:s inlärningar, men dessa verktyg har ändå helt olika syften.

## Skillnader i identitetskonfigurationer

CDP och CJA i realtid har inte samma definition av en person i dag. CDP i realtid är helt beroende av informationen i [Identitetsdiagram](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=en) för att skapa en sammanfogad profil.

CJA kan konfigureras att använda [Flerkanalsanalys](/help/cca/overview.md) som extraherar identifierare från datauppsättningar i datasjön och använder anpassad logik för att länka samman dem.

I framtiden kommer CJA att kunna använda Identity Graph.

## Skillnader i datauppsättningskonfiguration

Du kan välja att lägga in vissa data i CDP i realtid och vissa i CJA; ofta väljer kunderna att lägga in mer historiska data i CJA än vad som är relevant för CDP i realtid. Andra datauppsättningar kan vara mer relevanta för CDP i realtid än för CJA.

## Skillnader i bearbetningskonfigurationen

CJA tillåter omfattande dataändringar vid frågetillfället, t.ex. att kombinera fält, dela upp fält och andra ändringar som inkluderar/exkluderar, delsträngar, deduplicering av värden, sessionisering och filtrering på radnivå.

CDP erbjuder en annan uppsättning datahanteringsverktyg i realtid. Gäller [sammanfogningsprinciper](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) fastställa vilka data som ska prioriteras och vilka data som ska kombineras för att skapa en enhetlig bild av en person.

## Skillnader i TTL (Time to Live) och dataöverföring

Även om datauppsättningarna i CDP och CJA i realtid är desamma, kan CDP i realtid bara behålla ett mycket begränsat historikfönster. Däremot har CJA sannolikt många års data. Dessutom:

* CJA- och CDP-kunder i realtid kan ange anpassade kvarhållningsfönster för data, oberoende av varandra.

* CDP och CJA i realtid har olika logik för datainhämtning. CJA ignorerar poster utan ett person-ID eller tidsstämpel och har strikta gränser för hur många poster en enskild profil/person kan ha.

* CDP-kunder i realtid får 7 dagars tillgång till data i sjön, främst för att underlätta datainhämtning i profiler och för ad hoc-frågor.

* Det finns inga TTL-värden för CJA-kundernas data i sjön. CJA-användare kan dock själva ange ett anpassat kvarhållningsfönster i CJA när de skapar en anslutning.

* Profilarkivet i realtid CDP tillåter kundkonfigurerbara TTL:er. Kunderna kan ändra denna TTL till det de behöver för att hålla sig inom sina licensrättigheter.

## Skillnader i fördröjning för dataöverföring

CJA har ännu inte realtidsfunktionerna i CDP i realtid och som en följd av detta innehåller CJA-rapporter viss fördröjning innan data är tillgängliga för rapportering eller målgruppsgenerering. CDP bearbetar data i realtid via olika system med olika fördröjning.
