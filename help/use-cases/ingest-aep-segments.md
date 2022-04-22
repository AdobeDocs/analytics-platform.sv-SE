---
title: Ingest AEP audiences into Customer Journey Analytics
description: Beskriver hur man importerar AEP-målgrupper till Customer Journey Analytics för vidare analys.
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: cd1d639ad698c188c506881b2b17103b0a3559f2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Ingest AEP-målgrupper in i Customer Journey Analytics (CJA)

(Brandon, fyi, &#39;Unified Profile&#39; är en föråldrad term för &#39;kundprofil i realtid&#39; - enligt AEP:s doc manager. Du hittar inget dokument på UP i AEP-dokumentuppsättningen.)

I det här användningsexemplet utforskas ett tillfälligt, manuellt sätt att föra in Adobe Experience Platform-målgrupper i CJA. These audiences might have been created in the AEP Segment Builder, or Adobe Audience Manager, or other tools, and are stored in Real-time Customer Profile (RTCP). Målgrupperna består av listor med person-ID:n, profil-ID:n osv. och vi vill ta in dem i CJA Workspace för analys.

## Förutsättningar

* Tillgång till Adobe Experience Platform (AEP), särskilt kundprofil i realtid.
* Access to Customer Journey Analytics
* Kan du skriva egen kod?
* What else.

## Steg 1: Välj målgrupp(er) i kundprofilen i realtid {#audience}

Adobe Experience Platform [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP) ger en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive online, offline, CRM och tredje part. You likely already have audiences in RTCP that may have come from various sources. Pick one or more audiences.

## Step 2: Create a Profile Union dataset for the export

För att kunna exportera målgruppen till en datauppsättning som sedan kan ansluta till CJA måste du skapa en datauppsättning vars schema är en profil [Unionsschema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Unionsscheman består av flera scheman som delar samma klass och har aktiverats för profilen. Med unionsschemat kan du se en sammanslagning av alla fält i scheman som delar samma klass. Kundprofilen i realtid använder unionsschemat för att skapa en helhetsbild av varje enskild kund.

## Steg 3: Exportera en målgrupp till en datauppsättning via API-anrop {#export}

Before you can bring an audience into CJA, you need to export it to a dataset in AEP. Detta kan bara göras med segmenterings-API:t, och specifikt med [API-slutpunkt för exportjobb](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). You can create an export job and put the results in the Profile Union AEP dataset you created in Step 2.

## Steg 4: Redigera exportutdata

När vi skapar exportjobbet för en målgrupp behöver vi bara person-ID:t och målgrupps-ID:t för att kunna rapportera i CJA. The standard export job, however, contains more data and so we need to edit this output to remove extraneous data.

Here is an example of the export output in the Profile union dataset, **before** any editing:

![Unedited output](assets/export-unedited.png)

Observera följande:

* Målgrupps-ID:t finns under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* The status has to be &quot;realized&quot;, or &quot;entered&quot;, but not &quot;exited&quot;. Ersätt &quot;avslutad&quot; med &quot;tom&quot;.

This is the format of the Profile dataset that you can send into CJA.

![Redigerade utdata](assets/export-edited.png)

Här är de dataelement som måste finnas:

* `_aresprodvalidation`: Refers to your Organization ID. Din blir annorlunda.
* `personID`: I det här fallet ett eget namn
* `audienceMembershipIdList` strängfält: Målgrupps-ID
* Add a friendly name for the audience (`audienceMembershipIdName`), such as

   ![Eget målgruppsnamn](assets/audience-name)

## Step 5: Create a connection in CJA to this Profile dataset

[Create a connection](/help/connections/create-connection.md)

## Steg 6: Skapa en datavy

Lägg till `audienceMembershipIdName` och `personID` till datavyn.

## Step 7: Report in Workspace

Nu kan du rapportera om `audienceMembershipIdName` och `personID` i Workspace.
Skärmdump vore bra.

Så här gör du:

write up more steps for when you are dealing with people who are members of multiple audiences.




