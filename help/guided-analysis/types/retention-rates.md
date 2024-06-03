---
title: Bevarandegrad
description: Mät hur många användare som fortsätter att använda produkten.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: f4a235d90ad44dbb192b74a03accc7ad4a39e986
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 0%

---

# Bevarandegrad

The **[!UICONTROL Retention rates]** visar hur användarna fortsätter att använda produkten med tiden, vilket kan hjälpa er att förstå hur produktmarknaden passar in. Analysen räknar användare baserat på två viktiga händelser:

* Starthändelse: Första gången en användare interagerar med starthändelsen inom datumintervallet
* Returhändelse: Den senaste gången en användare interagerade med returhändelsen inom det analyserade datumintervallet

I den här vyn representerar diagrammets x-axel tiden sedan en användares första starthändelse och y-axeln den procentandel användare som interagerar med returhändelserna. Du kan visa både kvarhållning och kurvor över varaktigheter, och varaktigheterna som visas kan anpassas med frågeinställningarna. Under diagrammet innehåller en tabell aggregerade data med alternativet att visa enskilda kohorter, som är en grupp personer som utförde starthändelsen på samma datum.

![Bevarandefrekvens, bild](../assets/retention-rates.png){style="border:1px solid gray"}

## Användningsexempel

Exempel:

* **Kohortanalys**: Gruppera användare i kohorter baserat på de åtgärder de vidtar, t.ex. registreringar eller inköp. Du kan jämföra hur väl dessa grupper behåller och avgöra hur de ska förbättra varje grupps användarupplevelse.
* **Produktmarknad**: Mät regelbunden användning av produkten och visualisera som kvarhållningskurvor. Ju större lojalitet desto bättre anpassning av produktmarknaden, och där kurvan förenklas visas hur lång tid det tar att anpassa sig. Se analysen på övergripande nivå eller uppdelad efter enskilda produktfunktioner för att få djupare insikter.
* **Analys av prenumerationstjänst**: Om din produkt har en prenumeration eller en annan typ av återkommande intäktsmodell kan du se hur många användare som får ut det mesta av din produkt. Du kan identifiera vissa egenskaper och beteenden som dessa användare uppvisar.
* **Användarengagemang**: Utvärdera hur vissa typer av användare interagerar med produkten och jämför hur ofta de returnerar. Ett givet segment med lägre lojalitet än andra kan ge er insikt i hur ni kan förbättra potentiella delupplevelser som de kan ha.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Start event]**: De händelsekriterier som en användare måste uppfylla för att kunna inkluderas i din analys. Användare som använder starthändelsen räknas i kolumnen Användare i tabellen. Detta fungerar som nämnare för de kvarhållningsräntor som visas. En händelse stöds och egenskapsfilter kan tillämpas efter behov. Som standard är start- och returhändelsen länkad, vilket innebär att en användare måste göra den valda händelsen en gång för att kunna inkluderas i kohorten och sedan en gång till för att räknas som en returnerande användare. På menyn Mer kan du bryta länken mellan start- och returhändelserna om du vill att den returnerade åtgärden ska vara en annan än inkluderingsåtgärden.
* **[!UICONTROL Return events]**: De händelsevillkor som en användare måste interagera med för att räknas som en återkommande användare i tidsintervallen. Du kan välja upp till tre returhändelser som ska jämföras med kvarhållandet.
* **[!UICONTROL Counted as]**: Den nedräkningsmetod som du vill använda för användare som behålls. Alternativen är:
   * **[!UICONTROL Metric]**: Visa antalet [!UICONTROL Users] eller [!UICONTROL Percentage of users] behålls. Nämnaren för procentuella användare som behålls är de inkluderade användarna för kohorten och är densamma för alla varaktighetsintervall.
   * **[!UICONTROL Returning]**: Används för att styra hur returnerade användare räknas. Alternativen är:
      * **[!UICONTROL On or after]**: Kallas ofta&quot;obegränsad&quot; kvarhållning. Det här alternativet räknar en användare om de återgår till eller efter den angivna varaktigheten. Till exempel dag 7 eller när som helst efter dag 7. Det här alternativet är användbart när du vill visa hur användarna fortsätter att engagera och skapar en jämnare kvarhållningskurva som ett resultat.
      * **[!UICONTROL On exactly]**: Det här alternativet kallas ofta för &quot;begränsad&quot; kvarhållning och räknar en användare om de återgår exakt till den angivna varaktigheten. Till exempel på dag 7 exakt. Det här alternativet är användbart när du vill visa hur användare returnerar inom specifika tidsramar och generera en kvarhållningskurva med mer undulation som ett resultat. Obs! I kohortanalysen i Analysis Workspace används&quot;exakt&quot; beräkning som bas för analysen.
   * **[!UICONTROL Each]**: Den tidsperiod som du vill att varje längdbucket ska vara. Alternativen är:
      * **[!UICONTROL Day/Week/Month]**: Vilka alternativ som är tillgängliga beror på vilket datumintervall som har valts. Dessa alternativ är identiska med **[!UICONTROL Interval]** när du väljer datumintervall och uppdaterar inställningen automatiskt.
      * **[!UICONTROL Custom brackets]**: Det här alternativet är endast tillgängligt för inställningen &quot;På varje&quot;. Med den kan du räkna användare över en större tidsram, till exempel Dag 7-10 i stället för Dag 7.
   * **[!UICONTROL Duration settings]**: Används för att styra de varaktighetsintervall som visas i diagrammet och tabellen. En varaktighet är den tidsperiod som infaller efter starthändelsen när returhändelsen har inträffat. Obs! Användare som är kvalificerade för varaktighetsintervall baseras på förfluten tid, inte på kalenderdagar. Om en användare till exempel kvalificerar sig för en händelse kl. 11.55 den 6 september, kvalificerar sig för en return-händelse kl. 12.05 den 7 september, kommer de inte att visas i en-dagars tidsintervall. Ett helt dygn måste förflyta innan användaren kvalificerar sig för en-dagarslängd-bucket. Vilka tidsintervall som är tillgängliga beror på vilket datumintervall du anger.
      * **[!UICONTROL Auto durations]** definierar automatiskt tidsintervallen baserat på datumintervallets längd och hur nära den aktuella dagen som datumintervallet är.
      * **[!UICONTROL Custom durations]** gör att du kan anpassa de fyra varaktighetsintervall som visas i diagrammet och tabellen.
