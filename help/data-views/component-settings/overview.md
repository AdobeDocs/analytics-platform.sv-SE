---
title: Komponentinställningar
description: Visa huvudinställningar för en datavykomponent.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 3f20520a2021d9b6066b0492ed11a1a4619ab1d4
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# Komponentinställningar

Kärninställningar som används av en datavykomponent.

![Komponentinställningar](../assets/component-settings.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Component type] | Obligatoriskt. Gör att du kan ändra en komponent från Mått till Dimension eller tvärtom. Om du ändrar den här listrutan flyttas komponenten till dess respektive inkluderade komponentområde. |
| [!UICONTROL Component Name] | Obligatoriskt. Här kan du ange ett eget namn som visas i Analysis Workspace. Du kan byta namn på en komponent för att ge den ett namn som är specifikt för datavyn. |
| [!UICONTROL Description] | Valfritt, men rekommenderas. Ger information om komponenten till andra användare. |
| [!UICONTROL Tags] | Valfritt. Gör att du kan tagga komponenten med egna eller färdiga taggar för enklare sökning/filtrering i Analysis Workspace-gränssnittet. |
| [!UICONTROL Field Name] | Schemafältets namn. |
| [!UICONTROL Dataset type] | Obligatoriskt. Ett icke-redigerbart fält som visar vilken datamängdstyp (händelse, sökning eller profil) som komponenten kommer från. |
| [!UICONTROL Dataset] | Ett icke-redigerbart fält som visar vilken datamängd som komponenten kommer från. Det här fältet kan innehålla flera datauppsättningar. |
| [!UICONTROL Schema Type] | Ett icke redigerbart fält som visar komponentens datatyp.  Även om du kan använda en schemafälttyp som stöds i Platform stöds inte alla fälttyper i CJA. Följande datatyper stöds: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`och `Boolean`. Endast `String` Schemadatatypen tillåts för närvarande i uppslagsuppsättningar av data. |
| [!UICONTROL Component ID] | Obligatoriskt. The [CJA API](https://adobe.io/cja-apis/docs) använder det här fältet för att referera till komponenten. Varje komponent i en datavy måste vara unik. Adobe genererar automatiskt ett ID för varje komponent. Du kan dock klicka på redigeringsikonen och ändra komponent-ID:t. Om du ändrar komponent-ID bryts alla befintliga arbetsyteprojekt som innehåller den här komponenten. Även om varje komponent behöver ett unikt ID i en enda datavy, kan du använda samma komponent-ID i andra datavyer. Om du använder samma komponent-ID i andra datavyer kan du göra arbetsyteprojekt kompatibla över datavyer. |
| [!UICONTROL Schema Path] | Obligatoriskt. Ett icke-redigerbart fält som visar schemasökvägen som komponenten kommer från. |
| [!UICONTROL Hide component in reporting] | Gör att du kan strukturera komponenten utanför datavyn för icke-administratörer. Administratörer kan fortfarande komma åt den genom att klicka på [!UICONTROL Show All Components] i ett Analysis Workspace-projekt. |

Här är en video om komponentinställningar i datavyer:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
