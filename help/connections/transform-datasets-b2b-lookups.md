---
title: Omforma datauppsättningar för B2B-sökningar
description: Beskriver hur du omformar data i datauppsättningar för specifika B2B-sökscheman
solution: Customer Journey Analytics
feature: Connections
role: Admin
exl-id: 7729c1b9-b3ed-4662-a446-2088389bbd97
source-git-commit: eef9b420f1016254dece0a916b82bc99e2ca866e
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---

# Omforma datauppsättningar för B2B-sökningar

För att stödja personbaserade sökningar på B2B-data (inklusive konton, affärsmöjligheter, marknadsföringslistor och kampanjer) krävs en omvandling av B2B-sökdata.

Den här omvandlingen är bara tillgänglig för datauppsättningar med data för B2B-sökningsscheman, baserat på följande klasser:

* [XDM Business Account Person Relation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation)
* [XDM-affärsmöjlighet, personrelation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation)
* [XDM Business Marketing List-medlemmar](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members)
* [XDM Business Campaign-medlemmar](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members)

>[!NOTE]
>
>Det finns en gräns på högst 10 000 objekt för varje id. Den här begränsningen innebär att för varje person-ID kan du bara ha 10 000 konton, 10 000 möjligheter, 10 000 marknadsföringslistor eller 10 000 kampanjer.


Så här aktiverar du omformning för en sådan datauppsättning:

![Aktivera omformningsdatauppsättning](assets/transform-dataset.gif)

* Se till att du väljer rätt identifierare för **[!UICONTROL Key]** och **[!UICONTROL Matching key]**, till exempel `personKey.sourceKey`.

* Välj alternativ för att importera nya data och återfyllnad av datauppsättning.

* Välj **[!UICONTROL Transform dataset for B2B lookups]**.

  Det här alternativet omformar datauppsättningen så att den kan användas för personbaserade sökningar i B2B-scenarier.


  >[!IMPORTANT]
  >
  >När den är aktiverad och anslutningen har sparats går omvandlingen inte att ångra. Du kan inte ändra omformningsinställningen för en datauppsättning när en anslutning har sparats, förutom genom att ta bort och lägga till datauppsättningen en gång till i anslutningen.

Så här aktiverar du omformning för en eller flera datauppsättningar som redan ingår i en befintlig anslutning:

1. Ta bort datauppsättningarna från anslutningen.
1. Spara anslutningen.
1. Lägg till datauppsättningarna i anslutningen när du aktiverar omformning för datauppsättningarna.

## Bakgrundinformation

Icke-omformade datauppsättningar, för scheman som baseras på de fyra schemaklasserna som nämns ovan, kan innehålla flera rader för en enskild person-ID. Personbaserade sökningar matchar bara den senaste förekomsten av den person-ID:t, vilket förhindrar en korrekt person-ID-baserad sökning av konton, affärsmöjligheter, marknadsföringslistor eller kampanjer.

Transformeringen ändrar datauppsättningen för var och en av de fyra schemaklasserna (orange i bilden nedan) så att för varje personidentifierare skapas en (objektmatris) för relevanta data (konton, affärsmöjligheter, marknadsföringslistor eller kampanjer) i uppslagsuppsättningarna (rosa i bilden nedan). Med den här omvandlingen kan du arbeta korrekt med person-ID-baserade sökningar.

![B2B-scheman](./assets/b2b-schemas.svg)
