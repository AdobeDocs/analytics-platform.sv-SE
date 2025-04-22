---
title: Content Analytics-komponenter
description: Information om specifika Content Analytics-komponenter, som dimensioner, (beräknade) mått och härledda fält
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 1%

---

# Content Analytics-komponenter

Content Analytics lägger till följande kategorier av komponenter (dimensioner, (beräknade) mått, härledda fält) i de redan tillgängliga komponenterna i Customer Journey Analytics:

* [Upplev metadata](#experience-metadata)
* [Upplevelseattribut](#experience-attributes)
* [Experience events](#experience-events)
* [Resursmetadata](#asset-metadata)
* [Resursattribut](#asset-attributes)
* [Assets event](#asset-events)
* [Beräknade mått](#calculated-metrics)

I tabellerna nedan indikerar ![AI genererad](/help/assets/icons/AI.svg) ett AI/ML-genererat attribut/värdepar.

## Upplev metadata

| Titel | Beskrivning | Typ |
|---|---|---|
| Experience Channel | Kanal för upplevelsen. | Dimension |
| Experience ID | Unikt ID för upplevelsen. | Dimension |
| Experience Thumbnail URL | URL för upplevelsens miniatyrbild. | Dimension |
| Vågrätt procentdjup | Kvantifierbart värde för upplevelsens horisontella procentuella djup. | Dimension<br/>Härlett fält |
| Upplev vertikalt procentdjup | Kvantifierbart värde för upplevelsens vertikala procentdjup. | Dimension<br/>Härlett fält |

{style="table-layout:fixed"}



## Upplevelseattribut

| Titel | Beskrivning | Typ |
|---|---|---|
| Experience Attributes | ![AI genererade](/help/assets/icons/AI.svg) En fullständig lista över alla Experience Attribute-namn och -värden | Dimension<br>Härlett fält |
| Upplevelseläsbarhetspoäng | ![AI genererade](/help/assets/icons/AI.svg) läsbarhetspoäng för upplevelsen | Dimension |
| Upplevelsenyckelord | ![AI genererade](/help/assets/icons/AI.svg) nyckelord för upplevelsen. | Dimension<br>Härlett fält |
| Experience Persucrap Strategies | ![AI genererade](/help/assets/icons/AI.svg) strategier för upplevelser som finns i den angivna upplevelsen. Möjliga värden är: Social identitet, socialt korrektur, auktoritet, kreativitet, fotnoter i dörren, överkommande reaktion, återkoppling, förankring och jämförelse, sociala effekter, skrämsel och antropomorfism. | Dimension<br/>Härlett fält |
| Upplev berättelser | ![AI genererade](/help/assets/icons/AI.svg) berättelser som upplevelsen bygger på relevans från en marknadsförares vypunkt. | Dimension<br/>Härlett fält |
| Upplevelsetoner | ![AI genererade](/help/assets/icons/AI.svg) toner som upplevelsen bygger på relevans från en marknadsförares vypunkt | Dimension<br/>Härlett fält |
| Experience Marketing Eures | ![AI genererade](/help/assets/icons/AI.svg) Den känsla som anropades i läsaren när texten som används som en del av upplevelsen lästes: trängsel, exklusivitet, uppmuntran, utmaning, nyfikenhet, förstärkning, förtroende, enkelhet och fascination. | Dimension<br/>Härlett fält |
| Experience Emojis Count | ![AI genererade](/help/assets/icons/AI.svg) antal känslolägesikoner för upplevelsen. | Mått |
| Experience Hashtags Count | ![AI genererade](/help/assets/icons/AI.svg) antal hashtaggar för upplevelsen. | Mått |
| Antal upplevelsemeningar | ![AI genererade](/help/assets/icons/AI.svg) antal meningar för upplevelsen. | Mått |
| Upplev hur ordernas proportioner stoppas | ![AI genererade](/help/assets/icons/AI.svg) antal stoppord för upplevelsen. | Mått |
| Antal texttecken | ![AI genererade](/help/assets/icons/AI.svg) antal texttecken för upplevelsen. | Mått |
| Antal Experience Words | ![AI genererade](/help/assets/icons/AI.svg) Antal ord för upplevelsen. | Mått |
| Antal upplevelseord per mening | ![AI genererade](/help/assets/icons/AI.svg) Antal ord per mening för upplevelsen. | Mått |

{style="table-layout:fixed"}


## Experience events

| Titel | Beskrivning | Typ |
|---|---|---|
| Experience Views | Kvantifierbart mått på antalet visningar av upplevelsen. | Mått |
| Experience Clicks | Kvantifierbart mått på antalet klick i upplevelsen. | Mått |

{style="table-layout:fixed"}


## Resursmetadata

| Titel | Beskrivning | Typ |
|---|---|---|
| Tillgångs-ID | Unik identifierare för tillgången. Resursens binärfil avgör unikheten. Om resursens binärfil ändras ändras inte ID:t. Det unika ID:t kan vara URL:en, men kan också vara en hash som skapats. | Dimension |
| Resurs, HTML Path | Sammansatt HTML-sökväg för resursen. | Dimension |
| Resurslänk-URL | Närmaste sidankarpunkt för resursen. | Dimension |
| Resursens visningsbredd | Visningsbredd för innehållsresurs. | Dimension |
| Resursvisningshöjd | Visningshöjd för innehållsresurs. | Dimension |
| Resurs - absolut vänster | Innehållsresurs absolut vänster. | Dimension |
| Tillgång absolut överkant | Innehållsresurs absolut överkant. | Dimension |

{style="table-layout:fixed"}


## Resursattribut

| Titel | Beskrivning | Typ |
|---|---|---|
| Resursattribut | ![AI genererade](/help/assets/icons/AI.svg) En fullständig lista över alla resursattributnamn och -värden | Dimension<br>Härlett fält |
| Resursorientering | ![AI genererade](/help/assets/icons/AI.svg)-orientering för resursen. | Dimension<br/>Härlett fält |
| Övergripande ton för resurs | ![AI genererade](/help/assets/icons/AI.svg) Övergripande ton för resursen. | Dimension<br/>Härlett fält |
| Förgrundsfärger för resurs | ![AI genererade](/help/assets/icons/AI.svg) förgrundsfärger för resursen. | Dimension<br/>Härlett fält |
| Bakgrundsfärger för resurs | ![AI genererade](/help/assets/icons/AI.svg) bakgrundsfärger för resursen. | Dimension<br/>Härlett fält |
| Resurstaggar | ![AI genererade ](/help/assets/icons/AI.svg) taggar för resursen. | Dimension<br/>Härlett fält |
| Resursscener | ![AI genererade](/help/assets/icons/AI.svg) scener för resursen. | Dimension<br/>Härlett fält |
| Resursobjekt | ![AI genererade](/help/assets/icons/AI.svg) objekt för resursen. | Dimension<br/>Härlett fält |
| Resursfotostilar | ![AI genererade](/help/assets/icons/AI.svg) fotostilar för resursen. | Dimension<br/>Härlett fält |
| Typ av resursbild | ![AI genererade](/help/assets/icons/AI.svg) resursens bildtyp. Möjliga värden är: fotografi, skiss, målning, digital_tecknad film, infographics, graphic_design, collage och software_screenshot. | Dimension<br/>Härlett fält |
| Placering av kameran | ![AI genererade](/help/assets/icons/AI.svg) kamerapunkter för resursen. | Dimension<br/>Härlett fält |
| Kameranärhet för tillgångar | ![AI genererade](/help/assets/icons/AI.svg) kameraproximiteter för resursen. | Dimension<br/>Härlett fält |
| Kategorier för tillgångsanvändare | ![AI genererade](/help/assets/icons/AI.svg) personkategorier för resursen. Möjliga värden är: person, man, kvinna, social grupp, folkgrupp, människor, pojke, flicka och grabb. | Dimension<br/>Härlett fält |
| Resursens visuella innehållstäthet | ![AI genererade](/help/assets/icons/AI.svg) visuell innehållstäthet för resursen. Möjliga värden är: låg, medel eller hög. Låg innehållstäthet innebär en liten mängd information per ytenhet i bilden. | Dimension |
| Spridning av visuell uppmärksamhet för resurs | ![AI genererade](/help/assets/icons/AI.svg) spridning av mediets visuella uppmärksamhet. Möjliga värden är: låg, medel eller hög. Attention spread avser den grad i vilken betraktarens uppmärksamhet delas mellan olika delar av en bild. | Dimension<br/>Härlett fält |
| Ljusvillkor för resurs | ![AI genererade](/help/assets/icons/AI.svg) ljusförhållanden för resursen. Möjliga värden är: gyllene timmen, blå timmen, middag, övercast, night, high key, low key, day lighting, incandescent, fluorescent, colorful och studio. | Dimension<br/>Härlett fält |
| Inställning för resurskamera | ![AI genererade](/help/assets/icons/AI.svg) kamerainställning för resursen. Möjliga värden är: snabb slutarhastighet, lång exponering. bokeh blur, rörelseoskärpa, tilt-shift-oskärpa, flash, vidvinkel, svart och vitt, surrealistisk, dubbel exponering, makro och normalläge. | Dimension<br/>Härlett fält |

{style="table-layout:fixed"}


## Resurshändelser

| Titel | Beskrivning | Typ |
|---|---|---|
| Resursvyer | Kvantifierbart mått för antalet visningar av tillgången. | Mått |
| Resursklickningar | Kvantifierbart mått för antalet klick i tillgången. | Mått |

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

| Titel | Beskrivning | Typ |
|---|---|---|
| Klickfrekvens för resurs - styrfrekvens | Resursklickningar/resursvyer | Beräknat mått |
| upplevelseklickfrekvens | Experience Clicks/Experience Views | Beräknat mått |

{style="table-layout:fixed"}