* **[!UICONTROL Segments]**: De segment som du vill mäta. Varje markerat segment lägger till en rad i kohortabellen. Du kan inkludera upp till tre segment.

## Diagraminställningar

The [!UICONTROL Retention rates] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen inkluderar [!UICONTROL Bar] och [!UICONTROL Line].

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa kvarhållningsdata med. Giltiga alternativ är Daily, Weekly och Monthly. Samma datumintervall kan ha olika intervall, vilket påverkar alternativen för tidsintervall.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.

Om du väljer ett datumintervall som ligger nära den aktuella dagen inkluderas inte användare som till en början är för nära den aktuella dagen. Denna analys ger alltid alla användare möjlighet att ingå i alla tidsintervall. Ett meddelande under kalenderväljaren innehåller information om det datumintervall som användarna interagerar med och det intervall som bara är reserverat för återkommande användare:

* **[!UICONTROL Analyzing users who did the start event in [Date interval]]**: Om en användare engagerar sig i händelsen inom det här datumintervallet inkluderas de i analysen. Detta datumintervall garanterar att alla användare har tillräckligt med tid för att kvalificera sig för alla tidsintervall. Datumintervallet kan skilja sig från det du väljer om det ligger nära dagens datum.
* **[!UICONTROL Data from [Date interval] is reserved to complete the analysis]**: Om en användare engagerar för första gången inom den här perioden är de **not** ingår i analysen. För de senaste datumintervallen har dessa användare inte möjlighet att kvalificera sig för alla tidsintervall. För tidigare datumintervall var dessa användare aktiva utanför det valda datumintervallet.
