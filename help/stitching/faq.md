---
title: Vanliga frågor om titlar
description: Vanliga frågor och svar
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: f4115164-7263-40ad-9706-3b98d0bb7905
role: Admin
source-git-commit: 4cea79a6ba26a2e4f06bfc9c60fdfc03341a7d60
workflow-type: tm+mt
source-wordcount: '2084'
ht-degree: 2%

---

# Frågor och svar

Här är några vanliga frågor om stygn:

## Flytta över kanaler

+++ Hur kan jag använda stygn för att se hur människor flyttar från en kanal till en annan?

Du kan använda en Flow-visualisering med datauppsättnings-ID-dimensionen.

1. Logga in på [Customer Journey Analytics](https://analytics.adobe.com) och skapa ett tomt Workspace-projekt.
2. Välj fliken **[!UICONTROL ** Visualiseringar **]** till vänster och dra en **[!UICONTROL ** Flödesvisualisering **]** till arbetsytan till höger.
3. Markera fliken **[!UICONTROL ** Komponenter **]** till vänster och dra dimensionen **[!UICONTROL ** Datauppsättning-ID **]** till mittplatsen **[!UICONTROL ** Dimension eller Item **]**.
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

[Enhetsövergripande analys](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html) är en funktion som är specifik för traditionella Adobe Analytics och som gör att du kan förstå hur människor arbetar på olika enheter. Det finns två arbetsflöden för att länka samman enhetsdata: fältbaserad sammanfogning och enhetsgrafen.

Flerkanalsanalys är ett användningsfall som är specifikt för Customer Journey Analytics och som gör det möjligt att förstå hur människor arbetar på olika enheter och i olika kanaler. Den sammanfogar en datauppsättnings person-ID så att den datauppsättningen kan kombineras med andra datauppsättningar. Den här funktionen fungerar i design på ungefär samma sätt som fältbaserad stygning mellan olika enheter, men implementeringen är annorlunda på grund av att dataarkitekturen skiljer sig mellan traditionell Analytics och Customer Journey Analytics. Mer information finns i [Stitching](overview.md) och [cross-channel analysis](../use-cases/cross-channel/cross-channel.md) use case.

+++

## Sekretess

+++ Hur hanterar Stitching sekretessförfrågningar?

Adobe hanterar förfrågningar om integritet i enlighet med lokal och internationell lagstiftning. Adobe erbjuder [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) för att skicka in dataåtkomst och borttagningsbegäranden. Förfrågningarna gäller både den ursprungliga och den inmatade datauppsättningen.

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


| Händelsedatauppsättning | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace |
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

När en sekretessförfrågan tas emot för kunden med CustID Bob tas raderna med genomstrykningsposter bort. Andra händelser får en ny titel med det beständiga ID:t. Det första sammanslagna ID:t i den sammanslagna datauppsättningen uppdateras till **123**.

| Identitetskarta | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace |
|:---:|---|---|---|---|---|---|
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~1~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
|  | 2 | ts2 | 123 | ecid | Alex | CustId |


| Händelsedatauppsättning | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace |
|:---:|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ |
| | 3 | ts2 | 123 | ecid | Alex | CustId |


| Stitled dataset | ID | tidsstämpel | beständigt ID | beständigt namnutrymme | transient-id | transient namespace | Namnlöst ID | Namnutrymme med rutor |
|:---:|---|---|---|---|---|---|---|---|
| | 1 | ts0 | 123 | ecid | | | **123** | ecid |
| ![DeleteOutline](/help/assets/icons/DeleteOutline.svg) | ~~2~~ | ~~ts1~~ | ~~123~~ | ~~ecid~~ | ~~Bob~~ | ~~CustId~~ | ~~Bob~~ | ~~CustId~~ |
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
| 3 | 2023-05-12 12:03 | 456 | Odefinierad | **Odefinierad** |
| 4 | 2023-05-12 12:04 | 456 | - | **Odefinierad** |
| 5 | 2023-05-12 12:05 | 789 | Odefinierad | **Odefinierad** |
| 6 | 2023-05-12 12:06 | 012 | Odefinierad | **Odefinierad** |
| 7 | 2023-05-12 12:07 | 012 | - | **Odefinierad** |
| 8 | 2023-05-12 12:03 | 789 | Odefinierad | **Odefinierad** |
| 9 | 2023-05-12 12:09 | 456 | - | **Odefinierad** |
| 10 | 2023-05-12 12:02 | 123 | - | **Artikel** |
| | | **4 enheter** | **2 personer**:<br/>Händelser 1, 4, 7, 9, 10 har tagits bort | **2 personer**:<br/>Oautentiserad (komprimerad till en person) |

+++

## Jämförelse av mått

+++ Hur fungerar mätvärden i Customer Journey Analytics sammanslagna datauppsättningar jämfört med liknande värden i Customer Journey Analytics osökta datauppsättningar och med Adobe Analytics?

Vissa mätvärden i Customer Journey Analytics liknar mätvärden i traditionell analys, men andra är olika beroende på vad du jämför. I tabellen nedan jämförs flera vanliga mätvärden:

| **Customer Journey Analytics sammanfogade data** | **Customer Journey Analytics oschade data** | **Adobe Analytics** | **Analysera Ultimate med CDA** |
| ----- | ----- | ----- | ----- |
| **Personer** = Antal distinkta person-ID:n där Stitched ID väljs som person-ID. **Personer** kan vara högre eller lägre än **Unika besökare** i traditionella Adobe Analytics, beroende på utfallet av sammanfogningsprocessen. | **Personer** = Antal distinkta person-ID:n baserat på den kolumn som valts som person-ID. **Personer** i Analytics-källanslutningsdatauppsättningar liknar **Unika besökare** i traditionella Adobe Analytics om `endUserIDs._experience.aaid.id` används som person-ID i Customer Journey Analytics. | **Unika besökare** = Antal distinkta besökar-ID. **Unika besökare** kanske inte är samma som antalet distinkta **ECID** s. | Se [Personer](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html). |
| **Sessioner**: Definieras baserat på sessionsinställningarna i Customer Journey Analytics datavy. Sammanfogningsprocessen kan kombinera enskilda sessioner från flera enheter till en enda session. | **Sessioner**: Definieras baserat på sessionsinställningarna som anges i datavyn för Customer Journey Analytics. | **Besök**: Se [Besök](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html). | **Besök**: Definieras baserat på sessionsinställningarna som anges i den virtuella [CDA-rapportsviten](https://experienceleague.adobe.com/docs/analytics/components/cda/setup.html). |
| **Händelser** = antal rader i sammanslagna data i Customer Journey Analytics. Det här måttet ligger vanligtvis nära **förekomster** i traditionella Adobe Analytics. Observera dock Vanliga frågor och svar ovan om rader med ett tomt Persistent ID. | **Händelser** = antal rader i osydda data i Customer Journey Analytics. Det här måttet ligger vanligtvis nära **förekomster** i traditionella Adobe Analytics. Observera dock att om några händelser har ett tomt person-ID i de icke sammansatta data som finns i Experience Platform datavinje, ingår inte dessa händelser i Customer Journey Analytics. | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). | **Förekomster**: Se [Förekomster](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html). |

Andra mätvärden kan likna i Customer Journey Analytics och Adobe Analytics. Det totala antalet för [anpassade Adobe Analytics-händelser](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html) 1-100 är till exempel jämförbart mellan traditionella Adobe Analytics och Customer Journey Analytics (oavsett om de är sammanfogade eller inte). [Skillnader i funktioner](/help/getting-started/aa-vs-cja/cja-aa.md)), t.ex. borttagning av dubbletter av händelser mellan Customer Journey Analytics och Adobe Analytics, kan orsaka diskrepans mellan de två produkterna.

