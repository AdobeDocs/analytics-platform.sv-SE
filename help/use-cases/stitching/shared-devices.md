---
title: Delade enheter
description: Förklaring av hur delade enheter hanteras med hjälp av häftning och andra tekniker.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
hide-from-toc: true
role: Admin
source-git-commit: e4e1209ee4f3db7c625770f3e6baa60a74cd45ab
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 2%

---


# Delade enheter

Den här artikeln innehåller kontext på delade enheter, hur du hanterar och minskar data från delade enheter med hjälp av sammanfogning, och hur du förstår exponeringen för delade enheter i dina data med hjälp av frågetjänsten.

## Vad är en delad enhet?

En delad enhet är en enhet som används av mer än en person. Vanliga scenarier är enheter som surfplattor, enheter som används i kioskdatorer eller datorutrustning som delas av agenter i callcenters.

När två personer använder samma enhet och båda gör ett köp kan exempeldata för händelsen se ut så här:

| Tidsstämpel | Sidnamn | Enhets-ID | E-post |
|---|---|---|---|
| 2023-05-12 12:01 | Startsida | 1234 | |
| 2023-05-12 12:02 | Produktsida | 1234 | |
| 2023-05-12 | Orderlyckade | 1234 | <ryan@a.com> |
| 2023-05-12 | Produktsida | 1234 | |
| 2023-05-12 12:08 | Orderlyckade | 1234 | <cassidy@a.com> |

Orderhändelserna (köp) tilldelar korrekta data till rätt e-postadress. Hur tilldelningen påverkar er analys beror på hur ni utför analysen:

- Enhetscentrerad metod: analys utförd med enhets-ID. På så sätt inkluderas både autentiserade och icke-autentiserade data i analysen. Detta tillvägagångssätt tillåter dock inte en mer personbaserad analys.
- Personcentrerad metod: analys utförd med e-postadress eller annan personidentifierare. På så sätt inkluderas endast autentiserade händelser i analysen. Detta tillvägagångssätt ger ingen fullständig bild av kundresan, inklusive förvärv

## Förbättra personcentrerad analys

För att förbättra personcentrerad analys av delade enheter har du två alternativ: du kan använda sammanfogning eller så kan du implementera funktionen för återställning av ECID. Båda metoderna beskrivs närmare i avsnitten nedan.

### Stitlar

Sammanfogningsprocessen åtgärdar den brist på personcentrerad strategi som uppstår. Med Stitching läggs den valda personidentifieraren (i exempeldata, e-postadressen) till i händelser där den identifieraren inte finns. Stitching utnyttjar en mappning mellan enhets-ID:n och person-ID:n för att säkerställa att både autentiserad och oautentiserad trafik kan användas i analysen, så att den är personcentrerad. Mer information finns i [Stitching](/help/stitching/overview.md).

Stitching kan attribuera delade enhetsdata med antingen senaste-auth-attribuering eller enhetsdelad attribuering. Implementeringsändringar via ECID-återställning kan dock även gälla delade enheter.


#### Senaste auktoriseringsattribuering

Senaste autentiseringsattributen för all okänd aktivitet från en delad enhet till den användare som senast autentiserades. Senaste autentisering används i Audience Manager och är det rekommenderade sättet för användning av kunddataprofiler i realtid. Experience Platform Identity Service bygger diagrammet baserat på den senaste autentiseringsattribueringen och används som sådan i diagrambaserade stygn. Mer information finns i [Översikt över regler för länkning av identitetsdiagram](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview).

När du använder senaste-auth-attribuering i sammanfogning kommer Stitched ID:n att matchas enligt tabellen nedan.

| Tidsstämpel | Sidnamn | Enhets-ID | E-post | Namnlöst ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Startsida | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:02 | Produktsida | 1234 | | <cassidy@a.com> |
| 2023-05-12 | Orderlyckade | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 | Produktsida | 1234 | | <cassidy@a.com> |
| 2023-05-12 12:08 | Orderlyckade | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Startsida | 1234 | | <cassidy@a.com> |


