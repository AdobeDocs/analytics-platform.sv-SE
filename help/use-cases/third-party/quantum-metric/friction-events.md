---
title: Lägg till Quantum Metric-friktionshändelser i Customer Journey Analytics
description: Lägg till djupare insikter i Customer Journey Analytics med friktionshändelser som samlats in i Quantum Metric.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
source-git-commit: e6a77e75963fb43041c0533a28a9563a3849b8b0
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 0%

---

# Lägg till Quantum Metric-friktionshändelser i Customer Journey Analytics

Quantum Metric samlar in friktionshändelser som långsam sidinläsning, sidinläsningsfel, sidklickningar med mera. Dessa händelser kan skickas till Customer Journey Analytics som kompletterande händelser under kundresan. Med dessa kombinerade data kan ni bättre förstå friktionens påverkan på mätvärden längre fram i kedjan.

Det här användningsexemplet har två krav:

* Du måste vara berättigad till Quantum Metric-paketet **Dev Ops**.
* Du måste använda taggar i Adobe Experience Platform Data Collection.

## Steg 1: Hämta friktionshändelser med tillägget Quantum Metric-tagg

Quantum Metric CSM-teamet kan hjälpa dig att avgöra vilka schemaelement som ska läggas till och instruera dig att ändra implementeringen för att samla in önskade data för användning i Customer Journey Analytics. Kontakta Quantum Metric Customer Success Manager om du vill ha mer information.

I slutändan vill du börja spåra friktionshändelsens namn i ett fält.

## Steg 2: Bekräfta inkluderade datamängdsfält

Bekräfta att datauppsättningarna i din anslutning nu har ett sessions-ID för kvantmått i den önskade datauppsättningen.

## Steg 3: Lägg till en eller flera dimensioner och mått i datavyn i Customer Journey Analytics

Redigera den befintliga datavyn för att lägga till sessions-ID som en tillgänglig dimension i Customer Journey Analytics.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Data views]** på den översta menyn.
1. Välj önskad befintlig datavy.
1. Leta upp händelselistan för kvantmetrisk friktion till vänster och dra den till mätområdet i mitten.
1. I den högra rutan anger du inställningen [Inkludera/exkludera värden](/help/data-views/component-settings/include-exclude-values.md) till önskade friktionshändelser som du vill spåra. Du kan lägga till flera friktionshändelser i samma mätvärde för att kombinera dem. Du kan också dra en annan kopia av friktionshändelsefältet till mätområdet för att spåra andra friktionshändelser som ett separat mått.
1. När du har skapat alla önskade mått och mätvärden klickar du på **[!UICONTROL Save]**.

## Steg 4: Använd mått och mätvärden med övriga data i Analysis Workspace

Med händelsedata från Quantum Metric-friktionen som samlas in tillsammans med övriga besökardata kan du använda dem precis som du gör med andra mått eller mätvärden i Customer Journey Analytics.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Workspace]** på den översta menyn.
1. Välj ett befintligt projekt eller skapa ett projekt.
1. Skapa en [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md).
1. Dra önskade mått och mätvärden till Workspace Canvas för analys.

Möjliga analysidéer är:

* Trend friction-händelsedata över tid
* Lägg till Customer Journey Analytics-händelser som några steg och Quantum Metric-friktionshändelser i en utfalls- eller trattvisualisering. Med den här rapporten kan ni se var besökarna som oftast stöter på problem.
* Skapa och lägg på ett filter för besökare som upplever friktionshändelser för en djupare analys
