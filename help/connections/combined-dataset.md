---
title: Kombinerade datauppsättningar
description: Läs mer om hur CJA skapar en anslutning genom att kombinera datauppsättningar.
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---


# Kombinerade datauppsättningar

När du skapar en anslutning kombinerar CJA alla scheman och datauppsättningar till en enda datamängd. Denna kombinerade datamängd är vad CJA använder för rapportering. När du tar med flera scheman eller datauppsättningar i en anslutning:

* Systemen kombineras. Dubbla schemafält slås samman.
* Kolumnen &#39;Person ID&#39; i varje datamängd slås samman till en enda kolumn, oavsett deras namn. Denna kolumn är grunden för att identifiera unika besökare i CJA.
* Raderna bearbetas utifrån tidsstämpel.

## Exempel

Tänk på följande exempel. Du har två datauppsättningar med olika fält som innehåller olika data.

>[!NOTE]
>
>I Adobe Experience Platform lagras vanligtvis tidsstämpel i Unix millisekunder. I det här exemplet används datum och tid för läsbarhet.

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

Denna kombinerade datamängd är vad som används vid rapportering. Det spelar ingen roll från vilken datamängd en rad kommer. CJA behandlar alla data som om de finns i samma datamängd. Om ett matchande person-ID visas i båda datauppsättningarna anses de vara samma unika besökare. Om ett matchande person-ID visas i båda datauppsättningarna med en tidsstämpel inom 30 minuter anses de vara en del av samma session.

Detta koncept gäller också för tilldelning. Det spelar ingen roll från vilken datamängd en rad kommer. attributet fungerar exakt som om alla händelser kom från en enda datamängd. Använda ovanstående tabeller som exempel:

Om din anslutning bara omfattade den första tabellen och inte den andra, drar du en rapport med hjälp av `string_color` dimension och `metric_a` Mått som använder den sista pektilattributet skulle visa:

| sträng_färg | metrisk_a |
| --- | --- |
| Ospecificerad | 6 |
| Blå | 3 |
| Röd | 2 |

Om du har inkluderat båda tabellerna i anslutningen ändras attributet sedan `user_847` finns i båda datauppsättningarna. En rad från andra datauppsättningsattribut `metric_a` till &quot;Gul&quot; om de tidigare inte har specificerats:

| sträng_färg | metrisk_a |
| --- | --- |
| Gul | 6 |
| Blå | 3 |
| Röd | 2 |
