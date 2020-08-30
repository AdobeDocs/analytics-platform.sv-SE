---
title: Attributmodeller och granskningsfönster
description: Hur olika typer av tilldelning fördelar kredit mellan dimensionsposter.
translation-type: tm+mt
source-git-commit: e32311ce4975107e1b7ca2cb2eaadc2c68a93c92
workflow-type: tm+mt
source-wordcount: '1539'
ht-degree: 0%

---


# Attributmodeller och granskningsfönster

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Attributbegreppet i Adobe Analytics kräver två komponenter:

* **Attributmodell:** I modellen beskrivs hur konverteringar distribueras till träffar i en grupp. Till exempel första eller sista beröringen.
* **Fönster för attributsökning:** I uppslagsfönstret beskrivs vilka grupper av träffar som ska beaktas för varje modell. Besök eller besökare till exempel.

## Attributmodeller

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
| ![Tidsfördröjning](assets/time_decay.png) | Tidsfrist | Följer och exponentiell nedgång med en anpassad halveringstid, där standardvärdet är 7 dagar. Vikten på varje kanal beror på hur lång tid som förflutit mellan aktivering av pekpunkten och eventuell konvertering. Den formel som används för att fastställa krediten är `2^(-t/halflife)`där `t` är tiden mellan en pekpunkt och en konvertering. Alla pekpunkter normaliseras sedan till 100 %. | Perfekt för lag som regelbundet gör videoreklam eller marknadsför mot evenemang med ett förutbestämt datum. Ju längre en konvertering sker efter en marknadsföringshändelse, desto mindre kredit ges. |
| ![Deltagande](assets/participation.png) | Deltagande | Ger 100 % kredit till alla unika pekpunkter. Det totala antalet konverteringar är uppblåst jämfört med andra attributmodeller. Deltagande deduplicerar kanaler som visas flera gånger. | Utmärkt för att förstå vilka kunder som ofta exponeras för en given interaktion. Medieorganisationer använder ofta den här modellen för att beräkna innehållshastigheten. Detaljhandelsorganisationer använder ofta den här modellen för att förstå vilka delar av deras webbplats som är avgörande för konverteringen. |
| ![Algorithmic](assets/algorithmic.png) | [Algorithmic](/help/analysis-workspace/attribution/algorithmic.md) | Använder statistiska metoder för att dynamiskt fastställa den optimala kreditfördelningen för det valda måttet. | Det är användbart för att undvika gissningar eller heuristik när du väljer rätt tilldelningsmodell för ditt företag. |

## Återställningsfönster

Ett uppslagsfönster är den tid som en konvertering ska titta tillbaka för att inkludera pekpunkter. Attributmodeller som ger större kredit till de första interaktionerna ser större skillnader när du ser olika uppslagsfönster.

* **Besök fönstret för sökning:** Det ser ut ända fram till början av besöket där en konvertering skedde. Besök uppslagsfönster är smala eftersom de inte ser längre än till besöket. Besök granskningsfönster respekterar den ändrade besöksdefinitionen i virtuella rapportpaket.

* **Visitor-fönster:** Alla besök pågår fram till den 1:a i månaden i aktuellt datumintervall. Besöksfönster är breda eftersom de kan omfatta många besök. Vid besökssökning beaktas alla värden från början av månaden i rapportens datumintervall. Om rapportdatumintervallet t.ex. är 15-30 september, omfattar besökarens tidsintervall 1-30 september.

* **Anpassat uppslagsfönster:** Med det här alternativet kan du utöka attributfönstret utanför rapportdatumintervallet upp till högst 90 dagar. Anpassade granskningsfönster utvärderas för varje konvertering under rapporteringsperioden. Om en konvertering till exempel sker den 20 februari, skulle ett uppslagsfönster på 10 dagar utvärdera alla dimensionens pekpunkter från 10 till 20 feb i attributmodellen.

>[!NOTE]
>
>**[!UICONTROL Custom lookback windows]** för närvarande testas i begränsad omfattning. Se [Utsläpp av Adobe Analytics-funktioner](https://docs.adobe.com/content/help/sv-SE/analytics/landing/an-releases.html) för mer information.

## Exempel

Tänk på följande exempel:

1. Den 15 september anländer en besökare till din webbplats med hjälp av en betald sökannons, sedan går han.
2. Den 18 september anländer besökaren till din webbplats igen via en social medielänk som de fick från en vän. De lägger till flera artiklar i sin vagn, men köper ingenting.
3. Den 24 september skickar ditt marknadsföringsteam ett e-postmeddelande med en kupong för några av artiklarna i deras kundvagn. De tillämpar kupongen, men besöker flera andra platser för att se om det finns några andra kuponger tillgängliga. De hittar en till genom en bildskärm och gör sedan ett köp för 50 dollar.

Beroende på ditt granskningsfönster och din attributmodell får kanalerna olika kredit. Följande är några anmärkningsvärda exempel:

* Använda **första beröring** och **gå till uppslagsfönstret**, är det bara det tredje besöket som granskas. Mellan e-post och visning var e-post först, så e-post får 100 % kredit för 50 dollar.
* Använda **första beröring** och **besökarfönster** Vid alla tre besöken. Den betalda sökningen var först, så den får 100 % kredit för 50 dollar.
* Använda **linjär** och **gå till uppslagsfönstret**, är kredit uppdelad mellan e-post och visning. Båda kanalerna får 25 dollar i kredit.
* Använda **linjär** och **besökarfönster**, är kredit uppdelad mellan betald sökning, social sökning, e-post och visning. Varje kanal får 12,50 dollar i kredit för det här köpet.
* Använda **J-formad** och **besökarfönster**, är kredit uppdelad mellan betald sökning, social sökning, e-post och visning.
   * 60 % kredit ges för visning, för $30.
   * 20 procent kredit ges till betald sökning, för 10 dollar.
   * De återstående 20 procenten är uppdelade mellan social e-post och e-post, vilket ger 5 dollar till var och en.
* Använda **Tidsfördröjning** och **besökarfönster**, är kredit uppdelad mellan betald sökning, social sökning, e-post och visning. Använda standardhalveringstiden på 7 dagar:
   * Mellanrum på 0 dagar mellan visningspunkt och konvertering. `2^(-0/7) = 1`
   * Mellanrum på 0 dagar mellan e-postens kontaktpunkt och konvertering. `2^(-0/7) = 1`
   * 6 dagars mellanrum mellan social beröringspunkt och konvertering. `2^(-6/7) = 0.552`
   * Mellanrum på 9 dagar mellan betald sökningspunkt och konvertering. `2^(-9/7) = 0.41`
   * Om du normaliserar dessa värden får du följande resultat:
      * Visa: 33,8 %, få $16,88
      * E-post: 33,8 % för $16,88
      * Sociala: 18,6%, få $9,32
      * Betalad sökning: 13,8 %, få 6,92 $

>[!NOTE]
>
>Andra konverteringshändelser, t.ex. order eller anpassade händelser, delas också upp om kredit tillhör mer än en kanal. Om till exempel två kanaler bidrar till en anpassad händelse med en Linjärt-attributmodell får båda kanalerna 0,5 av den anpassade händelsen. Dessa händelsefraktioner summeras för alla besök och avrundas sedan till närmaste heltal för rapportering.
