---
title: Sammanfattningsdata
description: Lär dig mer om detaljer och information om hur du använder och konfigurerar sammanfattningsdata i en datavy.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
exl-id: 417443ae-a1ab-483b-a8fd-cff5ee8b6263
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 2%

---

# Sammanfattningsdata

Sammanfattningsdata är tidsseriedata som inte är knutna till ett personligt ID. Sammanfattningsdata representerar aggregerade data på en annan aggregeringsnivå, till exempel kampanjer. Du kan använda dessa data i Customer Journey Analytics för att stödja olika användningsfall. Till exempel data som innehåller ett datum och ett enda måttvärde, eller data som innehåller flera dimensioner och mätvärden.

Dessa sammanfattande data kan sedan användas för att presentera högnivåindikatorer eller utföra analyser. Exempel på sammanfattningsdata kan vara annonsvisningar, öppning av e-post, annonsutgifter, kostnad för sålda varor, S&amp;P-index med mera. Du kan också använda sammanfattningsdata för att överföra mål eller mål varje timme eller dag.

>[!NOTE]
>
>Sammanfattningsdata är tidsseriedata från en sammanfattningsdatauppsättning. Den sammanfattande datauppsättningen baseras på ett schema som använder klassen XDM Summary Metrics som basklass.
>Endast timbaserade eller dagliga tidsseriedata stöds.

>[!TIP]
>
>Du kan konfigurera en anslutning, datavy och senare rapportera om sammanfattningsdata för **endast**. Du behöver inte ha ytterligare händelse-, profil- eller sökdata som en del av konfigurationen.


## Exempel

Ett exempel på hur sammanfattningsdata används är att kombinera sammanfattade kampanjdata med klickströmsdata på webbplatsen för rapportering.

### Sammanfattningsdata

Dina sammanfattningsdata innehåller följande data för annonskampanjer.

| Kampanjkod | Impressions | Kostnad |
|---|---:|---:|
| abc123 | 1 250 | 1 500 dollar |
| def456 | 775 | 650 dollar |
| ghi789 | 500 | 500 dollar |


### Händelsedata

Dina klickströmsdata på platsen innehåller följande händelser.

| Spårningskod | Klickningar | Intäkter |
|---|---:|---:|
| abc123 | 1 250 | 7 200 dollar |
| def456 | 775 | 1 250 dollar |
| ghi789 | 500 | 750 dollar |

### Kombinerade data

Som förklaras i [Kombinerad händelsedatamängd](/help/connections/combined-dataset.md) skapar Customer Journey Analytics en övergripande kombinerad händelsedatamängd när du definierar en anslutning. När du konfigurerar datavyn för dimensioner som härstammar från en sammanfattningsdatauppsättning finns alternativ för att gruppera och dölja dimensioner som förberedelse för rapportering i Workspace. Sammanfattningsdata kombineras med händelsedata, särskilt för sammanfattningsdata, baserat på konfigurationen för [sammanfattningsdatagruppen](component-settings/summary-data-group.md).

| Spårningskod | Kampanjkod | Impressions | Kostnad | Klickningar | Intäkter |
|---|---|--:|--:|--:|--:|
| abc123 | abc123 | 1 250 | 1 500 dollar | 1 250 | 7 200 dollar |
| def456 | def123 | 775 | 650 dollar | 775 | 1 250 dollar |
| ghi789 | ghi789 | 500 | 500 dollar | 500 | 750 dollar |



### Rapportering

Genom att kombinera sammanfattade händelsedata och klickströmsdata på plats kan du rapportera i Workspace om avkastningen på annonskostnaderna.

| Spårningskod | Impressions | Kostnad | Klickningar | Intäkter | ROAS |
|---|--:|--:|--:|--:|:--|
| abc123 | 1 250 | 1 500 dollar | 1 250 | 7 200 dollar | 4,80 |
| def456 | 775 | 650 dollar | 775 | 1 250 dollar | 1,92 |
| ghi789 | 500 | 500 dollar | 500 | 750 dollar | 1,50 |


### Sökdata

Om du vill rapportera med en dimension som definieras i en extra uppslagsdatauppsättning (till exempel kampanjnamn) måste du följa dessa ytterligare steg:

