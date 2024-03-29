---
title: Hur stygn fungerar
description: Förstå begreppet stygn
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 506838a0-0fe3-4b5b-bb9e-2ff20feea8bc
role: Admin
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1109'
ht-degree: 7%

---

# Hur stygn fungerar

Stitching gör att minst två omgångar av data i en given datauppsättning används:

* **Livestning**: försöker sammanfoga varje träff (händelse) när den kommer in. Träffar från enheter som är&quot;nya&quot; i datauppsättningen (som aldrig har autentiserats) sammanfogas vanligtvis inte på den här nivån. Träffar från enheter som redan känns igen sammanfogas omedelbart.

* **Spela upp sammanfogning**:&quot;repriser&quot; data baserat på unika identifierare (tillfälliga ID:n) som den har lärt sig. På den här scenen sammanfogas träffar från tidigare okända enheter (beständiga ID:n) (till tillfälliga ID:n). Adobe har två repriser:
   * **Dagligen**: Data spelas upp varje dag med ett 24-timmarsfönster. Det här alternativet har en fördel som innebär att repriser är mycket oftare, men oautentiserade besökare måste autentisera samma dag som de besöker webbplatsen.
   * **Vecka**: Data spelas upp en gång i veckan med ett 7-dagars uppslagsfönster. Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än en vecka gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.

* **Integritet (valfritt)**: När sekretessrelaterade förfrågningar tas emot, förutom att den begärda identiteten tas bort, måste alla sammanslagningar av den identiteten i oautentiserade händelser ångras.

Data utanför uppslagsfönstret spelas inte upp igen. En besökare måste autentisera sig inom ett visst fönster för att kunna identifiera ett oautentiserat besök och ett autentiserat besök tillsammans. När en enhet känns igen är den sydd från den punkten framåt.

## Steg 1: Liveutjämning

Livestutlösare försöker sammanfoga varje händelse när den samlas till kända enheter och kanaler. Titta på följande exempel där Bob spelar in olika händelser som en del av en händelsedatamängd.

*Data så som de visas den dag de samlas in:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** |
| 5 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 | 246 | - | **Bob** | |
| 7 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 8 | 2023-05-12 | 3579 ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 9 | 2023-05-12 | 3579 ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 | 81911 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12: | 81911 | - | **Bob** |
| | | **3 enheter** | | **4 personer**:<br/>246, Bob, 3579, 81911 |

Både oautentiserade och autentiserade händelser på nya enheter räknas som separata personer (tillfälligt). Oautentiserade händelser på identifierade enheter sammanfogas live.

Attribution fungerar när den identifierande anpassade variabeln binder till en enhet. I exemplet ovan är alla händelser utom händelserna 1, 8, 9 och 10 direktsammanfogade (de använder alla `Bob` identifierare). Live stitching &#39;resolves&#39; the stitched ID for event 4, 6 and 12.

Fördröjda data (data med en tidsstämpel som är över 24 timmar gamla) hanteras enligt principen&quot;bästa insats&quot;, samtidigt som sammanslagningen av aktuella data prioriteras för högsta kvalitet.

## Steg 2: Spela upp sammanfogning igen

Med regelbundna intervall (en gång i veckan eller en gång om dagen, beroende på vilket fönster som valts) beräknas historiska data om baserat på enheter som nu känns igen. Om en enhet till att börja med skickar data utan att vara autentiserad och sedan loggar in, kopplas de oautentiserade händelserna om till rätt person. Följande tabell representerar samma data som ovan, men visar olika tal baserat på hur data spelas upp.

*Samma data efter replay:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) | Stitched ID (after replay) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob |
| 5 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 | 246 | - | **Bob** | Bob |
| 7 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 | 3579 ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 | 3579 ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** |
| 11 | 2023-05-12 | 81911 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12: | 81911 | - | **Bob** | Bob |
| | | **3 enheter** | | **4 personer**:<br/>246, Bob, 3579, 81911 | **2 personer**:<br/>Bob, 3579 |

{style="table-layout:auto"}

Attribution fungerar när den identifierande anpassade variabeln binder till en enhet. I exemplet ovan sammanfogas händelse 1 och 10 som ett resultat av repriser, vilket innebär att endast händelse 8 och 9 upphör att sammanfogas. Och minska personmåttet (kumulativt) till 2.

## Steg 3: Begäran om sekretess

När du tar emot en sekretessförfrågan tas raden med den ursprungliga användarinformationen bort, tillsammans med eventuella sammanfogade ID:n som innehåller samma personinformation. Följande tabell representerar samma data som ovan, men visar vilken effekt en sekretessförfrågan för Bob har på data efter att de har bearbetats. Raderna där Bob autentiserades tas bort (2, 3, 5, 7 och 11) tillsammans med Bob tas bort som ett tillfälligt ID för andra rader.

*Samma data efter en begäran om sekretess för Bob:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) | Stitched ID (after replay) | Transient ID (inloggnings-ID) | Stitched ID (after privacy request) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob** | Bob | - | 246 |
| 5 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 | 246 | - | **Bob** | Bob | - | 246 |
| 7 | 2023-05-12 | 246 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 | 3579 ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 9 | 2023-05-12 | 3579 ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 | 81911 | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12: | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **3 enheter** | | **4 personer**:<br/>246, Bob, 3579, 81911 | **2 personer**:<br/>Bob, 3579 |  | **3 personer**:<br/>246, 3579, 8191 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## Sammanfattning

* Med Stitching sammanfogas händelser omedelbart från kända enheter, men du kan inte omedelbart sammanfoga händelser från nya eller okända enheter.
* Data spelas upp med jämna mellanrum och ändrar historiska data i anslutningen baserat på enheter som den har lärt sig identifiera.
* Liveutläggning och repriser utförs på en datauppsättning. Resultatet är en ny utökad datauppsättning som är bättre lämpad att användas när den kombineras med andra datauppsättningar (till exempel callcenter-data) för att utföra flerkanalsanalys.
* Sekretessförfrågningar tar bort identiteter som har spridit sig till oautentiserade rader.
