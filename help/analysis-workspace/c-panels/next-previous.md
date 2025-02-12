---
description: En panel som visar nästa eller föregående dimensionsobjekt för en viss dimension.
title: Panelen Nästa eller föregående objekt
feature: Panels
role: User, Admin
exl-id: a5f6ce97-6720-4129-9ece-e2e834289d45
source-git-commit: 55b312552d32070875714a77e1177bf0da5f9d87
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 0%

---

# Panelen Nästa eller föregående objekt {#next-or-previous-item-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_button"
>title="Nästa eller föregående objekt"
>abstract="Skapa en panel för att förstå de tidigare dimensioner som personer kommer från eller nästa dimension kommer till."

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_nextorpreviousitem_panel"
>title="Kapsla eller föregående objekt"
>abstract="Analysera de vanligaste platserna som besökare tidigare kom från eller kom till nästa.<br/><br/>**Dimension**: Välj en dimension. Till exempel **Sida**.<br/>**Dimension-objekt**: Välj en specifik dimensionsobjekt. Exempel: **Hemsida**.<br/>**Riktning**: Välj **Nästa** om du vill visa dimensionsobjekten direkt efter den valda dimensionsobjektet. Välj **Föregående** om du vill se dimensionsobjekten som leder upp till den valda dimensionsposten.<br/>**Behållare**: Välj **Session** om du vill visa nästa/föregående dimensionsobjekt i samma session, eller välj **Person** om du vill visa nästa/föregående dimensionsobjekt för samma person."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_I den här artikeln dokumenteras panelen Nästa eller Föregående objekt i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Se [Nästa eller föregående objektpanel](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/next-previous) för_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]

Panelen **[!UICONTROL Next or previous item]** innehåller ett antal tabeller och visualiseringar för att identifiera nästa eller föregående dimensionsobjekt för en viss dimension. Du kanske till exempel vill utforska vilka sidor kunderna besöker oftast efter att de besökt hemsidan.

## Använd

Så här använder du en **[!UICONTROL Next or previous item]**-panel:

1. Skapa en **[!UICONTROL Next or previous item]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.

### Panelindata

Du kan konfigurera panelen [!UICONTROL Next or previous item] med följande indatainställningar:

![Nästa eller föregående objektpanel](assets/next-or-previous-item.png)

| Indata | Beskrivning |
| --- | --- |
| **[!UICONTROL Dimension]** | Välj dimensionen som du vill utforska nästa eller föregående objekt för. |
| **[!UICONTROL Dimension item]** | Välj den specifika dimensionsobjektet i mitten av nästa/föregående fråga. |
| **[!UICONTROL Direction]** | Ange om du letar efter dimensionsobjektet [!UICONTROL Next] eller [!UICONTROL Previous]. |
| **[!UICONTROL Container]** | Välj behållaren [!UICONTROL Session] eller [!UICONTROL Person] (standard) för att fastställa omfattningen för din fråga. |

{style="table-layout:auto"}

Välj **[!UICONTROL Build]** om du vill skapa panelen.

### Panelutdata

Panelen [!UICONTROL Next or previous item] returnerar en mängd data och visualiseringar som hjälper dig att förstå vilka förekomster som följer eller föregår specifika dimensionsobjekt.


![Nästa/Föregående panelutdata](assets/next-or-previous-item-output.png)


| Visualisering | Beskrivning |
| --- | --- |
| **[!UICONTROL Horizontal bar]** | Visar nästa (eller föregående) objekt baserat på den dimensionspost du väljer. Om du placerar pekaren över ett enskilt fält markeras motsvarande objekt i tabellen Frihand. |
| **[!UICONTROL Summary number]** | Sammanfattningsnummer på hög nivå för alla förekomster av nästa eller föregående dimensionsobjekt för den aktuella månaden (hittills). |
| **[!UICONTROL Freeform table]** | Visar nästa (eller föregående) objekt baserat på den dimensionspost som du väljer, i ett tabellformat. Det var till exempel de mest populära sidorna (av händelser) som folk gick till efter (eller före) hemsidan eller arbetsytesidan. |

{style="table-layout:auto"}


>[!MORELIKETHIS]
>
>[Skapa en panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
