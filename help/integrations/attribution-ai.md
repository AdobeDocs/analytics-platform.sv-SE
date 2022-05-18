---
description: Ta reda på hur AEP Attribution AI kan integreras med Workspace i CJA.
title: Integrera Attribution AI med CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: 5302d9213b66c327b59c3f4476fbf204f1078392
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 3%

---

# Integrera Attribution AI med CJA

>[!NOTE]
>
>Den här sidan håller på att byggas.

[Attribution AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/overview.html?lang=en), som en del av Adobe Experience Platform Intelligent Services, är en flerkanalig algoritmisk attribueringstjänst som beräknar påverkan och inkrementell påverkan av kundinteraktioner i förhållande till angivna resultat. Med Attribution AI kan marknadsförarna mäta och optimera marknadsförings- och annonsutgifterna genom att förstå effekten av varje enskild kundinteraktion under varje fas av kundresan.

Attribution AI har stöd för två kategorier av poäng: algoritmisk och regelbaserad. Algoritmiska poäng inkluderar inkrementella och påverkade poäng. Regelbaserade resultat inkluderar First Touch, Last Touch, Linear, U-shaped och Time-Decay. Attribution AI stöder 3 Experience Platform scheman: Experience Event, Adobe Analytics och Consumer Experience Event.

Attribution AI integreras med Customer Journey Analytics (CJA) i den utsträckning som Attribution AI kör modeller mot data och sedan importerar CJA dessa modellers utdata som en datauppsättning, som sedan kan integreras med resten av CJA-datauppsättningarna. Datauppsättningar som har Attribution AI kan sedan utnyttjas i datavyer och rapporter i CJA.

## Arbetsflöde

Vissa av stegen utförs i Adobe Experience Platform innan du arbetar med utdata i CJA.

### Steg 1: Hämta bakgrundsmusik för Attribution AI

Hämta bakgrundsmusik i Adobe Experience Platform enligt beskrivningen [här](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/getting-started.html?lang=en#downloading-attribution-ai-scores).

### Steg 2: Skapa en Attribution AI-instans

I Experience Platform skapar du en Attribution AI-instans genom att markera och mappa data, definiera händelser och utbilda data enligt beskrivningen [här](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/attribution-ai/user-guide.html).

### Steg 3: Konfigurera en CJA-anslutning till Attribution AI-datauppsättningar

I CJA kan du nu [skapa en eller flera anslutningar](/help/connections/create-connection.md) till datauppsättningar från Experience Platform som har instrumenterats för Attribution AI. Dessa datauppsättningar visas med prefixet &quot;Attribution AI Scores&quot;, vilket visas här:

![AAI-poäng](assets/aai-scores.png)

### Steg 4: Skapa datavyer baserade på dessa anslutningar

I CJA

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
