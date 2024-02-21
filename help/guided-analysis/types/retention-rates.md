---
title: Bevarandegrad
description: Mät hur många användare som fortsätter att använda produkten.
feature: Guided Analysis
keywords: produktanalys
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 0%

---

# Bevarandegrad

The **[!UICONTROL Retention rates]** vyn visar hur många procent användare som returnerar efter det ursprungliga engagemanget inom det önskade datumintervallet. Den vågräta axeln representerar antalet dagar sedan en användares ursprungliga engagemang. Den lodräta axeln representerar procentandelen användare som interagerar igen.

Denna analys räknar användarna baserat på två viktiga händelser:

* Starthändelse: Första gången en användare interagerar med händelsen inom datumintervallet
* Returhändelse: Den senaste gången en användare interagerade med händelsen inom det analyserade datumintervallet

Varaktighetskassetten &quot;Dag 0&quot; representerar den inledande tid som en användare interagerade med händelsen och är alltid lika med exakt 100 %. Den här bucket är nämnaren som används för att beräkna den procentandel användare som behålls.

Efterföljande varaktighetsintervall anger antalet användare som har returnerat på eller efter den tidslängden. Det här antalet är den täljare som används för att beräkna den procentandel användare som behålls.

* Om en användare endast engagerar sig i händelsen en gång under det önskade datumintervallet (det inledande engagemanget) visas de bara i&quot;dag 0&quot;-varaktighetsknappen.
* Om en användare engagerar sig i händelsen flera dagar efter att först ha kvalificerat sig för att ingå i analysen, visas de i den senaste kvalificerande varaktighetsgruppen och alla varaktighetsintervall som leder fram till den. Den här typen av beräkning kallas ibland för&quot;obegränsad kvarhållning&quot;.
* Om en användare engagerar sig i händelsen många gånger under det konfigurerade datumintervallet inkluderas endast den första och den sista händelsen i analysen.

![Bevarandefrekvens, bild](../assets/retention-rates.png){style="border:1px solid gray"}

## Användningsexempel

Exempel:

* **Kohortanalys**: Gruppera användare i kohorter baserat på de åtgärder de vidtar, t.ex. registreringar eller inköp. Du kan jämföra hur väl dessa grupper behåller och avgöra hur de ska förbättra varje grupps användarupplevelse.
* **Analys av prenumerationstjänst**: Om din produkt har en prenumeration eller en annan typ av återkommande intäktsmodell kan du se hur många användare som får ut det mesta av din produkt. Du kan identifiera vissa egenskaper och beteenden som dessa användare uppvisar för att bättre förstå hur er produktmarknad passar.
* **Användarengagemang**: Utvärdera hur vissa typer av användare interagerar med produkten och jämför hur ofta de returnerar. Ett givet segment med lägre lojalitet än andra kan ge er insikter om hur ni kan förbättra potentiella delupplevelser som de kan ha.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Start & return event]**: De händelsekriterier som en användare måste uppfylla för att kunna inkluderas i din analys. En händelse stöds, men du kan inkludera egenskapsfilter.
* **[!UICONTROL Counted as]**: Den nedräkningsmetod som du vill använda för användare som behålls. Alternativen inkluderar [!UICONTROL Users retained] och [!UICONTROL Percentage of users retained].
* **[!UICONTROL Segments]**: De segment som du vill mäta. Varje markerat segment lägger till en rad i kohortabellen. Du kan inkludera upp till tre segment.

## Diagraminställningar

The [!UICONTROL Retention rates] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen inkluderar [!UICONTROL Bar] och [!UICONTROL Line].

## Varaktighetsinställningar

Används för att styra hur användarna visas i analysen efter antal dagar.

* **[!UICONTROL Auto durations]**: Ange varaktighet automatiskt baserat på datumintervallets längd och hur nära den aktuella dagen som datumintervallet ligger. Varaktighetsintervall kurateras för de vanligaste användningsfallen.
* **[!UICONTROL Custom durations]**: Ange önskade tidsintervall manuellt. Du kan ange fyra varaktigheter.

Vilka tidsintervall som är tillgängliga beror på vilket datumintervall du anger.

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa kvarhållningsdata med. Giltiga alternativ är Daily, Weekly, Monthly och Quarterly. Samma datumintervall kan ha olika intervall, vilket påverkar automatisk inställning av varaktighetsintervall.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.

Om du väljer ett datumintervall som ligger nära den aktuella dagen inkluderas inte användare som till en början är för nära den aktuella dagen. Denna analys ger alltid alla användare möjlighet att ingå i alla tidsintervall. Ett meddelande under kalenderväljaren ger information om det datumintervall som användarna interagerar med, och det intervall som bara är reserverat för återkommande användare:

* **Analyserar användare som startade händelsen i [Datumintervall]**: Om en användare engagerar sig i händelsen inom det här datumintervallet inkluderas de i analysen. Detta datumintervall garanterar att alla användare har tillräckligt med tid för att kvalificera sig för alla tidsintervall. Datumintervallet kan skilja sig från det du väljer om det ligger nära dagens datum.
* **Data från [Datumintervall] är reserverad för att slutföra analysen**: Om en användare engagerar för första gången inom den här perioden är de **not** ingår i analysen. För de senaste datumintervallen har dessa användare inte möjlighet att kvalificera sig för alla tidsintervall. För tidigare datumintervall var dessa användare aktiva utanför det valda datumintervallet.

## Kohortabell

Tabellen nedanför diagrammet innehåller en sammanställd vy (liknande diagramdata) och en fullständig kohorttabell. Den fullständiga kohorttabellen innehåller information om varje enskilt datumintervall och när användare är engagerade.
