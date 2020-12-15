---
title: Konfigurera datavyer och attribuering
description: Beskriver hur du skapar en datavy till en plattformsdatauppsättning i Customer Journey Analytics
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 0%

---


# Komponent- och attribueringsinställningar

Varor, props och händelser i traditionell Adobe Analytics-mening finns inte längre i Customer Journey Analytics. I stället har du ett obegränsat antal schemaelement (dimensioner, mått, listfält). Alla attribueringsinställningar som du använde för att tillämpa på eVars och props under datainsamlingsprocessen tillämpas nu vid frågetiden - kallas även för rapporttidsbearbetning.

Klicka [här](https://docs.adobe.com/content/help/en/platform-learn/tutorials/cja/attribution-settings-in-data-views.html) om du vill se en videoöversikt.

Tänk på detta innan du använder attribueringsinställningar:

* I användargränssnittet för datavyer anger du standardattribuering. **Obs**: Vid ett senare datum kan du åsidosätta de här inställningarna i Workspace-projekt. Den här funktionen är dock inte tillgänglig för tillfället.

* Attributinställningarna i Customer Journey Analytics är icke-förstörande och retroaktiva. Med andra ord kan du inte göra datauppsättningarna i Customer Journey Analytics obotliga skador. Även om du råkar ta bort något av misstag kan du alltid gå tillbaka till [!UICONTROL Experience Platform] och hämta datauppsättningen igen. (Tänk dock på att det kommer att kosta ytterligare att få in datauppsättningen igen.)

* Om du vill ha en dimension som beter sig som en traditionell eVar (konverteringsvariabel) bör du konfigurera den med attributet&quot;Senaste beröringsbesök&quot; som standard.

* Om du vill ha en dimension som&quot;uppför sig&quot; som ett traditionellt utkast (trafikvariabel) bör du konfigurera den med&quot;samma Touch&quot;-attribuering som standard.

* Om du vill ha ett mätresultat som fungerar som standardmått bör du inte ändra någonting.

* Attributinställningar för mått åsidosätter attribueringsinställningar för dimensioner.

## Ange komponent- och attribueringsinställningar

När du har [angett och sparat datavyinställningar](/help/data-views/create-dataview.md) och lagt till komponenter kan du ange attribueringsinställningar om du vill göra det. Du kan ange inställningar för attribuering/förfallodatum/uppslag för mått och mätvärden. Om du t.ex. vill att attribueringen för en dimension ska finnas kvar, vill du förmodligen ange en anpassad förfallotid. Om du till exempel vill att en spårningskod (en kampanjvariabel) som är inställd på attributet Sista handen ska finnas kvar i en vecka, lägger du till en anpassad förfallotid på 1 vecka.

>[!IMPORTANT]
>Du kan välja att inte ange allokering/förfallodatum. I så fall fungerar dimensionerna som proppar (&quot;Samma Touch&quot;-attribueringsmodell). Mätvärden utan attributinställningar ärver inställningarna för den dimension som det här måttet används på.

![](assets/edit-component.png)

1. Ange komponent- och attribueringsinställningar för mått och mått. Mer information om de enskilda inställningarna finns nedan.

1. Klicka på **[!UICONTROL Save]** för att spara datavyn.


### Komponentinställning

Du kan ändra namnet på måttet eller dimensionen till något mer användarvänligt. Observera att det underliggande namnet inte ändras, bara visningsnamnet.

### Attributionsmodell

Modellen beskriver distributionen av konverteringar till händelser i en grupp. Till exempel första beröringen eller sista beröringen. Avgör hur Customer Journey Analytics tilldelar kredit för en success-händelse om en variabel tar emot flera värden före händelsen.

| UI-ikon | Attributionsmodell | Definition | När ska användas |
| --- | --- | --- | --- |
| ![Sista beröring](assets/last_touch1.png) | Sista beröring | Ger 100 % uppskattning av den beröringspunkt som inträffade senast före konverteringen. | Den mest grundläggande och vanliga attribueringsmodellen. Den används ofta för konverteringar med kort övervägandecykel. Last Touch används ofta av team som hanterar sökmarknadsföring eller analyserar interna söknyckelord. |
| ![Första beröring](assets/first_touch.png) | Första beröring | Ger 100 % kredit till den beröringspunkt som först visas i attribueringssökningsfönstret. | En annan gemensam attribueringsmodell som är användbar för att analysera marknadsföringskanaler som är avsedda att öka varumärkeskännedomen eller kundvärvningen. Den används ofta av webbannonsörer eller marknadsföringsteam på sociala medier, men den är också användbar när det gäller att utvärdera produktrekommendationernas effektivitet på plats. |
| ![Samma beröring](assets/same_touch.png) | Samma beröring | Ger 100 % kredit till just den händelse konverteringen inträffade. Om en beröringspunkt inte inträffar vid samma träff som en konvertering, klickas den under&quot;Ingen&quot;. | En användbar modell när du utvärderar innehållet eller användarupplevelsen som presenteras direkt vid konverteringen. Produkt- eller designteam använder ofta den här modellen för att bedöma hur effektiv en sida är där konverteringen sker. |
| ![Linjär](assets/linear.png) | Linjär | Ger samma beröm till alla kontaktytor som leder till konvertering. | Användbar för konverteringar med längre övervägandecykler eller användarupplevelser som kräver mer frekvent kundengagemang. Det används ofta av team som mäter hur effektiva mobilappsmeddelanden är eller med prenumerationsbaserade produkter. |
| ![U-formad](assets/u_shaped.png) | U-formad | Ger 40 % uppskattning av den första interaktionen, 40 % tack vare den sista interaktionen och delar de återstående 20 % på alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får båda 50 % rabatt. | En bra modell för dem som värderar interaktioner som har orsakat eller avslutat en konvertering, men ändå vill känna igen hjälpinteraktioner. U-Shaped-attribuering används ofta av team som har ett mer balanserat tillvägagångssätt, men som vill tillgodoräkna sig fler kanaler som har hittat eller avslutat en konvertering. |
| ![J-Shaped](assets/j_shaped.png) | J-Shaped | Ger 60 % kreativitet till den senaste interaktionen, 20 % tack till den första interaktionen och delar de återstående 20 % på alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får 75 % poäng för den senaste interaktionen och 25 % kredit ges till den första. | Den här modellen passar perfekt för dem som prioriterar Finders och Closers, men som vill fokusera på att stänga interaktioner. J-Shaped-attribuering används ofta av team som har ett mer balanserat tillvägagångssätt och vill tillgodoräkna kanaler som stängt en konvertering mer. |
| ![Inverterad J-formad](assets/inverse_j.png) | Inverterad J | Ger 60 % kredit till den första beröringspunkten, 20 % kredit till den sista beröringspunkten och delar de återstående 20 % till alla beröringspunkter däremellan. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För konverteringar med två kontaktpunkter får 75 % kredit för den första interaktionen och 25 % kredit för den sista. | Den här modellen är perfekt för dem som prioriterar finare och närare, men som vill fokusera på att hitta interaktioner. Inverterad J-attribuering används av team som använder ett mer balanserat tillvägagångssätt och vill tillgodoräkna kanaler som initierade en konvertering mer. |
| ![Anpassat](assets/custom.png) | Anpassad | Gör att du kan ange de vikter du vill ge de första beröringspunkterna, de sista beröringspunkterna och eventuella mellanliggande beröringspunkter. De angivna värdena normaliseras till 100 % även om de anpassade siffrorna inte läggs till i 100. Vid konvertering med en enda kontaktpunkt får du 100 % kredit. För interaktioner med två beröringspunkter ignoreras parametern middle. Den första och sista beröringspunkten normaliseras sedan till 100 % och krediteringen tilldelas därefter. | Den här modellen är perfekt för dem som vill ha fullständig kontroll över sin attribueringsmodell och har särskilda behov som andra attribueringsmodeller inte uppfyller. |
| ![Tidsminskning](assets/time_decay.png) | Time-Decay | Följer och exponentiell minskning med en anpassad halveringsparameter, där standardvärdet är 7 dagar. Vikten för varje kanal beror på hur lång tid det tar mellan öppnandet av kontaktpunkten och den slutliga konverteringen. Formeln som används för att bestämma kredit är `2`<sup>`(-t/halflife)`</sup>, där `t` är tiden mellan en beröringspunkt och en konvertering. Alla beröringspunkter normaliseras sedan till 100 %. | Perfekt för team som regelbundet genomför videoreklam eller marknadsför mot händelser med ett förutbestämt datum. Ju längre en konvertering sker efter en marknadsföringshändelse, desto mindre kredit ges. |
| ![Deltagande](assets/participation.png) | Deltagande | Alla unika kontaktpunkter får 100 % beröm. Det totala antalet konverteringar är uppblåst jämfört med andra attribueringsmodeller. Deltagande duplicerar kanaler som ses flera gånger. | Utmärkt för att förstå vilka kunder som ofta exponeras för en viss interaktion. Medieorganisationer använder ofta den här modellen för att beräkna innehållets hastighet. Butiksorganisationer använder ofta den här modellen för att förstå vilka delar av deras sajt som är avgörande för konverteringen. |

### Förfaller

Anger en tidsperiod eller händelse efter vilken dimensionsobjektet förfaller (inte längre får kredit för lyckade händelser). Du kan ange att attributet ska förfalla på session, person eller anpassad nivå.

| Inställning | Definition |
|---|---|
| Session | Kallas tidigare nivån &#39;Besök&#39;. Konverteringshändelser utanför sidvyn eller sessionen associeras inte med dimensionen eller måttet. |
| Person (rapporteringsfönster) | Kallas tidigare nivån &quot;Besökare&quot;. Konverteringshändelser som inte är kopplade till den här personen är inte kopplade till dimensionen eller måttet. |
| Anpassad tid | Ange anpassade minuter, timmar, dagar, månader eller kvartal. Konverteringshändelser efter den angivna tidsperioden associeras inte med dimensionen eller måttet. |

Mer information finns i [Attribution IQ doc](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html).

### Fönstret Lookback

Ett uppslagsfönster är den tid som en konvertering bör titta tillbaka för att inkludera kontaktpunkter. Attributionsmodeller som ger större tilltro till första interaktioner ser större skillnader när du visar olika uppslagsfönster.

* **Session:** Går tillbaka till början av sessionen där en konvertering inträffade. Besöksfönster är smala eftersom de inte ser längre ut än själva sessionen. Sessionssökningsfönster respekterar den ändrade besöksdefinitionen i datavyer.
* **Person (rapportfönster):** Looks at all sessions back to the 1st of the month of the current date range. Personsökningsfönster är breda, eftersom de kan omfatta många sessioner. Om rapportens datumintervall till exempel är 15 september - 30 september, inkluderar datumintervallet för personsökning 1 september - 30 september.
