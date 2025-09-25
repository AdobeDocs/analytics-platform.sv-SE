---
title: Data Mirror - översikt
description: Förstå hur man synkroniserar data mellan inbyggda datalagerlösningar och Customer Journey Analytics
solution: Customer Journey Analytics
feature: Basics
role: Admin
badgePremium: label="Beta"
exl-id: f40e1263-1f4a-416c-a045-15fbe68ce509
source-git-commit: edf7bdac87d9bed48244ad80521bbbf83c48f7b6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 1%

---

# Experience Platform Data Mirror - översikt

{{release-limited-testing}}

Data Mirror är en Experience Platform-funktion som gör det möjligt att ändra på radnivå från externa databaser till datasjön med hjälp av modellbaserade scheman. Det bevarar datarelationer, gör det unikt och stöder versionshantering utan att behöva använda ETL-processer (uppströms extract, transform och load).

Använd Experience Platform Data Mirror för att synkronisera infogningar, uppdateringar och borttagningar (ändringsbara data) från interna externa datalagerlösningar ([!DNL Snowflake], [!DNL Azure Databricks] eller [!DNL Google BigQuery]) direkt med data i Experience Platform. Data Mirror hjälper er att bevara databasmodellens struktur och dataintegritet när ni överför data till Experience Platform.

## Funktioner och fördelar

Data Mirror har följande viktiga funktioner för databassynkronisering:

* **Tillämpning av primärnyckel.** Ser till att datauppsättningar är unika och förhindrar dubblettposter vid förtäring.
* **Ändringsintag på radnivå.** Stöder detaljerade dataändringar, inklusive överföringar och borttagningar med precisionskontroll.
* **Schemarelationer.** Aktiverar externa och primära nyckelrelationer mellan datauppsättningar via beskrivningar.
* **Obeställbar händelsehantering.** Bearbetar ändringshändelser med version- och tidsstämpelbeskrivare, även när de kommer utanför sekvensen.
* **Integrering av direkt lagerställe.** Ansluter till molndatalager som stöds för synkronisering av ändringar i realtid.

Använd Data Mirror för att importera ändringar direkt från era källsystem, tillämpa schemaintegriteten och göra data tillgängliga för analyser, resesamordning och arbetsflöden för regelefterlevnad. Data Mirror eliminerar komplexa ETL-processer i tidigare led och snabbar upp implementeringen genom att möjliggöra direkt spegling av befintliga databasmodeller. Denna eliminering kan förbättra datastyrningen genom exakt kontroll över borttagningar och datahygien.

Se även [Experience Platform-dokumentationen om Data Mirror](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview){target="_blank"}.

## Data Mirror för Customer Journey Analytics

>[!NOTE]
>
>Funktionen Experience Platform Data Mirror för Customer Journey Analytics är tillgänglig i en **offentlig beta** fram till 25 mars 2026. Under betaperioden begränsas uppdateringarna av datainhämtning (CDC) till ett berättigande på 10 miljoner ändringsrader per dag för Customer Journey Analytics. Adobe förbehåller sig rätten att säga upp betaåtkomst till Experience Platform Data Mirror-funktioner om din organisation skulle överskrida denna gräns. Kontakta ditt Adobe-kontoteam om du vill få tillgång till den här funktionen.
>

Experience Platform Data Mirror för Customer Journey Analytics är tillgängligt för utvalda systemspecifika lösningar för datalager ([!DNL Azure Databricks], [!DNL Google BigQuery] och [!DNL Snowflake]). Customer Journey Analytics-versionen av Experience Platform Data Mirror kräver att följande program eller komponenter är korrekt konfigurerade:

* [Inbyggda datalagerlösningar](datawarehouse.md)
* [Experience Platform](aep.md)
* [Customer Journey Analytics](cja.md)

>[!MORELIKETHIS]
>
>[Data Mirror snabbstartsguide: Spegla och använda modellbaserade data](model-based.md)
>>[Data Mirror (Experience Platform-dokumentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-mirror/overview)
>>[Modellbaserade scheman (Experience Platform-dokumentation)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/model-based)
