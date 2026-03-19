---
title: Aktivera textning
description: Aktivera identitetssammanfogning för händelsedatamängder i Customer Journey Analytics. Lär dig hur du konfigurerar beständiga ID:n, person-ID:n och spelar om fönster i gränssnittet för anslutningar för att sammanfoga data.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: 9a1689d9-c1b7-42fe-9682-499e49843f76
source-git-commit: 1ad1698f10dd026b0bd5e67599ef35ab3c552286
workflow-type: tm+mt
source-wordcount: '1728'
ht-degree: 0%

---

# Aktivera sammanfogning

Du kan aktivera sammanfogning för en eller flera händelsedatamängder som du har konfigurerat som en del av anslutningen. Det Customer Journey Analytics-paket du har licensierat avgör hur många händelsedatamängder du kan aktivera för sammanfogning.

Du aktiverar sammanfogning som en del av [datauppsättningsinställningarna](/help/connections/create-connection.md#dataset-settings) för en händelsedatamängd när du [skapar en anslutning](/help/connections/create-connection.md) eller när du [redigerar en anslutning](/help/connections/manage-connections.md#edit-a-connection).

## Förutsättningar

Du måste kontrollera och uppfylla kraven för sammanfogningsmetoden som du anger: [fältbaserad sammanfogning](fbs.md#prerequisites) eller [diagrambaserad sammanfogning](gbs.md#prerequisites).


## Preflight-kontroller

Om du uppfyller kraven kan du utföra vissa preflight-kontroller av data i händelsedatauppsättningen innan du aktiverar identitetssammanfogning:

* Om du ska använda XDM-schemafält för beständigt ID eller person-ID kontrollerar du att identiteterna är korrekt markerade i schemat för händelsedatamängden. [Se Översikt över namnområde för identitet](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces).
* Verifiera identitetstäckning för både beständigt ID och person-ID:

   * **Beständigt ID**

     Fråga 7 dagar efter data där det beständiga ID-fältet inte är null och dividera med en fråga på 7 dagar med data för alla händelser i datauppsättningen. Procentandelen bör vara över 95 %.

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


   * **Person-ID**
      * För diagrambaserade sammanfogningar måste identitetsdiagrammet innehålla fragment som länkar ID-värden från det valda beständiga ID-namnutrymmet och ID-namnutrymmet. Du kan köra ett test genom att gå till [Experience Platform Identity Graphics Viewer](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer){target="_blank"} och fråga diagrammet efter några beständiga ID-värden. Kontrollera om dessa beständiga ID-värden är länkade till värden för person-ID i diagrammet.
      * För fältbaserad sammanfogning frågar du 7 dagar med data där ditt person-ID-fält inte är null och dividerar med en fråga på 7 dagar med data för alla händelser i din datamängd. Den här procentandelen bör helst vara över 5 procent.

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



## Aktivera identitetssammanfogning {#enable-identity-stitching}

Du kan aktivera identitetssammanfogning när du [lägger till](/help/connections/create-connection.md#add-datasets) eller [redigerar](/help/connections/create-connection.md#edit-a-dataset) en händelsedatamängd i en personbaserad anslutning. Identitetssammanfogning är inte tillgängligt för kontobaserade anslutningar.

>[!CONTEXTUALHELP]
>id="connection_changeto_identitygraph"
>title="Ändra till identitetsdiagram"
>abstract="Kontrollera att du har avslutat konfigurationen av identitetsdiagrammet innan du använder identitetsdiagrammet för sammanfogning."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/gbs" text="Diagrambaserad utjämning"

>[!CONTEXTUALHELP]
>id="connection_stitching_personid"
>title="Person-ID"
>abstract="Välj ett person-ID (den unika identifieraren för en person) bland de tillgängliga identiteterna. Om din licens innehåller diagrambaserade stygn och du vill använda den stygningsmetoden väljer du **[!UICONTROL Identity Graph]**."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics"
>title="Värden för textning"
>abstract="Stitching-mått beräknas med en exempeluppsättning data med händelsetidsstämplar från de senaste 7 dagarna.<br>Den här exempeluppsättningen data skiljer sig vanligtvis från exempeldata som används i tabellen **[!UICONTROL Preview]**."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_gbs_personidcoverage"
>title="Täckning för person-ID"
>abstract="Täckningen för det valda person-ID som används för identifiering under sammanslagningsprocessen (live och replay).<br/>För bästa resultat vid sammanfogning bör det finnas en (beständigt ID, person-ID)-relation i identitetsdiagrammet för varje beständigt ID."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_fbs_personidcoverage"
>title="Täckning för person-ID"
>abstract="Täckningen för det valda person-ID som används för identifiering under sammanslagningsprocessen (live och replay).<br/>För bästa sammanfogningsresultat bör person-ID (användarinformation) skickas på minst en händelse för varje beständigt ID (enhetsinformation)."

>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_persistentidcoverage"
>title="Beständig ID-täckning"
>abstract="Det här värdet används för identifiering under sammanfogningsprocessen (live och replay) om ett person-ID-värde inte kan identifieras. <br/>Händelser utan beständigt ID och inget person-ID tas bort från data. För bästa resultat bör ett beständigt ID finnas för alla händelser."


>[!CONTEXTUALHELP]
>id="connection_stitchingmetrics_badids"
>title="Felaktiga ID:n"
>abstract="Felaktiga ID:n är ID-värden som allvarligt påverkar rapporteringsdata."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/badids" text="Felaktiga ID:n"


### Inställningar för datauppsättning

Om du vill aktivera sammanfogning går du till händelsedatamängden **[!UICONTROL Datasets settings]** i dialogrutan **[!UICONTROL Add datasets]** eller **[!UICONTROL Edit dataset]**:

![Alternativ för identitetssammanfogning när du aktiverar identitetssammanfogning](assets/identity-stitching-ui.png)

1. Välj **[!UICONTROL Enable identity stitching]**.

   Om du aktiverar eller inaktiverar sammanfogning för en sparad händelsedatamängd i anslutningen visar dialogrutan **[!UICONTROL Change Person ID]** konsekvenserna av en ändring av person-ID. Välj **[!UICONTROL Continue]** om du vill fortsätta.

   Dialogrutan **[!UICONTROL Enable identity stitching]** sammanfattar konsekvenserna av att sy ihop identiteter. Välj **[!UICONTROL Continue]** om du vill fortsätta.

1. Välj ett beständigt ID i listrutan **[!UICONTROL Persistent ID]**.

   Om du väljer **[!UICONTROL Identity Map]** som beständigt ID måste du välja ett namnutrymme. Du har två alternativ:

   * Välj **[!UICONTROL Use primary identity namespace]** om du vill använda det primära identitetsnamnområdet.
   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.

1. Välj ett person-ID i listrutan **[!UICONTROL Person ID]**.

   Om du väljer **[!UICONTROL Identity Map]** som person-ID måste du välja ett namnutrymme. Du har två alternativ:

   * Välj **[!UICONTROL Use primary identity namespace]** om du vill använda det primära identitetsnamnområdet.
   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.


   Om du väljer **[!UICONTROL Identity Graph]** som person-ID (om du vill använda [diagrambaserad sammanfogning](/help/stitching/gbs.md)) måste du välja ett namnutrymme.

   >[!NOTE]
   >
   >Se till att du har rätt att använda identitetsdiagrammet.
   >

   Innan dess visas en **[!UICONTROL Change to identity graph]**-dialogruta för att kontrollera att du har slutfört konfigurationen av identitetsdiagrammet för datauppsättningen. Den här inställningen är en del av de [diagrambaserade förutsättningarna](/help/stitching/gbs.md#prerequisites) innan du kan använda identitetsdiagrammet för stygn. Välj **[!UICONTROL Continue]** om du vill fortsätta.

   * Välj ett namnutrymme i listrutan **[!UICONTROL Namespace]**.

1. Välj ett uppspelningsfönster i listrutan **[!UICONTROL Replay window]**. Vilka alternativ som är tillgängliga beror på vilket Customer Journey Analytics-paket du har rätt till.

1. Välj **[!UICONTROL Next]** om du vill se en förhandsvisning av händelsedatamängden som ska sammanfogas.


### Förhandsgranska datauppsättningar

>[!AVAILABILITY]
>
>Det utökade **[!UICONTROL Dataset preview]**-gränssnittet (inklusive **[!UICONTROL Stitching metrics]** och **[!UICONTROL Bad IDs]**) som beskrivs i det här avsnittet är i den begränsade testfasen av versionen och är kanske inte tillgängligt än i din miljö. Om den inte är tillgänglig ser du förhandsvisningen av datauppsättningen som en del av **[!UICONTROL Dataset settings]**-gränssnittet. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Customer Journey Analytics funktionsreleaser](/help/release-notes/releases.md).
>

Utöver det vanliga **[!UICONTROL Datasets preview]**-gränssnittet finns två ytterligare informationspaneler tillgängliga när [du lägger till](/help/connections/create-connection.md#add-datasets)- eller [redigerar](/help/connections/create-connection.md#edit-a-dataset)-datauppsättningar i en personbaserad anslutning.

>[!NOTE]
>För kunder som har Customer Journey Analytics i AWS väntar den här funktionen på att släppas.
>

![Alternativ för identitetssammanfogning när du aktiverar identitetssammanfogning](assets/identity-stitching-ui-preview.png)

#### Värden för textning

**[!UICONTROL Stitching metrics]** beräknas med en exempeluppsättning data med händelsetidsstämplar från de senaste 7 dagarna. Den här exempeluppsättningen med data skiljer sig vanligtvis från exempeldata som används i tabellen **[!UICONTROL Preview]**. Stitching metrics are details for:

* **[!UICONTROL Person ID coverage]**: Täckningen för det valda person-ID som används för identifiering under sammanslagningsprocessen (live och replay).
   * För bästa fältbaserade sammanfogningsresultat bör ett person-ID (användarinformation) skickas på minst en händelse för varje beständigt ID (enhetsinformation).
   * För att få bästa möjliga diagrambaserade häftningsresultat bör det finnas en (beständigt ID, person-ID)-relation i identitetsdiagrammet för varje beständigt ID.

  Personens ID-täckning visas som en procentandel och jämförs med vad som rekommenderas för en stabil utveckling eller i en produktionskonfiguration. Ju högre disponeringsvärde, desto bättre sammanfogningsresultat får du med det valda person-ID:t.

* **[!UICONTROL Persistent ID coverage]**: Det här värdet används för identifiering under sammanfogningsprocessen (live och replay) om ett person-ID-värde inte kan identifieras. Händelser utan beständigt ID och inget person-ID tas bort från data. För bästa resultat bör ett beständigt ID finnas för alla händelser.

  Beständig ID-täckning visas som en procentandel och jämförs med vad som är det minsta rekommenderade för en stabil utveckling eller en produktionskonfiguration.


#### Felaktiga ID:n

>[!INFO]
>
>Felaktiga ID:n kallas även BAVID:n i Customer Journey Analytics-gränssnittet.
> 

I Customer Journey Analytics är ett felaktigt ID en identifierare:

* med ett specifikt ID-värde som härstammar från antingen ett beständigt ID eller ett person-ID-fält i sammanfogningsaktiverade datauppsättningar, **och**
* är på mer än en miljon (1 000 000) händelser i anslutningsdata inom en månad.

När ett ID-värde markeras som ett felaktigt ID tas alla framtida händelser som innehåller det ID-värdet bort från anslutningsdata och visas inte i rapporten.

Exempel på användning av felaktiga ID:

* Du har anpassade värden eller platshållarvärden i person-ID-fältet (till exempel `undefined`). Sådana värden kan också påverka [sammanfogning och rapportering av datakvalitet](/help/stitching/faq.md#undefined-person-id-values).
* Om flera personer delar en enhet och det totala antalet övergångar mellan användare överstiger 50 000 i en fältbaserad sammanfogningskonfiguration. I det här scenariot upphör sammanfogningsprocessen att använda informationen om person-ID för den enheten och använder bara beständig ID-information i stället. Följaktligen skickas alla datauppsättningshändelser från den enheten till anslutningsdata med den beständiga ID-identiteten, vilket har stor risk att orsaka en situation med felaktiga ID:n.


>[!NOTE]
>**[!UICONTROL Stitching metrics]**, inklusive **[!UICONTROL Bad IDs]**, beräknas baserat på en begränsad datauppsättning. Information om hur du identifierar att det finns felaktiga ID:n för en datauppsättning som du tänker använda för sammanfogning finns i [tekniken för felaktiga ID:n](/help/technotes/badids.md).
>


### Spara

När du har sparat en anslutning startas sammanfogningsprocessen för sammanfogning av aktiverade datauppsättningar så snart som dataimporten för dessa datauppsättningar börjar.

>[!CAUTION]
>
>För datauppsättningar som har aktiverats för sammanfogning i gränssnittet Anslutningar rapporteras status för bakåtfyllning omedelbart och felaktigt som ![status grön](/help/assets/icons/StatusGreen.svg) **[!UICONTROL _x _-efterfyllningar slutförd]**&#x200B;för antalet slutförda efterfyllningar. Använd andra sätt för att kontrollera om data från den sammanslagna datauppsättningen är efterfyllda.
>


## Begränsningar

Utöver de [fältbaserade syningsbegränsningarna](/help/stitching/fbs.md#limitations) och [diagrambaserade syrebegränsningar](/help/stitching/gbs.md#limitations) gäller följande begränsningar när du aktiverar sydda i gränssnittet Anslutningar:

* Du kan bara sammanfoga en händelsedatamängd en gång som en del av en enda anslutning. Du kan inte definiera samma händelsedatamängd mer än en gång och använda en separat sammanfogningskonfiguration för varje instans. Om du vill använda olika sammanfogningskonfigurationer på samma datauppsättning använder du en separat anslutning för varje konfiguration.


## Migrering

Stitching som är aktiverat i gränssnittet Connections kan användas samtidigt utan problem med begärandebaserad sammanfogning.

Du har t.ex. webbaserade sammanslagna datauppsättningar i datasjön som ett resultat av tidigare eller nuvarande begäran om sammanfogning. Du kan lägga till sammanfogade data från en call-center-datauppsättning med hjälp av gränssnittet Anslutningar för att kombinera dessa data med de webbaserade data.

Så småningom kommer Adobe att migrera dina begärandatabaserade dataset till den nya sammanfogningen av anslutningar.
