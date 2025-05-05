---
title: Engagera Adobe Experience Platform-målgrupper i Customer Journey Analytics
description: Beskriver hur man importerar Adobe Experience Platform-målgrupper till Customer Journey Analytics för vidare analys.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '968'
ht-degree: 0%

---

# Engagera Adobe Experience Platform-målgrupper i Adobe Customer Journey Analytics

I det här användningsexemplet utforskas ett tillfälligt, manuellt sätt att föra ut Adobe Experience Platform (Adobe Experience Platform)-målgrupper till Customer Journey Analytics. Dessa målgrupper kan ha skapats i Adobe Experience Platform Segment Builder, Adobe Audience Manager eller andra verktyg och lagras i kundprofilen i realtid (RTCP). Målgrupperna består av en uppsättning profil-ID:n, tillsammans med tillämpliga attribut/händelser/osv. och vi vill föra in dem i Customer Journey Analytics Workspace för analys.

## Förutsättningar

* Tillgång till Adobe Experience Platform (Adobe Experience Platform), särskilt kundprofil i realtid.
* Tillgång till att skapa/hantera Adobe Experience Platform-scheman och datauppsättningar.
* Tillgång till Adobe Experience Platform Query Service (och möjlighet att skriva SQL) eller ett annat verktyg för att utföra vissa ljusomvandlingar.
* Tillgång till Customer Journey Analytics. Du måste vara produktadministratör för Customer Journey Analytics för att kunna skapa/ändra Customer Journey Analytics-anslutningar och datavyer.
* Möjlighet att använda Adobe-API:er (segmentering, eventuellt andra)

## Steg 1: Välj målgrupp(er) i kundprofilen i realtid {#audience}

Med Adobe Experience Platform [kundprofil för realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv) (RTCP) kan du se en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive online, offline, CRM och tredje part.

Du har förmodligen redan målgrupper i RTCP som kan ha kommit från olika källor. Välj en eller flera målgrupper att importera till Customer Journey Analytics.

## Steg 2: Skapa en profilunionsdatauppsättning för exporten

Om du vill exportera målgruppen till en datauppsättning som till slut kan läggas till i en anslutning i Customer Journey Analytics måste du skapa en datauppsättning vars schema är en [unionsschema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=sv-SE#understanding-union-schemas) för profilen.

Unionsscheman består av flera scheman som delar samma klass och har aktiverats för profilen. Med unionsschemat kan du se en sammanslagning av alla fält i scheman som delar samma klass. Kundprofilen i realtid använder unionsschemat för att skapa en helhetsbild av varje enskild kund.

## Steg 3: Exportera en målgrupp till profilunionens datauppsättning via API-anrop {#export}

Innan du kan ta in en målgrupp i Customer Journey Analytics måste du exportera den till en Adobe Experience Platform-datauppsättning. Detta kan bara göras med segmenterings-API:t, och specifikt med [API-slutpunkten för exportjobb](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=sv-SE).

Du kan skapa ett exportjobb med det målgrupps-ID du väljer och skicka resultatet i den Adobe Experience Platform-datauppsättning för profilunionen som du skapade i steg 2. Även om du kan exportera olika attribut/händelser för målgruppen behöver du bara exportera det specifika profil-ID-fält som matchar det person-ID-fält som används i den Customer Journey Analytics-anslutning som du ska använda (se steg 5 nedan).

## Steg 4: Redigera exporten

Resultaten av exportjobbet måste omvandlas till en separat profildatauppsättning för att kunna hämtas till Customer Journey Analytics.  Omvandlingen kan göras med [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=sv) eller något annat omformningsverktyg som du väljer. Vi behöver bara profil-ID (som matchar person-ID:t i Customer Journey Analytics) och ett eller flera målgrupps-ID:n för att kunna rapportera i Customer Journey Analytics.

Standardexportjobbet innehåller emellertid mer data och därför måste vi redigera dessa utdata för att ta bort överflödiga data, liksom flytta runt saker.  Du måste också skapa ett schema/en datauppsättning först innan du lägger till omformade data i den.

Här är ett exempel på exportutdata i profilunionens datauppsättning, **före** redigering:

![Oredigerade utdata](../assets/export-unedited.png)

Observera följande:

* Målgrupps-ID finns under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Statusen måste vara&quot;realiserad&quot;,&quot;införd&quot;, men inte&quot;avslutad&quot;.

Det här är formatet på profildatauppsättningen som du kan skicka till Customer Journey Analytics.

![Redigerade utdata](../assets/export-edited.png)

Här är de dataelement som måste finnas:

* `_aresprodvalidation`-strängfält: Refererar till ditt organisations-ID. Din blir annorlunda.
* `personID` strängfält: Detta är standardfältet för XDM-schema i profildatamängder för att identifiera personen. Använd profil-ID:t från exporten.
* `audienceMembershipId`-strängfält: målar-ID:t från exporten.  Obs! Det här fältet kan namnges vad du vill (från ditt eget schema).
* Lägg till ett eget namn för målgruppen (`audienceMembershipIdName`), till exempel

  ![Eget målgruppsnamn](../assets/audience-name.png)

* Lägg till andra målgruppsmetadata om du vill.

## Steg 5: Lägg till den här profildatauppsättningen i en befintlig anslutning i Customer Journey Analytics

Du kan [skapa en ny anslutning](/help/connections/create-connection.md), men de flesta kunder vill lägga till profildatauppsättningen i en befintlig anslutning. Målgrupps-ID:n&quot;berikar&quot; befintliga data i Customer Journey Analytics.

## Steg 6: Ändra befintlig (eller skapa ny) datavy för Customer Journey Analytics

Lägg till `audienceMembershipId`, `audienceMembershipIdName` och `personID` i datavyn.

## Steg 7: Rapportera i Workspace

Du kan nu rapportera `audienceMembershipId`, `audienceMembershipIdName` och `personID` i Workspace.

## Ytterligare information

* Du bör utföra den här processen regelbundet så att målgruppsdata uppdateras kontinuerligt i Customer Journey Analytics.
* Du kan importera flera målgrupper inom en enda Customer Journey Analytics-anslutning. Detta gör processen ännu mer komplicerad, men det är möjligt. För att detta ska fungera måste du göra några ändringar i ovanstående process:
   1. Utför den här processen för varje målgrupp i målgruppssamlingen inom RTCP.
   1. Customer Journey Analytics har stöd för arrayer/objektarrayer i profildatamängder. Det bästa alternativet är att använda en [array med objekt](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/complex-data/object-arrays.html?lang=sv-SE) för audiensMembershipId eller audiensMembershipIdName.
   1. I datavyn skapar du en ny dimension med delsträngsomformningen i fältet `audienceMembershipId` för att konvertera den kommaavgränsade värdesträngen till en array. Obs! Det finns för närvarande en gräns på 10 värden i arrayen.
   1. Du kan nu rapportera om den nya dimensionen `audienceMembershipIds` i Customer Journey Analytics Workspace.
