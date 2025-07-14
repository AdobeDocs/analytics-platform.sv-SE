---
title: Komponentinställningar
description: Visa huvudinställningar för en datavykomponent.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: f3bd60d6a371a16e606d9af60e3359d8128a3c9f
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# Komponentinställningar {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Komponentinställningar"
>abstract="Visa och konfigurera namn, beskrivning och andra inställningar för en komponent. Markera den här kryssrutan om du vill dölja den här komponenten för icke-adminanvändare vid rapportering. Administratörer kan fortfarande komma åt komponenten genom att välja **[!UICONTROL Show all components]** i ett Workspace-projekt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Sammanhangsetiketter"
>abstract="Om du tar bort en sammanhangsetikett kan det påverka specifika paneler eller rapporter där komponenten krävs."

<!-- markdownlint-enable MD034 -->


Följande information beskriver de inställningar som används av en datavykomponent.

![Komponentinställningar som beskrivs i det här avsnittet](../assets/component-settings.png)

| Inställning | Beskrivning/användningsfall |
| --- | --- |
| [!UICONTROL Component type] | Obligatoriskt. Gör att du kan ändra en komponent från Metric till Dimension eller tvärtom. Om du ändrar den här listrutan flyttas komponenten till respektive komponentområde. |
| [!UICONTROL Component name] | Obligatoriskt. Här kan du ange ett eget namn som visas i Analysis Workspace. Du kan byta namn på en komponent för att ge den ett namn som är specifikt för datavyn. |
| [!UICONTROL Description] | Valfritt, men rekommenderas. Ger information om komponenten till andra användare. |
| [!UICONTROL Tags] | Valfritt. Gör att du kan tagga komponenten med egna eller färdiga taggar för enklare sökning/filtrering i Analysis Workspace-gränssnittet. |
| [!UICONTROL Context labels] | Valfritt. En listruta med tillgängliga systemdefinierade etiketter som kan användas på en komponent. <p>Dessa etiketter kan behövas i följande situationer:</p> <ul><li>Om du vill definiera en uppsättning komponenter kan du använda i experimentrapporter med hjälp av [panelen Experimentation](/help/analysis-workspace/c-panels/experimentation.md) i Analysis Workspace-projekt.<p>Mer information finns i [Integrera med Journey Optimizer](/help/integrations/ajo.md#data-view) och [Målrapportering](/help/integrations/at.md).</p></li><li>Om du vill definiera en uppsättning komponenter kan du använda med kartvisualiseringen i Analysis Workspace-projekt.<p>Mer information finns i [Lägg till kontextetiketter i datavyer](/help/analysis-workspace/visualizations/map.md#add-context-labels-in-data-views) i [Karta](/help/analysis-workspace/visualizations/map.md).</p><p>**Obs!** Mappningsvisualiseringen är i den begränsade testfasen av versionen och är kanske inte tillgänglig än i din miljö.</p></li><li>När mallar från Adobe används. Som standard kommer vissa mallar från Adobe inte att fungera eftersom de innehåller komponenter som inte finns i datavyn.<p>För varje komponent som saknas finns en matchande sammanhangsetikett tillgänglig i datavyn. Du måste antingen lägga till den matchande kontextetiketten i en komponent som redan finns i datavyn, eller så måste du lägga till en ny komponent i datavyn och lägga till kontextetiketten i den.</p><p>Mer information finns i [Lägga till saknade komponenter i datavyn för en viss mall](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) i artikeln [Skapa och hantera mallar](/help/analysis-workspace/templates/create-templates.md).</p> |
| [!UICONTROL Schema field name] | Schemafältets namn. |
| [!UICONTROL Dataset type] | Obligatoriskt. Ett icke-redigerbart fält som visar vilken datamängdstyp (händelse, sökning eller profil) som komponenten kommer från. |
| [!UICONTROL Dataset] | Ett icke-redigerbart fält som visar vilken datamängd som komponenten kommer från. Det här fältet kan innehålla flera datauppsättningar. |
| [!UICONTROL Schema type] | Ett icke redigerbart fält som visar komponentens datatyp. Även om du kan använda en schemafälttyp som stöds i Platform, stöds inte alla fälttyper i Customer Journey Analytics. Följande datatyper stöds: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String` och `Boolean`. Endast schemadatatypen `String` är tillåten i uppslagsuppsättningar för sökdata. |
| [!UICONTROL Component ID] | Obligatoriskt. [Customer Journey Analytics API](https://adobe.io/cja-apis/docs) använder det här fältet för att referera till komponenten. Varje komponent i en datavy måste vara unik. Adobe genererar automatiskt ett ID för varje komponent, men du kan klicka på redigeringsikonen och ändra komponent-ID:t. Om du ändrar komponent-ID:t bryts alla befintliga Workspace-projekt som innehåller den här komponenten. Även om varje komponent behöver ett unikt ID i en enda datavy, kan du använda samma komponent-ID i andra datavyer. Om du använder samma komponent-ID i andra datavyer kan du göra Workspace-projekt kompatibla över datavyer. <br/>För profil- och sökbaserade komponenter har komponent-ID ett ID-prefix baserat på datauppsättnings-ID (till exempel: `642b28fcc1f0ee1c074265a0.person.name.firstName`). När du vill återanvända en profil- eller uppslagsbaserad komponent, som `person.name.firstName`, i ditt Workspace-projekt och konfigurera den här komponenten i olika datavyer måste du se till att du byter namn på komponent-ID:t unikt (till exempel: `myUniqueID.person.name.firstName`) i alla datavyer. |
| [!UICONTROL Path] | Obligatoriskt. Ett icke-redigerbart fält som visar den schemasökväg som komponenten kommer från. |
| [!UICONTROL Data Usage Labels] | Alla dataanvändningsetiketter som har tilldelats den här komponenten i Adobe Experience Platform. [Läs mer](/help/data-views/data-governance.md). |
| [!UICONTROL Hide component in reporting] | Gör att du kan strukturera komponenten utanför datavyn för icke-administratörer. Administratörer kan fortfarande komma åt den genom att klicka på [!UICONTROL Show All Components] i ett Analysis Workspace-projekt. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Komponenttypsinställningar](https://video.tv.adobe.com/v/333112/?quality=12&learn=on){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


