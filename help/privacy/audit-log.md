---
title: Granskningsloggar
description: Lär dig hur du visar och hanterar CJA-granskningsloggar.
exl-id: 360609f2-b811-49ee-ad4a-a54ceb23bfa3
source-git-commit: eceea9ef96701f66cceed5bcb50f92588df6e507
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 3%

---

# Granskningsloggar

För att öka insynen i och synligheten för aktiviteter som utförs i systemet kan du med Customer Journey Analytics (CJA) granska användaraktivitet för olika tjänster och funktioner i form av &quot;granskningsloggar&quot;. Loggarna utgör en verifieringskedja som kan hjälpa till med felsökningsproblem och hjälpa ditt företag att effektivt följa företagets policyer för datahantering och krav som t.ex. HIPAA (Health Insurance Portability and Accounability Act).

I grundläggande bemärkelse anger en granskningslogg **som** utförd **vad** och **när**. Varje åtgärd som registreras i en logg innehåller metadata som anger åtgärdstyp, datum och tid, e-post-ID för användaren som utförde åtgärden samt ytterligare attribut som är relevanta för åtgärdstypen.

Det här avsnittet handlar om granskningsloggar i CJA, inklusive hur du visar och hanterar dem i användargränssnittet.

## Åtkomst till granskningsloggar

När funktionen är aktiverad för din organisation samlas granskningsloggarna automatiskt in när aktiviteten inträffar. Du behöver inte aktivera loggsamling manuellt.

För att kunna visa och exportera granskningsloggar måste du ha fått **[!UICONTROL Audit Logs Access]** behörighet för åtkomstkontroll i Adobe Console. Läs mer om hur du hanterar individuella behörigheter för CJA-funktioner i [dokumentation om åtkomstkontroll](../admin/cja-access-control.md).

## Visa granskningsloggen i användargränssnittet

I CJA navigerar du till **[!UICONTROL Tools]** > **[!UICONTROL Audit Logs]**.

Granskningsloggen för i dag och i går visas som standard.

![granskningslogg](assets/audit_ui.png)

Du kan välja vilka kolumner som ska visas genom att gå till kolumnväljaren längst upp till höger.

## Visa information om enskilda loggposter

Dubbelklicka på knappen info (i) bredvid en beskrivning.

![granskningslogg](assets/info-button-audit.png)

Följande objekt visas:

| Objekt | Beskrivning |
| --- | --- |
| Åtgärdsnamn | Här är en lista över möjliga åtgärder: <ul><li>API_Request</li><li>Godkänn</li><li>Skapa</li><li>Redigera</li><li>Exportera</li><li>Login_failed</li><li>Inloggning_lyckades</li><li>Utloggning</li><li>Org_change</li><li>Uppdatera</li><li>Dela</li><li>Överför</li><li>Ogodkänd</li><li>Sluta dela</li></ul> |
| Beskrivning | En sammanfattning av åtgärden, komponenttypen (med ID) och andra värden. |
| Användarnamn | Användaren som utför åtgärden. |
| Komponenttyp | Möjliga komponenttyper är: <ul><li>Anteckning</li><li>Målgrupp</li><li>Beräknade mått</li><li>Anslutning</li><li>Data_grupp</li><li>Data_View (den här komponenttypen innehåller dimensioner och mått)</li><li>Feature_Access</li><li>Filter</li><li>IMS_Org</li><li>Mobil</li><li>Projekt</li><li>Rapport</li><li>Schemalagt_projekt</li><li>Användare</li><li>User_Group</li></ul> |
| IMS-organisations-ID | Ett unikt ID som ges till din instans när du loggar in på Adobe Experience Cloud första gången. Den ska ha följande format: xxx@AdobeOrg. |
| Användar-ID | Ett unikt ID som identifierar användaren som utförde den här åtgärden. |
| Skapad den | När den här åtgärden utfördes. |
| E-post | E-postadressen till användaren som utför åtgärden. |
| Komponent-ID | Ett unikt ID som identifierar komponenten som ska hanteras. |
| Logg-ID | Ett unikt ID som identifierar den här loggposten. |
| Användartyp | Möjliga typer är: IMS, OKTA |

### Filtrera granskningsloggar

Markera trattecknet (![filter](assets/filter-icon.png)) för att visa en lista med filterkontroller för att begränsa resultatet. Endast de sista 1 000 posterna visas, oavsett vilka filter som har valts.

![filter](assets/filters.png)

Följande filter är tillgängliga för granskningshändelser i användargränssnittet:

| Filter | Beskrivning |
| --- | --- |
| [!UICONTROL Date Range] | Filtrera på ett annat datumintervall genom att välja ett annat datum eller markera ett datumintervall genom att dra markören över flera datum. Som standard väljs dagens och gårdagens datum. |
| [!UICONTROL Action] | Filtrera på en eller flera av följande åtgärder: <ul><li>API_Request</li><li>Godkänn</li><li>Skapa</li><li>Redigera</li><li>Exportera</li><li>Login_failed</li><li>Inloggning_lyckades</li><li>Utloggning</li><li>Org_change</li><li>Uppdatera</li><li>Dela</li><li>Överför</li><li>Ogodkänd</li><li>Sluta dela</li></ul> |
| [!UICONTROL User ID] | Filtrera efter en viss användare med användar-ID:t. Du hittar användar-ID:t genom att välja knappen info (i) bredvid ett användarnamn. |
| [!UICONTROL Email] | Filtrera efter en viss användares e-postadress. Du hittar e-postmeddelandet genom att välja knappen info (i) bredvid ett användarnamn. |
| [!UICONTROL Component ID] | Filtrera på ett specifikt komponent-ID. Du hittar användar-ID:t genom att välja knappen info (i) för en önskad komponent. |
| [!UICONTROL Component Type] | Filtrera på en eller flera komponenttyper: <ul><li>Anteckning</li><li>Målgrupp</li><li>Beräknade mått</li><li>Anslutning</li><li>Data_grupp</li><li>Data_vy</li><li>Feature_Access</li><li>Filter</li><li>IMS_Org</li><li>Mobil</li><li>Projekt</li><li>Rapport</li><li>Schemalagt_projekt</li><li>Användare</li><li>User_Group</li></ul> |

{style=&quot;table-layout:auto&quot;}

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

{style=&quot;table-layout:auto&quot;}

## Hämta granskningsloggar

Du kan hämta granskningsloggar i CSV- eller JSON-format. Alla filter som används eller de markerade kolumnerna återspeglas i de hämtade filerna.

1. Klicka **[!UICONTROL Download]** längst upp till höger på skärmen.
1. Ange formatet.
1. Klicka **[!UICONTROL Download]** igen.

## Hantera granskningsloggar i API

Alla åtgärder som du kan utföra i användargränssnittet kan också utföras med API-anrop. Se [CJA API-referensdokument](https://developer.adobe.com/cja-apis/docs/api/#tag/Audit-Logs) för mer information.
