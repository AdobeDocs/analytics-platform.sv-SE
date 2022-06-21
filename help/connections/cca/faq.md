---
title: Vanliga frågor om flerkanalsanalys
description: Frågor och svar om flerkanalsanalys
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: f181584603d62b09ebc8538759d47fb1e03b007a
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 0%

---

# Frågor och svar

## Hur kan jag använda CCA för att se hur människor flyttar från en kanal till en annan?

Du kan använda en Flow-visualisering med datauppsättnings-ID-dimensionen.

1. Logga in på [analytics.adobe.com](https://analytics.adobe.com) och skapa ett tomt Workspace-projekt.
2. Klicka på fliken Visualiseringar till vänster och dra en flödesvisualisering till arbetsytan till höger.
3. Klicka på fliken Komponenter till vänster och dra dimensionen &quot;Datauppsättning-ID&quot; till mittplatsen med etiketten &quot;Dimension eller Artikel&quot;.
4. Denna flödesrapport är interaktiv. Klicka på något av värdena för att utöka flödena till efterföljande eller föregående sidor. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

Om du vill byta namn på dimensionsobjekt för datauppsättnings-ID kan du använda en uppslagsdatauppsättning.

## Hur långt tillbaka kan CCA skicka besökare?

Uppslagsfönstret för inmatning beror på hur ofta du vill ha data [spela upp](replay.md). Om du t.ex. konfigurerar CCA att spela upp data en gång i veckan, är uppslagsfönstret för inmatning sju dagar. Om du konfigurerar CCA att spela upp data varje dag är uppslagsfönstret för manuell inmatning 1 dag.

## Hur hanteras delade enheter?

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag.

Det tillfälliga ID:t åsidosätter det beständiga ID:t, så delade enheter betraktas som separata personer (även om de kommer från samma enhet).

## Hur hanterar CCA situationer där en person har ett stort antal beständiga ID:n?

I vissa fall kan en enskild användare associera med ett stort antal beständiga ID:n. Exempel är en person som ofta tar bort webbläsarcookies eller använder webbläsarens privata läge/inkognito-läge.

Antalet beständiga ID:n är irrelevant för det tillfälliga ID:t. En enskild användare kan tillhöra ett valfritt antal enheter utan att det påverkar CCA:s möjlighet att sammanfoga enheter.

## När jag har kontaktat min kontoansvarige med den önskade informationen, hur lång tid tar det innan den inmatade datauppsättningen blir tillgänglig?

Liveutjämning är tillgänglig cirka en vecka efter att Adobe har möjliggjort kanalövergripande analys. Tillgängligheten för förifyllning beror på mängden befintliga data. Små datauppsättningar (mindre än 1 miljon händelser per dag) tar normalt några dagar, medan stora datauppsättningar (1 miljard händelser per dag) kan ta en vecka eller mer.

## Hur hanterar flerkanalsanalys GDPR- och CCPA-begäranden?

Adobe hanterar förfrågningar om GDPR och CCPA i enlighet med lokal och internationell lagstiftning. Adobe erbjuder [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) för att skicka in förfrågningar om dataåtkomst och borttagning. Förfrågningarna gäller både den ursprungliga och den inmatade datauppsättningen.

## Vad händer om fältet för beständigt ID i en eller flera händelser är tomt?

Om `Persistent ID` fältet är tomt för en händelse i en datauppsättning som sammanfogas med fältbaserad sammanfogning, CCA-fyllning i `Stitched ID` för den händelsen på ett av två sätt:
* Om `Transient ID` fältet är inte tomt, CCA använder värdet i `Transient ID` som `Stitched ID`.
* Om `Transient ID` fältet är tomt, CCA lämnar även `Stitched ID` tom. I detta fall `Persistent ID`, `Transient ID`och `Stitched ID` kommer alla att vara tomma för händelsen. Händelser som detta tas bort från CJA i alla CJA-anslutningar med datauppsättningen sammanfogad där `Stitched ID` valdes som `Person ID`.

## Hur jämförs data i CJA-sammanslagna datauppsättningar med liknande värden i CJA-sammanslagna datauppsättningar och med traditionella Adobe Analytics?

Vissa mått i CJA liknar mätvärden i traditionell analys, men andra är helt olika beroende på vad du jämför. I tabellen nedan jämförs flera vanliga mätvärden:

| **CJA-sammanfogade data** | **CJA frigjorda data** | **Traditionell Adobe Analytics** | **Analytics Ultimate med CDA** |
| ----- | ----- | ----- | ----- |
| **Folk** = Antal distinkta `Person ID`s var `Stitched ID` väljs som `Person ID`. **Folk** kan vara högre eller lägre än **Unika besökare** i traditionell Adobe Analytics, beroende på utfallet av sammanfogningsprocessen. | **Folk** = Antal distinkta `Person ID`baseras på den kolumn som markerats som `Person ID`. **Folk** i Adobe Source Connector-datamängder liknar **Unika besökare** i traditionell Adobe Analytics om `endUserIDs. _experience. aaid.id` väljs som `Person ID` i CJA. | **Unika besökare** = Antal distinkta besökar-ID:n. Observera att **Unika besökare** får inte vara samma som antalet distinkta **ECID** s. | Se [Folk](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html). |
| **Sessioner**: Definieras baserat på sessionsinställningarna som anges i CJA-datavyn. Sammanfogningsprocessen kan kombinera enskilda sessioner från flera enheter till en enda session. | **Sessioner**: Definieras baserat på sessionsinställningarna som anges i CJA-datavyn. | **Besök**: Se [Besök](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html). | **Besök**: Definieras baserat på sessionsinställningarna som anges i [CDA Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html). |
| **Händelser** = antal rader i sammanslagna data i CJA. I allmänhet bör detta ligga nära **Förekomster** i traditionell Adobe Analytics. Observera dock Vanliga frågor och svar ovan om rader med en tom `Persistent ID`. | **Händelser** = antal rader i de osydda data i CJA. I allmänhet bör detta ligga nära **Förekomster** i traditionell Adobe Analytics. Observera dock att om några händelser har en tom `Person ID` dessa händelser kommer att utelämnas (ingår inte) i CJA i de data som inte sammanställts i AEP-sjön. | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Andra mätvärden kan likna dem i CJA och i traditionella Adobe Analytics. Det totala antalet för Adobe Analytics [anpassade händelser](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html) 1-100 bör i allmänhet vara mycket nära i traditionell Adobe Analytics och CJA (oavsett om de är sydda eller inte). Observera dock att detta kanske inte alltid stämmer på grund av [skillnader i funktionalitet](/help/getting-started/aa-vs-cja/cja-aa.md)), till exempel borttagning av dubbletter mellan CJA och traditionella Adobe Analytics.

## Kan CCA använda fält för identitetskarta?

Nej, CCA kan för närvarande inte använda identityMap-fält.
