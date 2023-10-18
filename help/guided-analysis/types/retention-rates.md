---
title: Bevarandegrad
description: Mät hur många användare som fortsätter att använda produkten.
feature: Guided Analysis
keywords: produktanalys
source-git-commit: 74525c4ce9ad1fd3f3abf35a9d9cb2c521d23874
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 0%

---

# Bevarandegrad

The **[!UICONTROL Retention rates]** vyn visar hur många procent användare som returnerar efter det ursprungliga engagemanget inom det önskade datumintervallet. Den vågräta axeln representerar antalet dagar sedan en användares första engagemang. Den lodräta axeln representerar procentandelen användare som interagerar igen.

Denna analys räknar användarna baserat på två viktiga händelser:

* Första gången en användare interagerade med händelsen inom datumintervallet
* Den senaste gången en användare interagerade med händelsen inom det analyserade datumintervallet

Varaktighetskassetten &quot;dag 0&quot; representerar första gången som en användare interagerar med händelsen och alltid är lika med exakt 100 %. Hur lång tid som går mellan det inledande engagemanget och det återkommande engagemanget avgör var användaren befinner sig.

* Om en användare endast engagerar sig i händelsen en gång under det önskade datumintervallet (det inledande engagemanget) visas de bara i tidsintervallet&quot;dag 0&quot;.
* Om en användare engagerar sig i händelsen flera dagar efter att först ha kvalificerat sig för att ingå i analysen, visas de i den senaste kvalificerande varaktighetsgruppen och alla varaktighetsintervall som leder fram till den.
* Om en användare engagerar sig i händelsen många gånger under det konfigurerade datumintervallet inkluderas endast den första och den sista händelsen i analysen.

## Användningsexempel

Exempel:

* **Kohortanalys**: Gruppera användare i kohorter baserat på alla händelser, t.ex. registreringar eller inköp. Du kan jämföra hur kantiga de här grupperna är och avgöra hur man ska förbättra gruppens användarupplevelse.
* **Analys av prenumerationstjänst**: Om din produkt har en prenumeration eller en annan typ av återkommande intäktsmodell kan du se hur många användare som får ut det mesta av din produkt. De som inte använder produkten eller tjänsten är mer benägna att försvinna, vilket gör det möjligt att identifiera och fokusera på användarna.
* **Användarengagemang**: Utvärdera hur vissa typer av användare interagerar med produkten och jämför hur ofta de returnerar. Ett givet segment med en brantare kundlojalitetskurva än andra kan ge er insikter om hur ni kan förbättra potentiella delupplevelser som de kan ha.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Start & return event]**: De händelsekriterier som en användare måste uppfylla för att kunna inkluderas i din analys. En händelse stöds, men du kan inkludera egenskapsfilter.
* **[!UICONTROL People]**: De segment som du vill mäta. Varje markerat segment lägger till en rad i kohortabellen. Du kan inkludera upp till tre segment.

## Diagraminställningar

The [!UICONTROL Retention rates] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Metric]**: Hur du vill mäta användarnas behållning. Alternativen inkluderar [!UICONTROL Users retained] och [!UICONTROL Percentage of users retained].
* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen inkluderar [!UICONTROL Bar] och [!UICONTROL Line].

## Varaktighetsinställningar

Används för att styra hur användarna visas i analysen efter antal dagar.

* **[!UICONTROL Auto durations]**: Ange varaktighet automatiskt baserat på datumintervallets längd och hur nära den aktuella dagen som datumintervallet ligger.
* **[!UICONTROL Custom durations]**: Ange önskade förflutna dagar manuellt. Du kan ange fyra varaktigheter.

Du kan inte ange en varaktighet som är längre än den tid det tar för en användare att interagera med en händelse och kvalificera sig för den sista tidsperioden innan den når den aktuella dagen. Om det aktuella datumet till exempel är 30 september och det konfigurerade datumintervallet är 1 september till 30 september, är den maximala längden för det här datumintervallet 14 dagar.

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa kvarhållningsdata för. Giltiga alternativ är Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall, vilket påverkar automatisk inställning av varaktighetsdagar.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.

Om du väljer ett datumintervall som ligger nära den aktuella dagen inkluderas inte användare som till en början är för nära den aktuella dagen. Denna analys ger alltid alla användare möjlighet att ingå i alla tidsintervall. Ett meddelande under kalenderväljaren ger information om det datumintervall som användarna interagerar med, och det intervall som bara är reserverat för återkommande användare:

* **Analyserar den första [Datumintervall] i kohorten från [Datumintervall]**: Om en användare engagerar sig i händelsen inom det här datumintervallet inkluderas de i analysen. Detta datumintervall garanterar att alla användare har tillräckligt med tid för att kvalificera sig för alla tidsintervall. Datumintervallet kan skilja sig från det du väljer om det ligger nära dagens datum.
* **Den slutliga [Datumintervall] är reserverad för att slutföra analysen**: Om en användare interagerar med händelsen för första gången inom detta intervall är de **not** ingår i analysen. Användare som till att börja med interagerar med händelsen inom det här intervallet har inte möjlighet att kvalificera sig för alla tidsintervall eller ligger utanför det önskade datumintervallet.

## Kohortabell

Tabellen nedanför diagrammet innehåller en sammanställd vy (liknande diagramdata) och en fullständig kohorttabell. Den fullständiga kohorttabellen innehåller information om varje enskilt datumintervall och när användare är engagerade.
