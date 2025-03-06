---
title: Content Analytics-komponenter
description: Information om specifika Content Analytics-komponenter, som dimensioner, (beräknade) mått och härledda fält
solution: Customer Journey Analytics
feature: Content Analytics
role: User
hide: true
hidefromtoc: true
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: cd31712c1dde1fc39f4d0dc81555c19b7690bcab
workflow-type: tm+mt
source-wordcount: '1384'
ht-degree: 1%

---

# Content Analytics-komponenter

>[!WARNING]
>
>Den här artikeln är ett preliminärt inofficiellt utkast till en kommande slutversion och ingår i Content Analytics-dokumentationen. Allt innehåll kan ändras och inga rättsliga skyldigheter kan härledas från den aktuella versionen av den här artikeln.
>

{{release-limited-testing}}

I Content Analytics läggs följande kategorier av komponenter (dimensioner, (beräknade) mått, härledda fält) till i de redan tillgängliga komponenterna i Customer Journey Analytics:

* [Upplev metadata](#experience-metadata)
* [Upplevelseattribut](#experience-attributes)
* [Experience events](#experience-events)
* [Resursmetadata](#asset-metadata)
* [Resursattribut](#asset-attributes)
* [Assets event](#asset-events)
* [Beräknade mått](#calculated-metrics)

I tabellerna nedan indikerar ![AI genererad](/help/assets/icons/AI.svg) ett AI/ML-genererat värde.

## Upplev metadata

| Titel | Beskrivning | Typ | Inställningar |
|---|---|---|---|
| Experience Channel | Kanal för upplevelsen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Upplev Source | Source URL för upplevelsen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Experience ID | Unikt ID för upplevelsen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Experience Name | Namn på upplevelsen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Experience Description | Beskrivning av upplevelsen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Experience Thumbnail URL | URL för upplevelsens miniatyrbild. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Vågrätt procentdjup | Kvantifierbart värde för upplevelsens horisontella procentuella djup. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Upplev vertikalt procentdjup | Kvantifierbart värde för upplevelsens vertikala procentdjup. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Upplev vågrätt pixeldjup | Kvantifierbart värde för upplevelsens horisontella pixeldjup. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Upplev vertikalt pixeldjup | Kvantifierbart värde för upplevelsens vertikala pixeldjup. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |

{style="table-layout:fixed"}



## Upplevelseattribut

| Titel | Beskrivning | Typ | Inställningar |
|---|---|---|---|
| Upplevelseläsbarhetspoäng | ![AI genererade](/help/assets/icons/AI.svg) läsbarhetspoäng för upplevelsen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Upplevelsenyckelord | ![AI genererade](/help/assets/icons/AI.svg) nyckelord för upplevelsen. | Dimension<br>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Experience Persucrap Strategies | ![AI genererade](/help/assets/icons/AI.svg) strategier för upplevelser som finns i den angivna upplevelsen. Möjliga värden är: Social identitet, socialt korrektur, auktoritet, kreativitet, fotnoter i dörren, överkommande reaktion, återkoppling, förankring och jämförelse, sociala effekter, skrämsel och antropomorfism. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Upplev berättelser | ![AI genererade](/help/assets/icons/AI.svg) berättelser som upplevelsen bygger på relevans från en marknadsförares vypunkt. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Upplevelsetoner | ![AI genererade](/help/assets/icons/AI.svg) toner som upplevelsen bygger på relevans från en marknadsförares vypunkt | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Experience Marketing Eures | ![AI genererade](/help/assets/icons/AI.svg) Den känsla som anropades i läsaren när den läste upplevelsen: Akutaktivitet, exklusivitet, Uppmuntrade, Utmaning, Nyhet, Achievement, Lita på, Enkelhet och Fascination. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Experience Emojis Count | ![AI genererade](/help/assets/icons/AI.svg) antal känslolägesikoner för upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |
| Experience Hashtags Count | ![AI genererade](/help/assets/icons/AI.svg) antal hashtaggar för upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |
| Antal upplevelsemeningar | ![AI genererade](/help/assets/icons/AI.svg) antal meningar för upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |
| Upplev hur ordernas proportioner stoppas | ![AI genererade](/help/assets/icons/AI.svg) antal stoppord för upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |
| Antal texttecken | ![AI genererade](/help/assets/icons/AI.svg) antal texttecken för upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |
| Antal Experience Words | ![AI genererade](/help/assets/icons/AI.svg) Antal ord för upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |
| Antal upplevelseord per mening | ![AI genererade](/help/assets/icons/AI.svg) Antal ord per mening för upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |

{style="table-layout:fixed"}


## Experience events

| Titel | Beskrivning | Typ | Inställningar |
|---|---|---|---|
| Upplevelsevyer | Kvantifierbart mått på antalet visningar av upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |
| Upplev klickningar | Kvantifierbart mått på antalet klick i upplevelsen. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |

{style="table-layout:fixed"}


## Resursmetadata

| Titel | Beskrivning | Typ | Inställningar |
|---|---|---|---|
| Resurs-Source | URL för resursens offentliga tillgängliga källa. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Tillgångs-ID | Unik identifierare för tillgången. Resursens binärfil avgör unikheten. Om resursens binärfil ändras ändras inte ID:t. Det unika ID:t kan vara URL:en, men kan också vara en hash som skapats. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resursnamn | Namnet på resursen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resurstyp | Typ av tillgång. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resursminiatyrbilds-URL | URL för resursens miniatyrbild. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resurs, HTML Path | Sammansatt HTML-sökväg för resursen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resurslänk-URL | Närmaste sidankarpunkt för resursen. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resursens visningsbredd | Visningsbredd för innehållsresurs. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resursvisningshöjd | Visningshöjd för innehållsresurs. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resurs - absolut vänster | Innehållsresurs absolut vänster. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Tillgång absolut överkant | Innehållsresurs absolut överkant. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Resurs skapad av | Identifierare för att skapa resurser. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Skapad resurs | Skapad resurs | Dimension | Senaste \| Session |
| Resursen uppdaterades senast av | Identifierare för tillgångsuppdatering. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Senast uppdaterad | Tillgångsuppdateringsdatum. | Dimension | Senaste \| Session |

{style="table-layout:fixed"}


## Resursattribut

| Titel | Beskrivning | Typ | Inställningar |
|---|---|---|---|
| Resursorientering | ![AI genererade](/help/assets/icons/AI.svg)-orientering för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Övergripande ton för resurs | ![AI genererade](/help/assets/icons/AI.svg) Övergripande ton för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Förgrundsfärger för resurs | ![AI genererade](/help/assets/icons/AI.svg) förgrundsfärger för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Bakgrundsfärg för resurs | ![AI genererade](/help/assets/icons/AI.svg) bakgrundsfärger för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Resurstaggar | ![AI genererade ](/help/assets/icons/AI.svg) taggar för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Resursscener | ![AI genererade](/help/assets/icons/AI.svg) scener för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Resursobjekt | ![AI genererade](/help/assets/icons/AI.svg) objekt för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Resursfotostilar | ![AI genererade](/help/assets/icons/AI.svg) fotostilar för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Typ av resursbild | ![AI genererade](/help/assets/icons/AI.svg) resursens bildtyp. Möjliga värden är: fotografi, skiss, målning, digital_tecknad film, infographics, graphic_design, collage och software_screenshot. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Placering av kameran | ![AI genererade](/help/assets/icons/AI.svg) kamerapunkter för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Kameranärhet för tillgångar | ![AI genererade](/help/assets/icons/AI.svg) kameraproximiteter för resursen. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Kategorier för tillgångsanvändare | ![AI genererade](/help/assets/icons/AI.svg) personkategorier för resursen. Möjliga värden är: person, man, kvinna, social grupp, folkgrupp, människor, pojke, flicka och grabb. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Resursens visuella innehållstäthet | ![AI genererade](/help/assets/icons/AI.svg) visuell innehållstäthet för resursen. Möjliga värden är: låg, medel eller hög. Låg innehållstäthet innebär en liten mängd information per ytenhet i bilden. | Dimension | Visa \| Inget värde<br/>Senaste \| Session |
| Spridning av visuell uppmärksamhet för resurs | ![AI genererade](/help/assets/icons/AI.svg) spridning av mediets visuella uppmärksamhet. Möjliga värden är: låg, medel eller hög. Attention spread avser den grad i vilken betraktarens uppmärksamhet delas mellan olika delar av en bild. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Ljusvillkor för resurs | ![AI genererade](/help/assets/icons/AI.svg) ljusförhållanden för resursen. Möjliga värden är: gyllene timmen, blå timmen, middag, övercast, night, high key, low key, day lighting, incandescent, fluorescent, colorful och studio. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |
| Inställning för resurskamera | ![AI genererade](/help/assets/icons/AI.svg) kamerainställning för resursen. Möjliga värden är: snabb slutarhastighet, lång exponering. bokeh blur, rörelseoskärpa, tilt-shift-oskärpa, flash, vidvinkel, svart och vitt, surrealistisk, dubbel exponering, makro och normalläge. | Dimension<br/>Härlett fält | Visa \| Inget värde<br/>Senaste \| Session |

{style="table-layout:fixed"}


## Resurshändelser

| Titel | Beskrivning | Typ | Inställningar |
|---|---|---|---|
| Resursvyer | Kvantifierbart mått för antalet visningar av tillgången. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |
| Klickningar på resurs | Kvantifierbart mått för antalet klick i tillgången. | Mått | Räkna värden<br/>Decimal \| Decimaler: 0 |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## Beräknade mått

| Titel | Beskrivning | Typ | Inställningar |
|---|---|---|---|
| Klickfrekvens för resurs - styrfrekvens | Resursklickningar / Resursvyer | Beräknat mått | |
| upplevelseklickfrekvens | Upplevelseklickningar/upplevelsevyer | Beräknat mått | |

{style="table-layout:fixed"}
