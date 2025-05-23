---
title: Vanliga frågor om titlar
description: Vanliga frågor och svar
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 1a003b38ef26eb811b19cd091c6e089f33ddb6f6
workflow-type: tm+mt
source-wordcount: '1918'
ht-degree: 3%

---

# Frågor och svar

Här är några vanliga frågor om stygn:

## Flytta över kanaler

+++ Hur kan jag använda stygn för att se hur människor flyttar från en kanal till en annan?

Du kan använda en Flow-visualisering med datauppsättnings-ID-dimensionen.

1. Logga in på [Customer Journey Analytics](https://analytics.adobe.com) och skapa ett tomt Workspace-projekt.
2. Välj fliken **[!UICONTROL ** Visualiseringar **]** till vänster och dra en **[!UICONTROL **&#x200B; Flödesvisualisering &#x200B;**]** till arbetsytan till höger.
3. Markera fliken **[!UICONTROL ** Komponenter **]** till vänster och dra dimensionen **[!UICONTROL ** Datauppsättning-ID **]** till mittplatsen **[!UICONTROL **&#x200B; Dimension eller Item &#x200B;**]**.
4. Den här flödesrapporten är interaktiv. Om du vill expandera flödena till efterföljande eller föregående sidor markerar du något av värdena. Använd högerklicksmenyn för att expandera eller komprimera kolumner. Olika dimensioner kan också användas i samma flödesrapport.

Om du vill byta namn på dimensionsobjekt för datauppsättnings-ID kan du använda en uppslagsdatauppsättning.

+++

## Spela upp

+++ Hur långt bak spelar syfilis upp besökare?

Uppslagsfönstret för att skriva in data igen beror på hur ofta du vill att data ska spelas upp. Om du t.ex. ställer in sammanfogning för att spela upp data en gång i veckan, är uppslagsfönstret för inmatning sju dagar. Om du konfigurerar att fästa ihop för att spela upp data varje dag är uppslagsfönstret för att skriva in igen en dag.

+++

## Delade enheter

+++ Hur hanteras delade enheter?

I vissa situationer är det möjligt att flera personer loggar in från samma enhet. Exempel är en delad enhet hemma, delade datorer i ett bibliotek eller en kioskdator i ett butiksuttag.

Det tillfälliga ID:t åsidosätter det beständiga ID:t, så delade enheter betraktas som separata personer (även om de kommer från samma enhet).

Mer information finns i [Använda delade enheter](/help/use-cases/stitching/shared-devices.md).

+++

## Många beständiga ID:n

+++ Hur hanteras situationer där en person har många beständiga ID:n när sammanfogning används?

I vissa fall kan en enskild användare associera med många beständiga ID:n. Ett exempel är en person som ofta tar bort webbläsarens cookies eller använder webbläsarens privata läge/inkognito-läge.

För fältbaserad stygn är antalet beständiga ID:n irrelevant till förmån för det tillfälliga ID:t. En enskild användare kan tillhöra ett valfritt antal enheter utan att det påverkar Customer Journey Analytics förmåga att fästa ihop olika enheter.

För diagrambaserade sammanfogningar kan en person ha många beständiga ID:n i identitetsdiagrammet. Diagrambaserad sammanfogning använder det beständiga ID:t baserat på det angivna namnutrymmet. Om det finns ett mer beständigt ID för samma namnutrymme används det lexicografiska först beständiga ID:t.

+++

## Förstärkningsprocess

+++ När jag har kontaktat mitt Adobe-kontoteam med den önskade informationen, hur lång tid tar det innan den inmatade datauppsättningen blir tillgänglig?

Livesutsättning är tillgänglig cirka en vecka efter det att Adobe möjliggör syning. Tillgängligheten för förifyllning beror på mängden befintliga data. Små datauppsättningar (mindre än 1 miljon händelser per dag) tar normalt några dagar, medan stora datauppsättningar (1 miljard händelser per dag) kan ta en vecka eller mer.

+++

## Enhetsövergripande analys jämfört med flerkanalsanalys

+++ Vad är skillnaden mellan enhetsövergripande analys (en funktion i traditionell analys) och flerkanalsanalys?

[Enhetsövergripande analys](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=sv-SE) är en funktion som är specifik för traditionella Adobe Analytics och som gör att du kan förstå hur människor arbetar på olika enheter. Det finns två arbetsflöden för att länka samman enhetsdata: fältbaserad sammanfogning och enhetsgrafen.

Flerkanalsanalys är ett användningsfall som är specifikt för Customer Journey Analytics och som gör det möjligt att förstå hur människor arbetar på olika enheter och i olika kanaler. Den sammanfogar en datauppsättnings person-ID så att den datauppsättningen kan kombineras med andra datauppsättningar. Den här funktionen fungerar i design på samma sätt som fältbaserad sammanfogning av analys över flera enheter, men implementeringen skiljer sig åt på grund av att dataarkitekturen skiljer sig mellan traditionell Analytics och Customer Journey Analytics. Mer information finns [i Sammanfogning](overview.md) och användningsfall för [flerkanalsanalys](../use-cases/cross-channel/cross-channel.md) .

+++

## Sekretess

+++ Hur hanterar Stitching sekretessförfrågningar?

Adobe hanterar förfrågningar om integritet i enlighet med lokal och internationell lagstiftning. Adobe erbjuder [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=sv-SE) för att skicka in dataåtkomst och borttagningsbegäranden. Förfrågningarna gäller både den ursprungliga och den inmatade datauppsättningen.

>[!IMPORTANT]
>
>Frigörandeprocessen, som en del av begäran om integritet, ändras i början av 2025. Den aktuella enhetsprocessen ändrar namn på händelser med den senaste versionen av kända identiteter. Denna omfördelning av händelser till en annan identitet kan få oönskade juridiska konsekvenser. För att åtgärda dessa problem uppdaterar den nya upplösningsprocessen från och med 2025 händelser som omfattas av sekretessposten med det beständiga ID:t.
> 

Tänk dig följande data för identiteter, händelser före sammanfogning och efter sammanfogning.

| Identitetskarta | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace |
|---|---|---|---|---|---|---|
|  | 1 | ts1 | 123 | ecid | Bob | CustId |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Händelsedatauppsättning | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace |
|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| | 2 | ts1 | 123 | ecid | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Stitled dataset | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace | Namnlöst ID | Namnutrymme med rutor |
|---|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | Bob | CustId |
| | 2 | ts1 | 123 | ecid | Bob | CustId | Bob | CustId |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Aktuell process för sekretesspolicy**

När en sekretessförfrågan tas emot för kunden med CustID Bob tas raderna med genomstrykningsposter bort. Andra händelser får en ny titel med hjälp av identitetskartan. Det första sammanslagna ID:t i den sammanslagna datauppsättningen uppdateras till **Alex**.

| Identitetskarta | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Händelsedatauppsättning | ID | Tidsstämpel | beständigt ID | Beständig namnrymd | Tillfälligt ID | Tillfälligt namnområde |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Stitled dataset | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace | Namnlöst ID | Namnutrymme med rutor |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **Alex** | CustId |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |


**Ny process för sekretesspolicy**

När en sekretessbegäran tas emot för en kund med CustID Bob tas raderna med genomstrukna poster bort. Andra händelser får en ny titel med det beständiga ID:t. Till exempel uppdateras det första sammanfogade ID:t i den sammanfogade datauppsättningen till **123**.

| Identitetskarta | ID | tidsstämpel | beständigt ID | Beständig namnrymd | Tillfälligt ID | Tillfälligt namnområde |
|:---:|---|---|---|---|---|---|
| ![Ta bort disposition](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Händelsedatauppsättning | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Stitled dataset | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace | Namnlöst ID | Namnutrymme med rutor |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid ecid~~ | ~~Guppa~~ | ~~CustId~~ | ~~Guppa~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId | Alex | CustId |

+++

## Tomma beständiga ID-värden

+++ Vad händer om fältet för beständigt ID i en eller flera händelser är tomt?

Om fältet för beständigt ID är tomt för en händelse i en datauppsättning som sammanfogas, bestäms ID:t för den händelsen på ett av två sätt:

* Om fältet Transient ID inte är tomt använder Customer Journey Analytics värdet i Transient ID som Stitched ID.
* Om fältet Transient ID är tomt lämnas också Stitched ID tomt. I det här fallet är Persistent ID, Transient ID och Stitched ID tomma för händelsen. Dessa typer av händelser tas bort från alla Customer Journey Analytics-anslutningar som använder datauppsättningen som sammanfogas där Stitched ID valdes som person-ID.

+++


## Odefinierade värden för transient-ID

+++ Vad händer om fältet Transient ID i en eller flera händelser har platshållarvärden, som `Undefined`?

Var försiktig med &quot;personkomprimering&quot;, som inträffar när sammanfogning används på data som använder platshållarvärden för tillfälliga ID:n. I exempeltabellen nedan fylls odefinierade person-ID:n som härstammar från en datauppsättning som härstammar från ett CRM-system i med värdet &#39;Odefinierad&#39;, vilket resulterar i felaktig återgivning av personer.

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after replay) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 123 | - | **Artikel** |
| 2 | 2023-05-12 12:02 | 123 | Kategori | **Artikel** |
| 3 | 2023-05-12 | 456 | Odefinierad | **Odefinierad** |
| 4 | 2023-05-12 12:04 | 456 | - | **Odefinierad** |
| 5 | 2023-05-12 | 789 | Odefinierad | **Odefinierad** |
| 6 | 2023-05-12 | 012 | Odefinierad | **Odefinierad** |
| 7 | 2023-05-12 | 012 | - | **Odefinierad** |
| 8 | 2023-05-12 | 789 | Odefinierad | **Odefinierad** |
| 9 | 2023-05-12 | 456 | - | **Odefinierad** |
| 10 | 2023-05-12 12:02 | 123 | - | **Artikel** |
| | | **4 enheter** | **2 personer**:<br/>Händelser 1, 4, 7, 9, 10 har tagits bort | **2 personer**:<br/>Oautentiserad (komprimerad till en person) |

+++

## Jämförelse av mått

+++ Hur fungerar mätvärden i Customer Journey Analytics sammanslagna datauppsättningar jämfört med liknande värden i Customer Journey Analytics osökta datauppsättningar och med Adobe Analytics?

Vissa mätvärden i Customer Journey Analytics liknar mätvärden i traditionell analys, men andra är olika beroende på vad du jämför. I tabellen nedan jämförs flera vanliga mätvärden:

| **Customer Journey Analytics sammanfogade data** | **Customer Journey Analytics oschade data** | **Adobe Analytics** | **Analysera Ultimate med CDA** |
| ----- | ----- | ----- | ----- |
| **Personer** = Antal distinkta person-ID:n där Stitched ID väljs som person-ID. **Personer** kan vara högre eller lägre än **Unika besökare** i traditionella Adobe Analytics, beroende på utfallet av sammanfogningsprocessen. | **Personer** = Antal distinkta person-ID:n baserat på den kolumn som valts som person-ID. **Personer** i Analytics-källanslutningsdatauppsättningar liknar **Unika besökare** i traditionella Adobe Analytics om `endUserIDs._experience.aaid.id` används som person-ID i Customer Journey Analytics. | **Unika besökare** = Antal distinkta besökar-ID. **Unika besökare** kanske inte är samma som antalet distinkta **ECID** s. | Se [Personer](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=sv-SE). |
| **Sessioner**: Definieras baserat på sessionsinställningarna i Customer Journey Analytics datavy. Sammanfogningsprocessen kan kombinera enskilda sessioner från flera enheter till en enda session. | **Sessioner**: Definieras baserat på sessionsinställningarna som anges i datavyn för Customer Journey Analytics. | **Besök**: Se [Besök](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=sv-SE). | **Besök**: Definieras baserat på sessionsinställningarna som anges i den virtuella [CDA-rapportsviten](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html?lang=sv-SE). |
| **Händelser** = antal rader i sammanslagna data i Customer Journey Analytics. Det här måttet ligger vanligtvis nära **förekomster** i traditionella Adobe Analytics. Observera dock Vanliga frågor och svar ovan om rader med ett tomt Persistent ID. | **Händelser** = antal rader i osydda data i Customer Journey Analytics. Det här måttet ligger vanligtvis nära **förekomster** i traditionella Adobe Analytics. Observera dock att om några händelser har ett tomt person-ID i de icke sammansatta data som finns i Experience Platform datavinje, ingår inte dessa händelser i Customer Journey Analytics. | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=sv-SE). | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=sv-SE). |

Andra mätvärden kan likna i Customer Journey Analytics och Adobe Analytics. Det totala antalet för [anpassade Adobe Analytics-händelser](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=sv-SE) 1-100 är till exempel jämförbart mellan traditionella Adobe Analytics och Customer Journey Analytics (oavsett om de är sammanfogade eller inte). [Skillnader i funktioner](/help/getting-started/aa-vs-cja/cja-aa.md)), t.ex. borttagning av dubbletter av händelser mellan Customer Journey Analytics och Adobe Analytics, kan orsaka diskrepans mellan de två produkterna.

+++

## Identitetskarta

+++ Kan Customer Journey Analytics använda fält för identitetskarta?

Nej, Customer Journey Analytics kan för närvarande inte använda Identity Map-fält för sammanfogning.

+++

## Växla till diagrambaserad sammanfogning

+++ Måste data kapslas om för att växla från fältbaserad sammanfogning till diagrambaserad sammanfogning?

Data behöver inte kapslas in på nytt i Experience Platform, men de måste konfigureras om i Customer Journey Analytics. Följ dessa steg:

1. Konfigurera den nya diagrambaserade sammanslagna datauppsättningen.
1. Konfigurera den nya datauppsättningen som en del av en ny anslutning i Customer Journey Analytics.
1. Växla din befintliga datavy till den nya anslutningen (och som sådan den nya grafbaserade, stilade datauppsättningen)
1. Ta bort den gamla anslutningen som använde den fältbaserade sammanfogade datauppsättningen.

+++

## Störningar i rapporteringen

+++ Skulle det bli några avbrott i befintliga rapporter?

Inte om du följer instruktionerna ovan. Annars ber vi Adobe Consulting om ytterligare support.

+++


