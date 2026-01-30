---
title: Använd stygn
description: Hur du använder stygn
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 9ace0679796c3a813b1fbd97c62c20faf64db211
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 0%

---

# Använd stygn

Du kan aktivera sammanfogning för en eller flera händelsedatamängder som du har konfigurerat som en del av anslutningen. Det Customer Journey Analytics-paket du har licensierat avgör hur många händelsedatamängder du kan aktivera för sammanfogning.

Du kan aktivera sammanfogning som en del av [datauppsättningsinställningarna](/help/connections/create-connection.md#dataset-settings) för en händelsedatauppsättning när du [skapar en anslutning](/help/connections/create-connection.md) eller när du [redigerar en anslutning](/help/connections/manage-connections.md#edit-a-connection).

## Förutsättningar

Så här aktiverar du sammanfogning av en händelsedatamängd i anslutningsgränssnittet:

* Schemat som datauppsättningen baseras på ska ha:

   * flera fält som är konfigurerade som en identitet och som gör att du kan välja olika värden för ett beständigt ID och ett person-ID.
   * minst ett fält som är markerat som primär identitet med ett associerat namnutrymme om du vill använda identitetskartan och det primära ID-namnutrymmet för ett beständigt ID eller person-ID.

* Om du vill använda diagrambaserad sammanfogning och du förväntar dig att händelsedatamängden ska bidra till identitetsdiagrammet (eftersom datamängden innehåller relevanta person-ID:n bredvid beständiga ID:n), bör du [aktivera datamängden för identitetstjänsten](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).

## Preflight-kontroller

Om du uppfyller kraven kan du utföra vissa preflight-kontroller av data i händelsedatauppsättningen innan du aktiverar identitetssammanfogning:

* Se till att identiteterna är korrekt markerade i schemat för händelsedatamängden. [Se Översikt över namnområde för identitet](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces).
* Verifiera identitetstäckning för både beständigt ID och person-ID:
   * Beständigt ID: Fråga efter 7 dagars data där ditt beständiga ID-fält inte är null och dividera med en fråga på 7 dagars data för alla händelser i datauppsättningen. Procentandelen bör vara över 95 %.

     Exempel på en fråga som du kan använda för verifiering:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSISTENT_ID_FIELD}) AS events_with_persistentid,
       ROUND(COUNT({PERSISTENT_ID_FIELD}) / COUNT(*), 2) AS percent_with_persistentid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Var:

      * `{PERSISTENT_ID_FIELD}` är fältet för det beständiga ID:t. Till exempel: `identityMap.ecid[0]`.
      * `{DATASET_TABLE_NAME}` är tabellnamnet för händelsedatamängden.
      * `{FORMAT_STRING}` är formatsträngen för tidsstämpelfältet. Till exempel: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE} ` är startdatum. Till exempel: `2024-01-01 00:00:00`.
      * `{END_DATE}` är slutdatumet i standardformat. Till exempel: `2024-01-08 00:00:00`.


   * Person-ID - Fråga 7 dagar efter data där ditt person-ID-fält inte är null och dividera med en fråga på 7 dagar med data för alla händelser i din datauppsättning. Procentandelen bör vara över 5%.

     Exempel på en fråga som du kan använda för verifiering:

     ```sql
     SELECT
       COUNT(*) AS total_events,
       COUNT({PERSON_ID_FIELD}) AS events_with_personid,
       ROUND(COUNT({PERSON_ID_FIELD}) / COUNT(*), 2) AS percent_with_personid_not_null
     FROM 
       {DATASET_TABLE_NAME}
     WHERE
       TO_TIMESTAMP(timestamp, '{FORMAT_STRING}') >= TIMESTAMP '{START_DATE}'
       AND TO_TIMESTAMP(timestamp, 'FORMAT_STRING') < TIMESTAMP '{END_DATE}';
     ```

     Var:

      * `{PERSON_ID_FIELD}` är fältet för person-ID:t. Till exempel: `identityMap.crmId[0]`.
      * `{DATASET_TABLE_NAME}` är tabellnamnet för händelsedatamängden.
      * `{FORMAT_STRING}` är formatsträngen för tidsstämpelfältet. Till exempel: `MM/DD/YY HH12:MI AM`.
      * `{START_DATE}` är startdatum. Till exempel: `2024-01-01 00:00:00`.
      * `{END_DATE}` är slutdatumet i standardformat. Till exempel: `2024-01-08 00:00:00`.



## Aktivera identitetssammanfogning

>[!NOTE]
>
>Om **[!UICONTROL Enable identity stitching]** inte är tillgängligt i gränssnittet Anslutningar använder du [förfrågningsproceduren för att aktivera sammanfogning](/help/stitching/use-stitching.md) för en datauppsättning.



Om du vill aktivera sammanfogning går du till händelsedatamängdsavsnittet i dialogrutan **[!UICONTROL Add datasets]** eller **[!UICONTROL Edit dataset]**:

![Alternativ för identitetssammanfogning när du aktiverar identitetssammanfogning](assets/identity-stitching-ui.png)

1. Välj **[!UICONTROL Enable identity stitching]**.

   Om du aktiverar sammanfogning för en befintlig händelsedatamängd visar dialogrutan **[!UICONTROL Change Person ID]** konsekvenserna av en ändring av person-ID på grund av användningen av sammanfogning. Välj **[!UICONTROL Continue]** om du vill fortsätta.

   Dialogrutan **[!UICONTROL Enable identity stitching]** sammanfattar konsekvenserna av att sy ihop identiteter. Välj **[!UICONTROL Continue]** om du vill fortsätta.

1. Välj ett beständigt ID i listrutan **[!UICONTROL Persistent ID]**.

   Om du väljer **[!UICONTROL Identity Map]** som beständigt ID måste du välja ett namnutrymme. Du har två alternativ:

   * Aktivera **[!UICONTROL Use primary identity namespace]** att använda det primära identitetsnamnområdet.
   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.

1. Välj ett person-ID i listrutan **[!UICONTROL Person ID]**.

   Om du väljer **[!UICONTROL Identity Map]** som person-ID måste du välja ett namnutrymme. Du har två alternativ:

   * Aktivera **[!UICONTROL Use primary identity namespace]** att använda det primära identitetsnamnområdet.
   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.


   Om du väljer **[!UICONTROL Identity Graph]** som person-ID (om du vill använda [diagrambaserad sammanfogning](/help/stitching/gbs.md)) måste du välja ett namnutrymme.

   >[!NOTE]
   >
   >Se till att du har rätt att använda identitetsdiagrammet.
   >

   Innan dess visas en **[!UICONTROL Change to identity graph]**-dialogruta för att kontrollera att du har [slutfört konfigurationen av identitetsdiagrammet för datauppsättningen](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) innan du använder identitetsdiagrammet för sammanfogning. Välj **[!UICONTROL Continue]** om du vill fortsätta.

   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.


1. Välj ett uppslagsfönster i listrutan **[!UICONTROL Lookback window]**. Vilka alternativ som är tillgängliga beror på vilket Customer Journey Analytics-paket du har rätt till.

När du har sparat en anslutning aktiveras sammanfogningsprocessen för datauppsättningar som är aktiverade för sammanfogning när dataanvändningen för dessa datauppsättningar börjar.

>[!CAUTION]
>
>För datauppsättningar som har aktiverats för sammanfogning i gränssnittet Anslutningar rapporteras status för bakåtfyllning omedelbart och felaktigt som ![status grön](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _-efterfyllningar slutförd]**för antalet slutförda efterfyllningar. Använd andra sätt för att kontrollera om data från den sammanslagna datauppsättningen är efterfyllda.
>


## Begränsningar

Utöver de [fältbaserade syningsbegränsningarna](/help/stitching/fbs.md#limitations) och [diagrambaserade syrebegränsningar](/help/stitching/gbs.md#limitations) gäller följande begränsningar när du aktiverar sydda i gränssnittet Anslutningar:

* Du kan bara sammanfoga en händelsedatamängd en gång som en del av en enda anslutning. Du kan inte definiera samma händelsedatamängd mer än en gång och använda en separat sammanfogningskonfiguration för varje instans. Om du vill använda olika sammanfogningskonfigurationer på samma datauppsättning använder du en separat anslutning för varje konfiguration.


## Migrering

Stitching som är aktiverat i gränssnittet Connections kan användas samtidigt utan problem med begärandebaserad sammanfogning.

Du har t.ex. webbaserade sammanslagna datauppsättningar i datasjön som ett resultat av tidigare eller nuvarande begäran om sammanfogning. Du kan lägga till sammanfogade data från en call-center-datauppsättning med hjälp av gränssnittet Anslutningar för att kombinera dessa data med de webbaserade data.

Så småningom kommer Adobe automatiskt att migrera dina begärandatabaserade dataset till den nya sammanfogningen av anslutningar.
