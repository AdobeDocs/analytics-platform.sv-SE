---
title: Kombinerade händelsedatamängder
description: Lär dig hur Customer Journey Analytics skapar en anslutning genom att kombinera datauppsättningar.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 1%

---


# Kombinerade händelsedatamängder

När du skapar en anslutning kombinerar Customer Journey Analytics alla scheman och datauppsättningar i en enda datauppsättning. Detta &#39;kombinerade händelsedatamängd&#39; är vad Customer Journey Analytics använder för rapportering. När du inkluderar flera scheman eller datauppsättningar i en anslutning:

* Scheman kombineras. Duplicerade schemafält sammanfogas.
* Kolumnen &quot;Person-ID&quot; i varje datauppsättning sammanfogas till en enda kolumn, oavsett namn. Denna kolumn är grunden för att identifiera unika personer i Customer Journey Analytics.
* Rader bearbetas baserat på tidsstämpel.
* Händelser löses ned till millisekundnivån.

## Exempel

Titta på följande exempel. Du har två händelsedatamängder, där vart och ett har olika fält som innehåller olika data.

>[!NOTE]
>
>Adobe Experience Platform lagrar vanligtvis tidsstämplar i Unix millisekunder. I det här exemplet används datum och tid för läsbarhet.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

När du skapar en anslutning med dessa två händelsedatamängder används följande tabell för rapportering.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

Den här kombinerade händelsedatamängden används för rapportering. Det spelar ingen roll vilken datauppsättning en rad kommer från. Customer Journey Analytics hanterar alla data som om de fanns i samma datauppsättning. Om ett matchande person-ID visas i båda datauppsättningarna betraktas de som samma unika person. Om ett matchande person-ID visas i båda datauppsättningarna med en tidsstämpel inom 30 minuter betraktas de som en del av samma session.

Detta koncept gäller också attribuering. Det spelar ingen roll vilken datauppsättning en rad kommer från. attribuering fungerar precis som om alla händelser kom från en enda datamängd. Använda tabellerna ovan som exempel:

Om anslutningen bara innehöll den första tabellen och inte den andra, drar du en rapport med hjälp av `string_color` dimension och `metric_a` mätvärden som använder den senaste beröringsattribueringen skulle visa:

| string_color | metrisk_a |
| --- | --- |
| Ospecificerad | 6 |
| Blå | 3 |
| Röd | 2 |

Om du däremot inkluderar båda tabellerna i anslutningen ändras attribueringen sedan `user_847` finns i båda datauppsättningarna. En rad från de andra datauppsättningsattributen `metric_a` till &#39;Gul&#39; där de tidigare inte var angivna:

| string_color | metrisk_a |
| --- | --- |
| Gul | 6 |
| Blå | 3 |
| Röd | 2 |

## Flerkanalsanalys

Nästa nivå med att kombinera datauppsättningar är flerkanalsanalys, där datauppsättningar från olika kanaler kombineras, baserat på en gemensam identifierare (person-ID). Flerkanalsanalys kan dra nytta av sammanfogningsfunktioner som gör att du kan ändra inmatningen av en datauppsättnings person-ID så att datauppsättningen uppdateras på rätt sätt för att möjliggöra en sömlös kombination av flera datauppsättningar. Stitching undersöker användardata från både autentiserade och oautentiserade sessioner för att generera ett sammanfogat ID.

Med flerkanalsanalys kan ni besvara frågor som:

* Hur många börjar sin upplevelse i en kanal och avslutar den i en annan?
* Hur många interagerar med mitt varumärke? Hur många och vilka typer av enheter använder de? Hur överlappar de?
* Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra uppgiften? Kommer kampanjklickningar som landar på en enhet att leda till konvertering någon annanstans?
* Hur påverkar min förståelse för kampanjens effektivitet om jag tänker på resor mellan olika enheter? Hur förändras min kanalanalys?
* Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de?
* Hur skiljer sig beteendet hos användare med flera enheter från dem som har en enda enhet?


Mer information om flerkanalsanalys finns i det specifika användningsfallet:

* [Flerkanalsanalys](../use-cases/cross-channel/cross-channel.md)

Mer information om hur du sammanställer diskussioner finns på:

* [Översikt över titlar](/help/stitching/overview.md)
* [Hur stygn fungerar](../stitching/explained.md)
* [Vanliga frågor](/help/stitching/faq.md)

