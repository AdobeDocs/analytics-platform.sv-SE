---
description: Beskriver vilka faktorer som påverkar konsekvensen i mätvärden mellan Real-time Customer Data Platform (CDP i realtid) och CJA.
title: Överensstämmelse mellan CDP och CJA i realtid
role: Admin
feature: CJA Basics
source-git-commit: 2318b303c981ad556dc61a3419af4cce9fbbf92b
workflow-type: tm+mt
source-wordcount: '765'
ht-degree: 0%

---


# Överensstämmelse mellan CDP och CJA i realtid

I verkliga scenarier kan man inte garantera att mätvärdena är konsekventa i Real-time Customer Data Platform (CDP i realtid) och Customer Journey Analytics (CJA). Det här dokumentet förklarar varför.

## CJA använder ännu inte identitetsdiagram

CDP och CJA har inte samma definition av en person i dag. CJA använder ännu inte [Identitetsdiagram](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) informera om sin definition av en person. CDP i realtid bygger helt på informationen i identitetsdiagrammet för att skapa en sammanfogad profil.

CJA använder en metod som kallas [Fältbaserad textning](/help/connections/cca/overview.md) som extraherar identifierare från datauppsättningar i datasjön och använder anpassad logik för att länka samman dem. Under den mellanliggande framtiden förväntas CJA börja använda [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) exporterar till datasjön, vilket möjliggör en gemensam syn på identitet över CDP och CJA i realtid.

>[!IMPORTANT]
>
>Att göra Adobe Experience Platform Identity Service till identitetskällan för alla Adobe Experience Platform-program gör inte automatiskt att mätvärdena blir enhetliga i alla program. Läs vidare för att lära dig varför.

## Flexibilitet i fråga om programdata

Experience Platform tillämpar inte strikta regler för att behålla data mellan kundprofilen i realtid och datasjön på samma sätt. I vissa fall fungerar data som [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) (aktivering) medan andra arbetar utanför [Data Lake](https://business.adobe.com/blog/basics/data-lake) (rapportering och frågetjänst).

CDP-kunder i realtid har vanligtvis inte 100 % av data i Adobe Experience Platform datasjön att gå in i Profil. Detta är utformat - kunderna bör specifikt aktivera data i sjön för profil. Med CJA kan dataanalytiker fritt välja vilka data de vill hämta för analys från datasjön, oberoende av vad som är aktiverat för CDP i realtid.

## Programspecifika modifierare

CJA tillåter omfattande dataändringar vid frågetillfället, t.ex. att kombinera fält, dela upp fält och andra ändringar som valutakonverteringar, deduplicering av värden, sessioner och filtrering på radnivå. Dessa funktioner är inte tillgängliga för CDP.

På samma sätt gäller CDP i realtid [sammanfogningsprinciper](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) fastställa vilka data som ska prioriteras och vilka data som ska kombineras för att skapa en enhetlig bild av en person. Dessa konfigurationer är väl integrerade i varje programs logik och delas inte.

## Beteende vid läsning eller skrivning

För CDP i realtid krävs sammanfogning av punktprofiler med hjälp av det senaste ID-diagrammet.

* CDP i realtid är avsett att sammanställa profilinformation i realtid för aktivering.

* Den kan i realtid hantera alla ändringar av set-identifierarna för en viss användare.

* Uppslagsfönstret styrs av segmentdefinitionen.

CJA kräver att data sammanfogas vid skrivning med ID Graph-export.

* CJA tillämpar komplexa förbearbetningssteg som indexering, delning och gruppering innan data blir klara för analys.

* Personidentifieraren för en viss användare är en viktig del av förbehandlingsstegen. Om personidentifieraren ändras efteråt kommer det att medföra betydande kostnader för upparbetning.

* Uppslagsfönstret styrs på programnivå.

## Skillnader i TTL (Time to Live) och dataöverföring

Även om datauppsättningarna i CDP och CJA i realtid är desamma, kan CDP i realtid bara behålla ett mycket begränsat historikfönster. Däremot har CJA sannolikt många års data. Dessutom:

* CJA- och CDP-kunder i realtid kan ange anpassade kvarhållningsfönster för data, oberoende av varandra.

* CDP och CJA i realtid har olika logik för datainhämtning. CJA ignorerar poster utan ett person-ID eller tidsstämpel och har strikta gränser för hur många poster en enskild profil/person kan ha.

* CDP-kunder i realtid får 7 dagars tillgång till data i sjön, främst för att underlätta datainhämtning i profiler och för ad hoc-frågor.

* Det finns inga TTL-värden för CJA-kundernas data i sjön. CJA-användare kan dock själva ange ett anpassat kvarhållningsfönster i CJA när de skapar en anslutning.

* Profilarkivet i realtid CDP tillåter kundkonfigurerbara TTL:er. Kunderna kan ändra denna TTL till det de behöver för att hålla sig inom sina licensrättigheter.

## Skillnader i behandlingen av den allmänna dataskyddsförordningen

Databearbetningslogik för GDPR och datahygien i realtid är helt annorlunda. Vi arbetar mot en enda strategi.

## Skillnader i fördröjning för dataöverföring

CJA-rapporter innehåller viss fördröjning innan data är tillgängliga för rapportering eller målgruppsskapande. CDP bearbetar data i realtid via olika system med olika fördröjning.