---
title: Lägg till Quantum Metric-friktionshändelser i Customer Journey Analytics
description: Lägg in friktionshändelser från Quantum Metric i Customer Journey Analytics beteendedata för att få djupare insikter i CJA.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: 1b7d5159-39b2-4ba4-be64-f448ae53c70e
source-git-commit: 11dc62cda2ceb7afabd3abd0944420601c8fa235
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 0%

---

# Lägg till Quantum Metric-friktionshändelser i Customer Journey Analytics

Quantum Metric samlar in friktionshändelser som långsam sidinläsning, sidinläsningsfel, sidklickningar med mera. Dessa händelser kan skickas till Customer Journey Analytics som kompletterande händelser under kundresan. Med dessa kombinerade data kan ni bättre förstå friktionens påverkan på mätvärden längre fram i kedjan.

## Förutsättningar:

Det här användningsexemplet har två krav:

* Du måste vara berättigad till Quantum Metric-paketet **Dev Ops**.
* Du måste använda taggar i Adobe Experience Platform Data Collection.

## Steg 1: Skapa ett schemafält för kvantmetrisk friktionshändelse

Det här användningsfallet kräver ett dedikerat schemafält att skicka data till. Du kan skapa det här fältet på valfri plats i ditt schema och ge det vilket namn du vill. Exempelvärden anges om din organisation inte har någon inställning för namn eller plats.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till **[!UICONTROL Data Collection]** > **[!UICONTROL Schemas]**.
1. Välj önskat schema i listan.
1. Välj ikonen ![Lägg till fält](/help/assets/icons/AddCircle.svg) bredvid det önskade objektet. Till exempel bredvid `Implementation Details`.
1. Ange [!UICONTROL Name] till höger. Exempel: `qmErrorName`.
1. Ange önskad [!UICONTROL Display name]. Exempel: `Quantum Metric error name`.
1. Välj [!UICONTROL Type] som **[!UICONTROL String]**.
1. Välj **[!UICONTROL Save]**.

## Steg 2: Fånga friktionshändelser med tillägget Quantum Metric-tagg

Se [Tillägg för kvantmetrisk datatyp](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) i guiden för destinationer för Adobe Experience Platform om du vill ha anvisningar om hur du ställer in dina taggar så att de inkluderar kvantmetrisk data. När du använder det här tillägget skickas fler rader till en befintlig datauppsättning.

Använd taggar i Adobe Experience Platform Data Collection för att manuellt ange namnet på friktionshändelsen så att den kan inkluderas i XDM-objektet och analyseras. Ett sätt att göra detta är i regelns egen kod:

```js
_satellite.setVar('qm_error_name','error rage click');
return true;
```

Lägg sedan till det dynamiskt angivna dataelementet i XDM-objektet:

![Namn på kvantmetriskt fel, bild](assets/error-name.png)

## Steg 3: Lägg till en eller flera dimensioner och mått i datavyn i Customer Journey Analytics

Redigera den befintliga datavyn för att lägga till sessions-ID som en tillgänglig dimension i Customer Journey Analytics.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Data views]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.
1. Välj önskad befintlig datavy.
1. Leta upp händelselistan för kvantmetrisk friktion till vänster och dra den till mätområdet i mitten.
1. I den högra rutan anger du inställningen [Inkludera/exkludera värden](/help/data-views/component-settings/include-exclude-values.md) till önskade friktionshändelser som du vill spåra. Du kan lägga till flera friktionshändelser i samma mätvärde för att kombinera dem. Du kan också dra en annan kopia av friktionshändelsefältet till mätområdet för att spåra andra friktionshändelser som ett separat mått.
1. När du har skapat alla önskade mått och mätvärden klickar du på **[!UICONTROL Save]**.
1. En fullständig lista över felhändelser finns i dokumentationen för Quantum Metric. Om du har ytterligare frågor kan du kontakta din kundsupportrepresentant för Quantum Metric eller skicka en begäran via [portalen för kvantmetrisk kundbegäran](https://community.quantummetric.com/s/public-support-page).

## Steg 4: Använd mått och mätvärden med övriga data i Analysis Workspace

Med händelsedata från Quantum Metric-friktionen som samlas in tillsammans med övriga besökardata kan du använda dem precis som du gör med andra mått eller mätvärden i Customer Journey Analytics.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Workspace]** på den översta menyn.
1. Välj ett befintligt projekt eller skapa ett projekt.
1. Skapa en [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Dra önskade mått och mätvärden till Workspace Canvas för analys.

Exempel på analysidéer är:

* Trend friction-händelsedata över tid
* Lägg till Customer Journey Analytics-händelser som några steg och Quantum Metric-friktionshändelser i en utfalls- eller trattvisualisering. Med den här rapporten kan ni se var besökarna som oftast stöter på problem.
* Skapa och tillämpa ett segment för besökare som upplever friktionshändelser för en djupgående analys
