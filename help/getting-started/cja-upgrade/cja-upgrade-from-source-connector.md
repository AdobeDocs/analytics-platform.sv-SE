---
title: Övergång från Analytics-källkopplingen till Web SDK för Customer Journey Analytics
description: Lär dig hur du går över till Web SDK från Analytics-källkopplingen när du uppgraderar till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4c0eef7d-7b0e-43b5-8126-d84d4fffd80c
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 0%

---

# Övergång från Analytics-källkopplingen till Web SDK för Customer Journey Analytics {#transition-from-source-connector}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector"
>title="Implementering av källanslutning för analyser"
>abstract="Med Analytics-källkopplingen kan ni enkelt få värde från Customer Journey Analytics, men kräver att ni betalar för både Adobe Analytics och Customer Journey Analytics. Den här guiden hjälper dig att gå mot en oberoende implementering av SDK för webben."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-delete"
>title="Ta bort den befintliga Analytics-källkopplingen"
>abstract="Analyskällans koppling som du har för närvarande är inte kompatibel med organisationens anpassade schema. Data finns dock fortfarande i analysrapportsviten. I det här steget tas den aktuella Analytics-källkopplingen bort så att du kan återskapa den med rätt schema i ett efterföljande steg.<br><br>Innan du tar bort källkopplingen kanske du vill samordna med andra i organisationen för att säkerställa att borttagningen av källkopplingen inte påverkar rapporteringen inom organisationen. Denna samordning kan ta flera veckor."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Det finns nackdelar med att använda Analytics-källkopplingen som enda implementering för Customer Journey Analytics.

Om din organisation redan har uppgraderat till Customer Journey Analytics med enbart källanslutningskomplementeringen för Analytics rekommenderar Adobe att man går över till en ny implementering av Web SDK för kontinuerlig datainsamling och använder källkopplingen för Analytics endast för historiska data.

## Förstå fördelar och nackdelar med att endast använda Analytics-källkopplingen

Information om för- och nackdelar med att använda Analytics-källkopplingen finns i [Använd Analytics-källkopplingen enbart för att uppgradera till Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-alternative-source-connector.md).

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

{{upgrade-final-step}}
