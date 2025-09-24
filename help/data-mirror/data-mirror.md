---
title: Data Mirror - översikt
description: Förstå hur man synkroniserar data mellan inbyggda datalagerlösningar och Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
hide: true
hidefromtoc: true
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: a6cdade9790ef4bc222eb5979b7370f7403b5ad5
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 1%

---

# Experience Platform Data Mirror - översikt

{{release-limited-testing}}

Data Mirror är en Experience Platform-funktion som gör det möjligt att ändra på radnivå från externa databaser till datasjön med hjälp av modellbaserade scheman. Den bevarar datarelationer, tillämpar unikt utseende och stöder versionshantering utan att kräva extraherings-, transformerings- och inläsningsprocesser (ETL) uppströms.

Använd Data Mirror för att synkronisera infogningar, uppdateringar och borttagningar (ändringsbara data) från externa datalagerlösningar som [!DNL Snowflake], [!DNL Azure Databricks] eller [!DNL Google BigQuery] direkt i Experience Platform. Data Mirror hjälper er att bevara databasmodellens struktur och dataintegritet när ni överför data till Experience Platform.


## Funktioner och fördelar

Data Mirror har följande viktiga funktioner för databassynkronisering:

* **Tillämpning av primärnyckel**. Ser till att datauppsättningarna blir unika och förhindrar dubblettposter vid förtäring.
* **Ändringsförslag på radnivå**. Stöder detaljerade dataändringar, inklusive överföringar och borttagningar med precisionskontroll.
* **Schemarelationer**. Aktiverar externa och primära nyckelrelationer mellan datauppsättningar via beskrivningar.
* **Obeställbar händelsehantering**. Bearbetar ändringshändelser med version- och tidsstämpelbeskrivare, även när de kommer ut ur sekvensen.
* **Integrering av direkt lagerställe**. Ansluter till molndatalager som stöds för synkronisering av ändringar i realtid.

Använd Data Mirror för att importera ändringar direkt från era källsystem, tillämpa schemaintegriteten och göra data tillgängliga för analyser, resesamordning och arbetsflöden för regelefterlevnad. Data Mirror eliminerar komplexa ETL-processer i tidigare led och snabbar upp implementeringen genom att möjliggöra direkt spegling av befintliga databasmodeller. Denna eliminering kan förbättra datastyrningen genom exakt kontroll över borttagningar och datahygien.

<!-- Add link when AEP docs are ready... -->

Se även Experience Platform dokumentation om Data Mirror.


## Data Mirror för Customer Journey Analytics

>[!NOTE]
>
>Funktionen Experience Platform Data Mirror för Customer Journey Analytics är tillgänglig i en **offentlig beta** fram till 25 mars 2026. Under betaperioden begränsas uppdateringarna av datainhämtning (CDC) till ett berättigande på 10 miljoner ändringsrader per dag för Customer Journey Analytics. Adobe förbehåller sig rätten att säga upp betaåtkomst till Experience Platform Data Mirror-funktioner om din organisation skulle överskrida denna gräns. Mer information om funktionen, inklusive faktureringskonsekvenser, finns i det här avsnittet av Experience League-dokumentationen.
>

Funktionen Experience Platform Data Mirror för Customer Journey Analytics är tillgänglig för utvalda inbyggda datalagerlösningar ([!DNL Azure Databricks], [!DNL Google BigQuery] och [!DNL Snowflake]). För Customer Journey Analytics-versionen av Data Mirror-funktionen krävs att du har konfigurerat och konfigurerat flera komponenter:

* [Inbyggd lösning för datalager](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)


>[!MORELIKETHIS]
>
>[Data Mirror snabbstartsguide: Spegla och använda modellbaserade data](model-based.md)
>
