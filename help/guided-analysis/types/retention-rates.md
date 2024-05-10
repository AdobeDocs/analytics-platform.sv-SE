---
title: Bevarandegrad
description: Mät hur många användare som fortsätter att använda produkten.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: 2b8afe1dbac5057f867437e2bfce27f3bd752d57
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 0%

---

# Bevarandegrad

The **[!UICONTROL Retention rates]** I den här vyn visas hur användarna upprepar användningsbeteendet i produkten med tiden, vilket kan hjälpa dig att förstå hur produktmarknaden passar in. I den här vyn representerar den vågräta axeln antalet dagar sedan en användares ursprungliga engagemang och den lodräta axeln den procentandel användare som interagerar igen.

Denna analys räknar användarna baserat på två viktiga händelser:

* Starthändelse: Första gången en användare interagerar med händelsen inom datumintervallet
* Returhändelse: Den senaste gången en användare interagerade med händelsen inom det analyserade datumintervallet

Varaktighetskassetten &quot;Dag 0&quot; representerar den inledande tid som en användare interagerade med händelsen och är alltid lika med exakt 100 %. Den här bucket är nämnaren som används för att beräkna den procentandel användare som behålls.

Efterföljande varaktighetsintervall anger antalet användare som har returnerat på eller efter den tidslängden. Det här antalet är den täljare som används för att beräkna den procentandel användare som behålls.

* Om en användare endast engagerar sig i händelsen en gång under det önskade datumintervallet (det inledande engagemanget) visas de bara i&quot;dag 0&quot;-varaktighetsknappen.
* Om en användare engagerar sig i händelsen flera dagar efter att först ha kvalificerat sig för att ingå i analysen, visas de i den senaste kvalificerande varaktighetsgruppen och alla varaktighetsintervall som leder fram till den. Den här typen av beräkning kallas ibland för&quot;obegränsad kvarhållning&quot;. Du kan ändra den här beräkningsinställningen i frågerinjen.

Användare som är kvalificerade för varaktighetsintervall baseras på förfluten tid, inte på kalenderdag. Om en användare till exempel kvalificerar sig för en händelse kl. 11.55 den 6 september, kvalificerar sig för en return-händelse kl. 12.05 den 7 september, kommer de inte att visas i en-dagars tidsintervall. Ett helt dygn måste förflyta innan användaren kvalificerar sig för en-dagarslängd-bucket.

![Bevarandefrekvens, bild](../assets/retention-rates.png){style="border:1px solid gray"}

## Användningsexempel

Exempel:

* **Kohortanalys**: Gruppera användare i kohorter baserat på de åtgärder de vidtar, t.ex. registreringar eller inköp. Du kan jämföra hur väl dessa grupper behåller och avgöra hur de ska förbättra varje grupps användarupplevelse.
* **Produktmarknad**: Mät regelbunden användning av produkten och visualisera som kvarhållningskurvor. Ju större lojalitet desto bättre anpassning av produktmarknaden, och där kurvan förenklas visas hur lång tid det tar att anpassa sig. Se analysen på övergripande nivå eller uppdelad efter enskilda produktfunktioner för att få djupare insikter.
* **Analys av prenumerationstjänst**: Om din produkt har en prenumeration eller en annan typ av återkommande intäktsmodell kan du se hur många användare som får ut det mesta av din produkt. Du kan identifiera vissa egenskaper och beteenden som dessa användare uppvisar.
* **Användarengagemang**: Utvärdera hur vissa typer av användare interagerar med produkten och jämför hur ofta de returnerar. Ett givet segment med lägre lojalitet än andra kan ge er insikt i hur ni kan förbättra potentiella delupplevelser som de kan ha.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Start event]**: De händelsekriterier som en användare måste uppfylla för att kunna inkluderas i din analys. Användare som deltar i starthändelsen inkluderas i den första gruppen med användare som totalt uppgår till 100 %. En händelse stöds, men du kan inkludera egenskapsfilter. Du kan länka ihop start- och returhändelser med hjälp av menyn med tre punkter. Länkning av start- och returhändelser innebär att villkoren som ska visas i den inledande varaktighetsgruppen och efterföljande varaktighetsintervall är desamma.
* **[!UICONTROL Return events]**: De händelsekriterier som en användare måste interagera med för att kunna inkluderas i efterföljande tidsintervall. Du kan välja upp till tre returhändelser. Varje return-händelse genererar en sida vid sida-analys med de andra inkluderade return-händelserna.
* **[!UICONTROL Counted as]**: Den nedräkningsmetod som du vill använda för användare som behålls. Alternativen är:
   * **[!UICONTROL Metric]**: Räkna antalet [!UICONTROL Users retained] eller [!UICONTROL Percentage of users retained].
   * **[!UICONTROL Returning]**: Som standard inkluderar den här analysen användare i den bucket som de returnerade och alla föregående bucklar. Ändra inställningen till **[!UICONTROL On exactly]** att bara inkludera användare i den specifika bucket som de kvalificerar sig för.
   * **[!UICONTROL Each]**: Den tidsperiod som du vill att varje längdbucket ska vara. Den här inställningen är identisk med **[!UICONTROL Interval]** när du väljer datumintervall.
   * **[!UICONTROL Duration settings]**: Används för att styra hur användarna visas i analysen efter antalet dagar. Vilka tidsintervall som är tillgängliga beror på vilket datumintervall du anger. **[!UICONTROL Auto durations]** anger automatiskt tidsintervall baserat på datumintervallets längd och hur nära den aktuella dagen som datumintervallet ligger. **[!UICONTROL Custom durations]** I kan du ange fyra varaktighetsintervall med önskade intervall manuellt.
* **[!UICONTROL Segments]**: De segment som du vill mäta. Varje markerat segment lägger till en rad i kohortabellen. Du kan inkludera upp till tre segment.

## Diagraminställningar

The [!UICONTROL Retention rates] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen inkluderar [!UICONTROL Bar] och [!UICONTROL Line]. Radvisualiseringen visar dag 0 visuellt i diagrammet.

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa kvarhållningsdata med. Giltiga alternativ är Daily, Weekly och Monthly. Samma datumintervall kan ha olika intervall, vilket påverkar alternativen för tidsintervall.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.

Om du väljer ett datumintervall som ligger nära den aktuella dagen inkluderas inte användare som till en början är för nära den aktuella dagen. Denna analys ger alltid alla användare möjlighet att ingå i alla tidsintervall. Ett meddelande under kalenderväljaren innehåller information om det datumintervall som användarna interagerar med och det intervall som bara är reserverat för återkommande användare:

* **[!UICONTROL Analyzing users who did the start event in [Date interval]]**: Om en användare engagerar sig i händelsen inom det här datumintervallet inkluderas de i analysen. Detta datumintervall garanterar att alla användare har tillräckligt med tid för att kvalificera sig för alla tidsintervall. Datumintervallet kan skilja sig från det du väljer om det ligger nära dagens datum.
* **[!UICONTROL Data from [Date interval] is reserved to complete the analysis]**: Om en användare engagerar för första gången inom den här perioden är de **not** ingår i analysen. För de senaste datumintervallen har dessa användare inte möjlighet att kvalificera sig för alla tidsintervall. För tidigare datumintervall var dessa användare aktiva utanför det valda datumintervallet.

## Kohortabell

Tabellen nedanför diagrammet innehåller en sammanställd vy (liknande diagramdata) och en fullständig kohorttabell. Den fullständiga kohorttabellen innehåller information om varje enskilt datumintervall och när användare är engagerade.