+++

## Identitetskarta

+++ Kan Customer Journey Analytics använda fält för identitetskarta?

Ja, Customer Journey Analytics kan använda Identity Map-fält för både [fältbaserad](/help/stitching/fbs.md#identitymap) och [diagrambaserad](/help/stitching/gbs.md#identitymap) sammanfogning.

+++

## Växla till diagrambaserad sammanfogning

+++ Måste data kapslas om för att växla från fältbaserad sammanfogning till diagrambaserad sammanfogning?

Data behöver inte kapslas in på nytt i Experience Platform, men de måste konfigureras om i Customer Journey Analytics. Följ dessa steg:

1. Konfigurera den nya diagrambaserade sammanslagna datauppsättningen med hjälp av diagrambaserade sammanfogningar.
1. Skapa en ny temporär anslutning med ett mycket litet tidsfönster med data.
1. Konfigurera den nya diagrambaserade datauppsättningen som en del av den här tillfälliga anslutningen.
1. Kontrollera med den nya tillfälliga anslutningen om den diagrambaserade sammanfogningen fungerar som den ska.
1. Om diagrambaserad sammanfogning fungerar som förväntat, begär du en ytterligare bakgrundsfyllning för den diagrambaserade datauppsättningen och byter sedan ut den fältbaserade datauppsättningen i din ursprungliga anslutning till den nya diagrambaserade datauppsättningen.
1. Ta bort den tillfälliga anslutningen.

+++

## Rapporteringsincidenter

+++ Skulle det bli några avbrott i befintliga rapporter?

Inte om du följer instruktionerna ovan. Annars ber vi Adobe Consulting om ytterligare support.

+++

## Aktivera en datauppsättning för identitetstjänsten

+++ Hur aktiverar man en datauppsättning enbart för identitetstjänsten? 

Du måste se till att en datauppsättning är aktiverad för identitetstjänsten för att kunna använda datauppsättningen i diagrambaserade sammanfogningar.

Du behöver inte ha någon licens för Real-Time Customer Data Platform för att använda diagrambaserad stygn. Diagrambaserad sammanfogning baseras på ett tillgängligt identitetsdiagram och inte på kundprofiler i realtid.

Om du bara vill aktivera en datauppsättning för identitetstjänsten använder du en `POST`-begäran till `/datasets`-slutpunkten som bara använder taggen `unifiedIdentity`. Exempel:

```shell
curl -X POST \
  https://platform.adobe.io/data/foundation/catalog/dataSets \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {ACCESS_TOKEN}' \
  -H 'x-api-key: {API_KEY}' \
  -H 'x-gw-ims-org-id: {ORG_ID}' \
  -H 'x-sandbox-name: {SANDBOX_NAME}' \
  -d '{
    "schemaRef": {
        "id": "https://ns.adobe.com/{TENANT_ID}/schemas/31670881463308a46f7d2cb09762715",
        "contentType": "application/vnd.adobe.xed-full-notext+json; version=1"
    },
    "tags": {
       "unifiedIdentity": ["enabled:true"]
    }
  }'
```

Om taggen `unifiedProfile` används i begäran returneras ett fel, även om du inte är licensierad för kunddataprofilen i realtid.

Mer information finns i [Skapa en datauppsättning aktiverad för profil och identitet](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/enable-for-profile#create-a-dataset-enabled-for-profile-and-identity).

+++ 
