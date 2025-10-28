---
description: Beskriver vilka faktorer som påverkar konsekvensen i mätvärden och antalet målgruppsmedlemskap mellan kunddataplattformen i realtid (CDP) och Customer Journey Analytics.
title: Överensstämmelse mellan mätvärden och målgruppsmedlemskap
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
source-git-commit: 359fe2a718ccef816377083aceb2652b4a905072
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---


# Överensstämmelse mellan mätvärden och målgruppsmedlemskap

I realtidsscenarier kan man inte garantera enhetlighet i mätvärden och målgruppsmedlemskap för kunddataplattformen i realtid (CDP i realtid) och Customer Journey Analytics. Det här dokumentet förklarar varför.

När man jämför antalet målgruppsmedlemskap mellan CDP och Customer Journey Analytics i realtid är det viktigt att tänka på de olika syftena med dessa två verktyg. CDP använder kundprofildata i realtid för att rikta digitala upplevelser till enskilda konsumenter, medan Customer Journey Analytics är utformat för att hjälpa användarna att förstå mönster inom viktiga affärsvärden och segment. Publiken publicerar från Customer Journey Analytics till CDP i realtid och låter en användare av dessa verktyg enkelt och direkt &quot;aktivera&quot; en insikt, och utnyttjar de inlärningar som gjorts i Customer Journey Analytics, men dessa verktyg har ändå helt olika syften.

## Skillnader i identitetskonfigurationer

CDP och Customer Journey Analytics i realtid har inte samma definition av en person idag. CDP i realtid är helt beroende av informationen i [identitetsdiagrammet](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html?lang=sv-SE) för att skapa en sammanfogad profil.

Customer Journey Analytics kan konfigureras att använda [Stitching](../stitching/overview.md). Om du använder [Fältbaserad sammanfogning](/help/stitching/fbs.md) som sammanfogningsmekanism anger du en identifierare från en datauppsättning i datasjön för att sammanfoga data i datauppsättningen med syfte att höja datauppsättningen med förbättrade sammanfogade profiler. Om du använder [Diagrambaserad stygn](/help/stitching/gbs.md) som stygn använder en liknande process identitetsdiagrammet baserat på ett angivet ID-namnutrymme.


## Skillnader i datauppsättningskonfiguration

Du kan välja att lägga in vissa data i CDP i realtid och vissa i Customer Journey Analytics. Ofta väljer kunderna att lägga in mer historiska data i Customer Journey Analytics än vad som är relevant för CDP i realtid. Andra datauppsättningar kan vara mer relevanta för CDP i realtid än för Customer Journey Analytics.

## Skillnader i bearbetningskonfigurationen

Customer Journey Analytics tillåter omfattande dataändringar vid frågetillfället, som att kombinera fält, dela upp fält och andra ändringar som inkluderar/exkluderar, delsträngar, deduplicering av värde, sessionisering och filtrering på radnivå.

CDP erbjuder en annan uppsättning datahanteringsverktyg i realtid. Den tillämpar [sammanfogningsprinciper](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=sv-SE) för att avgöra vilka data som ska prioriteras och vilka data som ska kombineras för att skapa en enhetlig vy för en person.

## Skillnader i TTL (Time to Live) och dataöverföring

Även om datauppsättningarna i CDP och Customer Journey Analytics i realtid är desamma, kan CDP i realtid bara behålla ett mycket begränsat historikfönster. Customer Journey Analytics har däremot antagligen många års data. Dessutom:

* Customer Journey Analytics- och CDP-kunder i realtid kan ange anpassade kvarhållningsfönster för data, oberoende av varandra.

* CDP och Customer Journey Analytics i realtid har olika logik för datainhämtning. Customer Journey Analytics ignorerar poster utan ett person-ID eller tidsstämpel och har strikta gränser för hur många poster en enskild profil/person kan ha.

* CDP-kunder i realtid får 7 dagars tillgång till data i sjön, främst för att underlätta datainhämtning i profiler och för ad hoc-frågor.

* Det finns inga TTL-värden för data i sjön för Customer Journey Analytics-kunder. Customer Journey Analytics-användare kan dock själva ange ett anpassat kvarhållningsfönster i Customer Journey Analytics när de skapar en anslutning.

* Profilarkivet i realtid CDP tillåter kundkonfigurerbara TTL:er. Kunderna kan ändra denna TTL till det de behöver för att hålla sig inom sina licensrättigheter.

## Skillnader i fördröjning för dataöverföring

Customer Journey Analytics har ännu inte realtidsfunktionerna i CDP i realtid och därför innehåller Customer Journey Analytics rapportering viss fördröjning innan data är tillgängliga för rapportering eller målgruppsframställning. CDP bearbetar data i realtid via olika system med olika fördröjning.
