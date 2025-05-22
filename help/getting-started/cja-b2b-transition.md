---
title: Övergångshandbok
description: Se hur man går över från Customer Journey Analytics till Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B edition"
hide: true
hidefromtoc: true
source-git-commit: c0446bd85b65109fd3311d54e33f9fb33af28f88
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Övergångsguide

{{draft-b2b}}

I den här guiden beskrivs hur du går över från Customer Journey Analytics till B2B edition i Customer Journey Analytics.

Artikeln förutsätter att du redan använder Customer Journey Analytics i viss utsträckning:

* Du har [anslutningar](/help/connections/overview.md) som importerar data till Customer Journey Analytics.
* Du har [datavyer](/help/data-views/data-views.md) som använder data från dessa anslutningar.
* Du har [projekt](/help/analysis-workspace/home.md) med rapporter och visualisering som utnyttjar dessa datavyer.

Om du inte har använt Customer Journey Analytics tidigare läser du [snabbstartsguiden för B2B edition](cja-b2b-quick-start-guide.md).


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
