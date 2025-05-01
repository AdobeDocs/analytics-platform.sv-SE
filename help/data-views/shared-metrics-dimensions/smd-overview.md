---
title: Översikt över delade mått och mått
description: Använd samma mått eller måttreferens för flera datavyer.
exl-id: 998a9f9b-cfa7-4b97-b32b-d50e35d01b39
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '1155'
ht-degree: 0%

---

# Översikt över delade mått och mått

Gemensamma mätvärden och dimensioner utgör en central plats för att hantera mått och mätvärden som kan användas i ett valfritt antal datavyer. Dessa komponenter är särskilt användbara för organisationer som använder flera datavyer, särskilt om dessa datavyer har gemensamma gemensamma komponentinställningar. Ändringar som görs i delade mätvärden och dimensioner tillämpas direkt i alla datavyer som de delas med. När du redigerar en enskild datavy kan delade dimensioner och mått identifieras med en ![ikon för delad komponent](/help/assets/icons/CCLibrary.svg) bredvid komponentnamnet.

Delade dimensioner och mätvärden gör att gemensamma komponenter kan användas i många datavyer, men de kan inte delas över flera anslutningar.

## Arbetsflöde

De flesta organisationer använder följande övergripande arbetsflöde för att deduplicera och underhålla mått och mätvärden över tid:

1. Importera komponenter från varje datavy som kan delas av flera datavyer. Om samma mått eller mått finns i flera datavyer rekommenderar Adobe att du importerar alla instanser av komponenten. Även om detta är den bästa metoden att importera dubbletter importeras de så att de kan dedupliceras och behåller sina respektive referenser till Workspace-projekt.
1. Granska alla komponenter som använder samma komponent-ID men som har olika komponentinställningar. För varje grupp med duplicerade komponenter väljer du de komponentinställningar som ska tillämpas på alla andra komponenter som delar det komponent-ID:t.
1. Granska alla komponenter som använder samma komponent-ID och som också har samma komponentinställningar. Dessa mått och mätvärden kan enkelt och säkert sammanfogas.

## [!UICONTROL Shared Metrics & Dimensions]-hanterare

**[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Data views]** > **[!UICONTROL Shared Metrics & Dimensions]**

Navigera till det här gränssnittet för att visa alla aktuella dimensioner och mått som är tillgängliga för delning över flera datavyer. Det övre högra hörnet innehåller två knappar för att lägga till komponenter i det här gränssnittet:

* **[!UICONTROL Import]**: Öppnar ett modalt fönster där du kan välja en datavy och sedan välja vilka komponenter som ska vara tillgängliga för delning.
* **[!UICONTROL Create new]**: Öppnar [redigeraren för delad komponent](shared-component-editor.md).

Direkt nedanför dessa två knappar visas fyra översiktskort:

![Förhandsgranskning av översiktskort](assets/overview-cards.png)

* **Mätvärden**: Det totala antalet mätvärden som är tillgängliga för delning mellan datavyer för den här anslutningen. Varje anslutning kan innehålla upp till 10 000 delade mätvärden.
* **Dimensioner**: Det totala antalet dimensioner som är tillgängliga för delning mellan datavyer för den här anslutningen. Varje anslutning kan innehålla upp till 10 000 delade dimensioner.
* **Duplicera komponenter som ska granskas**: När du importerar komponenter till flera datavyer kan vissa dimensioner eller mått dela samma komponent-ID. Siffran i det här översiktskortet visar det totala antalet komponenter som har samma komponent-ID men olika komponentinställningar. Om du väljer **[!UICONTROL Review]** aktiveras ett filter som gör att du kan välja vilken komponent som ska fungera som en källa till sanning för alla andra komponenter med samma ID.
* **Komponenter som är tillgängliga för sammanfogning**: Om en dimension eller ett mått delar samma komponent-ID och samma komponentinställningar är de i princip identiska och kan dedupliceras. Om du väljer **[!UICONTROL Review]** aktiveras ett filter som gör att du kan sammanfoga alla komponenter med samma komponent-ID till en enda delad dimension eller mätvärde.

Alla delade mått och mått visas under de fyra översiktskorten.

![Tillgängliga mått och måttförhandsvisningar](assets/shared-metrics-dimensions.png)

* **Filter**: Välj ikonen ![Filter ](../../assets/icons/Filter.svg) om du vill visa eller dölja tillgängliga filter. Följande filter är tillgängliga:
   * **[!UICONTROL Component type]**: Visa endast dimensioner eller endast mått.
   * **[!UICONTROL Dataset]**: Visa endast komponenter där datauppsättningen ingår i datavyer som en komponent delas med.
   * **[!UICONTROL Data view]**: Visa endast komponenter som delas med den datavyn.
   * **[!UICONTROL Created by]**: Visa endast komponenter som har skapats av en viss användare.
   * **[!UICONTROL Duplicates]**: Visa endast komponenter som har samma komponent-ID som en annan komponent. De här filtren är identiska med att granska komponenter via översiktskorten.
