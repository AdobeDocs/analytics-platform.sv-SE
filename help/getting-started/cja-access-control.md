---
title: CJA-åtkomstkontroll
description: Lär dig mer om åtkomstkontrollkrav för att skapa anslutningar, lägga till datauppsättningar, skapa datavyer osv.
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
source-git-commit: c80c10e1e4887bfe7fdc3b59d0dfe415b1b0d5eb
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---

# CJA-åtkomstkontroll

För att få tillgång till och utföra åtgärder i Customer Journey Analytics måste du lägga till som administratör i **Customer Journey Analytics produktprofil** i [Admin Console](https://adminconsole.adobe.com/enterprise/). Produktadministratörer har följande behörigheter:

* Skapa/uppdatera/ta bort anslutningar eller datavyer
* Uppdatera/ta bort projekt, filter, beräknade värden eller filter som skapats av andra användare
* Dela arbetsyteprojekt till alla användare

## Nödvändiga Adobe Experience Platform-behörigheter

Det räcker inte att bli produktadministratör i Customer Journey Analytics för att skapa, uppdatera eller ta bort en anslutning. Om du vill skapa en anslutning till en datauppsättning från Experience Platform måste du även ha Experience Platform-behörighet. Du måste vara en del av en **Experience Platform produktprofil** som ger dig följande behörigheter:

* Visa scheman
* Hantera scheman
* Visa identitetsnamnutrymmen
* Visa datauppsättningar

Mer information om behörigheter i Experience Platform finns i [Åtkomstkontroll i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

## Ge åtkomst till enskilda mått eller mått

Du kan inte bevilja eller neka tillstånd för enskilda mått eller mått i Customer Journey Analytics på samma sätt som i vanliga Adobe Analytics. Mätvärden och dimensioner kan ändras i [datavyer](/help/data-views/data-views.md) och kan således komma att ändras i CJA, vilket också ändrar rapporteringen retroaktivt.

## Användaråtkomst

Icke-produktadministratörer (användare) i Customer Journey Analytics kan inte visa datavyer eller anslutningar, men kan skapa filter, projekt och beräknade värden.

