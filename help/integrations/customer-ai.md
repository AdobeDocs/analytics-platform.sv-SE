---
description: Ta reda på hur AEP Customer AI integreras med Workspace i CJA.
title: Integrera kundens AI med CJA
role: Admin
solution: Customer Journey Analytics
exl-id: 5411f843-be3b-4059-a3b9-a4e1928ee8a9
source-git-commit: 75e72f94b90ad67a3f8e9506abb09b96a59383d8
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 0%

---

# Integrera kundens AI med CJA

[Kund-AI](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/overview.html?lang=en), som en del av Adobe Experience Platform Intelligent Services, ger marknadsförarna möjlighet att generera kundprognoser på individnivå.

Med hjälp av inflytelserika faktorer kan kundens AI tala om för er vad en kund kan tänkas göra och varför. Dessutom kan marknadsförarna dra nytta av kundernas AI-prognoser och insikter för att personalisera kundupplevelser genom att leverera de lämpligaste erbjudandena och budskapen.

Kundens AI bygger på individuella beteendedata och profildata för benägenhetsbedömning. Kundens AI är flexibelt eftersom det kan användas i flera datakällor, bland annat Adobe Analytics, Adobe Audience Manager, data för kundupplevelsehändelser och händelsedata för upplevelser. Om du använder källkopplingen för Experience Platform för att hämta in Adobe Audience Manager- och Adobe Analytics-data, hämtar modellen automatiskt standardhändelsetyperna för att utbilda och poängsätta modellen. Om du tar med din egen Experience Event-datauppsättning utan standardhändelsetyper måste alla relevanta fält mappas som anpassade händelser eller profilattribut om du vill använda dem i modellen. Detta kan göras i kundens AI-konfigurationssteg i Experience Platform. &#x200B;

Kundens AI integreras med Customer Journey Analytics (CJA) i den utsträckning som kundens AI-aktiverade datauppsättningar kan utnyttjas i datavyer och rapportering i CJA. Med den här integreringen kan du

* **Spåra benägenhetspoäng för ett användarsegment över tid**. Exempel: Hur stor är sannolikheten att en hotellkund köper en showbiljett på hotellets konsertplats?
* **Analysera vilka lyckade händelser eller attribut som är kopplade till benägenhetspoängen**. &#x200B;Exempel: Jag vill förstå attributen eller framgångshändelserna i samband med benägenhetspoängen.
* **Följ anmälningsflödet för kundbenägenhet över olika poängsättningsrundor**. Exempel: Jag skulle vilja förstå personer som till en början var användare med låg benägenhet, och som senare blev användare med stor benägenhet. &#x200B;
* **Titta på hur benägenheten är fördelad**. Användningsfall: Jag skulle vilja förstå hur de benägna poängen är fördelade på mig så att jag kan vara mer exakt med mina segment. &#x200B;Exempel: en återförsäljare vill göra en viss kampanj för 50 dollar i en produkt. De kanske bara vill göra en mycket begränsad befordran på grund av budgeten osv. De analyserar data och bestämmer sig för att endast inrikta sig på de 80 % mer &#x200B; kunderna.
* **Titta på sannolikheten att utföra en åtgärd för en viss kohort över tiden**. Användningsfall: Jag skulle vilja följa upp en viss kohort över tiden. Detta liknar det första, men du kan spåra en viss kohort över tiden. &#x200B; Exempel på hotell: En marknadsförare kan spåra sin bronsnivå jämfört med sin silvernivå, eller silvernivå jämfört med sin guldnivå över tiden. Då ser de varje kohorts benägenhet att boka hotellet över tiden. &#x200B;

## Arbetsflöde

Vissa av stegen utförs i Adobe Experience Platform innan du arbetar med utdata i CJA.

### Steg 1: Konfigurera en AI-instans för kund

När du har förberett dina data och har alla dina autentiseringsuppgifter och scheman på plats börjar du med att följa följande [Konfigurera en AI-instans för kund](https://experienceleague.adobe.com/docs/experience-platform/intelligent-services/customer-ai/user-guide/configure.html?lang=en) i Adobe Experience Platform.

### Steg 2: Konfigurera en CJA-anslutning till kundens AI-datauppsättningar

I CJA kan du nu [skapa en eller flera anslutningar](/help/connections/create-connection.md) till datauppsättningar från Experience Platform som har instrumenterats för kundens AI. Varje förutsägelse, som&quot;Sannolikhet att uppgradera konto&quot;, motsvarar en datauppsättning. Dessa datauppsättningar visas med prefixet&quot;Customer AI Scores in EE Format - name_of_application&quot;.

>[!IMPORTANT]
>
>Varje kund-AI-instans har två utdatamängder om växlingsknappen är aktiverad för att aktivera poäng för CJA under konfigurationen i steg 1. En utdatamängd visas i profilens XDM-format och en i Experience Event XDM-format.

![CAI-poäng](assets/cai-scores.png)

![Skapa anslutning](assets/create-conn.png)

Här är ett exempel på ett XDM-schema som CJA skulle ta med som en del av en befintlig eller ny datamängd:

![CAI-schema](assets/cai-schema.png)

(Observera att exemplet är en profildatamängd. Samma uppsättning schemaobjekt skulle ingå i en Experience Event-datauppsättning som CJA skulle hämta. Experience Event-datauppsättningen skulle innehålla tidsstämplar som poängdatum.) Alla kunder som får poäng i den här modellen har poäng, scoreDate osv. som är kopplade till dem.

### Steg 3: Skapa datavyer baserade på dessa anslutningar

I CJA kan du nu fortsätta till [skapa datavyer](/help/data-views/create-dataview.md) med mått (t.ex. poäng, poängdatum, sannolikhet o.s.v.) och mätvärden som infogades som en del av den anslutning du upprättade.

![Skapa datavy](assets/create-dataview.png)

### Steg 4: Rapport om CAI-poäng i Workspace

Skapa ett nytt projekt och dra in visualiseringar i CJA Workspace.

**Betyg för trendbenägenhet**

Här är ett exempel på ett Workspace-projekt med CAI-data som trendar benägenhetspoängen för ett användarsegment över tiden, i &#x200B; staplade stapeldiagram:

![Poängbukar](assets/workspace-scores.png)

**Tabell med orsakskoder**

Här är en tabell som visar orsakskoder för varför ett segment har hög eller låg &#x200B;:

![Orsakskoder](assets/reason-codes.png)

**Anmälningsflöde för kundbenägenhet**

I det här flödesdiagrammet visas inmatningsflödet för kundens benägenhet jämfört med olika poängserier &#x200B;:

![Inmatningsflöde](assets/flow.png)

**Fördelning av benägenhetspoäng**

I det här stapeldiagrammet visas hur &#x200B; kan fördelas:

![Distribution](assets/distribution.png)

**Propenthypsöverlappningar**

I det här Venedig-diagrammet visas hur benägenheten överlappar olika poäng:

![Propenthypsöverlappningar](assets/venn.png)