#### Enhetsdelning

Enhetsdelning attribuerar anonym aktivitet från en delad enhet till användaren i närmast närhet till den anonyma aktiviteten. Enhetsdelning används för närvarande i fältbaserad sammanfogning. Enhetsdelning är det rekommenderade sättet för analytiska användningsfall eftersom enhetsdelning ger kredit för både oautentiserad och autentiserad aktivitet till närmaste kända person. Enhetsdelning används för närvarande i fältbaserad sammanfogning.

När du använder enhetsdelad attribuering vid sammanfogning, kommer häftade ID:n att matchas enligt tabellen nedan.

| Tidsstämpel | Sidnamn | Enhets-ID | E-post | Namnlöst ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Startsida | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | Produktsida | 1234 | | <ryan@a.com> |
| 2023-05-12 | Orderlyckade | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 | Produktsida | 1234 | | <ryan@a.com> |
| 2023-05-12 12:08 | Orderlyckade | 1234 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Startsida | 1234 | | <cassidy@a.com> |


### ECID-återställning

Som namnet antyder implementerar ECID-återställning funktioner som återställer ECID på en förbestämd utlösare, i de flesta fall en inloggnings- eller utloggningshändelse. Med den här implementeringen får en enda enhet ett nytt ECID varje gång den förbestämda utlösaren aktiveras. Den här återställningen tvingar enheten att bli en *ny enhet* om och om igen från ett dataperspektiv. Återställningen av ECID förhindrar också att delade enheter visas i data. Inga ytterligare algoritmer krävs, men du har ansvaret för att implementera ECID-återställningssignalen som en del av Adobe-datainsamlingsimplementeringen.


När du använder ECID-återställning tolkas kapslade ID:n som i tabellen nedan.

| Tidsstämpel | Sidnamn | Enhets-ID | E-post | Namnlöst ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Startsida | 1234 | | <ryan@a.com> |
| 2023-05-12 12:02 | Produktsida | 1234 | | <ryan@a.com> |
| 2023-05-12 | Orderlyckade | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 | Produktsida | 5678 | | <cassidy@a.com> |
| 2023-05-12 12:08 | Orderlyckade | 5678 | <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Startsida | 5678 | | <cassidy@a.com> |

## Exponering för delad enhet

Tänk på flera faktorer för att förstå hur användbara delade enheter är i din organisation. Dessutom kan en förståelse för hur händelser från delade enheter bidrar till att förstå hur de påverkar den övergripande händelseinformationen som används för analysen.

Om du vill förstå hur den delade enheten exponeras kan du överväga att utföra följande frågor.

1. Förstå antalet enheter som delas. Du kan använda en fråga som räknar de enhets-ID:n som har två eller flera person-ID:n associerade med enhets-ID:t. En exempelfråga kan se ut så här:

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


2. För de delade enheterna, som är ett resultat av den första frågan, måste du förstå hur många händelser av det totala antalet händelser som kan tillskrivas dessa delade enheter. Den här attribueringen ger en bättre bild av hur delade enheter påverkar era data och hur de påverkas när ni utför analyser. En exempelfråga kan se ut så här:

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

3. För de händelser som tilldelas delade enheter (resultatet av den andra frågan) måste du förstå hur många av dessa händelser som INTE har ett person-ID. I annat fall anges hur många av de delade enhetshändelserna som är anonyma händelser. I slutändan påverkar den algoritm (senaste autentisering, enhetsdelning, ECID-reset) som du väljer för att förbättra datakvaliteten dessa anonyma delade enhetshändelser. En exempelfråga kan se ut så här:

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

4. Slutligen vill ni förstå vilken exponering varje kund skulle uppleva på grund av en felklassificering av händelser. För att få denna exponering måste du beräkna procentandelen anonyma händelser för varje delad enhet som relaterar till det totala antalet händelser. En exempelfråga kan se ut så här:

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


