---
title: Konfigurera datavyer och attribut
description: Beskriver hur du skapar en datavy till en plattformsdatamängd i kundresanalysen
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 0%

---


# Inställningar för komponenter och tilldelning

Varor, support och händelser i traditionell Adobe Analytics-mening finns inte längre i Customer Journey Analytics. I stället har du obegränsade schemaelement (dimensioner, mått, listfält). Alla tilldelningsinställningar som du tidigare tillämpade på eVars och support under datainsamlingsprocessen tillämpas nu vid frågestunden - kallas även för rapporttidsbearbetning.

Klicka [här](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/attribution-settings-in-data-views.html) för en videoöversikt.

Tänk på detta innan du tillämpar attributinställningar:

* I användargränssnittet för datavyer anger du standardattributet. **Anteckning**: Vid ett senare tillfälle kan du åsidosätta dessa inställningar i arbetsyteprojekt. Den här funktionen är dock inte tillgänglig för tillfället.

* Attributinställningarna i Customer Journey Analytics är icke-destruktiva och retroaktiva. Med andra ord kan du inte göra oåterkallelig skada på dina datamängder i Customer Journey Analytics. Även om du av misstag tar bort något kan du alltid gå tillbaka till [!UICONTROL Experience Platform] och för in datauppsättningen igen. (Kom ihåg att det kommer att medföra extra kostnader om datamängden återinförs.)

* Om du vill ha en dimension som &quot;uppför&quot; som en traditionell eVar (konverteringsvariabel) bör du konfigurera den med attributet &quot;Last Touch Visit&quot; som standard.

* Om du vill ha en dimension &quot;bete&quot; som ett traditionellt stöd (trafikvariabel) bör du konfigurera den med &quot;Samma Touch&quot;-attribut som standard.

* Om du vill ha ett metriskt &quot;beteende&quot; som ett standardmått bör du inte ändra någonting.

* Attributinställningar för mått åsidosätter attributinställningar för dimensioner.

## Ange inställningar för komponenter och attribut

Efter det att du har [ange och spara inställningar för datavyn](/help/data-views/create-dataview.md) och tillagda komponenter kan du ange attributinställningar om du väljer att göra det. Du kan ange inställningar för attribut/förfallotid/återsökning för dimensioner och mått. Om du t.ex. vill att attributet för en dimension ska bestå, kommer du troligen att ange en anpassad förfallotid. Om du t.ex. vill att en &#39;spårningskod&#39;-dimension (en kampanjvariabel) som är inställd på &#39;Last Touch&#39;-attribut ska bestå i en vecka, lägger du till en anpassad förfallotid på 1 vecka.

>[!IMPORTANT]
>Du kan välja att inte ange allokering/förfallodatum. I så fall beter sig dimensionerna på samma sätt som proppar (&quot;Samma Touch&quot;-attributmodell). Metoder utan attributinställningar ärver inställningarna för dimensionen som det här måttet används på.

![](assets/edit-component.png)

1. Ange inställningar för komponenter och attribut för dimensioner och mått. Se nedan för information om enskilda inställningar.

1. Klicka **[!UICONTROL Save]** för att spara datavyn.


### Komponentinställning

Du kan ändra namnet på måttet eller dimensionen till något mer användarvänligt. Observera att det underliggande namnet inte ändras, bara visningsnamnet.

### Attributmodell

Modellen beskriver distributionen av konverteringar till händelserna i en grupp. Till exempel första eller sista beröringen. Bestämmer hur kundresanalysen tilldelar kredit för en lyckad händelse om en variabel erhåller flera värden före händelsen.

