---
title: Formatera komponentinställningar
description: Konfigurera hur ett mått formateras.
exl-id: 5ce13fe9-29fa-474c-bae3-65f275153a59
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5c6e7c51369b451ac0efdcead86f71e38bd3a853
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---

# Formatera komponentinställningar

Med Format kan du bestämma hur ett givet mätvärde ska visas.

![Formatinställningar](../assets/format-settings.png)

| Inställning | Beskrivning |
| --- | --- |
| **[!UICONTROL Format]** | Här kan du ange formatering för ett mätresultat som Decimal, Time, Percent eller Currency. |
| **[!UICONTROL Decimal Places]** | Visas inte på datatyperna för heltalsschemat. Här kan du ange hur många decimaler ett mätresultat ska visa. |
| **[!UICONTROL Date]** | Här kan du bestämma hur du vill att datum- och tidsfältet ska visas när det används som en dimension i rapporter. [Läs mer](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Date-Time]** | Här kan du bestämma hur du vill att datum- och tidsfältet ska visas när det används som en dimension i rapporter. [Läs mer](../../use-cases/data-views/data-views-usecases.md#date-and-date-time-use-cases) |
| **[!UICONTROL Currency]** | Här kan du bestämma vilken valuta som måttet ska visas i. Se [Valuta](#currency) mer information. |
| **[!UICONTROL Show upward trend as]** | Här kan du ange om en uppåtgående trend för det här måttet är god (grön) eller dålig (röd). |
| **[!UICONTROL True value]** och **[!UICONTROL False value]** | Endast synlig för datatyperna Boolean-schema. Här kan du anpassa dimensionsobjektetiketten för `true` och `false` värden. |

{style="table-layout:auto"}


## Valuta

När du väljer **[!UICONTROL Currency]** som [!UICONTROL Format] för ett mätvärde kan du bestämma hur valutor ska visas och konverteras.

### Visa valuta

Så här visar du en valuta för ett mått:

1. Ange antalet **[!UICONTROL Decimal places]**.

2. Välj en valuta från **[!UICONTROL Display currency in]** lista.


### Konvertera och visa valuta

Så här aktiverar du konvertering av en valuta för ett mätresultat:

- Konfigurera din Customer Journey Analytics-anslutning så att den innehåller minst en händelsedatamängd som innehåller en valutakoddimension för varje händelse som innehåller ett valutamått. Denna valutakoddimension använder en alfabetisk valutakod som överensstämmer med [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) standard för att representera valutor. Till exempel USD för $, EUR för €, GBP för £.

- Du har (valfritt) använt [!UICONTROL Currency Code] sammanhangsetikett till en eller flera dimensioner som definierar valutakoder som är tillgängliga i datauppsättningen.

  Använda [!UICONTROL Currency Code] kontextetikett, i [!UICONTROL Components] -fliken i din datavy:

  <!--![Currency Context Label](../assets/currency-context-label.png)-->

   1. Välj dimensionen från en av dina datauppsättningar som innehåller valutakoderna. Exempel, [!UICONTROL Currency code].

   2. Välj **[!UICONTROL Currency Code]** från [!UICONTROL Context labels] lista.

  Upprepa de här stegen om du har fler dimensioner som innehåller valutakoder som du vill använda för valutakonvertering.

>[!NOTE]
>
>Det mätvärde som du väljer för valutakonvertering måste ha en numerisk typ (Double, Long, Integer, Short, Byte).


Så här definierar du hur du konverterar och visar en valuta för ett mätresultat:

1. Ange antalet **[!UICONTROL Decimal places]**.

2. Välj **[!UICONTROL Convert Concurrency]**.

3. Baserat på den tillämpade kontextetiketten är det lämpligt från **[!UICONTROL Currency code dimension]** listan väljs automatiskt. Du kan välja vilken annan dimension som helst, inklusive de dimensioner som du dessutom tillämpade kontextetiketten Valutakod på.

4. Välj en valuta från **[!UICONTROL Convert and display currency in]** lista.

### Vanliga frågor

+++ Hur genomförs valutakonvertering?

Vid rapporttiden konverteras värdet för måttet och den ursprungliga valutakoden till USD och konverteras sedan till den valuta som konfigurerats för visning. För denna konvertering används de dagliga valutakurserna som gäller vid tidpunkten för händelsen.

+++

