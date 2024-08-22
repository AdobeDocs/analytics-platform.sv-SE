---
title: Delade enheter
description: Förklaring av hur delade enheter hanteras med hjälp av häftning och andra tekniker.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hidefromtoc: true
role: Admin
source-git-commit: 1a5646700dba6362a35158890f2917fc472fbddd
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 0%

---


# Delade enheter

Den här artikeln innehåller kontext på delade enheter, hur du hanterar och minskar data från delade enheter med hjälp av sammanfogning, och hur du förstår exponeringen för delade enheter i dina data med hjälp av frågetjänsten.

## Vad är en delad enhet?

En delad enhet är en enhet som används av mer än en person. Vanliga scenarier är enheter som surfplattor, enheter som används i kioskdatorer eller datorutrustning som delas av agenter i callcenters.

När två personer använder samma enhet och båda gör ett köp kan exempeldata för händelsen se ut så här:

| Tidsstämpel | Sidnamn | Enhets-ID | E-post |
|---|---|---|---|
| 2023-05-12 12:01 | Startsida | `1234` | |
| 2023-05-12 12:02 | Produktsida | `1234` | |
| 2023-05-12 | Orderlyckade | `1234` | `ryan@a.com` |
| 2023-05-12 | Produktsida | `1234` | |
| 2023-05-12 12:08 | Orderlyckade | `1234` | `cassidy@a.com` |

Orderhändelserna (köp) tilldelar korrekta data till rätt e-postadress. Hur tilldelningen påverkar er analys beror på hur ni utför analysen:

- Enhetscentrerad metod: analys utförd med enhets-ID. På så sätt inkluderas både autentiserade och icke-autentiserade data i analysen. Detta tillvägagångssätt tillåter dock inte en mer personbaserad analys.
- Personcentrerad metod: analys utförd med e-postadress eller annan personidentifierare. På så sätt inkluderas endast autentiserade händelser i analysen. Detta tillvägagångssätt ger ingen fullständig bild av kundresan, inklusive förvärv

## Förbättra personcentrerad analys

Exempeldata är en blandning av både autentiserad och oautentiserad aktivitet för samma enhet. Utmaningen är att tilldela en person till den oautentiserade trafiken, så att ni kan utföra en personcentrerad analys och förhindra att kundreseanalyser tar bort aktiviteter som inte har något värde för person-ID. Du kan lösa det här problemet på två sätt: du kan använda häftning eller så kan du implementera funktionen för återställning av ECID. Båda alternativen beskrivs närmare i avsnitten nedan.

### Stitlar

Sammanfogningsprocessen åtgärdar den brist på personcentrerad strategi som uppstår. Med Stitching läggs den valda personidentifieraren (i exempeldata, e-postadressen) till i händelser där den identifieraren inte finns. Stitching utnyttjar en mappning mellan enhets-ID:n och person-ID:n för att säkerställa att både autentiserad och oautentiserad trafik kan användas i analysen, så att den är personcentrerad. Mer information finns i [Stitching](/help/stitching/overview.md).

Stitching kan attribuera delade enhetsdata med antingen senaste-auth-attribuering eller enhetsdelad attribuering. Implementeringsändringar via ECID-återställning kan dock även gälla delade enheter.


#### Senaste auktoriseringsattribuering

Senaste autentiseringsattributen för all okänd aktivitet från en delad enhet till den användare som senast autentiserades. Senaste autentisering används i Audience Manager och är det rekommenderade sättet för användning av kunddataprofiler i realtid. Experience Platform Identity Service bygger diagrammet baserat på den senaste autentiseringsattribueringen och används som sådan i diagrambaserade stygn. Mer information finns i [Översikt över regler för länkning av identitetsdiagram](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview).

När du använder senaste-auth-attribuering i sammanfogning kommer Stitched ID:n att matchas enligt tabellen nedan.

| Tidsstämpel | Sidnamn | Enhets-ID | E-post | Namnlöst ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Startsida | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:02 | Produktsida | `1234` | | `cassidy@a.com` |
| 2023-05-12 | Orderlyckade | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 | Produktsida | `1234` | | `cassidy@a.com` |
| 2023-05-12 12:08 | Orderlyckade | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Startsida | `1234` | | `cassidy@a.com` |


#### Enhetsdelning

Enhetsdelning attribuerar anonym aktivitet från en delad enhet till användaren i närmast närhet till den anonyma aktiviteten. Enhetsdelning används för närvarande i fältbaserad sammanfogning. Enhetsdelning är det rekommenderade sättet för analytiska användningsfall eftersom enhetsdelning ger kredit för både oautentiserad och autentiserad aktivitet till närmaste kända person. Enhetsdelning används för närvarande i fältbaserad sammanfogning.

När du använder enhetsdelad attribuering vid sammanfogning, kommer häftade ID:n att matchas enligt tabellen nedan.

| Tidsstämpel | Sidnamn | Enhets-ID | E-post | Namnlöst ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Startsida | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Produktsida | `1234` | | `ryan@a.com` |
| 2023-05-12 | Orderlyckade | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 | Produktsida | `1234` | | `ryan@a.com` |
| 2023-05-12 12:08 | Orderlyckade | `1234` | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Startsida | `1234` | | `cassidy@a.com` |


### ECID-återställning

Som namnet antyder implementerar ECID-återställning funktioner som återställer ECID på en förbestämd utlösare, i de flesta fall en inloggnings- eller utloggningshändelse. Med den här implementeringen får en enda enhet ett nytt ECID varje gång den förbestämda utlösaren aktiveras. Den här återställningen tvingar enheten att bli en *ny enhet* om och om igen från ett dataperspektiv. Återställningen av ECID förhindrar också att delade enheter visas i data. Inga ytterligare algoritmer krävs, men du har ansvaret för att implementera ECID-återställningssignalen som en del av Adobe-datainsamlingsimplementeringen.


När du använder ECID-återställning tolkas kapslade ID:n som i tabellen nedan.

| Tidsstämpel | Sidnamn | Enhets-ID | E-post | Namnlöst ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Startsida | `1234` | | `ryan@a.com` |
| 2023-05-12 12:02 | Produktsida | `1234` | | `ryan@a.com` |
| 2023-05-12 | Orderlyckade | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 | Produktsida | 5678 | | `cassidy@a.com` |
| 2023-05-12 12:08 | Orderlyckade | 5678 | `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Startsida | 5678 | | `cassidy@a.com` |

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

   För de delade enheter som identifieras avgör du hur många händelser av det totala antalet som kan tillskrivas dessa enheter. Detta ger insikt i vilken påverkan delade enheter har på dina data och vilka konsekvenser de har för analysen.

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


