---
description: ställa frågor om dataanalys i Customer Journey Analytics dokumentation
title: AI-assistenten för dataanalys i Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: 7f5eddcf1ceaa6228411867f5794bfe72b2ad6ab
workflow-type: tm+mt
source-wordcount: '1528'
ht-degree: 0%

---


# AI-assistenten för dataanalys i Customer Journey Analytics - Alpha

AI-assistenten för dataanalys är en intelligent, kontextmedveten konversationsagent som kan hjälpa dig att snabbare och effektivare svara på frågor du har om dina Analysis Workspace-data i Customer Journey Analytics.

Assistenten går igenom alla data i en datavy, inklusive olika typer av mått och komponenter, och översätter prompten till rätt mått, mått och datumintervall för analysen. Istället för att behöva bekanta dig med komponenterna i datavyn och sedan dra och släppa dem i den bästa kombinationen för att besvara din fråga, behöver du bara skriva in frågan i AI-assistenten.

## Omfattning kontra funktioner utanför omfånget för Alpha

### Funktioner i Alpha

| Funktion som stöds | Beskrivning |
| --- | --- |
| **Skapa och uppdatera visualiseringar** | Skapar en friformstabell och tillhörande visualisering (t.ex. linje, streck, munk).<p>Exempel: *Vad är vinsten för SKU:er från februari till maj?* |
| **Visualiseringstyper som stöds** | <ul><li>Linje</li><li>Flera rader</li><li>Frihandsfigur</li><li>Liggande</li><li>Munk</li><li>Sammanfattningsnummer</li></ul> |
| **Frågeidentifiering utanför scope** | Om du skickar in en fråga som inte omfattas, t.ex.&quot;exportera det här projektet&quot;, svarar assistenten genom att meddela att frågan inte omfattas. |
| **Tydligare frågor** | Om du ställer en fråga som inte har tillräckligt sammanhang för att AI-assistenten ska kunna svara på, eller är för generisk, svarar AI-assistenten med en klargörande fråga och/eller föreslagna alternativ. Exempel: <p>**Komponenter**<ul><li>Mått: *Vilket intäktsmått menade du?*</li><li>Dimension: *Vilka av de nedan &quot;regionerna&quot; vill du fokusera på?*</li><li>Filter: *Vilket kontofilter vill du använda?*</li><li>Datumintervall: *Med&quot;förra månaden&quot;, menade du den senaste hela månaden eller de senaste 30 dagarna?*</li></ul>**Dimension-objekt**: Vilket butiksnamn menade du? (t.ex. Store #5274, Store #2949 osv.) |
| **Flera varv** | AI-assistenten svarar på en fråga med kontexten från föregående uppmaning(n), vilket gör att användare kan uppdatera visualiseringar och ställa uppföljningsfrågor.Exempel: <ul><li>Fråga 1: *Trendhändelser från mars.*</li><li>Fråga 2: *Visa data från mars till april i stället*</li></ul> |
| **Feedback** | <ul><li>Tummen uppåt</li><li>Tummen nedåt</li><li>Flagga</li></ul> |

### Alpha-funktioner som inte är tillgängliga

| Funktionen stöds inte | Beskrivning |
| --- | --- |
| **Infogad sammanfattning eller svar** | AI-assistenten kan inte svara direkt i chattfältet med ett kortfattat svar på en användarfråga.Exempel på frågor som inte omfattas:<ul><li>*Ge mig en sammanfattning av insikterna från min senaste fråga.*</li><li>*Sammanfatta högdagrarna från linjevisualiseringen.*</li></ul> |
| **Tydligare frågor** | Tydliga frågor är begränsade till komponenter och dimensionsobjekt. AI-assistenten kan inte förtydliga datavyer, visualiseringar, datakornighet, jämförelse, omfång osv. Utan att klargöra några frågor blir assistenten som standard den som du mest troligt frågar efter. Om det returnerar en oväntad visualisering eller datagranularitet kan du sedan använda funktionen för flera omgångar/uppdateringar för att justera visualisering och data. |
| **Workspace-åtgärder/funktioner** | AI-assistenten kan inte vidta åtgärder för en användare i Workspace utöver att skapa och uppdatera visualiseringar. Den kan till exempel inte göra något av följande:<ul><li>Gränssnittsknappar för sammanhangsberoende åtgärder (lägg till i diagram, ny panel, ny tabell)</li><li>Dela</li><li>Exportera</li><li>Ladda ned</li><li>Hantera användarinställningar</li><li>Kurva</li><li>Hantera datavy</li><li>Analytics Dashboards-app</li><li>Tillskrivning</li></ul> |
| **Visualiseringstyper som inte stöds** | <ul><li>Flöde</li><li>Utfall</li><li>Kohortabell</li><li>Område, staplat område</li><li>Stapel staplad</li><li>Punkt</li><li>Kombination</li><li>Histogram</li><li>Vågrätt streck, vågrätt streck</li><li>Sammanfattning av nyckelmått</li><li>Spridning</li><li>Sammanfattningsändring</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |
| **Förklaring och verifiering** | Genomskinlig beskrivning eller citat av hur AI-assistenten genererade ett svar och ger dig ett sätt att bekräfta att svaret är korrekt. |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Få åtkomst till och använd AI-assistenten för dataanalys

1. Gå till [experience.adobe.com](https://experience.adobe.com/) och logga in med din Adobe ID.

2. Välj **Customer Journey Analytics** från startsidan för Experience Cloud

3. Klicka på **[!UICONTROL Blank project]** i banderollen högst upp på projektsidan för att öppna ett nytt tomt projekt.

4. Se till att den markerade datavyn för panelen är datavyn som aktiverades för AI Assistant-användning för Alpha-testning (kontakta taylorb@adobe.com eller Alpha i slackkanalen om du är osäker).

5. Klicka på ikonen för AI-assistentchatt längst upp till höger.

   ![AI Assistant-ikon](/help/assets/ai-asst-icon.png)

6. Ställ en dataanalysfråga i AI-assistenten i dialogrutan **[!UICONTROL Ask about Customer Journey Analytics]** längst ned.

### Exempel 1

Anta till exempel att du är intresserad av de order ditt företag fick i juli.

1. Ange *&quot;Trendorder i juli.&quot;*

   ![AI-fråga](/help/assets/ai-asst-prompt1.png)

2. AI Assistant samlar nu in insikter genom att undersöka data i datavyn, inklusive mått och komponenter. Uppmaningen översätts till rätt dimensioner, mått och dataintervall.

   Som du ser har den automatiskt genererat ett linjediagram och en frihandstabell med beställningar för juli.

   ![Svar på fråga - linjediagram och frihandstabell](/help/assets/ai-asst-result.png)

### Exempel 2

Sedan vill du se hur era intäkter står sig jämfört med region.

1. I fönstret anger du *&quot;Visa intäkt per region&quot;*

2. AI Assistant förstår på ett intelligent sätt att med&quot;region&quot; menar man&quot;kundregion&quot;. Det skapar ett stapeldiagram som bäst visar intäkter per region:

   ![Stapeldiagram](/help/assets/ai-asst-result2.png)

### Exempel 3

Nu ska vi titta på intäkterna per produktkategori.

1. I fönstret anger du *&quot;Andel av intäkter per produktkategori&quot;.*

2. Återigen väljer AI-assistenten för dataanalys den lämpligaste visualiseringen, i det här fallet **[!UICONTROL Donut]**-visualiseringen, för att besvara frågan.

   ![Ringdiagram](/help/assets/ai-asst-result3.png)

### Exempel 4

Slutligen vill ni veta vilken SKU som är mest lönsam och var ni bör investera marknadsföringsresurser.

1. Fråga *&quot;Vad är vinsten på SKU:er från februari till maj i promptfönstret?&quot;*

2. Ett enkelt **[!UICONTROL Bar]**-diagram ger det mest kortfattade svaret:

   ![Stapeldiagram](/help/assets/ai-asst-result4.png)

## Exempel på frågor om dataanalys

Här är några exempel på vanliga uppmaningar och vilka visualiseringar som AI-assistenten använder för att svara på dessa uppmaningar.

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

AI Assistant bearbetar sammanhanget som anges av varje användaruppmaning och försöker på ett intelligent sätt svara på den lämpligaste visualiseringen samt komponenter i en frihandstabell. AI-assistentens svar kan dock variera beroende på de specifika ord och fraser som används i en prompt, så små språkändringar kan leda till olika resultat. Så här får du ut det mesta: <ul><li>Var tydlig: Ta med exakta termer (som&quot;förra månadens försäljning i Kalifornien&quot;) för att begränsa svaret.</li><li>Använd Rensa mått och filter: Om du lägger till specifika mått (som&quot;Intäkter&quot;), dimensioner (t.ex.&quot;webbplatsnamn&quot;), filter (t.ex.&quot;iPhone-användare&quot;) och datumintervall (t.ex.&quot;senaste tre månader&quot;) kan AI Assistant fokusera på rätt data.</li><li>Ställ frågor direkt: Avvecklingsfrågor direkt, som&quot;Vad är den genomsnittliga intäkten per produktkategori i år?&quot; gör det enklare för AI Assistant att ge tydliga och relevanta insikter.</li></ul>

I tabellen nedan finns exempeltermer och fraser som du kan använda i uppmaningar med AI-assistenten för dataanalys i CJA, tillsammans med de typer av svar du kan förvänta dig. De här exemplen är utformade för att hjälpa dig att lära dig hur specifika ord eller strukturer kan påverka AI-assistentens resultat och ge dig mer exakta och värdefulla insikter. Observera att AI-assistenten använder generativ AI, så visualiseringar eller valda data kan variera något mellan liknande uppmaningar.

| Önskat resultat | Exempel på termer och fraser |
| --- | --- |
| Visualisering av sammanfattningsnummer | <ul><li>Totalt</li></ul> |
| Jämför komponenter | <ul><li>Jämför</li><li>VS</li><li>Kontrast</li><li>Vecka för vecka</li><li>Månad för månad</li><li>Kvartal över kvartal</li><li>År-över-år</li></ul> |
| Visualisering av ring | <ul><li>Andel</li><li>Andel av</li><li>Distribution</li><li>Procent</li><li>Bidrag</li><li>Del</li><li>Delar</li></ul> |
| Radvisualisering | <ul><li>Trend</li><li>[Mått] i [Tidsintervall]</li></ul> |
| Visualisering av fält | <ul><li>[Mått] av [dimension]</li></ul> |

## Förväntningar om testning av Alpha och efterfrågad feedback

När du har ställt varje fråga ska du noggrant granska assistentens svar. Det är viktigt att noggrant utvärdera de genererade visualiseringarna innan man ger feedback. Tänk på följande när du utvärderar svaret från AI-assistenten:

* Chatt rail-svar eller -mall: Utvärdera det textsvar som assistenten ger. Är svaret lämpligt med tanke på ert sammanhang?

* Visualisering/diagram: Utvärdera visualiseringen. Är det en lämplig/förväntad visualisering för din fråga eller skulle du ha förväntat dig en annan visualisering?

* Frihandstabell: Utvärdera frihandstabellen. Är frihandstabellens data korrekta? Delar den upp data där det efterfrågas? Används de filter som du har begärt eller väntat dig?

* Felmeddelande/Odefinierat: Om ett generiskt felmeddelande visas som anger att frågan ligger utanför definitionsområdet, kan du ge feedback om huruvida du anser att meddelandet som ligger utanför definitionsområdet är lämpligt med tanke på uppmaningen. Var prompten verkligen i sin linda?

**För varje svar ska du ge tummen uppåt eller tummen nedåt, baserat på svaret**

När du har markerat reglagen uppåt/nedåt, gör du ett val för de relevanta flervalsrutorna för feedback. Om du vill ge mer feedback lägger du till anteckningar i den öppna textrutan.

## Frågor och kontakt

* E-post `taylorb@adobe.com` (PM)
* Skicka frågor och feedback i Alpha-slackkanalen: #aep-cja-ai-assistent-testers ??


