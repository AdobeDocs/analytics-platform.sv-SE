---
title: Översikt över titlar
description: Översikt över häftning.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
exl-id: 1c42efac-b3d2-437b-8b0b-9c6fdfed8520
role: Admin
source-git-commit: 38bcb262023773763c0ff710a6aba4e06b864d01
workflow-type: tm+mt
source-wordcount: '3752'
ht-degree: 1%

---

# Stitlar

{{select-package}}

Identitetssammanfogning (eller helt enkelt sammanfogning) är en kraftfull funktion som ökar en händelsedatamängds lämplighet för flerkanalsanalys. Flerkanalsanalys är ett vanligt användningsfall som Customer Journey Analytics kan hantera, vilket gör att du kan kombinera och köra rapporter sömlöst på flera datauppsättningar från olika kanaler, baserat på en gemensam identifierare (person-ID).

När du kombinerar datauppsättningar med liknande person-ID:n överförs attribueringen mellan enheter och kanaler. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren stöter på ett problem med sin beställning och ger sedan kundtjänstteamet ett samtal för att hjälpa till att lösa det. Med flerkanalsanalys kan ni attribuera callcenter-händelser till den annons som de ursprungligen klickade på.

Tyvärr är inte alla händelsebaserade datauppsättningar som är en del av din anslutning i Customer Journey Analytics tillräckligt kompletta med data för att stödja denna attribuering. I synnerhet har webbaserade eller mobilbaserade upplevelsedatamängder ofta ingen faktisk person-ID-information tillgänglig för alla händelser.

Med hjälp av häftning kan du skriva in identiteter på nytt i en datamängds rader, så att person-ID (sammanfogat ID) är tillgängligt för varje händelse. Stitching tittar på användardata från både autentiserade och oautentiserade sessioner för att avgöra det gemensamma tillfälliga ID-värdet (person-ID) som kan användas som sammanfogat ID. Denna inmatning gör det möjligt att lösa olika poster till ett enda sammanfogat ID för analys på personnivå, i stället för på enhets- eller cookienivå.

Customer Journey Analytics har stöd för två typer av sammanfogning: fältbaserad sammanfogning och diagrambaserad sammanfogning.

## Förutsättningar

>[!IMPORTANT]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att utföra flerkanalsanalys korrekt.

Innan du använder stygn bör du kontrollera att din organisation har förberetts med följande:

- Stitching inkluderar sammanfogning av autentiserade och oautentiserade användardata. Se till att du följer tillämpliga lagar och bestämmelser, inklusive att erhålla nödvändiga slutanvändarbehörigheter, innan du aktiverar sammanfogning av en händelsedatamängd. Se [Definiera identitetsfält i användargränssnittet](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) för mer information.

