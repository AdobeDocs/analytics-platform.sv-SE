---
title: Vanliga frågor om flerkanalsanalys
description: Frågor och svar om flerkanalsanalys
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
hide: true
hidefromtoc: true
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 0%

---

# Frågor och svar

## Hur kan jag använda CCA för att se hur människor flyttar från en kanal till en annan?

Du kan använda en Flow-visualisering med datauppsättnings-ID-dimensionen.

1. Logga in på [analytics.adobe.com](https://analytics.adobe.com) och skapa ett tomt Workspace-projekt.
2. Klicka på fliken Visualiseringar till vänster och dra en flödesvisualisering till arbetsytan till höger.
3. Klicka på fliken Komponenter till vänster och dra dimensionen &quot;Datauppsättning-ID&quot; till mittplatsen med namnet &quot;Dimension eller Artikel&quot;.
4. Denna flödesrapport är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

Om du vill byta namn på dimensionsobjekt för datauppsättnings-ID kan du använda en uppslagsdatauppsättning.

## Hur långt bakåt återskriver CCA personer?

Uppslagsfönstret för inmatning beror på hur ofta du vill ha data [spela upp](replay.md). Om du till exempel konfigurerar CCA att spela upp data en gång i veckan, är uppslagsfönstret för inmatning sju dagar. Om du konfigurerar CCA att spela upp data varje dag är uppslagsfönstret för manuell inmatning en dag.

## Hur hanteras delade enheter?

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag.

Det tillfälliga ID:t åsidosätter det beständiga ID:t, så delade enheter betraktas som separata personer (även om de kommer från samma enhet).

## Hur hanterar CCA situationer där en person har många beständiga ID:n?

I vissa fall kan en enskild användare associera med många beständiga ID:n. Exempel är en person som ofta tar bort webbläsarcookies eller använder webbläsarens privata läge/inkognito-läge.

Antalet beständiga ID:n är irrelevant för det tillfälliga ID:t. En enskild användare kan tillhöra ett valfritt antal enheter utan att det påverkar CCA:s möjlighet att sammanfoga enheter.

## När jag har kontaktat mitt Adobe-kontoteam med den önskade informationen, hur lång tid tar det innan den inmatade datauppsättningen blir tillgänglig?

Liveutjämning är tillgänglig cirka en vecka efter att Adobe har aktiverat flerkanalsanalys. Tillgängligheten för förifyllning beror på mängden befintliga data. Små datauppsättningar (mindre än 1 miljon händelser per dag) tar normalt några dagar, medan stora datauppsättningar (1 miljard händelser per dag) kan ta en vecka eller mer.

## Vad är skillnaden mellan Enhetsövergripande analys (en funktion i Adobe Analytics) och kanalövergripande analys?

[Enhetsövergripande analys](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) är en funktion som är specifik för traditionella Adobe Analytics och som gör att du kan förstå hur människor arbetar på olika enheter. Det finns två arbetsflöden för att länka samman enhetsdata: fältbaserad sammanfogning och enhetsgrafen.

[Flerkanalsanalys](/help/cca/overview.md) är en funktion som är specifik för Customer Journey Analytics och som gör att du kan förstå hur människor arbetar på olika enheter och i olika kanaler. Det är ett nytt ID för en datauppsättning, vilket gör att datauppsättningen kan kombineras med andra datauppsättningar. Den här funktionen fungerar på liknande sätt som i CDA:s fältbaserade sammanfogning, men implementeringen skiljer sig åt när det gäller dataarkitekturen mellan Adobe Analytics och Customer Journey Analytics.

## Hur hanterar flerkanalsanalys GDPR- och CCPA-begäranden?

Adobe hanterar förfrågningar om GDPR och CCPA i enlighet med lokal och internationell lagstiftning. Adobe erbjuder [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) för att skicka in förfrågningar om dataåtkomst och borttagning. Förfrågningarna gäller både den ursprungliga och den inmatade datauppsättningen.

## Vad händer om fältet för beständigt ID i en eller flera händelser är tomt?

Om `Persistent ID` fältet är tomt för en händelse i en datauppsättning som sammanfogas med fältbaserad sammanfogning, CCA-fyllning i `Stitched ID` för den händelsen på ett av två sätt:

* Om `Transient ID` fältet är inte tomt, CCA använder värdet i `Transient ID` som `Stitched ID`.
* Om `Transient ID` fältet är tomt, CCA lämnar även `Stitched ID` tom. I detta fall `Persistent ID`, `Transient ID`och `Stitched ID` är alla tomma för händelsen. Dessa typer av händelser tas bort från alla Customer Journey Analytics-anslutningar som använder datauppsättningen som sammanfogas där `Stitched ID` valdes som `Person ID`.

## Hur fungerar mätvärden i datauppsättningar som sammanfogats med Customer Journey Analytics jämfört med liknande värden i datauppsättningar som inte sammanställts med Customer Journey Analytics och med traditionella Adobe Analytics?

Vissa mätvärden i Customer Journey Analytics liknar mätvärden i Adobe Analytics, men andra är helt olika beroende på vad du jämför. I tabellen nedan jämförs flera vanliga mätvärden:

| **data sammanfogade med Customer Journey Analytics** | **data som inte sammanfogats med Customer Journey Analytics** | **Traditionell Adobe Analytics** | **Analytics Ultimate med CDA** |
| ----- | ----- | ----- | ----- |
| **Folk** = Antal distinkta `Person ID`s var `Stitched ID` väljs som `Person ID`. **Folk** kan vara högre eller lägre än **Unika besökare** i traditionell Adobe Analytics, beroende på utfallet av sammanfogningsprocessen. | **Folk** = Antal distinkta `Person ID`baseras på den kolumn som markerats som `Person ID`. **Folk** i Adobe Source Connector-datamängder liknar **Unika besökare** i traditionell Adobe Analytics om `endUserIDs._experience.aaid.id` väljs som `Person ID` i Customer Journey Analytics. | **Unika besökare** = Antal distinkta person-ID:n. **Unika besökare** får inte vara samma som antalet distinkta **ECID** s. | Se [Folk](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html). |
| **Sessioner**: Definieras baserat på sessionsinställningarna i datavyn i Customer Journey Analytics. Sammanfogningsprocessen kan kombinera enskilda sessioner från flera enheter till en enda session. | **Sessioner**: Definieras baserat på sessionsinställningarna som anges i datavyn i Customer Journey Analytics. | **Besök**: Se [Besök](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html). | **Besök**: Definieras baserat på sessionsinställningarna som anges i [CDA Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html). |
| **Händelser** = antal rader i sammanslagna data i Customer Journey Analytics. Det här måttet ligger vanligtvis nära **Förekomster** i traditionell Adobe Analytics. Observera dock Vanliga frågor och svar ovan om rader med en tom `Persistent ID`. | **Händelser** = antal rader i osydda data i Customer Journey Analytics. Det här måttet ligger vanligtvis nära **Förekomster** i traditionell Adobe Analytics. Observera dock att om några händelser har en tom `Person ID` Dessa händelser ingår inte i Customer Journey Analytics i Experience Platform data-sjön. | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Andra mätvärden kan likna dem i Customer Journey Analytics och i Adobe Analytics. Det totala antalet för Adobe Analytics [anpassade händelser](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html) 1-100 är i allmänhet jämförbar mellan traditionella Adobe Analytics och Customer Journey Analytics (oavsett om de är sydda eller inte). [Skillnader i funktionalitet](/help/getting-started/aa-vs-cja/cja-aa.md)), till exempel vid borttagning av dubbletter mellan Customer Journey Analytics och traditionella Adobe Analytics, kan orsaka skillnader mellan de två produkterna.

## Kan CCA använda fält för identitetskarta?

Nej, CCA kan för närvarande inte använda fält för identitetskarta.
