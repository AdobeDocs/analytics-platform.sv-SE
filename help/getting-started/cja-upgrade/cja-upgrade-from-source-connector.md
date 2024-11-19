---
title: Gå från Analytics-källkopplingen till Web SDK för Customer Journey Analytics
description: Lär dig hur du går över till Web SDK från Analytics-källkopplingen när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: a1feb2e8458169ed208da2c42fab62d25e1015bb
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 0%

---

# Gå från Analytics-källkopplingen till Web SDK för Customer Journey Analytics

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i checklistan för uppgradering av [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Det finns nackdelar med att använda Analytics-källkopplingen som enda implementering för Customer Journey Analytics. Om din organisation redan har uppgraderat till Customer Journey Analytics med enbart källkopplingsimplementeringen i Analytics bör du överväga att gå över till en Web SDK-implementering.

Adobe rekommenderar att du använder Analytics-källkopplingen (för att hämta in historiska data) i kombination med en ny implementering av Web SDK (för kontinuerlig datainsamling).

## Förstå fördelar och nackdelar med att endast använda Analytics-källkopplingen

Information om för- och nackdelar med att använda Analytics-källkopplingen finns i [Använd Analytics-källkopplingen enbart för att uppgradera till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Gå från Analytics-källkopplingen till Web SDK

Här följer en högnivåprocess för att gå från källkopplingen för Analytics till en implementering som består av både källkopplingen för Analytics och en Web SDK-implementering:

1. Skapa en Web SDK-implementering, enligt beskrivningen i [Detaljerade rekommenderade uppgraderingssteg](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) i artikeln [Uppgradera från Adobe Analytics till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   När implementeringen av Web SDK har konfigurerats fortsätter du med följande steg.

1. Bestäm om du ska använda Adobe Analytics-schemat eller ett XDM-schema i Web SDK-implementeringen.

   Mer information finns i [Välj schema för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

1. (Villkorligt) Om du tänker använda Adobe Analytics-schemat med din Web SDK-implementering lägger du till datauppsättningen som skapades automatiskt av Analytics-källkopplingen till din Customer Journey Analytics-anslutning.

   Mer information finns i [Lägg till datakällans anslutningsdatauppsättning för Analytics i anslutningen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Villkorligt) Om du tänker skapa ett XDM-schema som ska användas med Web SDK-implementeringen:

   1. [Skapa ett XDM-schema för Analytics-källkopplingen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

   1. Lägg till datauppsättningen som skapades automatiskt med den ursprungliga Analytics-källkopplingen till din Customer Journey Analytics-anslutning.

      Mer information finns i [Lägg till datauppsättningen från den aktuella Analytics-källkopplingen till anslutningen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

   1. Ta bort den ursprungliga Analytics-källkopplingen. <!-- need to add steps somewhere about how to do this -->

   1. [Skapa en ny Analytics-källkoppling och mappningsfält](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
