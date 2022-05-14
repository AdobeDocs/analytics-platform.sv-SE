---
description: Ta reda på hur AEP Attribution AI kan integreras med Workspace i CJA.
title: Integrera Attribution AI med CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: e75836841cdaf8acd2408723111f13048d31505d
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 4%

---

# Integrera Attribution AI med CJA

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), som en del av Adobe Experience Platform Intelligent Services, är en flerkanalig algoritmisk attribueringstjänst som beräknar påverkan och inkrementell påverkan av kundinteraktioner i förhållande till angivna resultat. Med Attribution AI kan marknadsförarna mäta och optimera marknadsförings- och annonsutgifterna genom att förstå effekten av varje enskild kundinteraktion under varje fas av kundresan.

Attribution AI har stöd för två kategorier av poäng: algoritmisk och regelbaserad. Algoritmiska poäng inkluderar inkrementella och påverkade poäng. Regelbaserade resultat inkluderar First Touch, Last Touch, Linear, U-shaped och Time-Decay.

Attribution AI integreras med Customer Journey Analytics (CJA) i den utsträckning som Attribution AI kör modeller mot data och sedan importerar CJA dessa modellers utdata som en datauppsättning, som sedan kan integreras med resten av CJA-datauppsättningarna. Datauppsättningar som har Attribution AI kan sedan utnyttjas i datavyer och rapporter i CJA.

Attribution AI stöder 3 Experience Platform scheman: Experience Event, Adobe Analytics och Consumer Experience Event.

## Arbetsflöde

Vissa av stegen utförs i Adobe Experience Platform innan du arbetar med utdata i CJA.

### Hämta bakgrundsmusik för Attribution AI

1. I Experience Platform hämtar du Attribution AI enligt beskrivningen [här](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).
1. I Experience Platform skapar du en Attribution AI-instans genom att markera och mappa data, definiera händelser och utbilda data enligt beskrivningen [här](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).
1. I CJA

## Skillnader mellan Attribution AI och Attribution IQ

Så när bör ni använda Attribution AI data jämfört med [Attribution IQ](/help/analysis-workspace/attribution/overview.md), en inbyggd CJA-funktion? I den här tabellen visas några av skillnaderna i funktionalitet:

| Funktionalitet | Attribution AI | Attribution IQ |
| --- | --- | --- |
| Delar attribuering | Ja | Nej |
| Tillåter användare att justera modellen | Nej | Ja |
| Ger attribuering över flera kanaler (Obs! AAI använder inte samma sammanslagna data som CJA gör.) | Ja | Ja |
| Inkluderar inkrementella och påverkade poäng | Ja | Nej |
| Gör HTML-modellering | Ja | Ja |
| Gör HTML-modellering med prognoser | Ja | Nej |

{style=&quot;table-layout:auto&quot;}