1. Skapa ett nytt härlett fält som använder funktionen [Sök](/help/data-views/derived-fields/derived-fields.md#lookup) för att söka efter kampanjnamnet från uppslagsdatauppsättningen. I definitionen av funktionen [Sök](/help/data-views/derived-fields/derived-fields.md#lookup) använder du matchningen mellan kampanjkoden och spårningskoden för att söka efter kampanjnamnet.
1. Lägg till det nya härledda fältet som en dimensionskomponent i datavyn.
1. Konfigurera kampanjnamnets dimensionskomponent (från uppslagsdatauppsättningen) så att den har en sammanfattande datagrupp med det nyligen skapade härledda fältet.

I [Infoga och rapportera om sammanfattningsdata](/help/use-cases/data-views/summary-data.md) finns en detaljerad artikel om hur du använder, rapporterar om och analyserar sammanfattningsdata i Customer Journey Analytics.


## Förutsättningar

För att sammanfattningsdata ska kunna användas korrekt i rapporter och analyser måste du uppfylla ett antal krav. I följande avsnitt beskrivs dessa krav.

### Kornighet och tidszon

När du konfigurerar datauppsättningen som innehåller sammanfattningsdata i Customer Journey Analytics, märker du att granulariteten automatiskt kommer från dessa data. Markeringarna för **[!UICONTROL Timestamp]** och **[!UICONTROL Timezone]**-listrutan är inaktiverade eftersom båda är härledda från schemadefinitionen.

#### Kornighet

Du kan inte blanda och matcha timgranulariteten och daglig granularitet för dina sammanfattningsdata i en datauppsättning (eller med olika datauppsättningar) med hjälp av ett sammanfattningsdataschema. Om du t.ex. har dagliga och timmässiga detaljerade sammanfattningsdata för kampanjdata behöver du två scheman: en för dagen och en för timsammanfattningsdata. Överför sedan relevanta detaljerade data till datauppsättningar som är kopplade till rätt schema (till exempel överföra timdata till en datauppsättning som är kopplad till timsammanfattningsdataschemat).

#### Tidszon

Tidszonen för dina sammanfattningsdata definieras på sammanfattningsschemanivå i Experience Platform. Tidszonen gäller endast för timdetaljerade data.

- För daglig granularitet antar Experience Platform UTC, såvida inte en tidszonsförskjutning inkluderas i tidsstämpeln. När du lägger till sammanfattningsdatauppsättningen som innehåller dagliga sammanfattningsdata, ignorerar Customer Journey Analytics den tidszonsdefinition som angetts i schemat och respekterar den dag som är associerad med tidsstämpeln från data i datauppsättningen.
- För timgranularitet respekterar Customer Journey Analytics den tidszon som konfigurerats i schemat för sammanfattningsdata i Experience Platform när tidsstämpeln tolkas. Tabellen nedan innehåller några exempel på denna tolkning.

  | Tidsstämpel <br/> - källdata | Schema för tidszon<br/> | Tidsstämpel<br/>Upplevelse<br/>Plattform | Tidszon<br/>, data<br/>vy | Tidsstämpel<br/>kund<br/>resa<br>Analys |
  |---|---|---|:---|---|
  | 2024-07-29T01:00:00 | *standard-GMT* | 2024-07-29T01:00:00 | GMT | 2024-07-29T01:00:00 |
  | 2024-07-29T01:00:00 | *standard-GMT* | 2024-07-29T01:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | *standard-GMT* | 2024-07-30T06:00:00 | GMT | 2024-07-30T06:00:00 |
  | 2024-07-30T01:00:00-05:00 | *standard-GMT* | 2024-07-30T06:00:00 | PST | 2024-07-29T23:00:00 |
  | 2024-08-02 | *standard-GMT* | 2024-08-02T00:00:00 | IST | 2024-08-02T05:00:00 |
  | 2024-07-29T01:00:00 | `America/`<br/>`Los_Angeles` | 2024-07-28T18:00:00 | PST | 2024-07-28T18:00:00 |
  | 2024-07-30T01:00:00-05:00 | `Australia/`<br/>`Sydney` | 2024-07-30T17:00:00 | CET | 2024-07-30T08:00:00 |

  För tidszoner med 30 minuters förskjutning (till exempel IST, Indien, standardtid), tas 30 minuters förskjutningen bort vid rapportering av sammanfattningsdata. Till exempel: 12:30 rapporteras som 12:00.


För att vara säker på att rätt tidszon används för dina timgranulerade sammanfattningsdata måste du se till att schemat som används för sammanfattningsdata har rätt tidszon konfigurerad.

Om du vill konfigurera granularitet och tidszon för schemat med sammanfattningsdata måste du använda följande API-anrop eftersom det inte finns något motsvarande användargränssnitt tillgängligt.

```shell
curl -X POST \
https://platform.adobe.io/data/foundation/schemaregistry/tenant/descriptors \
 -H "Authorization: Bearer {$ACCESS_TOKEN}" \
 -H 'Content-Type: application/json' \
 -H 'x-api-key: {$API_KEY}' \
 -H 'x-gw-ims-org-id: {$ORG_ID}' \
 -H 'x-sandbox-name: {$SANDBOX_NAME}' \
 -d '{  
    "@type": "xdm:descriptorTimeSeriesGranularity",
    "xdm:sourceSchema": "{$SCHEMA_ID}",
    "xdm:sourceVersion": 1,
    "xdm:granularity": "{$GRANULARITY}",
    "xdm:ianaTimezone": "{$TIMEZONE}" 
 }'
```

| Variabel | Värde |
|---|---|
| `$ACCESS_TOKEN`<br/>`$API_KEY`<br/>`$ORG_ID`<br/>`$SANDBOX_NAME` | Mer information om hur du anger värden för dessa variabler finns i [Autentisera och få åtkomst till Experience Platform API:er](https://experienceleague.adobe.com/sv/docs/experience-platform/landing/platform-apis/api-authentication). |
| `$SCHEMA_ID` | Du kan hitta ID:t för ditt schema i Experience Platform-gränssnittet. Välj ditt sammanfattningsschema i listan med scheman och sök efter **[!UICONTROL API Usage]** > **[!UICONTROL Schema ID]** i den högra panelen. Använd det ID:t som värde. |
| `$GRANULARITY` | Ange `hour` eller `day` som värde. |
| `$TIMEZONE` | Ange rätt värde för tidszonsidentifierare från TZ-identifierarkolumnen i [List of tz database time zone](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones). Till exempel: `America/Los_Angeles`. |

## Komponentinställningar

Kontrollera att komponentinställningarna för en sammanfattningsdatagrupp är desamma. Mer information finns i [Komponentinställningar för sammanfattningsdatagrupp](component-settings/summary-data-group.md#same-component-settings).

>[!MORELIKETHIS]
>
>- I artikeln [Använd sammanfattningsdata](/help/use-cases/data-views/summary-data.md) finns ett detaljerat exempel på hur du använder och rapporterar om sammanfattningsdata.
>- Blogg: [Hur sammanfattningsdata förbättrar Adobe Customer Journey Analytics-datauppsättningar](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-summary-data-enhances-adobe-customer-journey-analytics/ba-p/704635?profile.language=sv)

