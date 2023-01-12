---
title: Ingest AEP-målgrupper into Customer Journey Analytics
description: Beskriver hur man importerar AEP-målgrupper till Customer Journey Analytics för vidare analys.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
source-git-commit: 04aaf9ae9f720255c97c9dc148953b5b9d6967ae
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---

# Ingest AEP-målgrupper in i Customer Journey Analytics (CJA)

I det här användningsexemplet utforskas ett tillfälligt, manuellt sätt att föra in Adobe Experience Platform-målgrupper i CJA. Dessa målgrupper kan ha skapats i AEP Segment Builder, Adobe Audience Manager eller andra verktyg och lagras i kundprofilen i realtid (RTCP). Målgrupperna består av en uppsättning profil-ID:n, tillsammans med tillämpliga attribut/händelser/osv. och vi vill ta in dem i CJA Workspace för analys.

## Förutsättningar

* Tillgång till Adobe Experience Platform (AEP), särskilt kundprofil i realtid.
* Tillgång till att skapa/hantera AEP-scheman och datauppsättningar.
* Tillgång till AEP Query Service (och möjlighet att skriva SQL) eller ett annat verktyg för att utföra vissa ljusomvandlingar.
* Tillgång till Customer Journey Analytics. Du måste vara CJA-produktadministratör för att kunna skapa/ändra CJA-anslutningar och datavyer.
* Möjlighet att använda Adobe-API:er (segmentering, eventuellt andra)

## Steg 1: Välj målgrupp(er) i kundprofilen i realtid {#audience}

Adobe Experience Platform [Kundprofil i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP) ger en helhetsbild av varje enskild kund genom att kombinera data från flera kanaler, inklusive online, offline, CRM och tredje part.

Du har förmodligen redan målgrupper i RTCP som kan ha kommit från olika källor. Välj en eller flera målgrupper att importera till CJA.

## Steg 2: Skapa en profilunionsdatauppsättning för exporten

För att kunna exportera målgruppen till en datauppsättning som sedan kan läggas till i en anslutning i CJA måste du skapa en datauppsättning vars schema är en profil [Unionsschema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).

Unionsscheman består av flera scheman som delar samma klass och har aktiverats för profilen. Med unionsschemat kan du se en sammanslagning av alla fält i scheman som delar samma klass. Kundprofilen i realtid använder unionsschemat för att skapa en helhetsbild av varje enskild kund.

## Steg 3: Exportera en målgrupp till profilunionens datauppsättning via API-anrop {#export}

Innan du kan hämta en målgrupp till CJA måste du exportera den till en AEP-datauppsättning. Detta kan bara göras med segmenterings-API:t, och specifikt med [API-slutpunkt för exportjobb](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en).

Du kan skapa ett exportjobb med valfritt målgrupps-ID och skicka resultatet i den AEP-datauppsättning för profilunionen som du skapade i steg 2. Även om du kan exportera olika attribut/händelser för målgruppen behöver du bara exportera det specifika profil-ID-fält som matchar det person-ID-fält som används i den CJA-anslutning som du kommer att använda (se steg 5 nedan).

## Steg 4: Redigera exportutdata

Resultaten av exportjobbet måste omvandlas till en separat profildatauppsättning för att kunna hämtas till CJA.  Den här omvandlingen kan göras med [AEP-frågetjänst](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en)eller något annat omformningsverktyg. Vi behöver bara profil-ID (som matchar person-ID:t i CJA) och ett eller flera målgrupps-ID:n för att kunna rapportera i CJA.

Standardexportjobbet innehåller emellertid mer data och därför måste vi redigera dessa utdata för att ta bort överflödiga data, liksom flytta runt saker.  Du måste också skapa ett schema/en datauppsättning först innan du lägger till omformade data i den.

Här är ett exempel på exportutdata i profilunionens datauppsättning, **före** redigering:

![Ej redigerade utdata](../assets/export-unedited.png)

Observera följande:

* Målgrupps-ID:t finns under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* Statusen måste vara&quot;realiserad&quot;,&quot;införd&quot;, men inte&quot;avslutad&quot;.

Det här är formatet på profildatauppsättningen som du kan skicka till CJA.

![Redigerade utdata](../assets/export-edited.png)

Här är de dataelement som måste finnas:

* `_aresprodvalidation` strängfält: Hänvisar till ditt organisations-ID. Din blir annorlunda.
* `personID` strängfält: Det här är det vanliga XDM-schemafältet för profildatauppsättningar som identifierar personen. Använd profil-ID:t från exporten.
* `audienceMembershipId` strängfält: Målgrupps-ID från exporten.  OBS! Det här fältet kan namnges vad du vill (från ditt eget schema).
* Lägg till ett eget namn för målgruppen (`audienceMembershipIdName`), till exempel

   ![Eget målgruppsnamn](../assets/audience-name.png)

* Lägg till andra målgruppsmetadata om du vill.

## Steg 5: Lägg till den här profildatauppsättningen i en befintlig anslutning i CJA

Du kan [skapa en ny anslutning](/help/connections/create-connection.md), men de flesta kunder vill lägga till profildatauppsättningen i en befintlig anslutning. Målgrupps-ID:n&quot;berikar&quot; befintliga data i CJA.

## Steg 6: Ändra befintlig (eller skapa ny) CJA-datavy

Lägg till `audienceMembershipId`, `audienceMembershipIdName` och `personID` till datavyn.

## Steg 7: Rapport på arbetsytan

Nu kan du rapportera om `audienceMembershipId`, `audienceMembershipIdName` och `personID` i Workspace.

## Ytterligare information

* Du bör utföra den här processen regelbundet så att målgruppsdata uppdateras kontinuerligt i CJA.
* Du kan importera flera målgrupper inom en enda CJA-anslutning. Detta gör processen ännu mer komplicerad, men det är möjligt. För att detta ska fungera måste du göra några ändringar i ovanstående process:
   1. Utför den här processen för varje målgrupp i målgruppssamlingen inom RTCP.
   1. CJA har stöd för arrayer/objektarrayer i profildatamängder. Använda en [array med objekt](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/object-arrays.html?lang=en) för publikenMembershipId eller audiensMembershipIdName är det bästa alternativet.
   1. I datavyn skapar du en ny dimension med hjälp av delsträngsomformningen på `audienceMembershipId` fält för att konvertera den kommaavgränsade värdesträngen till en array. OBS! det finns för närvarande en gräns på 10 värden i arrayen.
   1. Nu kan du rapportera om den nya dimensionen `audienceMembershipIds` i CJA Workspace.
