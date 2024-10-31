---
description: ställa frågor om dataanalys i Customer Journey Analytics dokumentation
title: AI-assistenten för dataanalys i Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: true
hide: true
source-git-commit: 1442aa9be5e6a6dc283ba559a2ff6c46de862425
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---


# AI-assistenten för dataanalys i Customer Journey Analytics - Alpha

AI-assistenten för dataanalys är en intelligent, kontextmedveten konversationsagent som kan hjälpa dig att snabbare och effektivare svara på frågor du har om dina Analysis Workspace-data i Customer Journey Analytics.

Assistenten går igenom alla data i en datavy, inklusive de olika typerna av mått och komponenter, och översätter prompten till rätt mått, mått och datumintervall för analysen. Istället för att behöva bekanta dig med komponenterna i datavyn och sedan dra och släppa dem i den bästa kombinationen för att besvara din fråga, behöver du bara skriva in frågan i AI-assistenten.

## Omfattning kontra funktioner utanför omfånget för Alpha

Funktioner som är inom omfånget:

| Funktion som stöds | Beskrivning |
| --- | --- |
| Skapa och uppdatera visualiseringar | Skapar en friformstabell och tillhörande visualisering (t.ex. linje, streck, munk).<p>Exempel: *Vad är vinsten för SKU:er från februari till maj?* |
| Visualiseringstyper som stöds | Linje-, flerrads-, frihandsfigur-, Bar-, Donut-, sammanfattningsnummernummervisualiseringar |
| Odefinierad snabb upptäckt | Om du skickar in en fråga som inte omfattas, t.ex.&quot;exportera det här projektet&quot;, svarar assistenten genom att meddela att frågan inte omfattas. |
| Tydligare frågor | Om du ställer en fråga som inte har tillräckligt sammanhang för att AI-assistenten ska kunna svara på, eller är för generisk, svarar AI-assistenten med en klargörande fråga och/eller föreslagna alternativ. Exempel: <p>**Komponenter**<ul><li>Mått: *Vilket intäktsmått menade du?*</li><li>Dimension: *Vilka av de nedan &quot;regionerna&quot; vill du fokusera på?*</li><li>Filter: *Vilket kontofilter vill du använda?*</li><li>Datumintervall: *Med&quot;förra månaden&quot;, menade du den senaste hela månaden eller de senaste 30 dagarna?*</li></ul>**Dimension-objekt**: Vilket butiksnamn menade du? (t.ex. Store #5274, Store #2949 osv.) |
| Flera svängar | AI Assistant svarar på en fråga med kontexten från en eller flera föregående uppmaningar, vilket gör att användare kan uppdatera visualiseringar och ställa uppföljningsfrågor. Exempel: *Visa data från mars till april istället.* |
| Feedback | <ul><li>Tummen uppåt</li><li>Tummen nedåt</li><li>Flagga</li></ul> |

Funktioner som inte är tillgängliga:

| Funktionen stöds inte | Beskrivning |
| --- | --- |
| Sammanfattning eller svar direkt | AI-assistenten kan inte svara direkt i chattfältet med ett kortfattat svar på en användarfråga.Exempel på frågor som inte omfattas:<ul><li>*Ge mig en sammanfattning av insikterna från min senaste fråga.*</li><li>*Sammanfatta högdagrarna från linjevisualiseringen.*</li></ul> |
| Tydligare frågor | Tydliga frågor är begränsade till komponenter och dimensionsobjekt. AI-assistenten kan inte förtydliga datavyer, visualiseringar, datakornighet, jämförelse, omfång osv. Utan att klargöra några frågor blir assistenten som standard den som användaren mest troligt frågar efter. Om det returnerar en oväntad visualisering eller datagranularitet kan användaren sedan använda multibläddrings-/uppdateringsfunktionen för att justera visualisering och data. |
| Workspace Actions / Capabilities | AI-assistenten kan inte vidta åtgärder för en användare i Workspace utöver att skapa och uppdatera visualiseringar. Den kan till exempel inte göra något av följande:<ul><li>Gränssnittsknappar för sammanhangsberoende åtgärder (lägg till i diagram, ny panel, ny tabell)</li><li>Dela</li><li>Exportera</li><li>Ladda ned</li><li>Hantera användarinställningar</li><li>Kurva</li><li>Hantera datavy</li><li>Analytics Dashboards-app</li><li>Tillskrivning</li></ul> |
| Visualiseringstyper som inte stöds | <ul><li>Flöde</li><li>Utfall</li><li>Kohortabell</li><li>Område, staplat område</li><li>Stapel staplad</li><li>Punkt</li><li>Kombination</li><li>Histogram</li><li>Vågrätt streck, vågrätt streck</li><li>Sammanfattning av nyckelmått</li><li>Spridning</li><li>Sammanfattningsändring</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> |
| Förklara och verifiera | Genomskinlig beskrivning eller citat av hur AI-assistenten genererade ett svar och ger dig ett sätt att bekräfta att svaret är korrekt. |

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

## AI-assistenten för dataanalys




## Använd AI-assistenten för dataanalys

1. I Customer Journey Analytics går du till den tilldelade sandlådan.

1. Öppna ett Workspace-projekt.


## Exempel på frågor om dataanalys

Här är några exempel på hur AI-assistenten svarar på frågor och förväntade visualiseringar:



## Uppmana till bästa praxis

TBD

## Förväntningar om testning av Alpha och efterfrågad feedback

TB D

## Frågor och kontakt

E-post `taylorb@adobe.com` (PM)
Skicka frågor och feedback via Alpha-slackkanalen