* **Sök**: Använd ikonen ![Sök ](../../assets/icons/Search.svg) för att söka efter en komponent efter namn.
* **[!UICONTROL Connection]**: En nedrullningsbar meny som ändrar [anslutningen](/help/connections/overview.md). Delade mått och mätvärden är alltid specifika för en enda anslutning.
* **[!UICONTROL Customize table]**: Välj ikonen ![Anpassa tabell](/help/assets/icons/ColumnSetting.svg) om du vill visa eller dölja kolumner i tabellen. Tillgängliga alternativ är:
   * **[!UICONTROL Field name]**: Namnet på den delade dimensionen eller måttet. Det här fältet visas alltid.
   * **[!UICONTROL Type]**: Anger om komponenten är en dimension eller ett mått. Det här fältet visas alltid.
   * **[!UICONTROL Dataset type]**: Datatypen. De flesta datauppsättningar är händelsedatamängder.
   * **[!UICONTROL Shared to data view]**: Alla datavyer som den här komponenten delas med. Det här fältet visas alltid. Markera länken om du vill öppna en modal som visar alla datavyer som den här komponenten är tillgänglig i.
   * **[!UICONTROL Datasets]**: Alla datauppsättningar som ingår i varje datavy som den här komponenten delas med. Markera länken om du vill öppna en modal lista med alla datamängder för komponenten.
   * **[!UICONTROL Created by]**: Namnet på den person som skapade eller importerade komponenten till det delade gränssnittet för mått och mått.
   * **[!UICONTROL Schema type]**: Det format som data lagras i. Exempel är `string`, `double` eller `boolean`.
   * **[!UICONTROL Component ID]**: Komponent-ID för dimensionen eller måttet. Alla komponenter som delar samma komponent-ID i det här gränssnittet måste granskas och dedupliceras.
   * **[!UICONTROL Schema]**: Schemasökvägen för dimensionen eller måttet. Exempel: `web.webPageDetails.URL`.
   * **[!UICONTROL Description]**: Komponentens [description](/help/data-views/component-settings/overview.md).
   * **[!UICONTROL Context labels]**: Komponentens [kontextetiketter](/help/data-views/component-settings/overview.md).
   * **[!UICONTROL Include/Exclude values]**: Visar antalet regler som anges under [Inkludera/exkludera värden](/help/data-views/component-settings/include-exclude-values.md).
   * **[!UICONTROL Data usage labels]**: [Dataanvändningsetiketter](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview) för schemafältet.
   * **[!UICONTROL Deprecated]**: Anger om den borttagna flaggan har angetts.
   * **[!UICONTROL Format]**: Det format som värden visas i. Booleaner visas vanligtvis som `True | False`, mått visas vanligtvis som `Decimal` osv.
   * **[!UICONTROL Metric deduplication]**: Komponentens [Metrisk deduplicering](/help/data-views/component-settings/metric-deduplication.md) -inställningar.
   * **[!UICONTROL Behavior]**: Komponentens [beteendeinställningar](/help/data-views/component-settings/behavior.md).
   * **[!UICONTROL Attribution]**: Komponentens [Attribution](/help/data-views/component-settings/attribution.md) -inställningar.
   * **[!UICONTROL No value option]**: Komponentens [inga värdealternativ](/help/data-views/component-settings/no-value-options.md).
   * **[!UICONTROL Value bucketing]**: Komponentens [Value Bucketing](/help/data-views/component-settings/value-bucketing.md) -inställningar.
   * **[!UICONTROL Persistence]**: Komponentens [Persistence](/help/data-views/component-settings/persistence.md) -inställningar.
   * **[!UICONTROL Lowercase]**: Anger om komponenten är i gemener aktiverad baserat på komponentens [beteendeinställningar](/help/data-views/component-settings/behavior.md).
   * **[!UICONTROL Substring]**: Komponentens [delsträngsinställningar](/help/data-views/component-settings/substring.md).
   * **[!UICONTROL Summary data group]**: Komponentens [Inställningar för datagrupp för sammanfattning](/help/data-views/component-settings/summary-data-group.md).
   * **[!UICONTROL Date created]**: Det datum då komponenten skapades eller importerades.
   * **[!UICONTROL Last modified]**: Om komponenten har ändrats efter att den skapades, datumet då den senast ändrades.
* **[!UICONTROL Job history]**: Välj ikonen ![ Historik ](/help/assets/icons/History.svg) för att öppna ett modalt fönster som visar alla instanser av import av dimensioner och mått från enskilda datavyer.

## Redigera komponenter eller dela komponenter till datavyer

Använd kryssrutan bredvid en komponent för att visa alla tillgängliga åtgärder som du kan utföra. Flera markeringar stöds.

![Förhandsgranska tillgängliga åtgärder](assets/smd-actions.png)

* ![Pennikon](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**: Öppna de valda dimensionerna och måtten i den [delade komponentredigeraren](shared-component-editor.md) där du kan justera deras [komponentinställningar](/help/data-views/component-settings/overview.md). När du markerar flera komponenter som ska redigeras öppnas alla i komponentredigeraren. Du kan skift + klicka på komponenter i komponentredigeraren om du vill redigera samma fält för flera komponenter.
* ![Delningsikon](/help/assets/icons/ShareAlt.svg) **[!UICONTROL Share to data view(s)]**: Öppnar ett fönster som visar alla datavyer som är tillgängliga i den valda anslutningen. Markera kryssrutan för varje datavy som du vill göra den här komponenten tillgänglig i och välj sedan **[!UICONTROL Share]**.
* ![Ikonen för att sluta dela ](/help/assets/icons/SaveTo.svg) **[!UICONTROL Unshare from data view(s)]**: Öppnar ett fönster som visar alla datavyer som den här komponenten för närvarande delas med. Markera kryssrutan för varje datavy som du vill ta bort den här komponentens tillgänglighet från och välj sedan **[!UICONTROL Unshare]**.
* ![Duplicera ikon](/help/assets/icons/Copy.svg) **[!UICONTROL Duplicate]**: Skapar en kopia av de markerade komponenterna. Ett nytt komponent-ID genereras för duplicerade komponenter.
* ![Ta bort ikon](/help/assets/icons/Delete.svg) **[!UICONTROL Delete]**: Tar bort de markerade komponenterna från gränssnittet. Om de markerade komponenterna delas med datavyer delas de inte.
