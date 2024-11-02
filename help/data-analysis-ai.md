---
description: ställa frågor om dataanalys i Customer Journey Analytics dokumentation
title: AI-assistenten för dataanalys i Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: e18d8facbd54ae65d158ce2c72f47709ef988f8f
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 0%

---


# AI-assistenten för dataanalys i Customer Journey Analytics - Alpha

AI-assistenten för dataanalys är en intelligent, kontextmedveten konversationsagent som kan hjälpa dig att snabbare och effektivare svara på frågor du har om dina Analysis Workspace-data i Customer Journey Analytics.

Assistenten går igenom alla data i en datavy, inklusive de olika typerna av mått och komponenter, och översätter prompten till rätt mått, mått och datumintervall för analysen. Istället för att behöva bekanta dig med komponenterna i datavyn och sedan dra och släppa dem i den bästa kombinationen för att besvara din fråga, behöver du bara skriva in frågan i AI-assistenten.

## Omfattning kontra funktioner utanför omfånget för Alpha

### Funktioner som är inom omfånget

| Funktion som stöds | Beskrivning |
| --- | --- |
| **Skapa och uppdatera visualiseringar** | Skapar en friformstabell och tillhörande visualisering (t.ex. linje, streck, munk).<p>Exempel: *Vad är vinsten för SKU:er från februari till maj?* |
| **Visualiseringstyper som stöds** | <ul><li>Linje</li><li>Flera rader</li><li>Frihandsfigur</li><li>Liggande</li><li>Munk</li><li>Sammanfattningsnummer</li></ul> |
| **Frågeidentifiering utanför scope** | Om du skickar in en fråga som inte omfattas, t.ex.&quot;exportera det här projektet&quot;, svarar assistenten genom att meddela att frågan inte omfattas. |
| **Tydligare frågor** | Om du ställer en fråga som inte har tillräckligt sammanhang för att AI-assistenten ska kunna svara på, eller är för generisk, svarar AI-assistenten med en klargörande fråga och/eller föreslagna alternativ. Exempel: <p>**Komponenter**<ul><li>Mått: *Vilket intäktsmått menade du?*</li><li>Dimension: *Vilka av de nedan &quot;regionerna&quot; vill du fokusera på?*</li><li>Filter: *Vilket kontofilter vill du använda?*</li><li>Datumintervall: *Med&quot;förra månaden&quot;, menade du den senaste hela månaden eller de senaste 30 dagarna?*</li></ul>**Dimension-objekt**: Vilket butiksnamn menade du? (t.ex. Store #5274, Store #2949 osv.) |
| **Flera varv** | AI Assistant svarar på en fråga med kontexten från en eller flera föregående uppmaningar, vilket gör att användare kan uppdatera visualiseringar och ställa uppföljningsfrågor. Exempel: *Visa data från mars till april istället.* |
| **Feedback** | <ul><li>Tummen uppåt</li><li>Tummen nedåt</li><li>Flagga</li></ul> |

### Funktioner som inte är tillgängliga

| Funktionen stöds inte | Beskrivning |
| --- | --- |
| **Infogad sammanfattning eller svar** | AI-assistenten kan inte svara direkt i chattfältet med ett kortfattat svar på en användarfråga.Exempel på frågor som inte omfattas:<ul><li>*Ge mig en sammanfattning av insikterna från min senaste fråga.*</li><li>*Sammanfatta högdagrarna från linjevisualiseringen.*</li></ul> |
| **Tydligare frågor** | Tydliga frågor är begränsade till komponenter och dimensionsobjekt. AI-assistenten kan inte förtydliga datavyer, visualiseringar, datakornighet, jämförelse, omfång osv. Utan att klargöra några frågor blir assistenten som standard den som du mest troligt frågar efter. Om det returnerar en oväntad visualisering eller datagranularitet kan du sedan använda funktionen för flera omgångar/uppdateringar för att justera visualisering och data. |
| **Workspace-åtgärder/funktioner** | AI-assistenten kan inte vidta åtgärder för en användare i Workspace utöver att skapa och uppdatera visualiseringar. Den kan till exempel inte göra något av följande:<ul><li>Gränssnittsknappar för sammanhangsberoende åtgärder (lägg till i diagram, ny panel, ny tabell)</li><li>Dela</li><li>Exportera</li><li>Ladda ned</li><li>Hantera användarinställningar</li><li>Kurva</li><li>Hantera datavy</li><li>Analytics Dashboards-app</li><li>Tillskrivning</li></ul> |
| **Visualiseringstyper som inte stöds** | <ul><li>Flöde</li><li>Utfall</li><li>Kohortabell</li><li>Område, staplat område</li><li>Stapel staplad</li><li>Punkt</li><li>Kombination</li><li>Histogram</li><li>Vågrätt streck, vågrätt streck</li><li>Sammanfattning av nyckelmått</li><li>Spridning</li><li>Sammanfattningsändring</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |
| **Förklaring och verifiering** | Genomskinlig beskrivning eller citat av hur AI-assistenten genererade ett svar och ger dig ett sätt att bekräfta att svaret är korrekt. |

## Tillgång till funktioner i användargränssnittet i Customer Journey Analytics

[Behöver vi det här avsnittet för Alpha?]

Följande parametrar styr åtkomsten till AI-assistentfunktionen för dataanalys:

* **Åtkomst till lösning**: AI-assistenten för dataanalys är tillgänglig för Customer Journey Analytics Prime- och Ultimate-kunder. Det finns inte i Adobe Analytics.

Det finns också i Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP och andra appar för Experience Platform.

* **Kontraktsåtkomst**: Om du inte kan använda AI Assistant kontaktar du organisationens administratör eller Adobe-kontorepresentant. Innan din organisation kan använda AI-assistenten för dataanalys måste du godkänna vissa GenAI-relaterade juridiska villkor.

* **Behörigheter**: I [!UICONTROL Adobe Admin Console] avgör behörigheten [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** åtkomsten till det här verktyget. En [produktprofiladministratör](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) måste följa de här stegen i [!UICONTROL Admin Console]:
   1. Navigera till **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Välj titeln för den produktprofil som du vill ge åtkomst till [!UICONTROL AI Assistant: Product Knowledge].
   1. Välj **[!UICONTROL Permissions]** i den specifika produktprofilen.
   1. Välj ![Redigera](/help/assets/icons/Edit.svg) om du vill redigera **[!UICONTROL Reporting Tools]**.
   1. Välj ![AddCircle](/help/assets/icons/AddCircle.svg) om du vill lägga till **AI-assistenten: Dataanalys** i **[!UICONTROL Included permission items]**.

      ![Lägg till behörighet](assets/ai-assistant-permissions.png).

   1. Välj **[!UICONTROL Save]** om du vill spara behörigheterna.

Mer information finns i [Åtkomstkontroll](/help/technotes/access-control.md#access-control).

## Få åtkomst till och använd AI-assistenten för dataanalys

1. Klicka på den här länken om du vill öppna Workspace i Labs IMS-organisationen (på scenen) och logga in med din Adobe ID.

1. Klicka på **[!UICONTROL Blank project]** i banderollen högst upp på projektsidan för att öppna ett nytt tomt projekt.

1. Klicka på ikonen för AI-assistentchatt längst upp till höger.

   ![AI Assistant-ikon](/help/assets/ai-asst-icon.png)

1. Ställ en dataanalysfråga i AI-assistenten i dialogrutan **[!UICONTROL Ask about Customer Journey Analytics]** längst ned.

### Exempel 1

Anta till exempel att du är intresserad av de order ditt företag fick i juli.

1. Ange&quot;Visa order i juli.&quot;

   ![AI-fråga](/help/assets/ai-asst-prompt1.png)

1. AI Assistant samlar nu in insikter genom att undersöka data i datavyn, inklusive mått och komponenter. Uppmaningen översätts till rätt dimensioner, mått och dataintervall.

   Som du ser har den automatiskt genererat ett linjediagram och en frihandstabell med beställningar för juli.

   ![Svar på fråga - linjediagram och frihandstabell](/help/assets/ai-asst-result.png)

### Exempel 2

Sedan vill du se hur era intäkter står sig jämfört med region.

1. I fönstret anger du&quot;Visa intäkt per region&quot;.

2. AI är tillräckligt smart för att förstå att&quot;region&quot; är&quot;kundregion&quot;. Det skapar ett stapeldiagram som bäst visar intäkter per region:

   ![Stapeldiagram](/help/assets/ai-asst-result2.png)

### Exempel 3

Nu ska vi titta på intäkterna per produktkategori.

1. I fönstret anger du&quot;Visa intäkt per produktkategori&quot;.

2. Återigen väljer AI-assistenten för dataanalys den lämpligaste visualiseringen, i det här fallet **[!UICONTROL Donut]**-visualiseringen, för att besvara frågan.

   ![Ringdiagram](/help/assets/ai-asst-result3.png)

### Exempel 4

Slutligen vill ni veta vilken SKU som är mest lönsam och var ni bör investera marknadsföringsresurser.

1. I promptfönstret frågar du&quot;What is the gain across SKUs from February to May.&quot;

1. Ett enkelt **[!UICONTROL Bar]**-diagram ger det mest kortfattade svaret:

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

TBD

## Förväntningar om testning av Alpha och efterfrågad feedback

När du har ställt varje fråga ska du noggrant granska assistentens svar. Det är viktigt att noggrant utvärdera de genererade visualiseringarna innan man ger feedback.

Utvärdera svaret: Ges svaret korrekt?

Om assistenten svarar i chattfältet: Utvärdera textsvaret.

* Om en visualisering/diagram visas: utvärdera visualiseringen. Är det rätt/förväntad visualisering för din fråga?

* Om en friformstabell visas: Utvärdera frihandstabellen. Är frihandstabellens data korrekta? Delar den upp data där det efterfrågas? Används de filter som du har begärt eller väntat dig?

* Om du får ett generiskt felmeddelande om att frågan ligger utanför räckvidden, kan du ge feedback om huruvida du anser att det meddelande som ligger utanför området är lämpligt med tanke på uppmaningen. Var prompten verkligen i sin linda?

För varje svar ger du tummen uppåt eller tummen nedåt, baserat på svaret

När du har markerat reglagen uppåt/nedåt, gör du ett val för de relevanta flervalsrutorna för feedback. Om du vill ge mer feedback lägger du till anteckningar i den öppna textrutan.

## Frågor och kontakt

E-post `taylorb@adobe.com` (PM)
Skicka frågor och feedback i Alpha-slackkanalen: #aep-cja-ai-assistent-testers ??


