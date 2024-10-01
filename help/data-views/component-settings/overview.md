---
title: Komponentinställningar
description: Visa huvudinställningar för en datavykomponent.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: a236b2126c4b998b4d97caab014556e3ee3a9e83
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---

# Komponentinställningar {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_settings"
>title="Komponentinställningar"
>abstract="Visa och konfigurera namn, beskrivning och andra inställningar för en komponent.<br/><br/>**Parametrar **<br/>**Dölj komponent i rapportering**: Om du markerar den här rutan döljs den här komponenten för icke-adminanvändare i rapporter. Administratörer kan fortfarande komma åt den genom att välja **[!UICONTROL Show all components]** i ett Workspace-projekt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_dataview_component_contextlabels"
>title="Sammanhangsetiketter"
>abstract="Om du tar bort en sammanhangsetikett kan det påverka specifika paneler eller rapporter där komponenten krävs."

<!-- markdownlint-enable MD034 -->


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
| [!UICONTROL Schema Type] | Ett icke redigerbart fält som visar komponentens datatyp. Även om du kan använda en schemafälttyp som stöds i Platform, stöds inte alla fälttyper i Customer Journey Analytics. Följande datatyper stöds: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` och `Boolean`. Endast schemadatatypen `String` är tillåten i uppslagsuppsättningar för sökdata. |
| [!UICONTROL Component ID] | Obligatoriskt. API:t [Customer Journey Analytics ](https://adobe.io/cja-apis/docs) använder det här fältet för att referera till komponenten. Varje komponent i en datavy måste vara unik. Adobe genererar automatiskt ett ID för varje komponent, men du kan klicka på redigeringsikonen och ändra komponent-ID:t. Om du ändrar komponent-ID:t bryts alla befintliga Workspace-projekt som innehåller den här komponenten. Även om varje komponent behöver ett unikt ID i en enda datavy, kan du använda samma komponent-ID i andra datavyer. Om du använder samma komponent-ID i andra datavyer kan du göra Workspace-projekt kompatibla över datavyer. <br/>För profil- och sökbaserade komponenter har komponent-ID ett ID-prefix baserat på datauppsättnings-ID (till exempel: `642b28fcc1f0ee1c074265a0.person.name.firstName`). När du vill återanvända en profil- eller uppslagsbaserad komponent, som `person.name.firstName`, i ditt Workspace-projekt och konfigurera den här komponenten i olika datavyer måste du se till att du byter namn på komponent-ID:t unikt (till exempel: `myUniqueID.person.name.firstName`) i alla datavyer. |
| [!UICONTROL Path] | Obligatoriskt. Ett icke-redigerbart fält som visar den schemasökväg som komponenten kommer från. |
| [!UICONTROL Data Usage Labels] | Alla dataanvändningsetiketter som har tilldelats den här komponenten i Adobe Experience Platform. [Läs mer](/help/data-views/data-governance.md). |
| [!UICONTROL Hide component in reporting] | Gör att du kan strukturera komponenten utanför datavyn för icke-administratörer. Administratörer kan fortfarande komma åt den genom att klicka på [!UICONTROL Show All Components] i ett Analysis Workspace-projekt. |

{style="table-layout:auto"}

Här är en video om komponentinställningar i datavyer:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
