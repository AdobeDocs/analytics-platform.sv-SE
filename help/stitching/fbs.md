---
title: Fältbaserad stygn
description: Förklaring av fältbaserad sammanfogning
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
source-git-commit: 4ce1b22cce3416b8a82e5c56e605475ae6c27d88
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Fältbaserad stygn

I fältbaserad sammanfogning anger du en händelsedatamängd samt ett beständigt ID (cookie) och tillfälligt ID (person-ID) för den datauppsättningen. Fältbaserad sammanfogning skapar en ny sammanfogad ID-kolumn i den nya sammanfogade datauppsättningen och uppdaterar den här sammanfogade ID-kolumnen baserat på rader som har ett övergående ID för det specifika beständiga ID:t. <br/>Du kan använda fältbaserad sammanfogning när du använder Customer Journey Analytics som en fristående lösning (du har inte tillgång till Experience Platform Identity Service och tillhörande identitetsdiagram). Eller om du inte vill använda det tillgängliga identitetsdiagrammet.

![Fältbaserad häftning](/help/stitching/assets/fbs.png)

## Så här fungerar fältbaserad sammanfogning

Med hjälp av häftning blir det minst två omgångar data i en given datauppsättning.

- **Liveutjämning**: försöker sammanfoga varje träff (händelse) när den kommer in. Träffar från enheter som är&quot;nya&quot; i datauppsättningen (som aldrig har autentiserats) sammanfogas vanligtvis inte på den här nivån. Träffar från enheter som redan känns igen sammanfogas omedelbart.

