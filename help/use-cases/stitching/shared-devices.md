---
title: Delade enheter
description: Förklaring av hur delade enheter hanteras med hjälp av häftning och andra tekniker.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
source-git-commit: 359fe2a718ccef816377083aceb2652b4a905072
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 0%

---

# Delade enheter

Den här artikeln innehåller kontext på delade enheter, hur du hanterar och minskar data från delade enheter med [sammanfogning](/help/stitching/overview.md) och hur du förstår exponeringen för delade enheter i dina data med hjälp av frågetjänsten.

## Vad är en delad enhet?

En delad enhet är en enhet som används av mer än en person. Vanliga scenarier är enheter som surfplattor, enheter som används i kioskdatorer eller datorutrustning som delas av agenter i ett callcenter.

När två personer använder samma enhet och båda gör ett autentiserat köp kan exempelhändelsedata se ut så här:

| Händelse | Tidsstämpel | Sidnamn | Enhets-ID | E-post |
|--:|---|---|---|---|
| 1 | 2023-05-12 12:01 | Startsida | `1234` | |
| 2 | 2023-05-12 12:02 | Produktsida | `1234` | |
| 3 | 2023-05-12 12:03 | Orderlyckade | `1234` | `ryan@a.com` |
| 4 | 2023-05-12 12:07 | Produktsida | `1234` | |
| 5 | 2023-05-12 12:08 | Orderlyckade | `1234` | `cassidy@a.com` |

Som du kan se i den här tabellen börjar en länk mellan ett enhets-ID och ett person-ID när autentisering sker på händelse 3 och 5. För att förstå effekten av marknadsföringssatsningar på personnivå måste dessa oautentiserade händelser tillskrivas rätt person.

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Förbättra personcentrerad analys

Sammanfogningsprocessen åtgärdar det här attribueringsproblemet genom att lägga till den valda identifieraren (i exempeldata, e-postmeddelandet) till händelser där identifieraren inte finns. Stitching utnyttjar en mappning mellan enhets-ID:n och person-ID:n för att säkerställa att både autentiserad och oautentiserad trafik kan användas i analysen, så att den är personcentrerad. Mer information finns i [Stitching](/help/stitching/overview.md).

Stitching kan attribuera delade enhetsdata med antingen senaste-auth-attribuering eller enhetsdelad attribuering. Alla försök att fästa oautentiserade händelser till en känd användare är icke-deterministiska.


### Senaste auktoriseringsattribuering

Senaste autentiseringsattributen för all okänd aktivitet från en delad enhet till den användare som senast autentiserades. Experience Platform identitetstjänst bygger grafen baserat på den senaste autentiseringsattribueringen och används därför i diagrambaserade stygn. Mer information finns i [Länkningsregler för identitetsdiagram](https://experienceleague.adobe.com/sv/docs/experience-platform/identity/features/identity-graph-linking-rules/identity-optimization-algorithm#identity-optimization-algorithm-details).

När senaste-auth-attribuering används för sammanfogning tolkas Stitched ID:n som i tabellen nedan.

| Tidsstämpel | Sidnamn | Enhets-ID | E-post | Namnlöst ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Startsida | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Produktsida | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:03 | Orderlyckade | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Produktsida | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Orderlyckade | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Startsida | `1234` | | `cassidy@a.com` |


### Enhetsdelning

Enhetsdelning attribuerar anonym aktivitet från en delad enhet till den senaste kända användaren, som tidigare sett. Enhetsdelning används för närvarande i fältbaserad sammanfogning.

När enhetsdelad attribuering används vid sammanfogning tolkas häftade ID:n som i tabellen nedan.

| Tidsstämpel | Sidnamn | Enhets-ID | E-post | Namnlöst ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Startsida | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Produktsida | `1234` | | `ryan@a.com` |
| 2023-05-12 12:03 | Orderlyckade | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Produktsida | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | Orderlyckade | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Startsida | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`| 
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` | 
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` | 
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## Exponering för delad enhet

Tänk på flera faktorer för att förstå hur användbara delade enheter är i din organisation. Dessutom kan en förståelse för hur händelser från delade enheter bidrar till att förstå hur de påverkar den övergripande händelseinformationen som används för analysen.

Om du vill förstå hur den delade enheten exponeras kan du överväga att utföra följande frågor.

1. **Identifiera delade enheter**

   Om du vill förstå hur många enheter som delas kan du utföra en fråga som räknar enhets-ID:n med två eller flera associerade person-ID:n. Detta hjälper till att identifiera enheter som används av flera personer.

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. **Attribution of events to shared devices**

   För de delade enheter som identifieras avgör du hur många händelser av det totala antalet som kan tillskrivas dessa enheter. Den här attribueringen ger insikt i hur delade enheter påverkar era data och vilka konsekvenser de kan få för analysen.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. **Identifiera anonyma händelser på delade enheter**

   Bland de händelser som kan tillskrivas delade enheter kan du identifiera hur många som saknar ett person-ID, vilket anger anonyma händelser. Den algoritm som du väljer (till exempel last-auth, device-split eller ECID-reset) för att förbättra datakvaliteten påverkar dessa anonyma händelser.

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. **Beräkna exponering vid felklassificering av händelser**

   Slutligen, utvärdera den exponering som varje kund kan drabbas av på grund av felklassificering av händelser. Beräkna procentandelen anonyma händelser över det totala antalet händelser för varje delad enhet. Detta bidrar till att förstå den potentiella effekten på kundens datakvalitet.

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```
