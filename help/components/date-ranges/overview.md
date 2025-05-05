---
title: Översikt över datumintervall
description: Lär dig vilka datumintervall som är och hur du kan använda dem vid rapportering.
feature: Calendar
exl-id: 99b31bd9-32f1-4da1-9e47-6d90c66282c5
role: User
source-git-commit: 747e77b964006404d70b500b28ec44005d65d944
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 0%

---

# Översikt över datumintervall

I ett Workspace-projekt använder du vanligtvis [kalendern i en panel](/help/analysis-workspace/c-panels/panels.md#calendar) för att ange datumintervallet för visualiseringarna i den panelen.

Med datumintervallkomponenter kan du definiera och åsidosätta kalenderinställningarna för panelen.

<!-- Very old video, should we show it?

+++ View a video illustrating use of calendar and date ranges

>[!VIDEO](https://video.tv.adobe.com/v/24136?format=jpeg)

{{videoaa}}
+++

-->

## Använd datumintervall

Du kan använda en datumintervallkomponent för att definiera om kalendern för panelen.

Du kan också använda ett datumintervall i en frihandstabell som ett mått eller en dimension.

![Användning av datumintervall](/help/components/date-ranges/assets/date-ranges-usage.png)

- **Mått**. Om du till exempel vill jämföra en dimension för två olika månader för ett visst mått.
- **Dimension**. Om du vill jämföra ett mått för olika dimensionsobjekt för datumintervalldimensionen.

>[!NOTE]
>
>När du använder datumintervall i en frihandstabell åsidosätter datumintervallen den kalender som har angetts för panelen som frihandstabellen tillhör.
>

Du använder ett datumintervall på samma sätt som du [använder valfri komponent](/help/components/overview.md#analysis-workspace-components). Du drar datumintervallet från komponentpanelen ![Kalender](/help/assets/icons/Calendar.svg) **[!UICONTROL Date ranges]** och släpper komponenten på:

- **[!UICONTROL Calendar]**: Du ![Växlar](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** den aktuella kalenderkonfigurationen med datumintervallet.
- **Kolumnrubrik för mått**: Du ![Växlar](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** måttet, ![Lägg till ](/help/assets/icons/Add.svg)**[!UICONTROL Add]**&#x200B;datumintervallet som ett mått eller ![Filter](/help/assets/icons/Filter.svg)**[!UICONTROL Filter]**&#x200B;måttet med datumintervallkomponenten.
- **kolumnrubrik för Dimension**: ![Byt](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** de aktuella dimensionerna. Den nya dimensionen är nu **[!UICONTROL Date ranges]**. När dimensionen är datumintervall kan du ![lägga till ](/help/assets/icons/Add.svg)**[!UICONTROL Add]**&#x200B;ytterligare datumintervall som dimensionsobjekt.
- **Dimension**: Du ![Bryter](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** den specifika dimensionsposten efter datumintervallet.

Du kan också lägga till en datumintervallkolumn direkt i en visualisering av en frihandsfigur:

1. I en måttkolumn väljer du på snabbmenyn:

   - **[!UICONTROL Add time period column]**. Du kan välja mellan föreslagna alternativ som baseras på den aktuella kalendern eller skapa ett [anpassat datumintervall](#custom-date-ranges).
   - **[!UICONTROL Compare time periods]**. Du kan välja mellan ett föreslaget alternativ som är baserat på den aktuella kalendern eller skapa ett [anpassat datumintervall](#custom-date-ranges).

1. Beroende på vad du har valt läggs ytterligare datumintervallkolumner till i Frihand-tabellen.

## Standarddatumintervall

Analysis Workspace tillhandahåller ett antal standarddatumintervall.


| Dag | Vecka | Månad | Kvartal | År |
|---|---|---|---|---|
| Idag | Den här veckan | Den här månaden | Detta kvartal | I år |
| Igår | Den här veckan (förutom idag) | Den här månaden (förutom idag) | Detta kvartal (förutom idag) | I år (förutom idag) |
| För 2 dagar sedan | för 2 veckor sedan | för 2 månader sedan |   |  |
| För 3 dagar sedan | För 3 veckor sedan | För 3 månader sedan |  | |
| De senaste 7 dagarna | Senaste veckan | Senaste månaden | Sista kvartalet | Förra året |
| De senaste 14 dagarna | De senaste två fullveckorna | De senaste två fullständiga månaderna | Senaste fyra fullständiga kvartal | |
| De senaste 30 dagarna | De senaste tre fullständiga veckorna | De senaste tre fullständiga månaderna | | |
| De senaste 60 dagarna | De senaste fyra fullveckorna | De senaste 6 fullständiga månaderna | | |
| De senaste 90 dagarna | De senaste 12 fullveckorna | De senaste 12 fullständiga månaderna | | |
| De senaste 7 fullständiga dagarna | De senaste 52 fullveckorna | De senaste 13 fullständiga månaderna | | |
| De senaste 14 fullständiga dagarna | | | | |
| De senaste 30 fullständiga dagarna | | | | |
| De senaste 90 fullständiga dagarna | | | | |

<table style="table-layout:fixed">

## Anpassade datumintervall

Du kan skapa egna anpassade datumintervall. Se [Skapa datumintervall](/help/components/date-ranges/create.md) för de olika alternativ som är tillgängliga för att skapa datumintervall. Du kan sedan skapa, ändra och spara datumintervall i [datumintervallverktyget](create.md#date-range-builder).

Du använder [datumintervallhanteraren](manage.md) för att hantera datumintervall.