- **Spela upp sammanfogning**:&quot;Spelar upp&quot; data baserat på unika identifierare (tillfälliga ID:n) som den har lärt sig. På den här scenen sammanfogas träffar från tidigare okända enheter (beständiga ID:n) (till tillfälliga ID:n). Uppspelningen bestäms av två parametrar: **frequency** och **lookback window**. Adobe erbjuder följande kombinationer av dessa parametrar:
   - **Daglig sökning efter en daglig frekvens**: Data spelas upp varje dag med ett 24-timmars uppslagsfönster. Det här alternativet har en fördel som innebär att repriser är mycket oftare, men oautentiserade besökare måste autentisera samma dag som de besöker webbplatsen.
   - **Veckovis uppslag med en veckofrekvens**: Data spelas upp en gång i veckan med ett veckovisa uppslagsfönster (se [alternativ](#options)). Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än en vecka gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.
   - **Veckovis uppspelning på en veckofrekvens**: Data spelas upp en gång i veckan med ett varannan vecka-uppslag (se [alternativ](#options)). Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än två veckor gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.
   - **Månadsvis uppslag på en veckofrekvens**: Data spelas upp varje vecka med ett månadsuppslag (se [alternativ](#options)). Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än en månad gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.

- **Sekretess**: När sekretessrelaterade förfrågningar tas emot, förutom att den begärda identiteten tas bort, måste alla sammanfogningar av den identiteten i oautentiserade händelser ångras.

  >[!IMPORTANT]
  >
  >Frigörandeprocessen, som en del av begäran om integritet, ändras i början av 2025. Den aktuella enhetsprocessen ändrar namn på händelser med den senaste versionen av kända identiteter. Denna omfördelning av händelser till en annan identitet kan få oönskade juridiska konsekvenser. För att åtgärda dessa problem uppdaterar den nya upplösningsprocessen från och med 2025 händelser som omfattas av sekretessposten med det beständiga ID:t.
  > 


Data utanför uppslagsfönstret spelas inte upp igen. En besökare måste autentisera sig inom ett visst fönster för att få ett oautentiserat besök och ett autentiserat besök att identifieras tillsammans. När en enhet känns igen är den sydd från den punkten framåt.

### Steg 1: Liveutjämning

Livestutlösare försöker sammanfoga varje händelse när den samlas till kända enheter och kanaler.

+++ Information

Titta på följande exempel där Bob spelar in olika händelser som en del av en händelsedatamängd.

*Data som de såg ut den dag de samlades in:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 | `81911` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12: | `81911` | - | **`Bob`** |
| | | **3 enheter** | | **4 personer**:<br/>`246`, `Bob`, `3579`, `81911` |

Både oautentiserade och autentiserade händelser på nya enheter räknas som separata personer (tillfälligt). Oautentiserade händelser på identifierade enheter sammanfogas live.

Attribution fungerar när den identifierande anpassade variabeln är kopplad till en enhet. I exemplet ovan är alla händelser utom händelserna 1, 8, 9 och 10 direktsammanfogade (de använder alla identifieraren `Bob`). Live stitching &#39;resolves&#39; the stitched ID for event 4, 6 and 12.

Försenade data (data med en tidsstämpel som är över 24 timmar gamla) hanteras enligt principen&quot;bästa insats&quot;, samtidigt som sammanslagningen av aktuella data prioriteras för högsta kvalitet.

+++

### Steg 2: Spela upp sammanfogning igen

Med regelbundna intervall (en gång i veckan eller en gång om dagen, beroende på vilket fönster som valts) beräknas historiska data om baserat på enheter som nu känns igen. Om en enhet till att börja med skickar data utan att vara autentiserad och sedan loggar in, kopplas de oautentiserade händelserna om till rätt person.

+++ Information

Följande tabell representerar samma data som ovan, men visar olika tal baserat på hur data spelas upp.

*Samma data efter uppspelning:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) | Stitched ID (after replay) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 | `81911` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12: | `81911` | - | **`Bob`** | `Bob` |
| | | **3 enheter** | | **4 personer**:<br/>`246`, `Bob`, `3579`, `81911` | **2 personer**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

Attribution fungerar när den identifierande anpassade variabeln är kopplad till en enhet. I exemplet ovan sammanfogas händelse 1 och 10 som ett resultat av repriser, vilket innebär att endast händelse 8 och 9 upphör att sammanfogas. Och minska personmåttet (kumulativt) till 2.

+++

### Steg 3: Begäran om sekretess

När du tar emot en begäran om sekretess, tas det sammanslagna ID:t bort i alla poster för den användare som omfattas av sekretessbegäran.

+++ Information

Följande tabell representerar samma data som ovan, men visar vilken effekt en sekretessförfrågan för Bob har på data efter att de har bearbetats. Raderna där Bob är autentiserad tas bort (2, 3, 5, 7 och 11) och Bob tas bort som ett tillfälligt ID för andra rader.

*Samma data efter en sekretessförfrågan för Bob:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) | Stitched ID (after replay) | Transient ID (inloggnings-ID) | Stitched ID (after privacy request) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Pil höger](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 | `246` | Bob ![Pil höger](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 | `246` | Bob ![Pil höger](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 | `81911` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil ned](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12: | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 enheter** | | **4 personer**:<br/>246, `Bob`, `3579`, `81911` | **2 personer**:<br/>Bob, `3579` |  | **3 personer**:<br/>`246`, `3579`, `81911` |

+++

## Förutsättningar

Följande krav gäller specifikt för fältbaserad sammanfogning:

- Händelsedatauppsättningen i Adobe Experience Platform, som du vill använda sammanfogning på, måste ha två kolumner som hjälper till att identifiera besökare:

   - Ett **beständigt ID**, en identifierare som är tillgänglig på varje rad. Till exempel ett besökar-ID som genererats av ett Adobe Analytics AppMeasurement-bibliotek eller ett ECID som genererats av Adobe Experience Platform Identity Service.
   - Ett **övergående ID**, en identifierare som bara är tillgänglig på vissa rader. Till exempel ett hashas användarnamn eller en e-postadress när en besökare autentiserar. Du kan använda praktiskt taget vilken identifierare som helst. Stitching ser till att det här fältet innehåller den faktiska person-ID-informationen. För bästa resultat av sammanfogning bör ett tillfälligt ID skickas inom datauppsättningens händelser minst en gång för varje beständigt ID. Om du tänker ta med den här datauppsättningen i en Customer Journey Analytics-anslutning är det bättre att de andra datauppsättningarna också har en liknande gemensam identifierare.

- Båda kolumnerna (beständigt ID och tillfälligt ID) måste definieras som ett identitetsfält med ett identitetsnamnutrymme i schemat för den datauppsättning som du vill sammanfoga. När du använder identitetssammanfogning i Real-time Customer Data Platform med fältgruppen [`identityMap` ](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) måste du fortfarande lägga till identitetsfält med ett identitetsnamnområde. Identifieringen av identitetsfält krävs eftersom Customer Journey Analytics inte stöder fältgruppen `identityMap`. När du lägger till ett identitetsfält i schemat, men även använder fältgruppen `identityMap`, ska du inte ange det extra identitetsfältet som en primär identitet. Om du anger ytterligare ett identitetsfält som primär identitet stör det `identityMap`-fältgruppen som används för Real-time Customer Data Platform.

## Begränsningar

Följande begränsningar gäller specifikt för fältbaserad sammanfogning:

- De nuvarande funktionerna för manuell inmatning är begränsade till ett steg (beständigt ID till tillfälligt ID). Återinmatning i flera steg (till exempel beständigt ID till ett tillfälligt ID och sedan till ett annat tillfälligt ID) stöds inte.
- Om en enhet delas av flera personer och det totala antalet övergångar mellan användare överstiger 50 000, slutar Customer Journey Analytics att fästa data för den enheten.
- Anpassade ID-mappningar som används i din organisation stöds inte.
- Stiting är skiftlägeskänsligt. För datauppsättningar som genereras via Analytics-källkopplingen rekommenderar Adobe att du granskar alla VISTA-regler eller bearbetningsregler som gäller för det tillfälliga ID-fältet. Denna granskning säkerställer att inga av dessa regler inför nya formulär med samma ID. Du bör t.ex. se till att inga VISTA-regler eller bearbetningsregler för endast en del av händelserna introducerar lägre radering till det tillfälliga ID-fältet.
- När du använder Stitching kombineras eller sammanfogas inte fält.
- Det tillfälliga ID-fältet ska innehålla en enda typ av ID (ID:n från ett enda namnutrymme). Det tillfälliga ID-fältet ska till exempel inte innehålla en kombination av inloggnings-ID och e-post-ID.
- Om flera händelser inträffar med samma tidsstämpel för samma beständiga ID, men med olika värden i fältet för transient ID, väljs ID baserat på alfabetisk ordning. Om ett beständigt ID A har två händelser med samma tidsstämpel och en av händelserna anger Bob och den andra anger Ann, väljer Ann när de sammanfogar.
- Var försiktig med scenarier där tillfälliga ID:n innehåller platshållarvärden, till exempel `Undefined`. Mer information finns i [Vanliga frågor](faq.md).

