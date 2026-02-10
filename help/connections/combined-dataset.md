---
title: Kombinerade händelsedatamängder
description: Lär dig hur Customer Journey Analytics skapar en anslutning genom att kombinera datauppsättningar.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 3%

---


# Kombinerade händelsedatamängder

När du skapar en anslutning kombinerar Customer Journey Analytics alla händelsedatamängder till en enda datauppsättning. Den här kombinerade händelsedatamängden är vad Customer Journey Analytics använder för rapportering (tillsammans med profil- och uppslagsdatauppsättningar). När du inkluderar flera händelsedatamängder i en anslutning:

* Data för fält i datauppsättningar som baseras på **samma schemasökväg** sammanfogas till en enda kolumn i den kombinerade datauppsättningen.
* Kolumnen för person-ID, som anges för varje datauppsättning, sammanfogas till en enda kolumn i den kombinerade datauppsättningen, **oavsett namn**. Denna kolumn är grunden för att identifiera unika personer i Customer Journey Analytics.
* Rader bearbetas baserat på tidsstämpel.
* Händelser löses ned till millisekundnivån.

## Exempel

Titta på följande exempel. Du har två händelsedatamängder, där vart och ett har olika fält som innehåller olika data.

>[!NOTE]
>
>Adobe Experience Platform lagrar vanligtvis en tidsstämpel i UNIX® millisekunder. I det här exemplet används datum och tid för läsbarhet.

| example_id | tidsstämpel | string_color | string_Animal | metrisk_a |
| --- | --- | --- | --- | ---: |
| user_310 | 1 Jan 7:02 AM | Röd | Fox | |
| user_310 | 1 Jan 7:04 AM | | | 2 |
| user_310 | 1 Jan 7:08 AM | Blå | | 3 |
| user_847 | 2 Jan 12:31 PM | | Sköldpadda | 4 |
| user_847 | 2 Jan 12:44 PM | | | 2 |

| different_id | tidsstämpel | string_color | string_shape | metrisk_b |
| --- | --- | --- | --- | ---: |
| user_847 | 2 Jan 12:26 PM | Gul | Cirkel | 8,5 |
| user_847 | 2 jan 1:01 PM | Röd | | |
| alternateid_656 | 2 Jan 8:58 PM | Röd | Fyrkant | 4,2 |
| alternateid_656 | 2 Jan 9:03 PM | | Triangel | 3,1 |

När du skapar en anslutning med dessa två händelsedatamängder och har identifierat

* `example_id` som person-ID för den första datauppsättningen, och
* `different_id` som person-ID för den andra datauppsättningen,

följande kombinerade datauppsättning används för rapportering.

| id | tidsstämpel | string_color | string_Animal | string_shape | metrisk_a | metrisk_b |
| --- | --- | --- | --- | --- | ---: | ---: |
| user_310 | 1 Jan 7:02 AM | Röd | Fox | | | |
| user_310 | 1 Jan 7:04 AM | | | | 2 | |
| user_310 | 1 Jan 7:08 AM | Blå | | | 3 | |
| user_847 | 2 Jan 12:26 PM | Gul | | Cirkel | | 8,5 |
| user_847 | 2 Jan 12:31 PM | | Sköldpadda | | 4 | |
| user_847 | 2 Jan 12:44 PM | | | | 2 | |
| user_847 | 2 jan 1:01 PM | Röd | | | | |
| alternateid_656 | 2 Jan 8:58 PM | Röd | | Fyrkant | | 4,2 |
| alternateid_656 | 2 Jan 9:03 PM | | | Triangel | | 3,1 |

Tänk på det här scenariot för att illustrera vikten av schemasökvägar. I den första datauppsättningen baseras `string_color` på schemasökvägen `_experience.whatever.string_color` och i den andra datauppsättningen på schemasökvägen `_experience.somethingelse.string_color`. I det här scenariot sammanfogas data **inte** till en kolumn i den resulterande kombinerade datauppsättningen. I stället är resultatet två `string_color`-kolumner i den kombinerade datauppsättningen:

