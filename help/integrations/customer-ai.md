---
description: Ta reda på hur AEP Customer AI integreras med Workspace i CJA.
title: Integrera kundens AI med CJA
role: Admin
solution: Customer Journey Analytics
source-git-commit: d59128c34deb7d8fb65d0fad4e6029453c449ea4
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 0%

---


# Integrera kundens AI med CJA

[Kund-AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), som en del av Adobe Experience Platform Intelligent Services, ger marknadsförarna möjlighet att generera kundprognoser på individnivå.

Med hjälp av inflytelserika faktorer kan kundens AI tala om för er vad en kund kan tänkas göra och varför. Dessutom kan marknadsförarna dra nytta av kundernas AI-prognoser och insikter för att personalisera kundupplevelser genom att leverera de lämpligaste erbjudandena och budskapen.

Kundens AI fungerar genom att analysera någon av följande datauppsättningar för att förutsäga bortfall eller konverteringsbenägenhetspoäng:

* Adobe Analytics-data med Analytics-källkopplingen
* Adobe Audience Manager-data med hjälp av Audience Manager-källkopplingen
* Experience Event-datauppsättning
* CEE-datauppsättning (Consumer Experience Event)

Kundens AI integreras med Customer Journey Analytics (CJA) i den utsträckning som kundens AI-aktiverade datauppsättningar kan utnyttjas i datavyer och rapportering i CJA.

## Arbetsflöde

Vissa av stegen utförs i Adobe Experience Platform innan du arbetar med utdata i CJA.

### Steg 1: Hämta AI-poäng för kunder

Hämtning av kundens AI-poäng görs via en kombination av Experience Platform API-anrop, enligt beskrivningen [här](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/getting-started.html?lang=en#downloading-customer-ai-scores).

### Steg 2: Definiera AI-indata och -utdata för kunder

Den här processen beskrivs i [Indata och utdata i kundens AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/input-output.html?lang=en) dokumentation.

### Steg 3: Konfigurera en AI-instans för kund

När du har förberett dina data och har alla dina autentiseringsuppgifter och scheman på plats börjar du med att följa följande [Konfigurera en AI-instans för kund](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) guide.

### Steg 4: Konfigurera en CJA-anslutning till kundens AI-datauppsättningar

I CJA kan du nu [skapa en eller flera anslutningar](/help/connections/create-connection.md) till datauppsättningar från Experience Platform som har instrumenterats för kundens AI. Dessa datauppsättningar visas med prefixet&quot;Customer AI Scores&quot;, vilket visas här:

![CAI-poäng](assets/cai-scores.png)

Varje förutsägelse, som&quot;Sannolikhet att uppgradera konto&quot;, motsvarar en datauppsättning.

Här är ett exempel på ett XDM-schema som CJA skulle ta med som en del av en befintlig datamängd eller en ny datamängd:

![CAI-schema](assets/cai-schema.png)

(Observera att exemplet är en profildatamängd. Samma uppsättning schemaobjekt skulle ingå i en Experience Event-datauppsättning som CJA skulle hämta. Experience Event-datauppsättningen skulle innehålla tidsstämplar som poängdatum.) Alla kunder som får poäng i den här modellen har poäng, scoreDate osv. som är kopplade till dem.

### Steg 5: Skapa datavyer baserade på dessa anslutningar

I CJA kan du nu fortsätta att skapa datavyer med de dimensioner som togs in som