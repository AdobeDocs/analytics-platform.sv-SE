---
description: ställa frågor om dataanalys i Customer Journey Analytics-dokumentationen
title: AI-assistenten för dataanalys i Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: true
hide: true
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
source-git-commit: ac3ec479938acf509bbd26be282b75e75dd49c33
workflow-type: tm+mt
source-wordcount: '1633'
ht-degree: 0%

---

# Visa data med AI-assistenten i Customer Journey Analytics

AI Assistant i Customer Journey Analytics är en generativ agent för AI-konversation som snabbt och effektivt besvarar frågor om dina data. Det bygger upp relevanta visualiseringar i Analysis Workspace med komponenter från datavyn och med era faktiska data.

Med hjälp av AI Assistant kan du besvara datacentrerade frågor i Analysis Workspace. Det kan spara massor av tid som du annars skulle behöva lägga på att manuellt skapa visualiseringar i Analysis Workspace och bekanta dig med komponenterna i datavyn.

![AI-assistenten för dataanalys](assets/cja-ai-asst-da.gif)

## Omfattning kontra funktioner som inte omfattas av Alpha-versionen

### Omfattande Alpha-funktioner

| Funktion som stöds | Beskrivning |
| --- | --- |
| **Skapa och uppdatera visualiseringar** | Skapar en friformstabell och tillhörande visualisering (t.ex. en linje, streck, munstycke).<p>Exempel: *Vad är vinsten för SKU:er från februari till maj?* |
| **Visualiseringstyper som stöds** | <ul><li>Linje</li><li>Flera rader</li><li>Frihandsregister</li><li>Liggande</li><li>Munk</li><li>Sammanfattningsnummer</li></ul> |
| **Frågeidentifiering utanför scope** | Om du skickar in en fråga som inte omfattas, till exempel&quot;exportera det här projektet&quot;, svarar assistenten genom att meddela att frågan inte omfattas. |
| **Tydligare frågor** | Om du ställer en fråga som inte har tillräckligt sammanhang för att AI-assistenten ska kunna svara på, eller är för generisk, svarar AI-assistenten med en klargörande fråga eller föreslagna alternativ. Exempel: <p>**Komponenter**<ul><li>Mått: *Vilket intäktsmått menade du?*</li><li>Dimension: *Vilka av nedanstående &quot;regioner&quot; vill du fokusera på?*</li><li>Filter: *Vilket kontofilter vill du använda?*</li><li>Datumintervall: *Med&quot;förra månaden&quot;, menade du den senaste hela månaden eller de senaste 30 dagarna?*</li></ul>**Dimension-objekt**: Vilket butiksnamn menade du? (Exempel: Store #5274, Store #2949 osv.) |
| **Flera varv** | AI Assistant besvarar en fråga med kontexten från tidigare uppmaningar så att användarna kan uppdatera visualiseringar och ställa uppföljningsfrågor. Exempel: <ul><li>Fråga 1: *Trendhändelser från mars.*</li><li>Fråga 2: *Visa data från mars till april i stället*</li></ul> |
| **Verifierbarhet** | Data kan verifieras och korrigeras med hjälp av den genererade frihandstabellen och datavisualisering. Om en användare till exempel frågar *Trendbeställningar förra månaden* kan du bekräfta att rätt mått (&quot;order&quot;) och datumintervall (&quot;sista månaden&quot;) har valts på den nyligen genererade panelen, datavisualisering och frihandstabellen. |
| **Feedback** | <ul><li>Tummen upp</li><li>Tummen ned</li><li>Flagga</li></ul> |

### OMFATTANDE Beta-funktioner

| Funktionen stöds inte | Beskrivning |
| --- | --- |
| **Infogad sammanfattning eller svar** | AI-assistenten kan inte svara direkt i chattfältet med ett kortfattat svar på en användarfråga. Exempeluppmaningar utanför omfånget:<ul><li>*Ge mig en sammanfattning av insikterna från min senaste fråga.*</li><li>*Sammanfatta högdagrarna från linjevisualiseringen.*</li></ul> |
| **Tydligare frågor** | Tydliga frågor är begränsade till komponenter och dimensionsobjekt. AI-assistenten kan inte klargöra saker som datavyer, visualiseringar, datagranularitet, jämförelse och omfattning. När det inte går att använda klargörande frågor blir assistenten som standard det du mest troligt frågar efter. Om det returnerar en oväntad visualisering eller datagranularitet kan du sedan använda funktionen för flera omgångar/uppdateringar för att justera visualisering och data. |
| **Workspace-åtgärder/funktioner** | AI-assistenten kan inte vidta åtgärder för en användare i Workspace utöver att skapa och uppdatera visualiseringar. Den kan till exempel inte göra något av följande:<ul><li>Gränssnittsknappar för sammanhangsberoende åtgärder (lägg till i diagram, ny panel, ny tabell)</li><li>Dela</li><li>Exportera</li><li>Ladda ned</li><li>Hantera användarinställningar</li><li>Kurva</li><li>Hantera datavy</li><li>Analytics Dashboards-app</li><li>Tillskrivning</li></ul> |
| **Visualiseringstyper som inte stöds** | <ul><li>Flöde</li><li>Utfall</li><li>Kohortabell</li><li>Område, staplat område</li><li>Stapel, staplad</li><li>Punkt</li><li>Kombination</li><li>Histogram</li><li>Vågrätt streck, vågrätt streck</li><li>Sammanfattning av nyckelmått</li><li>Spridning</li><li>Sammanfattningsändring</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to Data visualization in AI Assistant:

* **Solution access**: Data visualization in AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data visualization in AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data visualization]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data visualization** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Få åtkomst till och använd datavisualisering i AI Assistant

