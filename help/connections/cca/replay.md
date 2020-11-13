---
title: Så här spelar du upp
description: Förstå begreppet"replay" i flerkanalsanalys
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---


# Så här spelar du upp

Flerkanalsanalys gör att data kan skickas vidare på en viss anslutning:

* **Livestning**: CCA försöker sy ihop varje träff när den kommer in. Nya Net-enheter till datauppsättningen som aldrig har loggat in sammanfogas vanligtvis inte på den här nivån. Enheter som redan känns igen sammanfogas omedelbart.
* **Spela upp**: CCA&quot;repriser&quot; data baserat på unika identifierare som den har lärt sig. I det här steget sammanfogas nya enheter till anslutningen. Adobe har två repriser:
   * Dagligen: Data spelas upp varje dag med ett 24-timmars uppslagsfönster. Det här alternativet har en fördel som innebär att repriser är mycket oftare, men oautentiserade besökare måste autentisera samma dag som de besöker webbplatsen.
   * Vecka: Data spelas upp en gång i veckan med ett 7-dagars uppslagsfönster. Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Data som är yngre än en vecka sammanfogas dock inte.

## Steg 1: Live-syn

CCA försöker sammanfoga varje händelse när den samlas till kända enheter och kanaler. Titta på följande exempel där Bob använder två olika kanaler.

*Data så som de visas den dag de samlas in:*

| Tidsstämpel | Beständigt ID för webbdatauppsättning | Övergångs-ID för webbdatauppsättning | ID för kundtjänstperson | Använt person-ID | Förklaring av träffen | Personmått (kumulativt) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob besöker din webbplats på sin dator, oautentiserad | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob loggar in på skrivbordet | `2` (246 och Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob ringer kundtjänst | `2` (246 och Bob) |
| `4` | `3579` | - | - | `3579` | Bob kommer åt din webbplats på sin mobila enhet, oautentiserad | `3` (246, Bob och 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob loggar in via mobilen | `3` (246, Bob och 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob ringer till kundtjänst igen | `3` (246, Bob och 3579) |
| `7` | `246` | - | - | `Bob` | Bob besöker din webbplats på sin dator igen, oautentiserad | `3` (246, Bob och 3579) |

Både oautentiserade och autentiserade händelser på nya enheter räknas som separata personer (tillfälligt). Oautentiserade händelser på kända enheter sys i realtid.

Attribution fungerar så snart den identifierande anpassade variabeln kopplar till en enhet. I exemplet ovan är alla händelser utom händelserna 1 och 4 sammanfogade (de använder alla identifieraren `Bob`). Attribution works on events 1 and 4 after replay stitching.

## Steg 2: Spela upp sammanfogning

Med regelbundna intervall (en gång i veckan eller en gång om dagen beroende på vilket fönster som valts) beräknar CCA om historiska data baserat på enheter som den nu känner igen. Om en enhet först skickar data utan att vara autentiserad och sedan loggar in, binder CCA dessa oautentiserade händelser till rätt person. Följande tabell representerar samma data som ovan, men visar olika tal baserat på hur data spelas upp.

*Samma data efter replay:*

| Tidsstämpel | Beständigt ID för webbdatauppsättning | Övergångs-ID för webbdatauppsättning | ID för kundtjänstperson | Använt person-ID | Förklaring av träffen | Personmått (kumulativt) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob besöker din webbplats på sin dator, oautentiserad | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob loggar in på skrivbordet | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob ringer kundtjänst | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob kommer åt din webbplats på sin mobila enhet, oautentiserad | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob loggar in via mobilen | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob ringer till kundtjänst igen | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob besöker din webbplats på sin dator igen, oautentiserad | `1` (Bob) |

## Omslag

* CCA sammanfogar omedelbart kända enheter, men sammanfogar inte omedelbart nya eller okända enheter.
* Data spelas upp med jämna mellanrum och ändrar historiska data i anslutningen baserat på enheter som den har lärt sig identifiera.
