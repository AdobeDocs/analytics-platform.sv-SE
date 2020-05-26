---
title: Kombinerade datauppsättningar
description: Lär dig hur CJA skapar en anslutning genom att kombinera datauppsättningar.
translation-type: tm+mt
source-git-commit: fa354af31237c4963ba0affa89652bfdeae45ea0
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---


# Kombinerade datauppsättningar

När du skapar en anslutning kombinerar CJA alla scheman och datauppsättningar i en enda datauppsättning. Den här kombinerade datauppsättningen är vad CJA använder för rapportering. När du inkluderar flera scheman eller datauppsättningar i en anslutning:

* Scheman kombineras. Duplicerade schemafält sammanfogas.
* Kolumnen &quot;Person-ID&quot; i varje datauppsättning sammanfogas till en enda kolumn, oavsett namn. Den här kolumnen är grunden för att identifiera unika besökare i CJA.
* Rader bearbetas baserat på tidsstämpel.

## Exempel

Titta på följande exempel. Du har två datauppsättningar, där vart och ett har olika fält som innehåller olika data.

>[!NOTE] Adobe Experience Platform lagrar vanligtvis tidsstämplar i Unix millisekunder. I det här exemplet används datum och tid för läsbarhet.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |
| `user_310` | `1 Jan 7:04 AM` |  |  | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  | `3` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` |  |  | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  | `Triangle` | `3.1` |

När du skapar en anslutning med dessa två datauppsättningar används följande tabell för rapportering.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` |  |  |  |
| `user_310` | `1 Jan 7:04 AM` |  |  |  | `2` |  |
| `user_310` | `1 Jan 7:08 AM` | `Blue` |  |  | `3` |  |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` |  | `Circle` |  | `8.5` |
| `user_847` | `2 Jan 12:31 PM` |  | `Turtle` |  | `4` |  |
| `user_847` | `2 Jan 12:44 PM` |  |  |  | `2` |  |
| `user_847` | `2 Jan 1:01 PM` | `Red` |  |  |  |  |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` |  | `Square` |  | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` |  |  | `Triangle` |  | `3.1` |

Den här kombinerade datauppsättningen används för rapportering. Det spelar ingen roll vilken datauppsättning en rad kommer från. CJA hanterar alla data som om de fanns i samma datauppsättning. Om ett matchande person-ID visas i båda datauppsättningarna betraktas de som samma unika besökare. Om ett matchande person-ID visas i båda datauppsättningarna med en tidsstämpel inom 30 minuter betraktas de som en del av samma session.

Detta koncept gäller också attribuering. Det spelar ingen roll vilken datauppsättning en rad kommer från. attribuering fungerar precis som om alla händelser kom från en enda datamängd. Använda tabellerna ovan som exempel:

Om din anslutning endast innehöll den första tabellen och inte den andra skulle det visa att dra en rapport med hjälp av `string_color` mått och `metric_a` mått med hjälp av den senaste beröringsattribueringen:

| string_color | metrisk_a |
| --- | --- |
| Ospecificerad | 6 |
| Blå | 3 |
| Röd | 2 |

Om du däremot inkluderade båda tabellerna i anslutningen, ändras attribueringen eftersom den `user_847` finns i båda datauppsättningarna. En rad från den andra datauppsättningsattributen `metric_a` till Gul, där de tidigare inte var angivna:

| string_color | metrisk_a |
| --- | --- |
| Gul | 6 |
| Blå | 3 |
| Röd | 2 |
