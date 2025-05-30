---
title: Övergångshandbok
description: Se hur man går över från Customer Journey Analytics till Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
source-git-commit: 2fad11178853e08783b8f48671b504f50b6e0770
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# Övergångsguide

{{draft-b2b}}

I den här guiden beskrivs hur du går över från Customer Journey Analytics till B2B edition i Customer Journey Analytics.

Artikeln förutsätter att du redan använder Customer Journey Analytics i viss utsträckning:

* Du har [anslutningar](/help/connections/overview.md) som importerar data till Customer Journey Analytics.
* Du har [datavyer](/help/data-views/data-views.md) som använder data från dessa anslutningar.
* Du har [projekt](/help/analysis-workspace/home.md) med rapporter och visualiseringar som utnyttjar dessa datavyer.

Om du inte har använt Customer Journey Analytics tidigare läser du [snabbstartsguiden för B2B edition](cja-b2b-quick-start-guide.md).

Om du är Adobe Analytics-användare och tänker använda Customer Journey Analytics B2B edition ska du först läsa [uppgraderingen från Adobe Analytics till dokumentationen för Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md).


## Befintlig implementering

Den befintliga implementeringen av Customer Journey Analytics förändras inte alls när du har licensierats och etablerats för Customer Journey Analytics B2B edition.

Alla befintliga anslutningar betraktas som [personbaserade anslutningar](cja-b2b-concepts-features.md#connections-and-identifiers) och fortsätter att fungera utan någon uppdatering. Allt som bygger på data från de här personbaserade anslutningarna, som datavyer, arbetsyteprojekt, segment, schemalagd export, varningar med mera, fortsätter att fungera som det ursprungligen var planerat och tänkt.

>[!IMPORTANT]
>
>Du kan inte ändra befintliga personbaserade anslutningar till en kontobaserad anslutning. Det krävs en ny kontobaserad anslutning för att B2B edition-funktionerna ska kunna användas.
>


## Implementera B2B-funktioner

Om du vill implementera B2B-funktioner i din befintliga implementering måste du göra följande:

1. Modellera era B2B-data. Customer Journey Analytics B2B edition förutsätter åtminstone kontobaserade tidsseriedata och drar nytta av ytterligare profil- eller sökpostdata. som kontodata, köp av gruppdata, affärsmöjlighetsdata, medlemsdata i marknadsföringslistan med mera.

   * Ange vilken identifierare som du vill använda som primär kontoidentifierare (konto-ID). Ett befintligt CRM-verktyg eller ett annat verktyg (till exempel Demandbase) hjälper dig att identifiera den identifieraren.
   * Identifiera ytterligare identifierare för de andra B2B-data som du tänker använda: global kontoidentifierare, affärsmöjlighets-ID, inköpsgrupps-ID och personidentifierare.

1. Förbered era B2B-data. Se till att ni lägger till och samlar in kontoidentifierare för alla tidsseriens händelsedata och relevanta postdata. Se också till att dina händelsedata för tidsserier och sökningsposten innehåller andra identifierare för relevanta händelser. En händelse som till exempel signalerar flytten till en annan försäljningsfas bör ha en affärsmöjlighets-ID. Och den identifieraren bör ingå i dina sökdata för affärsmöjligheter.

1. [Skapa en ny kontobaserad anslutning](/help/connections/create-connection.md#account-based-connection). Välj vilka valfria behållare du vill inkludera, [lägg till datauppsättningar](/help/connections/create-connection.md#add-datasets) och definiera [inställningarna för varje datauppsättning](/help/connections/create-connection.md#dataset-settings). Använd [match efter container](cja-b2b-concepts-features.md#match-by-container) för att söka efter postdatauppsättningar när det är möjligt.

1. [Skapa datavyer](/help/data-views/create-dataview.md) baserat på din nya anslutning.

   * Se till att du lägger till alla relevanta fält som mätvärden eller dimensioner från de data du har kapslat.
   * Använd komponentinställningar (som beständighet, attribuering med mera) om det behövs.
   * Lägg till ytterligare härledda fält där det är lämpligt.

1. [Skapa arbetsyteprojekt](/help/analysis-workspace/build-workspace-project/create-projects.md) för att rapportera och få insikter om dina B2B-data. Använd specifika B2B-funktioner, som [containers](cja-b2b-concepts-features.md#containers), för att få djupgående insikter.

   Du kan kombinera rapporter och insikter från B2B (personbaserade) och B2B (kontobaserade) genom att använda flera [paneler](/help/analysis-workspace/c-panels/panels.md) i ett arbetsyteprojekt.
