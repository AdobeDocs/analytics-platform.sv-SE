---
title: CJA-åtkomstkontroll
description: Läs om kraven för åtkomstkontroll för de tre åtkomstnivåerna i CJA.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: ed1885b4dd560bdbce66a1fa2bad1bcd822a3ea3
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# CJA-åtkomstkontroll

Customer Journey Analytics (CJA) styrs av tre behörighetsnivåer eller tre roller: Produktadministratörsroll, administratörsroll för produktprofil och åtkomst på användarnivå. I det här avsnittet förklaras de här rollerna mer ingående.

## Produktadministratörsroll

Produktadministratörer har behörighet att utföra alla uppgifter som krävs inom CJA. Du måste läggas till som produktadministratör för **Customer Journey Analytics produktprofil** i [Admin Console](https://adminconsole.adobe.com/enterprise/) under Customer Journey Analytics > fliken Administratörer > Lägg till administratör. Produktadministratörer har följande behörigheter:

* Skapa/uppdatera/ta bort anslutningar eller datavyer
* Uppdatera/ta bort projekt, filter, beräknade värden eller filter som skapats av andra användare
* Dela arbetsyteprojekt till alla användare

Det räcker inte att bli produktadministratör i Customer Journey Analytics för att skapa, uppdatera eller ta bort en anslutning. Om du vill skapa en anslutning till en datauppsättning från Experience Platform måste du även ha Experience Platform-behörighet. Du måste vara en del av en **Experience Platform produktprofil** som ger dig följande behörigheter:

* Datamodellering: Visa scheman, hantera scheman
* Datahantering: Visa datauppsättningar, hantera datauppsättningar
* Dataintag: Hantera källor
* Visa identitetsnamnutrymmen

Mer information om behörigheter i Experience Platform finns i [Åtkomstkontroll i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

## Administratörsroll för produktprofil

Den här rollen liknar produktadministratören, men har ett mer begränsat omfång. En produktprofil är en uppsättning behörigheter. En produktprofiladministratör kan till exempel ge åtkomst till alla eller specifika datavyer till medlemmar i en produktprofil. För rapporteringsverktyg kan dessa administratörer lägga till följande behörigheter:

![behörigheter för Admin Console](assets/permissions.png)

## Åtkomst på användarnivå

Icke-produktadministratörer (användare) i Customer Journey Analytics kan inte skapa, redigera eller visa datavyer eller anslutningar. Användare kan skapa filter, projekt, målgrupper och beräknade värden med specialbehörigheter i Admin Console.

## Projektstrukturering för arbetsyta

Mer information om hur du begränsar komponenter (dimensioner, mått, segment, datumintervall) på projektnivån för arbetsytan och hur kursen är kopplad till datavyer finns i [Kuratprojekt](/help/analysis-workspace/curate-share/curate.md).

## Ge åtkomst till enskilda mått eller mått

Du kan inte bevilja eller neka tillstånd för enskilda mått eller mått i Customer Journey Analytics på samma sätt som i vanliga Adobe Analytics. Mätvärden och dimensioner kan ändras i [datavyer](/help/data-views/data-views.md) och kan således komma att ändras i CJA, vilket också ändrar rapporteringen retroaktivt.

