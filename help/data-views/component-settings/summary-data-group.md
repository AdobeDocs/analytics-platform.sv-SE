---
title: Komponentinställningar för sammanfattningsdatagrupp
description: Information om och om hur du konfigurerar dimensioner från datauppsättningar för att säkerställa att du kan rapportera korrekt om sammanfattningsdata.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: cba5904191b0602557903b5b9f32a2b793c8207d
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# [!UICONTROL Summary data group] komponentinställningar

En sammanfattningsdatagrupp skapar en association mellan alla dimensioner i grupperingen och används för att kombinera dimensioner från sammanfattningsdatamängder med andra dimensioner för rapportering.

![Komponentinställningar för sammanfattningsdatagrupp](/help/data-views/assets/summary-data-group.png)

Så här skapar du en gruppering av dimensioner:

1. Välj en dimension.
1. Välj ![SparrNed](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Summary data group]**.
1. Aktivera **[!UICONTROL Create grouping]**.
1. Välj en dimension i listrutan **[!UICONTROL Dimension]** som du vill gruppera med den valda dimensionen från det första steget. Observera att endast dimensioner som du redan har lagt till i datavyn är tillgängliga i listrutan.
1. Du kan även aktivera **[!UICONTROL Hide in reporting]** för att dölja den grupperade dimensionen från rapportering. Att aktivera det här alternativet liknar att konfigurera **[!UICONTROL Hide in reporting]** för den grupperade dimensionen separat. Mer information finns i [Komponentinställningar](overview.md).
1. Om du vill lägga till ytterligare dimensioner till grupperingen väljer du ![Lägg till](/help/assets/icons/Add.svg) **[!UICONTROL Add dimension to group]**.<br/>Du kan lägga till upp till nio dimensioner, eftersom en sammanfattningsdatagrupp har en gräns på tio dimensioner.

## Samma komponentinställningar

När du grupperar dimensioner måste du se till att inställningarna för [!UICONTROL Substring], [!UICONTROL Behavior (Lower case)] och [!UICONTROL Include exclude values], för var och en av dimensionerna som ingår i gruppen, är desamma. Annars kan varje dimension av gruppen potentiellt returnera olika resultat före grupperingen.
Exempel:

1. Du har skapat en sammanfattningsdatagrupp för `campaign_code` (del av sammanfattningsdata) och `tracking_code` (del av dina händelsedata).
1. Du har tillämpat [!UICONTROL Behavior (Lower case)] på dimensionen `campaign_code` men inte på dimensionen `tracking_code`.

Värden i `tracking_code` kan eventuellt visas som annorlunda än `campaign_code`.

>[!IMPORTANT]
>
>Se till att du grupperar dimensioner från endast en dimension och inte använder gruppering från flera dimensioner. Om du till exempel skapar en gruppering genom att lägga till dimensionen `campaign_name` i dimensionen `tracking_code` ska du inte skapa en gruppering för dimensionen `campaign_name` också.
>


