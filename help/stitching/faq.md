---
title: Vanliga frågor om titlar
description: Vanliga frågor och svar
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 80d5a864e063911b46ff248f2ea89c1ed0d14e32
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 1%

---

# Frågor och svar

Här är några vanliga frågor om stygn:

+++**Hur kan jag använda stygn för att se hur människor flyttar från en kanal till en annan?**

Du kan använda en Flow-visualisering med datauppsättnings-ID-dimensionen.

1. Logga in på [Customer Journey Analytics](https://analytics.adobe.com) och skapa ett tomt Workspace-projekt.
2. Välj **[!UICONTROL ** Visualiseringar **]** till vänster och dra en **[!UICONTROL ** Flöde **]** visualisering till arbetsytan till höger.
3. Välj **[!UICONTROL ** Komponenter **]** till vänster och dra dimensionen **[!UICONTROL ** Datauppsättnings-ID **]** till mittplatsen med etiketten **[!UICONTROL ** Dimension eller objekt **]**.
4. Den här flödesrapporten är interaktiv. Om du vill expandera flödena till efterföljande eller föregående sidor markerar du något av värdena. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

Om du vill byta namn på dimensionsobjekt för datauppsättnings-ID kan du använda en uppslagsdatauppsättning.

+++

+++**Hur långt bak spelar syfilis upp besökare?**

Uppslagsfönstret för att skriva in data igen beror på hur ofta du vill att data ska spelas upp. Om du t.ex. ställer in sammanfogning för att spela upp data en gång i veckan, är uppslagsfönstret för inmatning sju dagar. Om du konfigurerar att fästa ihop för att spela upp data varje dag är uppslagsfönstret för att skriva in igen en dag.

+++

+++**Hur hanteras delade enheter?**

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag.

Det tillfälliga ID:t åsidosätter det beständiga ID:t, så delade enheter betraktas som separata personer (även om de kommer från samma enhet).

+++

+++**Hur hanteras situationer där en person har många beständiga ID:n när sammanfogning används?**

I vissa fall kan en enskild användare associera med många beständiga ID:n. Ett exempel är en person som ofta tar bort webbläsarens cookies eller använder webbläsarens privata läge/inkognito-läge.

För fältbaserad stygn är antalet beständiga ID:n irrelevant till förmån för det tillfälliga ID:t. En enskild användare kan tillhöra ett valfritt antal enheter utan att det påverkar Customer Journey Analytics förmåga att sy ihop sig mellan olika enheter.

För diagrambaserade sammanfogningar kan en person ha många beständiga ID:n i identitetsdiagrammet. Diagrambaserad sammanfogning använder det beständiga ID:t baserat på det angivna namnutrymmet. Om det finns ett mer beständigt ID för samma namnutrymme används det lexicografiska först beständiga ID:t.

+++

+++**När jag har kontaktat mitt Adobe-kontoteam med den önskade informationen, hur lång tid tar det innan den inmatade datauppsättningen blir tillgänglig?**

Det finns direktutjämning ungefär en vecka efter det att Adobe har synat sig. Tillgängligheten för förifyllning beror på mängden befintliga data. Små datauppsättningar (mindre än 1 miljon händelser per dag) tar normalt några dagar, medan stora datauppsättningar (1 miljard händelser per dag) kan ta en vecka eller mer.

+++

+++**Vad är skillnaden mellan enhetsövergripande analys (en funktion i traditionell analys) och flerkanalsanalys?**

[Enhetsövergripande analys](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) är en funktion som är specifik för traditionella Adobe Analytics och som gör att du kan förstå hur människor arbetar på olika enheter. Det finns två arbetsflöden för att länka samman enhetsdata: fältbaserad sammanfogning och enhetsgrafen.

Flerkanalsanalys är ett användningsfall som är specifikt för Customer Journey Analytics och som gör det möjligt att förstå hur människor arbetar på olika enheter och i olika kanaler. Den sammanfogar en datauppsättnings person-ID så att den datauppsättningen kan kombineras med andra datauppsättningar. Den här funktionen fungerar i design på ungefär samma sätt som fältbaserad stygning mellan olika enheter, men implementeringen är annorlunda på grund av att dataarkitekturen skiljer sig mellan traditionell Analytics och Customer Journey Analytics. Se [Stitlar](overview.md) och [flerkanalsanalys](../use-cases/cross-channel/cross-channel.md) finns mer information.

+++

+++**Hur hanterar Stitching sekretessförfrågningar?**

Adobe hanterar förfrågningar om sekretess i enlighet med lokal och internationell lagstiftning. Adobe erbjuder [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) för att skicka in förfrågningar om dataåtkomst och borttagning. Förfrågningarna gäller både den ursprungliga och den inmatade datauppsättningen.

+++

+++**Vad händer om fältet för beständigt ID i en eller flera händelser är tomt?**

Om fältet för beständigt ID är tomt för en händelse i en datauppsättning som sammanfogas, bestäms ID:t för den händelsen på ett av två sätt:

* Om fältet Transient ID inte är tomt använder Customer Journey Analytics värdet i Transient ID som Stitched ID.
* Om fältet Övergående ID är tomt lämnar Customer Journey Analytics också fältet Stitched ID tomt. I det här fallet är Persistent ID, Transient ID och Stitched ID tomma för händelsen. Dessa typer av händelser tas bort från alla Customer Journey Analytics-anslutningar med datauppsättningen som sammanfogas där Stitched ID valdes som person-ID.

+++


+++**Vad händer om fältet Transient ID i en eller flera händelser har platshållarvärden, som &#39;Undefined&#39;?**

Var försiktig med &quot;personkomprimering&quot;, som inträffar när sammanfogning används på data som använder platshållarvärden för tillfälliga ID:n. I exempeltabellen nedan fylls odefinierade person-ID:n som härstammar från en datauppsättning som härstammar från ett CRM-system i med värdet &#39;Odefinierad&#39;, vilket resulterar i felaktig återgivning av personer.

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after replay) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Kategori** |
| 2 | 2023-05-12 12:02 | 123 | Kategori | **Kategori** |
| 3 | 2023-05-12 | 456 | Odefinierad | **Odefinierad** |
| 4 | 2023-05-12 12:04 | 456 | - | **Odefinierad** |
| 5 | 2023-05-12 | 789 | Odefinierad | **Odefinierad** |
| 6 | 2023-05-12 | 012 | Odefinierad | **Odefinierad** |
| 7 | 2023-05-12 | 012 | - | **Odefinierad** |
| 8 | 2023-05-12 | 789 | Odefinierad | **Odefinierad** |
| 9 | 2023-05-12 | 456 | - | **Odefinierad** |
| 10 | 2023-05-12 12:02 | 123 | - | **Kategori** |
| | | **4 enheter** | **2 personer**:<br/>Händelser 1, 4, 7, 9, 10 utelämnade | **2 personer**:<br/>Torsk, oautentiserad (komprimerad till en person) |