| id | tidsstämpel | _upplevelse.<br/>vad som helst.<br/>strängfärg | _upplevelse.<br/>något annat.<br/>strängfärg | string_Animal | string_shape | metrisk_a | metrisk_b |
|---|---|---|---|---|---|---:|---:|
| user_310 | 1 Jan 7:02 AM | Röd | | Fox | | | |
| user_310 | 1 Jan 7:04 AM | | | | | 2 | |
| user_310 | 1 Jan 7:08 AM | Blå | | | | 3 | |
| user_847 | 2 Jan 12:26 PM | | Gul | | Cirkel | | 8,5 |
| user_847 | 2 Jan 12:31 PM | | | Sköldpadda |  | 4 | |
| user_847 | 2 Jan 12:44 PM | | | | | 2 | |
| user_847 | 2 jan 1:01 PM | | Röd | | | | |
| alternateid_656 | 2 Jan 8:58 PM | | Röd | | Fyrkant | | 4,2 |
| alternateid_656 | 2 Jan 9:03 PM | | | | Triangel | | 3,1 |

Den här kombinerade händelsedatamängden används för rapportering. Det spelar ingen roll vilken datauppsättning en rad kommer från. Customer Journey Analytics hanterar alla data som om de fanns i samma datauppsättning. Om ett matchande person-ID visas i båda datauppsättningarna betraktas de som samma unika person. Om ett matchande person-ID visas i båda datauppsättningarna med en tidsstämpel inom 30 minuter betraktas de som en del av samma session. Fält med identiska schemasökvägar sammanfogas.

Detta koncept gäller också attribuering. Det spelar ingen roll vilken datamängd en rad kommer från. Attribution fungerar exakt som om alla händelser kom från en enda datamängd. Använda tabellerna ovan som exempel:

Om din anslutning bara innehöll den första tabellen och inte den andra skulle följande visas om du drog en rapport med måtten `string_color` och `metric_a` med hjälp av den senaste beröringsattribueringen:

| string_color | metrisk_a |
| --- | ---: |
| Ospecificerad | 6 |
| Blå | 3 |
| Röd | 2 |

Om du däremot inkluderade båda tabellerna i anslutningen, ändras attribueringen eftersom `user_847` finns i båda datauppsättningarna. En rad från den andra datauppsättningsattributen `metric_a` till Gul, där de tidigare var ospecificerade:

| string_color | metrisk_a |
| --- | ---: |
| Gul | 6 |
| Blå | 3 |
| Röd | 2 |

>[!NOTE]
>
>Om ett sammanfogat fält är en söknyckel för en händelsedatamängd i anslutningen, kommer den associerade sökdatamängden att förbättra **alla** värden för det fältet. Det spelar ingen roll vilken händelsedatamängd en rad kommer från, eftersom sökrelationen är associerad med den delade schemasökvägen.

## Flerkanalsanalys

Nästa nivå med att kombinera datauppsättningar är flerkanalsanalys, där datauppsättningar från olika kanaler kombineras, baserat på en gemensam identifierare (person-ID). Flerkanalsanalys kan dra nytta av sammanfogningsfunktioner som gör att du kan ändra inmatningen av en datauppsättnings person-ID så att datauppsättningen uppdateras på rätt sätt för att möjliggöra en sömlös kombination av flera datauppsättningar. Stitching undersöker användardata från både autentiserade och oautentiserade sessioner för att generera ett sammanfogat ID.

Med flerkanalsanalys kan ni besvara frågor som:

* Hur många börjar sin upplevelse i en kanal och avslutar den i en annan?
* Hur många interagerar med mitt varumärke? Hur många och vilka typer av enheter använder de? Hur överlappar de?
* Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra uppgiften? Kommer kampanjklickningar som landar på en enhet att leda till konvertering någon annanstans?
* Hur påverkar min förståelse för kampanjens effektivitet om jag tänker på resor mellan olika enheter? Hur förändras min funnel-analys?
* Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de?
* Hur skiljer sig beteendet hos användare med flera enheter från dem som har en enda enhet?


Mer information om flerkanalsanalys finns i det specifika användningsexemplet:

* [Flerkanalsanalys](../use-cases/cross-channel/cross-channel.md)

Mer information om hur du syser ut finns på:

* [Översikt över titlar](/help/stitching/overview.md)
* [Vanliga frågor](/help/stitching/faq.md)

