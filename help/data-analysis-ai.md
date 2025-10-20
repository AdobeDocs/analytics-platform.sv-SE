---
description: Så här ställer du frågor om dataanalys i Customer Journey Analytics-dokumentationen
title: Visualisera data med Data Insights Agent i Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: bb44ba8d36a2c21c789f0df6a84ea0432ca20029
workflow-type: tm+mt
source-wordcount: '2388'
ht-degree: 0%

---

# Visualisera data med Data Insights Agent

>[!AVAILABILITY]
>
>Data Insights Agent är tillgängligt för berättigade kunder under en begränsad tid. Åtkomsten till Data Insights Agent upphör 30 november 2025. Om du vill fortsätta använda Data Insights Agent utan avbrott kontaktar du Adobe kontorepresentant för att få veta mer om Data Insights Agent licenser.

Data Insights Agent, som är tillgängligt från [AI-assistenten](/help/ai-assistant.md) i Customer Journey Analytics, är en generativ AI-konversationsagent som snabbt och effektivt besvarar frågor om dina data. Det bygger upp relevanta visualiseringar i Analysis Workspace med komponenter från datavyn och med era faktiska data.

Genom att använda Data Insights Agent för att besvara datacentrerade frågor i Analysis Workspace kan du spara oräkneliga timmar som du annars skulle behöva lägga på att manuellt skapa visualiseringar i Analysis Workspace och bekanta dig med komponenterna i datavyn.

![Data Insights Agent i AI-assistenten](assets/cja-ai-asst-da.gif)

## Funktioner som är inom och utanför omfånget