- Importera önskade data till Adobe Experience Platform:

   - Information om Adobe Analytics finns på [Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   - Andra typer av data finns i [Skapa ett schema](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) och [Ingrediera data](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) i Adobe Experience Platform-dokumentationen.

Du kan dra nytta av flerkanalsanalys om du kombinerar en eller flera av dina sammanfogade datauppsättningar med andra datauppsättningar, till exempel callcenter-data, som en del av arbetet med att definiera din Customer Journey Analytics-anslutning. Den här anslutningskonfigurationen förutsätter att dessa andra datauppsättningar redan innehåller ett person-ID på varje rad, som liknar det sammanfogade ID:t.


## Begränsningar

>[!IMPORTANT]
>
>- Inget stöd för att använda `identityMap` som det beständiga ID:t. Du måste definiera en specifik identifierare i datauppsättningen (till exempel `ECID`) som det beständiga ID:t.
>
>- Använd alla ändringar du gör i källhändelsens dataschema även i det nya sammanfogade dataschemat, annars bryts den sammanfogade datauppsättningen.
>
>- Om du tar bort källdatauppsättningen avbryts bearbetningen av den sammanfogade datauppsättningen och tas bort av systemet.
>
>- Dataanvändningsetiketter sprids inte automatiskt till det sammanslagna dataset-schemat. Om du har använt dataanvändningsetiketter på källdataschemat måste du använda dessa dataanvändningsetiketter manuellt på det sammanslagna dataset-schemat. Se [Hantera dataanvändningsetiketter i Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) för mer information.

Stitching är en banbrytande och robust funktion, men har begränsningar för hur den kan användas.

- Endast händelsedatamängder stöds. Andra datauppsättningar, till exempel uppslagsdatauppsättningar, stöds inte.
- Med hjälp av fästfunktionen omvandlas inte det fält som används för sammanfogning på något sätt. Vid Stitching används värdet i det angivna fältet som det finns i den osydda datauppsättningen inom datarinden.
- Smältningsprocessen är skiftlägeskänslig. Om ibland ordet &#39;Bob&#39; visas i fältet, och ibland ordet &#39;BOB&#39; visas, behandlas dessa id:n som två separata personer.

Försäkra dig om att du inte förväxlar stygn med:

- Sammanfogningen av två eller flera datauppsättningar. Gäller endast en datauppsättning. Sammanfogning av datauppsättningar sker som ett resultat av att du konfigurerar en Customer Journey Analytics-anslutning och väljer samma person-ID för de markerade datauppsättningarna i anslutningen.

- Sammanfogning av två datauppsättningar. I Customer Journey Analytics används ofta en join för uppslag eller klassificeringar i Analysis Workspace. Även om sammanfogning använder sammanfogningsfunktioner innebär själva processen mer än sammanfogningar.


## Fältbaserad stygn

Du anger en händelsedatamängd samt det beständiga ID:t (cookie) och det tillfälliga ID:t (person-ID) för den datauppsättningen. Fältbaserad sammanfogning skapar en ny sammanfogad ID-kolumn i den nya sammanfogade datauppsättningen och uppdaterar den här sammanfogade ID-kolumnen baserat på rader som har ett övergående ID för det specifika beständiga ID:t. <br/>Du kan använda fältbaserad stygn när du använder Customer Journey Analytics som en fristående lösning (som inte har tillgång till Experience Platform Identity Service och tillhörande identitetsdiagram). Eller om du inte vill använda det tillgängliga identitetsdiagrammet.

![Fältbaserad stygn](/help/stitching/assets/fbs.png)

### Så här fungerar fältbaserad sammanfogning

Med hjälp av häftning blir det minst två omgångar data i en given datauppsättning.

- **Livestning**: försöker sammanfoga varje träff (händelse) när den kommer in. Träffar från enheter som är&quot;nya&quot; i datauppsättningen (som aldrig har autentiserats) sammanfogas vanligtvis inte på den här nivån. Träffar från enheter som redan känns igen sammanfogas omedelbart.

- **Spela upp sammanfogning**:&quot;repriser&quot; data baserat på unika identifierare (tillfälliga ID:n) som den har lärt sig. På den här scenen sammanfogas träffar från tidigare okända enheter (beständiga ID:n) (till tillfälliga ID:n). Adobe har två repriser:
   - **Dagligen**: Data spelas upp varje dag med ett 24-timmarsfönster. Det här alternativet har en fördel som innebär att repriser är mycket oftare, men oautentiserade besökare måste autentisera samma dag som de besöker webbplatsen.
   - **Vecka**: Data spelas upp en gång i veckan med det valda uppslagsfönstret (se [alternativ](#options)). Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än en vecka gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.

- **Integritet**: När sekretessrelaterade förfrågningar tas emot, förutom att den begärda identiteten tas bort, måste alla sammanslagningar av den identiteten i oautentiserade händelser ångras.

Data utanför uppslagsfönstret spelas inte upp igen. En besökare måste autentisera sig inom ett visst fönster för att få ett oautentiserat besök och ett autentiserat besök att identifieras tillsammans. När en enhet känns igen är den sydd från den punkten framåt.

#### Steg 1: Liveutjämning

Livestutlösare försöker sammanfoga varje händelse när den samlas till kända enheter och kanaler.

+++ Information

Titta på följande exempel där Bob spelar in olika händelser som en del av en händelsedatamängd.

*Data som de såg ut samma dag som de samlades in:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 3 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** |
| 5 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 | `246` | - | **`Bob`** |
| 7 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` |
| 8 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 9 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`81911`** |
| 11 | 2023-05-12 | `81911` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 12 | 2023-05-12 12: | `81911` | - | **`Bob`** |
| | | **3 enheter** | | **4 personer**:<br/>`246`, `Bob`, `3579`, `81911` |

Både oautentiserade och autentiserade händelser på nya enheter räknas som separata personer (tillfälligt). Oautentiserade händelser på identifierade enheter sammanfogas live.

Attribution fungerar när den identifierande anpassade variabeln är kopplad till en enhet. I exemplet ovan är alla händelser utom händelserna 1, 8, 9 och 10 direktsammanfogade (de använder alla `Bob` identifierare). Live stitching &#39;resolves&#39; the stitched ID for event 4, 6 and 12.

Försenade data (data med en tidsstämpel som är över 24 timmar gamla) hanteras enligt principen&quot;bästa insats&quot;, samtidigt som sammanslagningen av aktuella data prioriteras för högsta kvalitet.

+++

#### Steg 2: Spela upp sammanfogning igen

Med regelbundna intervall (en gång i veckan eller en gång om dagen, beroende på vilket fönster som valts) beräknas historiska data om baserat på enheter som nu känns igen. Om en enhet till att börja med skickar data utan att vara autentiserad och sedan loggar in, kopplas de oautentiserade händelserna om till rätt person.

+++ Information

Följande tabell representerar samma data som ovan, men visar olika tal baserat på hur data spelas upp.

*Samma data efter replay:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) | Stitched ID (after replay) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` |
| 5 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` |
| 6 | 2023-05-12 | `246` | - | **`Bob`** | `Bob` |
| 7 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` |
| 8 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 | `81911` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 12 | 2023-05-12 12: | `81911` | - | **`Bob`** | `Bob` |
| | | **3 enheter** | | **4 personer**:<br/>`246`, `Bob`, `3579`, `81911` | **2 personer**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

Attribution fungerar när den identifierande anpassade variabeln är kopplad till en enhet. I exemplet ovan sammanfogas händelse 1 och 10 som ett resultat av repriser, vilket innebär att endast händelse 8 och 9 upphör att sammanfogas. Och minska personmåttet (kumulativt) till 2.

+++

#### Steg 3: Begäran om sekretess

När du tar emot en begäran om sekretess, tas det sammanslagna ID:t bort i alla poster för den användare som omfattas av sekretessbegäran.

+++ Information

Följande tabell representerar samma data som ovan, men visar vilken effekt en sekretessförfrågan för Bob har på data efter att de har bearbetats. Raderna där Bob är autentiserad tas bort (2, 3, 5, 7 och 11) och Bob tas bort som ett tillfälligt ID för andra rader.

*Samma data efter en begäran om sekretess för Bob:*

| Händelse | Tidsstämpel | Beständigt ID (cookie-ID) | Transient ID (inloggnings-ID) | Stitched ID (after live stitch) | Stitched ID (after replay) | Transient ID (inloggnings-ID) | Stitched ID (after privacy request) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 3 | 2023-05-12 | `246` | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 5 | 2023-05-12 | `246` | Bob ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 6 | 2023-05-12 | `246` | - | **`Bob`** | `Bob` | - | `246` |
| 7 | 2023-05-12 | `246` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` | `Bob` | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `246` |
| 8 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 | `3579` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 | `81911` | `Bob` ![Högerpil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | `Bob` ![Pil nedåt](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | `Bob` ![Pil upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | `81911` |
| 12 | 2023-05-12 12: | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 enheter** | | **4 personer**:<br/>246, `Bob`, `3579`, `81911` | **2 personer**:<br/>Bob, `3579` |  | **3 personer**:<br/>`246`, `3579`, `81911` |

+++

### Förutsättningar

Följande krav gäller specifikt för fältbaserad sammanfogning:

- Händelsedatauppsättningen i Adobe Experience Platform, som du vill använda sammanfogning på, måste ha två kolumner som hjälper till att identifiera besökare:

   - A **beständigt ID**, en identifierare som är tillgänglig på varje rad. Till exempel ett besökar-ID som genererats av ett Adobe Analytics AppMeasurement-bibliotek eller ett ECID som genererats av Adobe Experience Cloud Identity Service.
   - A **tillfälligt ID**, en identifierare som bara finns på vissa rader. Till exempel ett hashas användarnamn eller en e-postadress när en besökare autentiserar. Du kan använda praktiskt taget vilken identifierare som helst. Stitching ser till att det här fältet innehåller den faktiska person-ID-informationen. För bästa resultat av sammanfogning bör ett tillfälligt ID skickas inom datauppsättningens händelser minst en gång för varje beständigt ID. Om du tänker ta med den här datauppsättningen i en Customer Journey Analytics-anslutning är det bättre att de andra datauppsättningarna också har en liknande gemensam identifierare.

- Båda kolumnerna (beständigt ID och tillfälligt ID) måste definieras som ett identitetsfält med ett identitetsnamnutrymme i schemat för den datauppsättning som du vill sammanfoga. När du använder identitetssammanfogning i Real-time Customer Data Platform använder du [`identityMap` fältgrupp](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity)måste du fortfarande lägga till identitetsfält med ett identitetsnamnutrymme. Identifiering av identitetsfält krävs eftersom sammanfogning av Customer Journey Analytics inte stöder `identityMap` fältgrupp. När du lägger till ett identitetsfält i schemat, samtidigt som du använder `identityMap` fältgrupp, ange inte det extra identitetsfältet som en primär identitet. Om du anger ytterligare ett identitetsfält som primär identitet påverkas inte `identityMap` fältgrupp för Real-time Customer Data Platform.

### Begränsningar

Följande begränsningar gäller specifikt för fältbaserad sammanfogning:

- De nuvarande funktionerna för manuell inmatning är begränsade till ett steg (beständigt ID till tillfälligt ID). Återinmatning i flera steg (till exempel beständigt ID till ett tillfälligt ID och sedan till ett annat tillfälligt ID) stöds inte.
- Om en enhet delas av flera personer och det totala antalet övergångar mellan användare överstiger 50 000, slutar Customer Journey Analytics att fästa data för den enheten.
- Anpassade ID-mappningar som används i din organisation stöds inte.
- Stiting är skiftlägeskänsligt. För datauppsättningar som genereras via Analytics-källkopplingen rekommenderar Adobe att du granskar alla VISTA-regler eller bearbetningsregler som gäller för det tillfälliga ID-fältet. Denna granskning säkerställer att inga av dessa regler inför nya formulär med samma ID. Du bör t.ex. se till att inga VISTA-regler eller bearbetningsregler för endast en del av händelserna introducerar lägre radering till det tillfälliga ID-fältet.
- När du använder Stitching kombineras eller sammanfogas inte fält.
- Det tillfälliga ID-fältet ska innehålla en enda typ av ID (ID:n från ett enda namnutrymme). Det tillfälliga ID-fältet ska till exempel inte innehålla en kombination av inloggnings-ID och e-post-ID.
- Om flera händelser inträffar med samma tidsstämpel för samma beständiga ID, men med olika värden i fältet för transient ID, väljs ID baserat på alfabetisk ordning. Om ett beständigt ID A har två händelser med samma tidsstämpel och en av händelserna anger Bob och den andra anger Ann, väljer Ann när de sammanfogar.
- Var försiktig med scenarier där transient-ID:n innehåller platshållarvärden, till exempel `Undefined`. Se [Vanliga frågor](faq.md) för mer information.


## Diagrambaserad utjämning

Du anger en händelsedatamängd samt det beständiga ID:t (cookie) och namnområdet för det tillfälliga ID:t (person-ID) för den datauppsättningen. Diagrambaserad sammanfogning skapar en ny kolumn för det sammanfogade ID:t i den nya sammanfogade datauppsättningen. Sedan används det beständiga ID:t för att fråga efter identitetsdiagrammet från identitetstjänsten i Experience Platform, med det namnområde som anges, för att uppdatera det sammanfogade ID:t.

![Diagrambaserad stygn](/help/stitching/assets/gbs.png)

### Hur grafbaserad stygn fungerar

Med hjälp av häftning blir det minst två omgångar data i en given datauppsättning.

- **Livestning**: försöker sammanfoga varje träff (händelse) när den kommer in, med det beständiga ID:t för att leta upp det tillfälliga ID:t för det markerade namnutrymmet genom att fråga efter identitetsdiagrammet. Om det tillfälliga ID:t är tillgängligt från sökningen sammanfogas detta tillfälliga ID omedelbart.

- **Spela upp sammanfogning**:&quot;repriser&quot; data baserat på uppdaterade identiteter från identitetsdiagrammet. På den här scenen sammanfogas träffar från tidigare okända enheter (beständiga ID:n) när identitetsdiagrammet har matchat identiteten för ett namnutrymme. Adobe har två repriser:
   - **Dagligen**: Data spelas upp varje dag med ett 24-timmarsfönster. Det här alternativet har en fördel som innebär att repriser är mycket oftare, men oautentiserade besökare måste autentisera samma dag som de besöker webbplatsen.
   - **Vecka**: Data spelas upp en gång i veckan med uppslagsfönstret (se [alternativ](#options)). Det här alternativet ger en fördel som gör att oautentiserade sessioner kan autentiseras mycket lättare. Ej sammanfogade data som är mindre än en vecka gamla bearbetas dock inte om förrän nästa veckovisa uppspelning.

- **Integritet**: När sekretessrelaterade förfrågningar tas emot, förutom att den begärda identiteten tas bort från källdatauppsättningen, måste alla sammanslagningar av den identiteten i oautentiserade händelser ångras. Identiteten måste också tas bort från identitetsdiagrammet för att förhindra att den specifika identiteten häftas med i framtiden.

Data utanför uppslagsfönstret spelas inte upp igen. En besökare måste autentisera sig inom ett visst fönster för att få ett oautentiserat besök och ett autentiserat besök att identifieras tillsammans. När en enhet känns igen är den sydd från den punkten framåt.

Tänk på följande två identitetsdiagram för beständigt ID `246` och `3579`, hur dessa identitetsdiagram uppdateras över tid och hur uppdateringarna påverkar stegen i diagrambaserade sammanfogningar.

![Identitetsdiagram 246](assets/identity-graph-246.svg)
![Identitetsdiagram 3579](assets/identity-graph-3579.svg)

Du kan visa ett identitetsdiagram över tiden för en viss profil med [Identity Graph Viewer](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). Se även [Länkningslogik för identitetstjänst](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) för att få en bättre förståelse för logiken som används vid länkning av identiteter.

#### Steg 1: Liveutjämning

Livehäftning försöker häfta ihop varje händelse vid samlingen till känd information från identitetsdiagrammet.

+++ Information

| | Tid | Beständigt ID<br/>`ECID` | Namnutrymme<br/>`Email` ![Diagram](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID (after live stitch) |
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` |
| 2 | 2023-05-12 14:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 4 | 2023-05-12 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `3579` |
| 5 | 2023-05-12 19:00 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 | 2023-05-13 16:30 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

Du kan se hur det sammanslagna ID:t löses för varje händelse. Baserat på tidpunkten, det beständiga ID:t och sökningen av identitetsdiagrammet för det angivna namnutrymmet (samtidigt).
När sökningen matchar mer än ett sammanfogat id (som för händelse 7) markeras det lexikografiska första ID som returneras av identitetsdiagrammet (`a.b@yahoo.co.uk` i exemplet).

+++

#### Steg 2: Spela upp sammanfogning igen

Med jämna mellanrum (beroende på vilket uppslagsfönster som har valts) beräknas om sammanfogningar av historiska data baserat på den senaste versionen av identitetsdiagrammet vid tidpunkten för intervallet.

+++ Information

I och med att en upprepningssammanslagning sker 2023-05-13 16:30 med en 24-timmars uppslagsfönsterkonfiguration sys vissa händelser i exemplet om (anges av ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Tid | Beständigt ID<br/>`ECID` | Namnutrymme<br/>`Email` ![Diagram](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Namnlöst ID<br/>(efter livad stygn) | Namnlöst ID<br/>(efter repriser 24 timmar) |
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


I och med att repriser görs vid 2023-05-13 16:30, med en 7-dagars uppslagsfönsterkonfiguration, sammanfogas alla händelser i exemplet på nytt.


| | Tid | Beständigt ID<br/>`ECID` | Namnutrymme<br/>`Email` ![Diagram](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Namnlöst ID<br/>(efter livad stygn) | Namnlöst ID<br/>(efter replay 7 dagar) |
|---|---|---|---|---|---|
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Spela upp](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 | 2023-05-13 16:30 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

#### Steg 3: Begäran om sekretess

När du tar emot en begäran om sekretess, tas det sammanslagna ID:t bort i alla poster för den användare som omfattas av sekretessbegäran.

+++ Information

Följande tabell representerar samma data som ovan, men visar vilken effekt en sekretessbegäran (till exempel 2023-05-13 18:00) har på exempelhändelserna.

| | Tid | Beständigt ID<br/>`ECID` | Namnutrymme<br/>`Email` ![Diagram](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID (after privacy request) |
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00 | `246` | `246`  ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00 | `246` | `246`  ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00 | `246` | `246`  ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00 | `3579` | `3579` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 | 2023-05-13 16:30 | `246` | `246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Länk](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

### Förutsättningar

Följande krav gäller specifikt för diagrambaserad sammanfogning:

- Händelsedatauppsättningen i Adobe Experience Platform, som du vill använda sammanfogning på, måste ha en kolumn som identifierar en besökare på varje rad, **beständigt ID**. Till exempel ett besökar-ID som genererats av ett Adobe Analytics AppMeasurement-bibliotek eller ett ECID som genererats av Adobe Experience Cloud Identity Service.
- Identitetsdiagrammet från Experience Cloud Identity Service måste ha ett namnutrymme (till exempel `Email`, eller `Phone`) som du vill använda vid sammanfogning för att lösa problemet **tillfälligt ID**. Se [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home) för mer information.

>[!NOTE]
>
>Det gör du **not** kräver en Real-time Customer Data Platform-licens för diagrambaserad sammanfogning. The **Välj** eller högre paket med Customer Journey Analytics innehåller de behörigheter som krävs för användaridentitetstjänsten.



### Begränsningar

Följande begränsningar gäller specifikt för diagrambaserad sammanfogning:

- Tidsstämplar beaktas inte när du frågar efter ett tillfälligt ID med det angivna namnutrymmet. Det är alltså möjligt att ett beständigt ID sammanfogas med ett tillfälligt ID från en post som har en tidigare tidsstämpel.
- Inget stöd för delade enheter. När flera identiteter returneras används den första lexikografiska identiteten genom att identitetsdiagrammet efterfrågas med ett namnutrymme.
- I identitetsdiagrammet finns det en hård gräns på tre månader för att efterfylla identiteter. Du använder bakåtfyllnadsidentiteter om du inte använder ett Experience Platform-program, som Real-time Customer Data Platform, för att fylla i identitetsdiagrammet.
- The [Garantier för identitetstjänst](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) gäller. Se till exempel följande [statiska gränser](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
   - Maximalt antal identiteter i ett diagram: 50.
   - Maximalt antal länkar till en identitet för ett enskilt batchintag: 50.
   - Maximalt antal identiteter i en XDM-post för diagraminmatning: 20.
   - Minsta antal identiteter i en XDM-post för pejling: 2.


## Använd stygn

När organisationen uppfyller alla [krav](#prerequisites) och förstår vanliga [begränsningar](#limitations) och specifik metod för stygn ([fältbaserad](#limitations-1) och [diagrambaserad](#limitations-2)) kan du följa de här stegen när du vill börja använda häftning i Customer Journey Analytics.

### Alternativ

Välj alternativ för sammanfogning. Paketet Customer Journey Analytics avgör vilka alternativ som är tillgängliga för inledande varaktighet för bakåtfyllnad, uppslagsfönster, uppspelningsfrekvens och maximalt antal datauppsättningar som tillåts för sammanfogning. Se [Customer Journey Analytics produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html) för mer information.

| | Customer Journey Analytics<br/>Välj | Customer Journey Analytics<br/>Prime | Customer Journey Analytics<br/>Ultimate |
|---|---|---|---|
| Varaktighet för engångssammanfogning av bakfyllning | 13 månader | 13 månader | 25 månader |
| Fönster för uppspelning och uppspelningsfrekvens | <li>1 dag, varje dag</li><li>upp till 7 dagar, varje vecka</li> | <li>1 dag, varje dag</li><li>upp till 14 dagar, varje vecka</li> | <li>1 dag, varje dag</li><li>upp till 30 dagar, varje vecka</li> |
| Högsta antal datauppsättningar som tillåts för sammanfogning | 5 | 10 | 50 |

### Begär support

1. Kontakta Adobe kundsupport med följande information:

   - En begäran om aktivering av sammanfogning.
   - Datauppsättnings-ID för den datauppsättning som du vill ändra inmatning för.
   - Kolumnnamnet (identitetssökväg och namnutrymme) för det beständiga ID:t för den önskade datauppsättningen (identifieraren som visas på varje rad).
   - För fältbaserad sammanfogning är kolumnnamnet för det tillfälliga ID:t för den önskade datauppsättningen (personidentifieraren, som också fungerar som en länk mellan datauppsättningar i samband med en anslutning). För diagrambaserad sammanfogning används det identitetsnamnutrymme som ska användas för att fråga efter identitetsdiagrammet.
   - Du kan välja mellan uppslagsfönster och uppspelningsfrekvens. Se ditt Customer Journey Analytics-paket för [alternativ](#options) tillgängliga.
   - Namn på sandlåda.


2. Adobe kundsupport samarbetar med Adobe och gör det möjligt att sy ihop bilder när du får din begäran. När den är aktiverad visas en ny inmatad datauppsättning som innehåller en ny kolumn för sammanfogade ID i Adobe Experience Platform. Adobe kundsupport kan ange den nya datauppsättningens ID.

3. När Adobe aktiveras första gången fylls data i baklänges. Se ditt Customer Journey Analytics-paket för [option](#options) tillgängliga.

4. Om du vill använda den nya sammanfogade datauppsättningen i en flerkanalsanalys måste du lägga till den nya sammanfogade datauppsättningen i en [anslutning](../connections/overview.md) i Customer Journey Analytics. Lägg sedan till andra datauppsättningar som krävs för flerkanalsanalys och välj rätt person-ID för varje datauppsättning.

5. [Skapa en datavy](/help/data-views/create-dataview.md) baserat på anslutningen.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

När datavyn har konfigurerats kan du köra din Customer Journey Analytics-rapportanalys över olika kanaler och enheter.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->

