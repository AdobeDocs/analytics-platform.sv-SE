---
title: Granskningsloggar
description: Lär dig hur du visar och hanterar Customer Journey Analytics granskningsloggar.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
feature: Privacy
role: Admin
source-git-commit: 9ed7b541ebb1a89b286040c4ea96025b08029499
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 1%

---

# Granskningsloggar {#audit-logs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_userid"
>title="Användar-ID"
>abstract="Du hittar användar-ID:t genom att klicka på informationsknappen i en loggpost som innehåller den önskade användaren."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="tools_auditlog_componentid"
>title="Komponent-ID"
>abstract="Komponent-ID:t hittas genom att klicka på knappen info på en loggpost som innehåller den önskade komponenten."

<!-- markdownlint-enable MD034 -->


För att öka insynen i och synligheten för aktiviteter som utförs i systemet kan du med Adobe Customer Journey Analytics granska användaraktiviteter för olika tjänster och funktioner i form av &quot;granskningsloggar&quot;. Loggarna utgör en verifieringskedja som kan hjälpa till med felsökningsproblem och hjälpa ditt företag att effektivt följa företagets policyer för datahantering och krav som t.ex. HIPAA (Health Insurance Portability and Accounability Act).

I grundläggande bemärkelse anger en granskningslogg **vem** utförde **vad**-åtgärden och **när**. Varje åtgärd som registreras i en logg innehåller metadata som anger åtgärdstyp, datum och tid, e-post-ID för användaren som utförde åtgärden samt ytterligare attribut som är relevanta för åtgärdstypen.

Det här avsnittet handlar om granskningsloggar i Customer Journey Analytics, inklusive hur du visar och hanterar dem i användargränssnittet.

## Åtkomst till granskningsloggar

När funktionen är aktiverad för din organisation samlas granskningsloggarna automatiskt in när aktiviteten inträffar. Du behöver inte aktivera loggsamling manuellt.

För att kunna visa och exportera granskningsloggar måste du ha beviljats åtkomstkontrollbehörighet **[!UICONTROL Audit Logs Access]** i Adobe Console. Mer information om hur du hanterar enskilda behörigheter för Customer Journey Analytics-funktioner finns i [åtkomstkontrollsdokumentationen](../technotes/access-control.md).

## Visa granskningsloggen i användargränssnittet

I Customer Journey Analytics går du till **[!UICONTROL Tools]** > **[!UICONTROL Audit Logs]**.

Granskningsloggen för i dag och i går visas som standard.

![Granskningsloggmarkering idag och i går. ](assets/audit_ui.png)

Du kan välja vilka kolumner som ska visas genom att gå till kolumnväljaren längst upp till höger.

## Visa information om enskilda loggposter

Dubbelklicka på knappen info (i) bredvid en beskrivning.

![Granskningslogg som markerar informationsknappen. ](assets/info-button-audit.png)

Följande objekt visas:

* **[!UICONTROL Action Name]**: Den åtgärd som utfördes. Möjliga värden är:
   * API_REQUEST: Alla åtgärder utlöser en backend API-begäran. Information visas om vad API-begäran var.
   * GODKÄNNANDE: En godkännandeåtgärd utfördes.
   * CREATE: En Skapa-åtgärd utfördes.
   * DELETE: En raderingsåtgärd utfördes.
   * REDIGERA: En redigeringsåtgärd utfördes.
   * EMBARGO: När du begränsar en begäran i [Rapporteringsaktivitetshanteraren](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/reporting-activity-manager/reporting-activity-cancel-requests) registreras åtgärden i granskningsloggen under EMBARGO.
   * EXPORT: En exportåtgärd utfördes.
   * ORG_CHANGE: En åtgärd för organisationsändring utfördes.
   * UPPDATERA: En uppdateringsåtgärd utfördes.
   * DELA: En delningsåtgärd utfördes.
   * ÖVERFÖRING: En överföringsåtgärd utfördes.
   * OGODKÄND: En åtgärd av typen &quot;unGodkänn&quot; utfördes.
   * UNSHARE: En åtgärd av typen unshare utfördes.