1. Gå till [experience.adobe.com](https://experience.adobe.com/) och logga in med din Adobe ID.

2. Välj **Customer Journey Analytics** från Experience Cloud Home.

3. Välj **[!UICONTROL Blank project]** i banderollen högst upp på projektsidan om du vill öppna ett nytt tomt projekt.

4. Se till att den valda datavyn för panelen är samma datavy som aktiverades för AI Assistant för Beta-testning.

   Om du är osäker kontaktar du Beta Slack-kanal.

5. Välj ikonen för AI Assistant-chatt längst upp till höger på sidan.

   Om chattikonen inte visas kontaktar du administratören så att han/hon kan aktivera följande funktioner i Admin Console:

   * **[!UICONTROL AI Assistant: Product Knowledge]**

   * **[!UICONTROL AI Assistant: Data Analysis]**

   Mer information finns i [dessa instruktioner](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access).

   ![AI Assistant-ikon](/help/assets/ai-asst-icon.png)

6. Ställ en datavisualiseringsfråga i AI-assistenten i dialogrutan **[!UICONTROL Ask about Customer Journey Analytics]** längst ned på sidan.

   Mer information finns i följande exempel.

### Exempel 1

Anta till exempel att du är intresserad av de order ditt företag fick i juli.

**Fråga:** Ange *&quot;Trendorder i juli.&quot;*

![AI-fråga](/help/assets/ai-asst-prompt1.png)

**Svar:** AI-assistenten samlar in insikter genom att undersöka data i datavyn, inklusive mått och komponenter. Det översätter uppmaningen till rätt dimensioner och mätvärden inom dataområdet.

Som du ser genereras automatiskt ett linjediagram och en frihandstabell för juli.

![Svar på fråga - linjediagram och frihandstabell](/help/assets/ai-asst-result.png)

### Exempel 2

Sedan vill du se hur era intäkter står sig jämfört med region.

**Fråga:** I fönstret anger du *&quot;Visa intäkt per region&quot;*

**Svar:** AI-assistenten förstår på ett intelligent sätt att efter &quot;region&quot; menar du &quot;kundregion&quot;. Det skapar ett stapeldiagram som bäst visar intäkter per region:

![Stapeldiagram](/help/assets/ai-asst-result2.png)

### Exempel 3

Därefter vill du, förutom att förstå intäkter per region, också se data för vinst per region. I stället för att upprepa föregående fråga kan du be AI-assistenten att uppdatera den senaste visualiserings- och frihandstabellen.

**Fråga:** Skriv *&quot;Lägg till vinst&quot;* i fönstret där uppmaningen visas.

**Svar:** Diagrammet **[!UICONTROL Bar]** ger fortfarande det mest kortfattade svaret, men vinstmåttet har lagts till som en kolumn i frihandstabellen:

![Stapeldiagram](/help/assets/ai-asst-result4.png)

### Exempel 4

Slutligen ska vi titta på intäkterna per produktkategori.

**Fråga:** I fönstret anger du *&quot;Andel intäkter per produktkategori.&quot;*

**Svar:** Även här väljer datavisualisering i AI Assistant den lämpligaste visualiseringen, i det här fallet **[!UICONTROL Donut]**-visualisering, för att besvara frågan.

![Ringdiagram](/help/assets/ai-asst-result3.png)

## Exempel på visualiseringsmeddelanden för data

Nedan följer några exempel på vanliga uppmaningar och de visualiseringar som AI-assistenten använder för att svara på dessa uppmaningar.

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

AI Assistant bearbetar kontexten i varje användarprompt och försöker på ett intelligent sätt svara med den lämpligaste visualiseringen och de lämpligaste komponenterna i en frihandstabell.

Svaren kan variera beroende på de specifika ord och fraser som används i uppmaningen, och smärre språkändringar kan leda till olika resultat.

För att få bästa möjliga resultat bör du följa följande riktlinjer:

* Var specifik: Inkludera exakta termer för att begränsa svaret. Här följer ett exempel på en specifik fråga:&quot;Sista månadens försäljning i Kalifornien&quot;

* Använd tydliga mätvärden och filter: Genom att lägga till specifika mätvärden (t.ex.&quot;Intäkter&quot;), dimensioner (t.ex.&quot;webbplatsnamn&quot;), filter (t.ex.&quot;iPhone-användare&quot;) och datumintervall (t.ex.&quot;de senaste tre månaderna&quot;) kan AI Assistant fokusera på rätt data.

* Ställ direkta frågor: Fraseringsfrågor gör det enklare för AI-assistenten att ge tydliga och relevanta insikter. Här följer ett exempel på hur du ställer en direkt fråga i en fråga:&quot;Vad är den genomsnittliga intäkten per produktkategori i år?&quot;

Granska följande tabell med exempeltermer och fraser som du kan använda i uppmaningar med datavisualisering i AI Assistant, tillsammans med de typer av svar du kan förvänta dig.

De här exemplen är utformade för att hjälpa dig att lära dig hur specifika ord eller strukturer kan påverka AI-assistentens resultat och ge dig mer exakta och värdefulla insikter. AI-assistenten använder generativ AI, så visualiseringar eller valda data kan variera något mellan liknande uppmaningar.

| Önskat resultat | Exempel på termer och fraser |
| --- | --- |
| Visualisering av sammanfattningsnummer | <ul><li>Totalt</li></ul> |
| Jämför komponenter | <ul><li>Jämför</li><li>VS</li><li>Kontrast</li><li>Vecka för vecka</li><li>Månad för månad</li><li>Kvartal över kvartal</li><li>År-över-år</li></ul> |
| Visualisering av ring | <ul><li>Andel</li><li>Andel av</li><li>Distribution</li><li>Procent</li><li>Bidrag</li><li>Del</li><li>Delar</li></ul> |
| Radvisualisering | <ul><li>Trend</li><li>[Mått] i [Tidsintervall]</li></ul> |
| Streckvisualisering | <ul><li>[Mått] av [Dimension]</li></ul> |

## Beta testar förväntningar och begär feedback

När du har ställt varje fråga ska du noggrant granska assistentens svar. Det är viktigt att noggrant utvärdera de genererade visualiseringarna innan man ger feedback.

Tänk på följande när du utvärderar ett svar från AI-assistenten:

* Chatt rail-svar eller -mall: Utvärdera det textsvar som assistenten ger. Är svaret lämpligt med tanke på ert budskap?

* Visualisering/diagram: Utvärdera visualiseringen. Är det en lämplig eller förväntad visualisering för din fråga eller skulle du ha förväntat dig en annan visualisering?

* Frihandstabell: Utvärdera frihandstabellen. Är frihandstabellens data korrekta? Delar den upp data där det efterfrågas? Används de filter som du har begärt eller väntat dig?

* Felmeddelande/Odefinierat: Om ett generiskt felmeddelande om att frågan ligger utanför definitionsområdet visas, kan du ge feedback om huruvida du anser att meddelandet som ligger utanför definitionsområdet är lämpligt, med tanke på din uppmaning. Var din fråga verkligen i omfång?

**För varje svar ska du ge tummen uppåt eller tummen nedåt, baserat på svaret.**

När du har dragit reglagen uppåt eller nedåt kan du göra en markering för de relevanta flervalsrutorna för feedback. Om du vill ge mer feedback lägger du till anteckningar i den öppna textrutan.

## Frågor och kontakt

* Skicka frågor och feedback i Alpha Slack-kanalen: #cja-assistent-data-alpha
