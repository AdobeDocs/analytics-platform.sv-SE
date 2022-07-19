---
title: CJA-åtkomstkontroll
description: Lär dig mer om åtkomstkontrollkrav för att skapa anslutningar, lägga till datauppsättningar, skapa datavyer osv.
solution: Customer Journey Analytics
feature: CJA Basics
source-git-commit: 13513561ec288c1f4ab69128769cd0e7c059e44b
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# CJA-åtkomstkontroll

Om du vill skapa anslutningar, lägga till datauppsättningar och så vidare, behöver du följande behörigheter i [Admin Console](https://adminconsole.adobe.com/enterprise/):

* Om du vill få åtkomst till Customer Journey Analytics eller skapa en anslutning måste du lägga till som administratör för **Customer Journey Analytics** i [Admin Console](https://adminconsole.adobe.com/enterprise/). Produktadministratörer har följande behörigheter:
   * Skapa/uppdatera/ta bort anslutningar eller datavyer
   * Uppdatera/ta bort projekt, filter, beräknade värden eller filter som skapats av andra användare
   * Dela ett Workspace-projekt till alla användare
* Det räcker inte att bli produktadministratör i Customer Journey Analytics för att skapa, uppdatera eller ta bort en anslutning. Om du vill skapa en anslutning till en datauppsättning från Experience Platform måste du även ha Experience Platform-behörighet. Du måste vara en del av en **Experience Platform produktprofil** som ger dig följande behörigheter:
   * Visa scheman
   * Hantera scheman
   * Visa identitetsnamnutrymmen
   * Visa datauppsättningar

Mer information om behörigheter i Experience Platform finns i [Åtkomstkontroll i Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html).

>[!NOTE]
>
>Du kan inte bevilja eller neka tillstånd för enskilda mått eller mått i Customer Journey Analytics på samma sätt som i vanliga Adobe Analytics. Mätvärden och dimensioner kan ändras i [datavyer](/help/data-views/data-views.md) och kan således komma att ändras i CJA, vilket också ändrar rapporteringen retroaktivt.

## Användaråtkomst

Icke-produktadministratörer (användare) i Customer Journey Analytics kan inte visa datavyer eller anslutningar, men kan skapa filter, projekt och beräknade värden.