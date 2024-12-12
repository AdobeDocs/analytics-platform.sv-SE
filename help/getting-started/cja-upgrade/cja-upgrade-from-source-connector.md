---
title: Övergång från Analytics-källkopplingen till Web SDK för Customer Journey Analytics
description: Lär dig hur du går över till SDK för webben från Analytics-kontakten när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: f4fd3c1932a736577d480e86cad70f55de75cb21
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 0%

---

# Övergång från Analytics-källkopplingen till Web SDK för Customer Journey Analytics

>[!NOTE]
> 
>Använd informationen på den här sidan när du besvarar frågor i checklistan för uppgradering av [Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

Det finns nackdelar med att använda Analytics-källkopplingen som enda implementering för Customer Journey Analytics.

Om din organisation redan har uppgraderat till Customer Journey Analytics med enbart implementering av Analytics-källkopplingen rekommenderar Adobe att du går över till en implementering som använder Analytics-källkopplingen (för historiska data), i kombination med en ny implementering av Web SDK (för kontinuerlig datainsamling).

## Förstå fördelar och nackdelar med att endast använda Analytics-källkopplingen

Information om för- och nackdelar med att använda Analytics-källkopplingen finns i [Använd Analytics-källkopplingen enbart för att uppgradera till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-exclusively.md).

## Övergång från Analytics-källkopplingen till Web SDK

Här följer en högnivåprocess för övergång från exklusiv användning av Analytics-källkopplingen till en implementering som består av både Analytics-källkopplingen och en Web SDK-implementering:

1. Skapa en Web SDK-implementering enligt beskrivningen i [Detaljerade rekommenderade uppgraderingssteg](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps) i artikeln [Uppgradera från Adobe Analytics till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md).

   När implementeringen av Web SDK har konfigurerats fortsätter du med följande steg.

1. [Skapa ett XDM-schema för Analytics-källkopplingen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md).

1. Mappa varje Adobe Analytics-dimension från Analytics-källkopplingen till dimensionen i Web SDK-schemat.

   1. 
      <!-- how do you get here -->

   1. Välj fliken **[!UICONTROL Custom]** i avsnittet **[!UICONTROL Map standard fields]**.

   1. Välj **[!UICONTROL Add new mapping]**.

      ![mappa schemafält](assets/schema-mapping.png)

   1. I **[!UICONTROL Source field]** väljer du ett Adobe Analytics-fält i fältgruppen Adobe Analytics ExperienceEvent-mall. I **[!UICONTROL Target field]** markerar du sedan XDM-fältet som du vill mappa det till.

   1. Upprepa den här processen för varje fält i fältgruppen Adobe Analytics ExperienceEvent-mall som du använder för att samla in data i Adobe Analytics.

1. Lägg till datauppsättningen som skapades automatiskt med den ursprungliga Analytics-källkopplingen till din Customer Journey Analytics-anslutning.

   Mer information finns i [Lägg till datauppsättningen från den aktuella Analytics-källkopplingen till anslutningen](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-dataset.md).

1. (Villkorligt) Om du använder uppslagsdatauppsättningar måste du skapa uppslagsdatauppsättningen och lägga till den i anslutningen. Mer information finns i [Skapa uppslagsdatauppsättningar för att klassificera data i Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md).

1. Ta bort den ursprungliga Analytics-källkopplingen. <!-- need to add steps somewhere about how to do this -->

1. [Skapa en ny Analytics-källkoppling och mappningsfält](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md).
