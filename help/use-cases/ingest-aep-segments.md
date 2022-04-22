---
title: Ingest AEP-målgrupper into Customer Journey Analytics
description: Beskriver hur man importerar AEP-målgrupper till Customer Journey Analytics för vidare analys.
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: ed01fd0899cac21fff156e0c31dc2b52ff7c8cca
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 0%

---


# Ingest AEP-målgrupper in i Customer Journey Analytics (CJA)

>[!NOTE]
>
>Det här avsnittet är under uppbyggnad.

(Brandon, fyi, &#39;Unified Profile&#39; är en föråldrad term för &#39;kundprofil i realtid&#39; - enligt AEP:s doc manager. Du hittar inget dokument på UP i AEP-dokumentuppsättningen.)

I det här användningsexemplet utforskas ett tillfälligt, manuellt sätt att föra in Adobe Experience Platform-målgrupper i CJA. Dessa målgrupper kan ha skapats i AEP Segment Builder, Adobe Audience Manager eller andra verktyg och lagras i kundprofilen i realtid (RTCP). Målgrupperna består av listor med person-ID:n, profil-ID:n osv. och vi vill ta in dem i CJA Workspace för analys.

## Förutsättningar

* Tillgång till Adobe Experience Platform (AEP), särskilt kundprofil i realtid.
* Åtkomst till Customer Journey Analytics
* Kan du skriva egen kod?
* Vad annat.

## Steg 1: Välj målgrupp(er) i kundprofilen i realtid {#audience}

Adobe Experience Platform [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP) ger en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive online, offline, CRM och tredje part. Du har förmodligen redan målgrupper i RTCP som kan ha kommit från olika källor. Välj en eller flera målgrupper.

## Steg 2: Skapa en profilunionsdatauppsättning för exporten

För att kunna exportera målgruppen till en datauppsättning som sedan kan ansluta till CJA måste du skapa en datauppsättning vars schema är en profil [Unionsschema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Unionsscheman består av flera scheman som delar samma klass och har aktiverats för profilen. Med unionsschemat kan du se en sammanslagning av alla fält i scheman som delar samma klass. Kundprofilen i realtid använder unionsschemat för att skapa en helhetsbild av varje enskild kund.

## Steg 3: Exportera en målgrupp till en datauppsättning via API-anrop {#export}

Innan du kan hämta en målgrupp till CJA måste du exportera den till en datauppsättning i AEP. Detta kan bara göras med segmenterings-API:t, och specifikt med [API-slutpunkt för exportjobb](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). Du kan skapa ett exportjobb och skicka resultaten i den AEP-datauppsättning för profilunion som du skapade i steg 2.

## Steg 4: Redigera exportutdata

När vi skapar exportjobbet för en målgrupp behöver vi bara person-ID:t och målgrupps-ID:t för att kunna rapportera i CJA. Standardexportjobbet innehåller emellertid fler data och därför måste vi redigera dessa utdata för att ta bort överflödiga data.

Här är ett exempel på exportutdata i profilunionens datauppsättning, **före** redigering:

![Ej redigerade utdata](assets/export-unedited.png)

Observera följande:

* Målgrupps-ID:t finns under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Statusen måste vara&quot;realiserad&quot;,&quot;införd&quot;, men inte&quot;avslutad&quot;. Ersätt &quot;avslutad&quot; med &quot;tom&quot;.

Det här är formatet på profildatauppsättningen som du kan skicka till CJA.

![Redigerade utdata](assets/export-edited.png)

Här är de dataelement som måste finnas:

* `_aresprodvalidation`: Hänvisar till ditt organisations-ID. Din blir annorlunda.
* `personID`: I det här fallet ett eget namn
* `audienceMembershipIdList` strängfält: Målgrupps-ID
* Lägg till ett eget namn för målgruppen (`audienceMembershipIdName`), till exempel

   ![Eget målgruppsnamn](assets/audience-name.png)

## Steg 5: Skapa en anslutning i CJA till den här profildatauppsättningen

[Skapa en anslutning](/help/connections/create-connection.md)

## Steg 6: Skapa en datavy

Lägg till `audienceMembershipIdName` och `personID` till datavyn.

## Steg 7: Rapport på arbetsytan

Nu kan du rapportera om `audienceMembershipIdName` och `personID` i Workspace.
Skärmdump vore bra.

Så här gör du:

skriva upp fler steg för när ni har att göra med personer som är medlemmar i flera olika målgrupper.