* **[!UICONTROL Date Created]**: Datum och tid då åtgärden utfördes.
* **[!UICONTROL Description]**: En sammanfattning av åtgärden.
* **[!UICONTROL User Name]**: Användaren som utförde åtgärden. Ibland kanske användarnamnet saknas. Du bör använda funktionen [Produktanvändning](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/tools/product-usage/usage-overview) eftersom den alltid innehåller inloggningsnamnet.
* **[!UICONTROL Email]**: E-postadressen till användaren som utförde åtgärden.
* **[!UICONTROL Component Name]**: Komponenten som användaren utförde en åtgärd på.
* **[!UICONTROL Component Type]**: Komponenttypen. Möjliga värden är:
   * ANTECKNING
   * MÅLGRUPP
   * CALCULATED_METRIC
   * ANSLUTNING
   * DATA_GROUP
   * DATA_VIEW
   * DATASET_STITCHING
   * DATE_RANGE
   * FEATURE_ACCESS
   * FILTER
   * IMS_ORG
   * MOBILE
   * PROJEKT (Workspace)
   * RAPPORT
   * SCHEDULED_PROJECT
   * ANVÄNDARE
   * USER_GROUP
* **[!UICONTROL Component ID]**: ID:t för komponenten som användaren vidtagit åtgärder för.
* **[!UICONTROL IMS Org ID]**: Organisationens IMS-ID i formatet `ABC123@AdobeOrg`.
* **[!UICONTROL Log ID]**: Ett unikt ID som identifierar loggposten.
* **[!UICONTROL User ID]**: Det unika ID:t som identifierar användaren som utförde åtgärden.
* **[!UICONTROL User Type]**: Autentiseringstypen som används. Giltiga värden är:
   * IMS
   * OKTA

### Filtrera granskningsloggar

Markera trattikonen (![filter](assets/filter-icon.png)) om du vill visa en lista med filterkontroller för att begränsa resultatet. Endast de sista 1 000 posterna visas, oavsett vilka filter som har valts.

![Granskningslogg som visar de filter som visas för datumintervall.](assets/filters.png)

Följande filter är tillgängliga för granskningshändelser i användargränssnittet:

| Filter | Beskrivning |
| --- | --- |
| [!UICONTROL Date Range] | Filtrera på ett annat datumintervall genom att välja ett annat datum eller markera ett datumintervall genom att dra markören över flera datum. Som standard väljs dagens och gårdagens datum. |
| [!UICONTROL Action] | Filtrera på ett åtgärdsnamn som listas ovan. |
| [!UICONTROL User ID] | Filtrera efter en viss användare med användar-ID:t. Du hittar användar-ID:t genom att välja knappen info (i) bredvid ett användarnamn. |
| [!UICONTROL Email] | Filtrera efter en viss användares e-postadress. Du hittar e-postmeddelandet genom att välja knappen info (i) bredvid ett användarnamn. |
| [!UICONTROL Component ID] | Filtrera på ett specifikt komponent-ID. Du hittar användar-ID:t genom att välja knappen info (i) för en önskad komponent. |
| [!UICONTROL Component Type] | Filtrera på någon av komponenttyperna ovan. |

{style="table-layout:auto"}

## Händelsetyper som hämtats av granskningsloggar

I följande tabell visas vilka åtgärder för vilka komponenttyper som registreras av granskningsloggar:

| Komponenttyp | Åtgärder |
| --- | --- |
| [!UICONTROL Annotation] | <ul><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL Audience] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li><li>Exportera</li><li>Uppdatera</li></ul> |
| [!UICONTROL Calculated Metric] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL Connection] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL Data View] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL Date Range] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL Filter] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL IMS Org] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL Project] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL Report] | <ul><li>API_Request</li></ul> |
| [!UICONTROL Scheduled Project] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL User] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |
| [!UICONTROL User Group] | <ul><li>API_Request</li><li>Skapa</li><li>Ta bort</li><li>Redigera</li></ul> |

{style="table-layout:auto"}

## Hämta granskningsloggar

Du kan hämta granskningsloggar i CSV- eller JSON-format. Alla filter som används eller de markerade kolumnerna återspeglas i de hämtade filerna.

1. Klicka på **[!UICONTROL Download]** längst upp till höger på skärmen.
1. Ange formatet.
1. Klicka på **[!UICONTROL Download]** igen.

## Hantera granskningsloggar i API

Alla åtgärder som du kan utföra i användargränssnittet kan också utföras med API-anrop. Mer information finns i [Customer Journey Analytics API-referensdokumentet](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs).