+++

+++**Hur fungerar mätvärden i datauppsättningar som sammanfogats med Customer Journey Analytics jämfört med liknande värden i datauppsättningar som inte sammanställts med Customer Journey Analytics och med Adobe Analytics?**

Vissa mätvärden i Customer Journey Analytics liknar mätvärden i traditionell analys, men andra är olika beroende på vad du jämför. I tabellen nedan jämförs flera vanliga mätvärden:

| **data sammanfogade med Customer Journey Analytics** | **data som inte sammanfogats med Customer Journey Analytics** | **Adobe Analytics** | **Analytics Ultimate med CDA** |
| ----- | ----- | ----- | ----- |
| **Folk** = Antal distinkta person-ID:n där Stitched ID väljs som person-ID. **Folk** kan vara högre eller lägre än **Unika besökare** i traditionell Adobe Analytics, beroende på utfallet av sammanfogningsprocessen. | **Folk** = Antal distinkta person-ID:n baserat på den kolumn som valts som person-ID. **Folk** i Analytics-källanslutningsdatauppsättningar liknar **Unika besökare** i traditionell Adobe Analytics om `endUserIDs._experience.aaid.id` används som person-ID i Customer Journey Analytics. | **Unika besökare** = Antal distinkta besökar-ID. **Unika besökare** får inte vara samma som antalet distinkta **ECID** s. | Se [Folk](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html). |
| **Sessioner**: Definieras baserat på sessionsinställningarna i datavyn i Customer Journey Analytics. Sammanfogningsprocessen kan kombinera enskilda sessioner från flera enheter till en enda session. | **Sessioner**: Definieras baserat på sessionsinställningarna som anges i datavyn i Customer Journey Analytics. | **Besök**: Se [Besök](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html). | **Besök**: Definieras baserat på sessionsinställningarna som anges i [CDA Virtual Report Suite](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html). |
| **Händelser** = antal rader i sammanslagna data i Customer Journey Analytics. Det här måttet ligger vanligtvis nära **Förekomster** i traditionell Adobe Analytics. Observera dock Vanliga frågor och svar ovan om rader med ett tomt Persistent ID. | **Händelser** = antal rader i osydda data i Customer Journey Analytics. Det här måttet ligger vanligtvis nära **Förekomster** i traditionell Adobe Analytics. Observera dock att om några händelser har ett tomt person-ID i de data som inte sammanställts i datavjön i Experience Platform, ingår inte dessa händelser i Customer Journey Analytics. | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Andra mätvärden kan vara liknande i Customer Journey Analytics och Adobe Analytics. Det totala antalet för Adobe Analytics [anpassade händelser](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html) 1-100 är jämförbar mellan Adobe Analytics och Customer Journey Analytics (oavsett om de är sydda eller inte). [Skillnader i funktionalitet](/help/getting-started/aa-vs-cja/cja-aa.md)), till exempel vid borttagning av dubbletter mellan Customer Journey Analytics och Adobe Analytics, kan orsaka diskrepans mellan de två produkterna.

+++

+++**Kan Customer Journey Analytics använda fält för identitetskarta?**

Nej, Customer Journey Analytics kan för närvarande inte använda Identitetskarta-fält för sammanfogning.

+++

+++**Kommer data att behöva kapslas om för att växla från fältbaserad sammanfogning till diagrambaserad sammanfogning?**
Data behöver inte kapslas in i Experience Platform, men måste konfigureras om i Customer Journey Analytics. Följ dessa steg:

1. Konfigurera den nya diagrambaserade sammanslagna datauppsättningen.
1. Konfigurera den nya datauppsättningen som en del av en ny anslutning i Customer Journey Analytics.
1. Växla din befintliga datavy till den nya anslutningen (och som sådan den nya grafbaserade, stilade datauppsättningen)
1. Ta bort den gamla anslutningen som använder den fältbaserade sammanslagna datauppsättningen.

+++

+++**Skulle det bli några avbrott i befintliga rapporter?**

Inte om du följer instruktionerna ovan. Annars ber vi Adobe Consulting om ytterligare support.

+++


