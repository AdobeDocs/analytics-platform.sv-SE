---
title: Komponentinställningar
description: Visa huvudinställningar för en datavykomponent.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: aa0a6715c216730e0768cfa870ea75f315455101
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 0%

---

# Komponentinställningar

Följande information beskriver de inställningar som används av en datavykomponent.

![Komponentinställningar som beskrivs i det här avsnittet](../assets/component-settings.png)

| Inställning | Beskrivning/användningsfall |
| --- | --- |
| [!UICONTROL Component type] | Obligatoriskt. Gör att du kan ändra en komponent från Mått till Dimension eller tvärtom. Om du ändrar den här listrutan flyttas komponenten till respektive komponentområde. |
| [!UICONTROL Component Name] | Obligatoriskt. Här kan du ange ett eget namn som visas i Analysis Workspace. Du kan byta namn på en komponent för att ge den ett namn som är specifikt för datavyn. |
| [!UICONTROL Description] | Valfritt, men rekommenderas. Ger information om komponenten till andra användare. |
| [!UICONTROL Tags] | Valfritt. Gör att du kan tagga komponenten med egna eller färdiga taggar för enklare sökning/filtrering i Analysis Workspace-gränssnittet. |
| [!UICONTROL Context labels] | Valfritt. En nedrullningsbar lista med tillgängliga systemdefinierade etiketter som kan användas på en komponent. Dessa etiketter kan behövas för att definiera en uppsättning komponenter som används för rapportering i Analysis Workspace-projekt eller paneler. |
| [!UICONTROL Schema field name] | Schemafältets namn. |
| [!UICONTROL Dataset type] | Obligatoriskt. Ett icke-redigerbart fält som visar vilken datamängdstyp (händelse, sökning eller profil) som komponenten kommer från. |
| [!UICONTROL Dataset] | Ett icke-redigerbart fält som visar vilken datamängd som komponenten kommer från. Det här fältet kan innehålla flera datauppsättningar. |
| [!UICONTROL Schema Type] | Ett icke redigerbart fält som visar komponentens datatyp. Även om du kan använda en schemafälttyp som stöds i Platform, stöds inte alla fälttyper i Customer Journey Analytics. Följande datatyper stöds: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`och `Boolean`. Endast `String` schemadatatyp tillåts i uppslagsdatauppsättningar för närvarande. |
| [!UICONTROL Component ID] | Obligatoriskt. The [CUSTOMER JOURNEY ANALYTICS API](https://adobe.io/cja-apis/docs) använder det här fältet för att referera till komponenten. Varje komponent i en datavy måste vara unik. Adobe genererar automatiskt ett ID för varje komponent, men du kan klicka på redigeringsikonen och ändra komponent-ID:t. Om du ändrar komponent-ID bryts alla befintliga arbetsyteprojekt som innehåller den här komponenten. Även om varje komponent behöver ett unikt ID i en enda datavy, kan du använda samma komponent-ID i andra datavyer. Om du använder samma komponent-ID i andra datavyer kan du göra arbetsyteprojekt kompatibla över datavyer. <br/>För profil- och uppslagsbaserade komponenter har komponent-ID ett ID-prefix baserat på datauppsättnings-ID (till exempel: `642b28fcc1f0ee1c074265a0.person.name.firstName`). När du vill återanvända en profil- eller uppslagsbaserad komponent, som `person.name.firstName`, i ditt Workspace-projekt och konfigurera den här komponenten i olika datavyer, se till att du byter namn på komponent-ID:t unikt (till exempel: `myUniqueID.person.name.firstName`) i alla datavyer. |
| [!UICONTROL Path] | Obligatoriskt. Ett icke-redigerbart fält som visar den schemasökväg som komponenten kommer från. |
| [!UICONTROL Data Usage Labels] | Alla dataanvändningsetiketter som har tilldelats den här komponenten i Adobe Experience Platform. [Läs mer](/help/data-views/data-governance.md). |
| [!UICONTROL Hide component in reporting] | Gör att du kan strukturera komponenten utanför datavyn för icke-administratörer. Administratörer kan fortfarande komma åt den genom att klicka på [!UICONTROL Show All Components] i ett Analysis Workspace-projekt. |

{style="table-layout:auto"}

Här är en video om komponentinställningar i datavyer:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