| Funktion | I omfånget | Odefinierad |
| --- | --- | --- |
| **Visualiseringstyper** | <ul><li>Linje</li><li>Flera rader</li><li>Frihandsregister</li><li>Liggande</li><li>Munk</li><li>Sammanfattningsnummer</li></ul> | <ul><li>Flöde</li><li>Utfall</li><li>Kohortabell</li><li>Område, staplat område</li><li>Stapel, staplad</li><li>Punkt</li><li>Kombination</li><li>Histogram</li><li>Vågrätt streck, vågrätt streck</li><li>Sammanfattning av nyckelmått</li><li>Spridning</li><li>Sammanfattningsändring</li><li>Text</li><li>Treemap</li><li>Venn</li><li>Guidad analys: aktiv tillväxt, konverteringstrender, engagemang, förstahandseffekt, frekvens, tratt, nettotillväxt, Release impact, Retention, Timeline, Trends</li></ul> |
| **Workspace-åtgärder och agentfunktioner** | <ul><li>Skapa och uppdatera visualiseringar<p>Skapar en friformstabell och tillhörande visualisering (t.ex. en linje, streck, munstycke).<p>Exempel: *Vad är vinsten för SKU:er från februari till maj?*</p></li><li>Ställ uppföljningsfrågor<p>Svara på en fråga i sammanhanget från tidigare uppmaningar. Exempel:</p> <ul><li>Fråga 1: *Trendhändelser från mars.*</li><li>Fråga 2: *Visa data från mars till april i stället*</li></ul> </li><li>Odefinierad snabb upptäckt<p>Om du skickar en fråga som ligger utanför omfånget, till exempel *Exportera det här projektet*, svarar Data Insights Agent genom att informera dig om att frågan ligger utanför omfånget.</p></li></ul> | <ul><li>Dela</li><li>Exportera</li><li>Ladda ned</li><li>Hantera användarinställningar</li><li>Hantera datavy</li><li>Analytics Dashboards-app</li><li>Tillskrivning</li><li>Sammanfattning eller svar direkt<p>Data Insights Agent kan inte svara direkt i chattfältet med ett kortfattat svar från en användarfråga. Exempel på uppmaningar som inte omfattas är *Ge mig en sammanfattning av insikterna från min senaste fråga* och *Sammanfatta markeringarna från radvisualiseringen.*</p></li></ul> |
| **Tydligare frågor** | Om du ställer en fråga som inte har tillräckligt sammanhang för att Data Insights Agent ska kunna svara på, eller är för generisk, svarar Data Insights Agent med en klargörande fråga eller föreslagna alternativ. <p>Följande klargörande frågor är exempel på komponentrelaterade frågor:</p><ul><li>Mått: *Vilket intäktsmått menade du?*</li><li>Dimension: *Vilka av nedanstående &quot;regioner&quot; vill du fokusera på?*</li><li>Segment: *Vilket kontosegment vill du tillämpa?*</li><li>Datumintervall: *Med&quot;förra månaden&quot;, menade du den senaste hela månaden eller de senaste 30 dagarna?*</li></ul><p>Följande klargörande fråga är ett exempel på en fråga som rör dimensionsobjekt:</p> <ul><li>Vilket &quot;butiksnamn&quot; menade du? (Exempel: Store #5274, Store #2949 osv.)</li></ul> | Tydliga frågor är begränsade till komponenter och dimensionsobjekt. Data Insights Agent kan inte förtydliga saker som datavyer, visualiseringar, datakornighet, jämförelse och omfattning. När klarläggandefrågor inte kan användas, används agenten som standard det som du troligen efterfrågar. Om det returnerar en oväntad visualisering eller datagranularitet kan du ställa en uppföljningsfråga eller justera visualisering och data. |
| **Datasäkerhet och -korrekthet** | Datasäkerheten och korrektheten kan bekräftas genom att man visar den genererade frihandstabellen och datavisualiseringen. <p>Om du till exempel ber Data Insights Agent att *trendbeställa förra månaden* kan du bekräfta att rätt mått (&quot;order&quot;) och datumintervall (&quot;sista månaden&quot;) har valts på den nyligen genererade panelen, datavisualisering och frihandstabellen. | Data Insights Agent svarar inte genom att informera dig om vilka komponenter eller visualiseringar som lagts till.</p> |
| **Återkopplingsmekanismer** | <ul><li>Tummen upp</li><li>Tummen ned</li><li>Flagga</li></ul> |  |


## Hantera åtkomst till Data Insights Agent {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="Aktivera för Data Insights Agent"
>abstract="Med det här alternativet aktiveras datavyn för användning med Data Insights Agent. Data Insights Agent är en generativ AI-konverteringsagent som kan nås via AI Assistant i Customer Journey Analytics. Det hjälper er att snabbt analysera data med textmeddelanden. Det bygger upp relevanta visualiseringar i Analysis Workspace med komponenter från datavyn och med era faktiska data."

<!-- markdownlint-enable MD034 -->

Följande parametrar styr åtkomsten till Data Insights Agent i Customer Journey Analytics:

* **Lösningsåtkomst**: Data Insights Agent är tillgängligt för alla Customer Journey Analytics-kunder som en del av ett program med begränsad åtkomst till och med den 30 november 2025. Det finns inte i Adobe Analytics.

* **Kontraktsåtkomst**: Om du inte kan använda Data Insights Agent i AI-assistenten kontaktar du organisationens administratör eller Adobe-kontoteam. Innan din organisation kan använda Data Insights Agent måste du godkänna vissa juridiska villkor för generativ AI.

* **Behörigheter**: Nödvändiga behörigheter måste beviljas i [!UICONTROL Adobe Admin Console] innan användare kan komma åt Data Insights Agent.

  Om du vill bevilja behörigheter måste en [produktprofiladministratör](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) utföra följande steg i [!UICONTROL Admin Console]:
   1. I **[!UICONTROL Admin Console]** väljer du fliken **[!UICONTROL Products]** för att visa sidan **[!UICONTROL All products and services]**.
   1. Välj **[!UICONTROL Customer Journey Analytics]**.
   1. På fliken **[!UICONTROL Product Profiles]** väljer du titeln för den produktprofil som du vill ge åtkomst till [!UICONTROL AI Assistant: Product Knowledge].
   1. Välj fliken **[!UICONTROL Permissions]** i den specifika produktprofilen.

      ![Fliken Behörigheter i Admin Console](assets/ai-assistant-permissions-tab.png)

   1. Markera redigeringsikonen **[!UICONTROL Reporting Tools]** Redigera![&#x200B; på raden &#x200B;](/help/assets/icons/Edit.svg) i den angivna tabellen.
   1. Bläddra till eller sök efter **[!UICONTROL AI Assistant: Product Knowledge]** och välj sedan plusikonen ![AddCircle](/help/assets/icons/AddCircle.svg) bredvid den här behörigheten.

      Behörigheten **[!UICONTROL AI Assistant: Product Knowledge]** läggs till i kolumnen **[!UICONTROL Included permission items]**.

      ![Lägg till behörighet](assets/ai-assistant-permissions.png).

   1. Välj fliken **[!UICONTROL Data View Tools]** och välj sedan plusikonen ![AddCircle](/help/assets/icons/AddCircle.svg) bredvid behörigheten **[!UICONTROL Data Insights Agent]** .

      Behörigheten **[!UICONTROL Data Insights Agent]** läggs till i kolumnen **[!UICONTROL Included permission items]**.

      ![Lägg till behörighet](assets/ai-assistant-permissions-dataviewtools.png).

   1. Välj fliken **[!UICONTROL Data Views]** för att välja de datavyer som du vill aktivera för Data Insights Agent.

      >[!IMPORTANT]
      >
      >Tänk på följande när du aktiverar datavyer:
      >* Du kan aktivera maximalt 50 datavyer per IMS-organisation. Om du aktiverar mer än 50 datavyer för alla produktprofiler för en viss organisation kommer Data Insights Agent att använda de 50 mest använda datavyer.
      >* Data Insights Agent kan referera till de inkluderade datavyerna någon gång under samma dag som du aktiverar dem i Admin Console.

   1. Sök efter eller bläddra till de datavyer som du vill aktivera och välj sedan plusikonen ![AddCircle](/help/assets/icons/AddCircle.svg) bredvid namnet på varje datavy.

      Varje datavy som du lägger till visas i kolumnen **[!UICONTROL Included permission items]**.

      ![Lägg till behörighet](assets/ai-assistant-permissions-dataviews.png).

   1. Välj **[!UICONTROL Save]** om du vill spara behörigheterna.

  Mer information om åtkomstkontroll finns i [Åtkomstkontroll](/help/technotes/access-control.md#access-control).

## Få tillgång till Data Insights Agent i AI-assistenten

1. Gå till [experience.adobe.com](https://experience.adobe.com/) och logga in med din Adobe ID.

2. Välj **Customer Journey Analytics** från Experience Cloud Home.

3. Välj **[!UICONTROL Blank project]** i banderollen högst upp på projektsidan om du vill öppna ett nytt tomt projekt.

4. Kontrollera att den markerade datavyn för panelen är en datavy som har aktiverats för användning med Data Insights Agent, vilket beskrivs i [Hantera åtkomst till Data Insights Agent i Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

5. Välj ikonen för AI Assistant-chatt längst upp till höger på sidan.

   Om chattikonen inte visas kontaktar du administratören så att han/hon kan aktivera följande funktioner i Admin Console:

   * Rapporteringsverktyg: **[!UICONTROL AI Assistant: Product Knowledge]**

   * Datavy Tools: **[!UICONTROL Data Insights Agent]**

   Mer information finns i [Hantera åtkomst till Data Insights Agent i Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![AI Assistant-ikon](/help/assets/ai-asst-icon.png)

6. Ställ en datavisualiseringsfråga med Data Insights Agent i dialogrutan **[!UICONTROL Ask about Customer Journey Analytics]** längst ned på sidan.

   Mer information finns i följande exempel.

### Exempel 1

Anta till exempel att du är intresserad av de order ditt företag fick i juli.

**Fråga:** Ange *&quot;Trendorder i juli.&quot;*

![AI-fråga](/help/assets/ai-asst-prompt1.png)

**Svar:** Data Insights Agent samlar in insikter genom att undersöka data i datavyn, inklusive mått och komponenter. Det översätter uppmaningen till rätt dimensioner och mätvärden inom dataområdet.

Som du ser genereras automatiskt ett linjediagram och en frihandstabell för juli.

![Svar på fråga - linjediagram och frihandstabell](/help/assets/ai-asst-result.png)

### Exempel 2

Sedan vill du se hur era intäkter står sig jämfört med region.

**Fråga:** I fönstret anger du *&quot;Visa intäkt per region&quot;*

**Svar:** Data Insights Agent förstår på ett intelligent sätt att med&quot;region&quot; menar du&quot;kundregion&quot;. Det skapar ett stapeldiagram som bäst visar intäkter per region:

![Stapeldiagram](/help/assets/ai-asst-result2.png)

### Exempel 3

Sedan vill ni, förutom att förstå intäkterna per region, också se data för vinst per region. I stället för att upprepa föregående fråga kan du be Data Insights Agent att uppdatera den senaste visualiserings- och frihandstabellen.

**Fråga:** Skriv *&quot;Lägg till vinst&quot;* i fönstret där uppmaningen visas.

**Svar:** Diagrammet **[!UICONTROL Bar]** ger fortfarande det mest kortfattade svaret, men vinstmåttet har lagts till som en kolumn i frihandstabellen:

![Stapeldiagram](/help/assets/ai-asst-result4.png)

### Exempel 4

Slutligen ska vi titta på intäkterna per produktkategori.

**Fråga:** I fönstret anger du *&quot;Andel intäkter per produktkategori.&quot;*

**Svar:** Även här väljer Data Insights Agent den lämpligaste visualiseringen, i det här fallet **[!UICONTROL Donut]**-visualiseringen, för att besvara frågan.

![Ringdiagram](/help/assets/ai-asst-result3.png)

## Få tillgång till Data Insights Agent i alla Experience Cloud-program

Med Adobe Experience Platform Agent Orchestrator får du tillgång till funktionerna i Data Insights Agent i flera Adobe Experience Cloud-program, som Adobe Journey Optimizer och Real-Time CDP.

Agent Orchestrator tolkar er begäran, avgör vilka specialistagenter som behövs och ordnar dem för att leverera rätt svar. Den håller reda på sammanhanget över interaktioner i flera omgångar, så att du kan bygga vidare på tidigare frågor på ett naturligt sätt.

Mer information finns i [Adobe Experience Platform Agent Orchestrator](http://www.adobe.com/go/agent-orchestrator-home).

## Exempel på visualiseringsmeddelanden för data

Nedan följer några exempel på vanliga uppmaningar och de visualiseringar som Data Insights Agent använder för att svara på dessa uppmaningar.

| Exempelfråga | Förväntad visualisering |
| --- | --- |
| Visa vinst i [månad] | Linje<p>Om du frågar efter en trend eller ett mätvärde inom ett visst tidsintervall returneras som standard en radinvisualisering. |
| Trendorder på [månad] | Linje |
| Visa intäkter per region i [månad] | Liggande |
| Inkomstandel per produktkategori | Munk |
| Beställningar per veckodag, från januari till maj | Liggande |
| Visa order efter kön, från mars till juni | Liggande |
| Vad är vinsten för SKU:er från februari till maj? | Liggande |
| Intäkter efter butiksnamn i [månad] | Liggande |
| Vilka var mina tio största SKU:er med vinst på [månad]? | Liggande |
| Andel inköp per månad på året | Munk |
| Total vinst i [månad] | Sammanfattningsnummer<p>Om användaren frågar efter&quot;summan&quot; för ett mätvärde i ett visst tidsintervall bör det returnera en visualisering av sammanfattningsnummer. |


## Uppmana till bästa praxis

Data Insights Agent bearbetar sammanhanget i de olika användarprompterna och försöker på ett intelligent sätt svara på den lämpligaste visualiseringen och komponenterna i ett frihandsbord.

Svaren kan variera beroende på de specifika ord och fraser som används i uppmaningen, och smärre språkändringar kan leda till olika resultat.

För att få bästa möjliga resultat bör du följa följande riktlinjer:

* **Var specifik:** Ta med exakta termer för att begränsa svaret. Följande är ett exempel på en specifik fråga:&quot;Sista månadens försäljning i Kalifornien&quot;

* **Använd tydliga mått, dimensioner och segment:** Genom att lägga till specifika mått (som&quot;Intäkter&quot;), dimensioner (som&quot;webbplatsnamn&quot;), segment (som&quot;iPhone-användare&quot;) och datumintervall (som&quot;de senaste tre månaderna&quot;) kan Data Insights Agent fokusera på rätt data.

* **Ställ direkta frågor:** Med fasningsfrågor blir det enklare för Data Insights Agent att ge tydliga och relevanta insikter. Här följer ett exempel på hur du ställer en direkt fråga i en fråga:&quot;Vad är den genomsnittliga intäkten per produktkategori i år?&quot;

Läs följande tabell med exempeltermer och fraser som du kan använda i uppmaningar med Data Insights Agent, tillsammans med de typer av svar du kan förvänta dig.

De här exemplen är utformade för att hjälpa dig att få kunskap om hur specifika ord eller strukturer kan påverka Data Insight-agentens utdata och säkerställa mer exakta och värdefulla insikter. Data Insights Agent använder generativ AI, så visualiseringar eller valda data kan variera något mellan liknande uppmaningar.

| Önskat resultat | Exempel på termer och fraser |
| --- | --- |
| Visualisering av sammanfattningsnummer | <ul><li>Totalt</li></ul> |
| Jämför komponenter | <ul><li>Jämför</li><li>VS</li><li>Kontrast</li><li>Vecka för vecka</li><li>Månad för månad</li><li>Kvartal över kvartal</li><li>År-över-år</li></ul> |
| Visualisering av ring | <ul><li>Andel</li><li>Andel av</li><li>Distribution</li><li>Procent</li><li>Bidrag</li><li>Del</li><li>Delar</li></ul> |
| Radvisualisering | <ul><li>Trend</li><li>[Mått] i [Tidsintervall]</li></ul> |
| Streckvisualisering | <ul><li>[Mått] av [Dimension]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->


## Bästa praxis för konfiguration

Nedan följer god praxis för din Customer Journey Analytics-konfiguration (datavy, calculate metrics, segments, and more) för att se till att Data Insights Agent kan hitta rätt komponenter och returnera renare svar utan att behöva fråga dig om ytterligare information.

* **Balansera vilka komponenter du behöver**. Lägg inte till alla fält i datauppsättningarna som mått eller dimensionskomponenter i datavyn. Särskilt de som du verkligen inte kommer att använda i din analys. Å andra sidan bör du inte begränsa dig till enbart de fält som du tror att du behöver för din analys. En alltför begränsad datavy begränsar flexibiliteten i analysen och Data Insights Agent-funktionaliteten.
* **Använd alltid egna visningsnamn**. Se till att alla fält som du definierar i datavyn, antingen som mått eller dimensionskomponent, har ett eget komponentnamn. Processen att byta namn på fält med ett eget namn är särskilt relevant för fält från Adobe Analytics källanslutningsdatauppsättningar. Dessa fält har ofta ovänliga namn som inte går att identifiera, som `eVar41` eller `prop25`.
* **Använd distinkta namn**. Distinkta namn är särskilt relevanta när du använder samma fält som både en metrisk komponent och en dimensionskomponent i datavyn. Eller när du använder ett fält i flera komponenter av samma typ (till exempel i två olika mätvärden), där var och en har olika komponentinställningar.
* **Använd en komponentnamnkonvention**. Du kan använda en komponentnamnkonvention för att gruppera komponenter. **[!UICONTROL Orders | Product]** och **[!UICONTROL Orders | Customer]** kan till exempel skilja mellan olika ordervärden som kan finnas i dina data.
* **Använd dataordlistan**. Lägg till beskrivning och andra relevanta data för komponenter i datamappningen. Data Insight Agent använder för närvarande inte beskrivning och taggar från Data Dictionary, men det kan hända i framtiden.
* **Använd godkända beräknade värden**. Godkänn en process där endast godkända beräknade mätvärden används som komponenter i datavyn och undvik att använda experimentella beräknade mätvärden.
* **Dela nödvändiga segment**. Se till att du delar segment och gör segment synliga som krävs för Data Insights Agent-uppmaningar.
* **Standardisera med komponentnamn över datavyer**. Om du använder samma fält som en komponent i flera datavyer måste du använda ett enda användarvänligt namn och en enda identifierare för den komponenten. Med ett enda namn och en identifierare kan Data Insights Agent växla datavyer utan att tappa sitt sammanhang.

>[!MORELIKETHIS]
>
>[Komponentinställningar](/help/data-views/component-settings/overview.md)
>&#x200B;>[Dataordlista &#x200B;](/help/components/data-dictionary/data-dictionary-overview.md)
>&#x200B;>[Godkänn beräknat mått &#x200B;](/help/components/calc-metrics/cm-workflow/cm-approving.md)
>&#x200B;>[Dela segment &#x200B;](/help/components/segments/seg-share.md)
>