| UI-ikon | Attributmodell | Definition | När ska du använda |
| --- | --- | --- | --- |
| ![Sista beröring](assets/last_touch1.png) | Sista beröring | Ger 100 % beröm till den beröringspunkt som inträffade senast före konverteringen. | Den mest grundläggande och gemensamma tilldelningsmodellen. Den används ofta för omräkningar med kort omräkningscykel. Last Touch används vanligen av team som hanterar sökmarknadsföring eller analyserar interna söknyckelord. |
| ![Första beröring](assets/first_touch.png) | Första beröring | Ger 100 % kredit till den beröringspunkt som först sågs i attributsökfönstret. | En annan gemensam tilldelningsmodell som är användbar för analys av marknadsföringskanaler som är avsedda att öka medvetenheten om varumärket eller förvärvet av kunder. Den används ofta av presentationsgrupper eller sociala marknadsföringsteam, men är också bra för att bedöma produktrekommendationernas effektivitet på plats. |
| ![Samma beröring](assets/same_touch.png) | Samma beröring | Ger 100 % kredit till den mycket drabbade platsen för omvandlingen. Om en pekpunkt inte inträffar på samma träff som en konvertering, så blockeras den under &quot;Ingen&quot;. | En användbar modell när du utvärderar innehållet eller användarupplevelsen som presenterades omedelbart vid konverteringen. Produkt- eller designgrupper använder ofta den här modellen för att bedöma effektiviteten hos en sida där konvertering sker. |
| ![Linjär](assets/linear.png) | Linjär | Ger lika mycket beröm till varje beröringspunkt som leder fram till en konvertering. | Användbar för konverteringar med längre eftertanke eller användarupplevelser som kräver mer frekvent kundservice. Den används ofta av team som mäter effektiviteten hos mobilappmeddelanden eller med prenumerationsbaserade produkter. |
| ![U-formad](assets/u_shaped.png) | U-formad | Ger 40 % kredit till den första interaktionen, 40 % kredit till den sista interaktionen och delar upp de återstående 20 % till eventuella kontaktpunkter mellan. För konverteringar med en enda kontaktpunkt ges 100 % kredit. För konverteringar med två kontaktpunkter ges 50 % kredit till båda. | En utmärkt modell för dem som värderar interaktioner som införde eller avslutade en konvertering, men som ändå vill känna igen medhjälpande interaktioner. U-formad tilldelning används ofta av grupper som har en mer balanserad inställning men som vill ge större kredit till kanaler som hittat eller avslutat en konvertering. |
| ![J-Shaped](assets/j_shaped.png) | J-Shaped | Ger 60 % kredit till den senaste interaktionen, 20 % kredit till den första interaktionen och delar upp de återstående 20 % till eventuella kontaktpunkter mellan. För konverteringar med en enda kontaktpunkt ges 100 % kredit. För konverteringar med två beröringspunkter ges 75 % kredit till den sista interaktionen, och 25 % kredit ges till den första. | Den här modellen är utmärkt för dem som prioriterar findrar och closers, men som vill fokusera på att stänga interaktioner. J-Shaped-tilldelningen används ofta av grupper som intar en mer balanserad hållning och vill ge större kredit till kanaler som avslutade en konvertering. |
| ![Inverterad J-formad](assets/inverse_j.png) | Inverse J | Ger 60 % kredit till den första pekpunkten, 20 % kredit till den sista pekpunkten och delar upp de återstående 20 % till eventuella kontaktpunkter däremellan. För konverteringar med en enda kontaktpunkt ges 100 % kredit. För konverteringar med två beröringspunkter ges 75 procent kredit till den första interaktionen, och 25 procent kredit ges till den sista. | Den här modellen är idealisk för dem som prioriterar sökare och stängare, men som vill fokusera på att hitta interaktioner. Inverterad J-tilldelning används av team som har en mer balanserad inställning och vill ge mer kredit till kanaler som initierade en konvertering. |
| ![Anpassat](assets/custom.png) | Anpassad | Med det här alternativet kan du ange de vikter du vill ge till de första pekpunkterna, de sista pekpunkterna och eventuella mellanliggande pekpunkter. De angivna värdena normaliseras till 100 % även om de angivna anpassade talen inte läggs till i 100. För konverteringar med en enda kontaktpunkt ges 100 % kredit. För interaktioner med två pekpunkter ignoreras mittparametern. Den första och sista punkten normaliseras sedan till 100 procent, och krediter tilldelas därefter. | Denna modell är perfekt för dem som vill ha full kontroll över sin tilldelningsmodell och som har särskilda behov som andra tilldelningsmodeller inte uppfyller. |
| ![Tidsfördröjning](assets/time_decay.png) | Tidsfrist | Följer och exponentiell nedgång med en anpassad halveringstid, där standardvärdet är 7 dagar. Vikten på varje kanal beror på hur lång tid som förflutit mellan aktivering av pekpunkten och eventuell konvertering. Den formel som används för att fastställa krediten är `2`<sup>`(-t/halflife)`</sup>där `t` är tiden mellan en pekpunkt och en konvertering. Alla pekpunkter normaliseras sedan till 100 %. | Perfekt för lag som regelbundet gör videoreklam eller marknadsför mot evenemang med ett förutbestämt datum. Ju längre en konvertering sker efter en marknadsföringshändelse, desto mindre kredit ges. |
| ![Deltagande](assets/participation.png) | Deltagande | Ger 100 % kredit till alla unika pekpunkter. Det totala antalet konverteringar är uppblåst jämfört med andra attributmodeller. Deltagande deduplicerar kanaler som visas flera gånger. | Utmärkt för att förstå vilka kunder som ofta exponeras för en given interaktion. Medieorganisationer använder ofta den här modellen för att beräkna innehållshastigheten. Detaljhandelsorganisationer använder ofta den här modellen för att förstå vilka delar av deras webbplats som är avgörande för konverteringen. |

### Förfallodatum

Anger en tidsperiod eller händelse efter vilken dimensionsobjektet upphör att gälla (tar inte längre emot kredit för lyckade händelser). Du kan ställa in attributets förfallotid på session, person eller anpassad nivå.

| Inställning | Definition |
|---|---|
| Sessionssession | Tidigare känd som &quot;besöksnivån&quot;. Konverteringshändelser utanför sidvyn eller sessionen associeras inte med dimensionen eller måttet. |
| Person (rapporteringsfönster) | Tidigare känd som Visitor-nivån. Konverteringshändelser som inte är kopplade till den här personen associeras inte med dimensionen eller måttet. |
| Anpassad tid | Ange anpassade minuter, timmar, dagar, månader eller kvartal. Omvandlingshändelser efter den angivna tidsperioden associeras inte med dimensionen eller måttet. |

Mer information finns i [Attribut IQ doc](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html).

### Fönstret Lookback

Ett uppslagsfönster är den tid som en konvertering ska titta tillbaka för att inkludera pekpunkter. Attributmodeller som ger större kredit till de första interaktionerna ser större skillnader när du ser olika uppslagsfönster.

* **Session:** Söker tillbaka till början av den session där en konvertering inträffade. Besök uppslagsfönster är smala eftersom de inte ser längre ut än till sessionen. Sessionsgranskningsfönster respekterar den ändrade besöksdefinitionen i datavyer.
* **Person (rapportperiod):** Alla sessioner säkerhetskopieras fram till den 1:a i månaden för det aktuella datumintervallet. Personsökfönster är breda, eftersom de kan omfatta många sessioner. Om rapportdatumintervallet t.ex. är den 15 september - den 30 september, omfattar personsökningsdatumintervallet den 1 september - den 30 september.
