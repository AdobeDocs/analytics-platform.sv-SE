---
description: Översikt över hur du använder standardmallar i Analysis Workspace.
title: Använd mallar
feature: Workspace Basics
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: 9f2f79e264d9cdd460751c50fe252bb7237682fd
workflow-type: tm+mt
source-wordcount: '13205'
ht-degree: 0%

---

# Använd mallar

Mallar (eller företagsmallar) i Analysis Workspace ger snabba insikter i de vanligaste rapportscenarierna. Nedan följer några exempel på frågor som du kan besvara med mallar:

* Hur många personer besöker er webbplats
* Hur många av dessa besökare är unika besökare (räknas bara en gång)
* Hur de kom till webbplatsen (t.ex. om de följde en länk eller kom dit direkt)
* Vilka nyckelord besökarna använde för att söka efter webbplatsinnehåll
* Hur länge besökarna var kvar på en viss sida eller på hela webbplatsen
* Vilka länkar besökarna klickade på och när de lämnade webbplatsen
* Vilka marknadsföringskanaler är mest effektiva för att generera intäkter eller konverteringshändelser?
* Hur mycket tid de tillbringade med att titta på en video
* Vilka webbläsare och enheter de använde för att besöka din webbplats

Följande information beskriver hur du får åtkomst till och använder mallar från fliken [!UICONTROL Templates] i Analysis Workspace.

## Öppna och köra en mall

1. I Analysis Workspace väljer du fliken [!UICONTROL **Workspace**].

1. Välj [!UICONTROL **Mallar**].

   ![Fliken Rapporter](assets/view-prebuilt-reports.png)

1. I sökfältet börjar du skriva namnet på mallen som du vill söka efter och väljer den sedan i listan med mallar.

   eller

   Välj den mallkategori som du vill visa och välj sedan mallen i listan med mallar.

   >[!TIP]
   >
   >Om du vill navigera på menyn med piltangenterna trycker du på snedstreck (/) och sedan på nedpilen. Tryck på Retur för att läsa in den valda mallen.

   En lista över tillgängliga mallar finns i avsnittet [Tillgängliga mallar](#available-templates) nedan.

1. (Valfritt) Visa och använd mallar som innehåller komponenter som inte är tillgängliga i datavyn. (Som standard är de enda mallarna som visas de som använder komponenter som är tillgängliga i datavyn.)

   1. Markera (namn på filteralternativ?) för att visa mallar som kräver ytterligare komponenter.

      <!-- add screenshot -->

   1. Markera den mall som du vill använda.

   1. Om mallen innehåller komponenter som inte är tillgängliga i datavyn visas ett meddelande som anger vilka komponenter som saknas. Klicka (button?) för att gå till datavyn där du automatiskt kan skapa dem. <!--how do you do this? Walk through the process -->

1. Välj mallen för att skapa en rapport baserad på den mall du valde.

## Anpassa och spara en mall {#use-reports}

En mall kanske inte passar dina behov exakt, men den kan göra att du kommer nära. I dessa fall kan du använda mallen som utgångspunkt och sedan anpassa den så att den passar dina specifika syften.

Om du navigerar bort från en mall efter att ha gjort ändringar uppmanas du att spara eller ignorera ändringarna. Om du sparar ändringar i en mall sparas mallen som ett nytt projekt.

Så här anpassar och sparar du en mall:

1. I Adobe Analytics väljer du fliken [!UICONTROL **Workspace**].

1. Välj fliken [!UICONTROL **Mallar**].

1. Markera den mall som du vill visa. Välj till exempel rapporten [!UICONTROL **Sidor**] under [!UICONTROL **Mest populära**].

   Sidmallen, som den visas i Analysis Workspace, visar två [visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([stapeldiagram](/help/analysis-workspace/visualizations/bar.md) och [sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md)) samt en [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). Det mätvärde som används är förekomster.

   ![Sidmallar](assets/pages-report.png)

1. Gör något av följande:

   * Visa mallen.
   * Dra ett eller flera segment till segmentsläppzonen längst upp. Dra till exempel segmentet [!UICONTROL **Mobila kunder**] och visa resultatet.
   * Ändra datumintervallet genom att gå till kalendern längst upp till höger.
   * Lägg in dimensionsanalyser, dra in andra mätvärden och anpassa mallen efter behov.

1. (Valfritt) Spara mallen som ett projekt genom att välja [!UICONTROL **Projekt**] > [!UICONTROL **Spara**].

   Mallen sparas som ett nytt projekt. Den ändrar inte den befintliga rapporten. Mer information om hur du sparar en rapport som ett projekt finns i [Spara projekt](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Tillgängliga mallar

Så här kommer du åt alla tillgängliga färdiga mallar:

1. I Adobe Analytics väljer du fliken [!UICONTROL **Workspace**] och sedan fliken [!UICONTROL **Mallar**] .

   Fördefinierade mallar ordnas efter kategori.

   <!--add screenshot-->

1. Välj en kategori om du vill visa mallarna i den.

   Följande avsnitt motsvarar de tillgängliga kategorierna och ger information om varje mall.

   * [[!UICONTROL ](#most-popular)

   * [[!UICONTROL ](#engagement)

   * [[!UICONTROL ](#web-conversion)

   * [[!UICONTROL ](#web-audience)

   * [[!UICONTROL ](#web-acquisition)

   * [[!UICONTROL ](#mobile-mobile-app)

   * [[!UICONTROL ](#mobile-mobile-device-information)

   * [[!UICONTROL ](#time-parting)

   * [[!UICONTROL ](#cross-channel)

   * [[!UICONTROL ](#other-channels)

   * [[!UICONTROL ](#ajo)

### Mest populära {#most-popular}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--training"
>title="Mall för självstudiekurser"
>abstract="Lär dig vanliga Analysis Workspace-termer och steg för att skapa din första analys."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pagesRankedReport"
>title="Identifiera de mest populära och minst populära sidorna."
>abstract="**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.<br/>Den här mallen använder måtten Siddimension och Sidvyer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--pageViewsOvertimeReport"
>title="Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. "
>abstract="**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.<br/>Den här mallen använder måtten Dag och Sidvisning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitsOvertimeReport"
>title="Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.<br/>Den här mallen använder måtten Dag och Besök."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--visitorsOvertimeReport"
>title="Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. "
>abstract="**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.<br/>Den här mallen använder måtten Dag och Unika besökare. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--keyMetricsReport"
>title="Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. <br/>Den här mallen använder måtten Dag, Sidvisning, Besök och Unika besökare."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--siteSectionRankedReport"
>title="Se de populäraste eller mest högpresterande avsnitten på webbplatsen."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.<br>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.<br/>Den här mallen använder dimensionen Platsavsnitt och Visits-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--next-page-report"
>title="Se de vanligaste platserna där man besöker en viss plats omedelbart efter besök eller omedelbart."
>abstract="**Detta kan hjälpa dig** att förstå hur trafiken flyttas från en viss sida till andra delar av webbplatsen och förstå de sökvägar som användarna tar för att komma fram till en viss sida.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om siddesignen eller layouten kan optimeras för att dirigera människor till mer önskade sidor, som en sida för att göra ett köp eller lämna en granskning. Eller utvärdera om informationen på den aktuella sidan kan ge den riktning eller de åtgärder som folk vill ha när de kommer från föregående sidor. Du kan också bedöma om sidor som inte visas som tidigare sidor behöver mer framträdande länkar till den aktuella sidan.<br/>Den här mallen använder panelen Nästa eller Föregående objekt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignRankedReport"
>title="Visa länkarna som lyckades mest när det gällde att köra trafik till er webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka spårningskoder (och de länkar de är kopplade till) som var de mest använda för att komma åt din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att justera din strategi för var du lägger till länkar till din webbplats.<br/>Den här mallen använder spårningskoddimensionen och Visits-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productsRankedReport"
>title="Visa antalet order per produkt. Data visas över en tidsperiod."
>abstract="**Detta kan hjälpa dig** att förstå vilka produkter som har störst eller lägst efterfrågan.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera dina marknadsföringsstrategier för att marknadsföra högpresterande produkter eller för att förbättra eller avbryta underpresterande produkter. Du kan också justera produktlagret baserat på din analys av data.<br/>Den här mallen använder produktdimensionen och ordermåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelRankedReport"
>title="Visa de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att förstå vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.<br/>Den här mallen använder dimensionen Senaste beröringskanal och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--lastTouchChannelDetailRankedReport"
>title="Visa information om de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att förstå inte bara vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar, utan även information om dessa marknadsföringskanaler. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.<br/>Den här mallen använder dimensionen Senaste beröringskanaldetalj och det unika besökarmåttet. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--revenueOvertimeReport"
>title="Visa det monetära beloppet för produkter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att förstå hur intäkterna ökar eller minskar över tid. Du kan kombinera det här måttet med vilken dimension som helst för att lära dig vilka dimensionsobjekt som har bidragit till intäkterna.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel framtida projektintäkter baserade på tidigare trender. Ni kan också lägga till ytterligare en dimension, som spårningskoddimensionen, för att lära er vilka kampanjer som genererar störst intäkter.<br/>Den här mallen använder måtten Dag och Intäkter."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ordersOvertimeReport"
>title="Visa det totala antalet inköpshändelser. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur intresset för dina produkter och tjänster ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som gör mest beställningar och hur dessa beställningar trendar över tid.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra order före och efter det att kampanjen har startats. Eller så kan du jämföra årsavgiftsbeställningar.<br/>Den här mallen använder måtten Dag och Order."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Utbildning - självstudiekurs**] | Lär dig vanliga Analysis Workspace-termer och steg för att bygga din första analys |
| [!UICONTROL **Sidor**] | <!--duplicated in Engagement section--> Identifiera de mest populära och minst populära sidorna. <p>**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.</p><p>I den här mallen används måtten Siddimension och Sidvisning.</p> |
| [!UICONTROL **Sidvisningar**] | <!--duplicated in Engagement section--> Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten Dag och Sidvisning.</p> |
| [!UICONTROL **Webbbesök**] | <!--duplicated in Engagement section--> Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten Dag och Besök.</p> |
| [!UICONTROL **Webbbesökare**] | <!--duplicated in Engagement section--> Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.</p><p>I den här mallen används måtten Dag och Unika besökare.</p> |
| [!UICONTROL **Nyckeltal**] | <!--duplicated in Engagement section--> Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. </p><p>I den här mallen används måtten Dag, Sidvisning, Besök och Unika besökare.</p> |
| [!UICONTROL **Webbplatsavsnitt**] | Se de populäraste eller mest högpresterande avsnitten på webbplatsen. <p>**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.</p> <p>Den här mallen använder dimensionen Platsavsnitt och måttet Besök.</p> |
| [!UICONTROL **Nästa och Föregående sida**] | Se de vanligaste platserna där man besöker en viss plats omedelbart efter besök eller omedelbart. <p>**Detta kan hjälpa dig** att förstå hur trafiken flyttas från en viss sida till andra delar av webbplatsen och förstå de sökvägar som användarna tar för att komma fram till en viss sida.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om siddesignen eller layouten kan optimeras för att dirigera människor till mer önskade sidor, som en sida för att göra ett köp eller lämna en granskning. Eller utvärdera om informationen på den aktuella sidan kan ge den riktning eller de åtgärder som folk vill ha när de kommer från föregående sidor. Du kan också bedöma om sidor som inte visas som tidigare sidor behöver mer framträdande länkar till den aktuella sidan.</p><p>Den här mallen använder panelen Nästa eller Föregående objekt.</p> |
| [!UICONTROL **Kampanjer (spårningskod)**] | Visa länkarna som lyckades mest när det gällde att köra trafik till er webbplats. <p>**Detta kan hjälpa dig** att bättre förstå vilka spårningskoder (och de länkar de är kopplade till) som var de mest använda för att komma åt din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att justera din strategi för var du lägger till länkar till din webbplats.</p><p>I den här mallen används spårningskoddimensionen och Visits-måttet.</p> |
| [!UICONTROL **Produkter**] | Visa antalet order per produkt. Data visas över en tidsperiod. <p>**Detta kan hjälpa dig** att förstå vilka produkter som har störst eller lägst efterfrågan.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera dina marknadsföringsstrategier för att marknadsföra högpresterande produkter eller för att förbättra eller avbryta underpresterande produkter. Du kan också justera produktlagret baserat på din analys av data.</p><p>I den här mallen används måtten Produkt och Order.</p> |
| [!UICONTROL **Senaste Touch Marketing Channel**] | Visa de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att förstå vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.</p><p>I den här mallen används måtten Senaste beröringskanal och Unika besökare.</p> |
| [!UICONTROL **Information om senaste beröringskanal**] | Visa information om de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att förstå inte bara vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar, utan även information om dessa marknadsföringskanaler. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.</p><p>I den här mallen används dimensionen Senaste beröringskanaldetalj och det unika besökarmåttet.</p> |
| [!UICONTROL **Intäkter**] | <!--duplicated in Web Conversion section-->Visa det monetära beloppet för produkter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder.<p>**Detta kan hjälpa dig** att förstå hur intäkterna ökar eller minskar över tid. Du kan kombinera det här måttet med vilken dimension som helst för att lära dig vilka dimensionsobjekt som har bidragit till intäkterna.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel framtida projektintäkter baserade på tidigare trender. Ni kan också lägga till ytterligare en dimension, som spårningskoddimensionen, för att lära er vilka kampanjer som genererar störst intäkter.</p><p>I den här mallen används måtten Dag och Intäkter.</p> |
| [!UICONTROL **Beställningar**] | <!--duplicated in Web Conversion section-->Visa det totala antalet inköpshändelser. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur intresset för dina produkter och tjänster ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som gör mest beställningar och hur dessa beställningar trendar över tid.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra order före och efter det att kampanjen har startats. Eller så kan du jämföra årsavgiftsbeställningar.</p><p>I den här mallen används måtten Dag och Order.</p> |

### Webb: Engagemang {#web-engagement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_template_time_spent"
>title="Se den genomsnittliga tid besökarna tillbringar på er webbplats under varje besök, liksom den genomsnittliga tid som användarna tillbringar innan ett lyckat besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur lång tid det tar för besökarna att utföra en önskad åtgärd, till exempel göra ett köp.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om ändringar av din webbplats förbättrar besökarens förmåga att snabbt nå en lyckad händelse.<br/>Den här mallen använder måtten Dag och Tid per besök (sekunder), Dag och Antal besök (sekunder)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-content-consumption"
>title="Se vilket webbinnehåll som konsumeras mest och engagerande användare."
>abstract="**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen.<br/>I den här mallen används måtten Siddimension och Sidvisning, Visits-måttet, det unika besökarmåttet, starthastighetsmåttet, avhoppsfrekvensen, avslutningsmåttet och innehållshastighetsmåttet. Flödesvisualiseringar används också för in-, avslutnings- och toppavsnitt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--media-content-consumption"
>title="Se vilket medieinnehåll som konsumeras mest och engagerande användare."
>abstract="**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen.<br/>I den här mallen används måtten Siddimension och Sidvisning, Visits-måttet, det unika besökarmåttet, starthastighetsmåttet, avhoppsfrekvensen, avslutningsmåttet och innehållshastighetsmåttet. Flödesvisualiseringar används också för in-, avslutnings- och toppsektioner, en satsytevisualisering som visar sidvyer för de vanligaste sidorna, en streckvisualisering som visar sidvisningar efter paketerad tid och en linjevisualisering som visar en trendvy över den genomsnittliga tiden som har tillbringats på webbplatsen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--page-summary-report"
>title="Visa viktig information om alla sidor i egenskaperna. Visar sidvyer, en trendlinje, en flödesvisualisering och mycket mer."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur människor interagerar med en viss sida.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera sidans prestanda över en tidsperiod eller bättre förstå vad som driver trafik till sidan.<br/>Den här mallen använder måttet Sidvyer. Det använder även linjevisualisering och Flow-visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--entryPageRankedReport"
>title="Visa de översta sidorna som andra kommer åt när de besöker webbplatsen första gången."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.<br/>Den här mallen använder måttet för sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--exitPageRankedReport"
>title="Visa de översta sidorna som andra kommer åt direkt innan de lämnar din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka sidor som leder personer bort från webbplatsen. <br/>**Baserat på vad du lär dig kan du** göra något av följande, till exempel uppdatera vanliga avslutssidor för att optimera upplevelsen som andra får innan de lämnar webbplatsen, eller inkludera innehåll eller länkar för att uppmuntra andra att stanna kvar på webbplatsen.<br/>Den här mallen använder måttet för sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Nyckeltal**] | <!--duplicated in Most popular section--> Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. </p><p>I den här mallen används måtten Dag, Sidvisning, Besök och Unika besökare.</p> |
| [!UICONTROL **Sidvisningar**] | <!--duplicated in Most popular section-->Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten Dag och Sidvisning.</p> |
| [!UICONTROL **Sidor**] | <!--duplicated in Most popular section-->Identifiera de mest populära och minst populära sidorna. <p>**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.</p><p>I den här mallen används måtten Siddimension och Sidvisning.</p> |
| [!UICONTROL **Besök**] | <!--duplicated in Most popular section-->Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten Dag och Besök.</p> |
| [!UICONTROL **Besökare**] | <!--duplicated in Most popular section-->Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.</p><p>I den här mallen används måtten Dag och Unika besökare.</p> |
| [!UICONTROL **Spenderad tid**] | Se den genomsnittliga tid besökarna tillbringar på er webbplats under varje besök, liksom den genomsnittliga tid som användarna tillbringar innan ett lyckat besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur lång tid det tar för besökarna att utföra en önskad åtgärd, till exempel göra ett köp.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om ändringar av din webbplats förbättrar besökarens förmåga att snabbt nå en lyckad händelse.</p><p>I den här mallen används måtten Dag och Tid per besök (sekunder), Dag och Antal besök (sekunder).</p> |
| [!UICONTROL **Webbplatsavsnitt**] | <!--duplicated in Most popular section-->Se de populäraste eller mest högpresterande avsnitten på webbplatsen. <p>**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.</p> <p>Den här mallen använder dimensionen Platsavsnitt och måttet Besök.</p> |
| [!UICONTROL **Webbinnehållskonsumtion**] | Se vilket webbinnehåll som konsumeras mest och engagerande användare.<p>**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen <!-- not sure about these takeaways... -->.</p> <p>I den här mallen används måtten Siddimension och Sidvisning, Visits-mått, Unika besökare, Inmatningshastighet, Studsfrekvens, Exit Rate-mått och Innehållshastighet. Flödesvisualiseringar används också för in-, avslutnings- och toppavsnitt.</p> |
| [!UICONTROL **Medieinnehållskonsumtion**] | Se vilket medieinnehåll som konsumeras mest och engagerande användare.<p>**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen <!-- not sure about these takeaways... -->.</p> <p>I den här mallen används måtten Siddimension och Sidvisning, Visits-mått, Unika besökare, Inmatningshastighet, Studsfrekvens, Exit Rate-mått och Innehållshastighet. Flödesvisualiseringar används också för in-, avslutnings- och toppsektioner, en satsytevisualisering som visar sidvyer för de vanligaste sidorna, en streckvisualisering som visar sidvisningar efter paketerad tid och en linjevisualisering som visar en trendvy över den genomsnittliga tiden som har tillbringats på webbplatsen.</p> |
| [!UICONTROL **Nästa och föregående sida**] | <!--duplicated in Most popular section-->Se de vanligaste platserna där man besöker en viss plats.<p>**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att besökas innan de lämnar webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen<!-- not sure about these takeaways... -->.</p> <p>I den här mallen används måtten Siddimension, Sidvyer, Besök, Unika besökare, Inmatningshastighet, Studsfrekvens, Exit Rate och Content Velocity. Flödesvisualiseringar används också för in-, avslutnings- och toppsektioner, en Scatterplot-visualisering som visar sidvisningar för de vanligaste sidorna, en Bar-visualisering som visar sidvisningar efter paketerad tid och en Line-visualisering som visar en trendvy över den genomsnittliga tiden som har tillbringats på webbplatsen.</p> |
| **Sidsammanfattning** | Visa viktig information om alla sidor i egenskaperna. Visar sidvyer, en trendlinje, en flödesvisualisering och mycket mer.  <p>**Detta kan hjälpa dig** att bättre förstå hur människor interagerar med en viss sida.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera sidans prestanda över en tidsperiod eller bättre förstå vad som driver trafik till sidan.</p><p>I den här mallen används måttet Sidvyer. Det använder även linjevisualisering och Flow-visualisering.</p> |
| **Startsidor** | Visa de översta sidorna som andra kommer åt när de besöker webbplatsen första gången. <p>**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.</p><p>Den här mallen använder måttet Sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering.</p> |
| **Avsluta sidor** | Visa de översta sidorna som andra kommer åt direkt innan de lämnar din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka sidor som leder personer bort från webbplatsen. </p><p>**Baserat på vad du lär dig kan du** göra något av följande, till exempel uppdatera vanliga avslutssidor för att optimera upplevelsen som andra får innan de lämnar webbplatsen, eller inkludera innehåll eller länkar för att uppmuntra andra att stanna kvar på webbplatsen.</p><p>Den här mallen använder måttet Sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering.</p> |

### Webb: Konvertering {#web-conversion}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--productConversionReport"
>title="Produktkonverteringstrattmall"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-products-template"
>title="Se vilka produkter som ger bäst resultat."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.<br/>Den här mallen använder måtten Produktvyer, kundvagnstillägg, Beställningar, Intäkter och Enheter. Det använder också produktdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartConversionReport"
>title="Visa hur många gånger personer har utfört utcheckningshändelser, t.ex. lagt till artiklar i kundvagnen, visat kundvagnen, tagit bort artiklar från kundvagnen och checkat ut."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka delar av processen som leder till konvertering och vilka som löper större risk att överge kundvagnen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att minska friktionen i vissa steg i utcheckningsprocessen.<br/>Den här mallen använder"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartsOvertimeReport"
>title="Visa antalet personer som har lagt till en produkt i kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå antalet personer som lägger till en produkt i kundvagnen, till skillnad från det totala antalet produkter som läggs till i en kundvagn.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att mäta effektiviteten hos dina produktsidor.<br/>Den här mallen använder Carts-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartViewsOvertimeReport"
>title="Se hur många gånger kunderna har sett sin kundvagn."
>abstract="**Det här kan hjälpa dig** att bättre förstå utcheckningsupplevelsen i ett försök att minska antalet kundvagnsavhoppningar eller analysera tiden mellan kundvagnstillägg och utcheckning av olika produkter.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, till exempel erbjuda kampanjer för produkter som ligger längst i varukorgar och som löper störst risk att överges.<br/>Den här mallen använder måttet för kundvagnsvyer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartAdditionsOvertimeReport"
>title="Se hur många gånger någon har lagt till något i kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kundintresset för en produkt är tillräckligt högt för att de ska kunna lägga till den i kundvagnen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra produktrekommendationerna för alla kunder. Detta kan göras genom att analysera vilka produkter som ofta läggs till i samma varukorgar och föreslå relaterade produkter som baseras på artiklar som redan finns i varukorgen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cartRemovalsOvertimeReport"
>title="Se hur många gånger någon har tagit bort något från kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kunderna inte längre är intresserade av en produkt, eller så kan det hjälpa dig att förstå var det kan finnas problem i utcheckningsprocessen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel ta bort eventuella hinder som kan finnas i utcheckningsprocessen, till exempel en komplicerad användarupplevelse.<br/>Den här mallen använder måttet för kundvagnsborttagning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--purchaseConversionReport"
>title="Inköpskonverteringstrattmall"
>abstract=""

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Produktkonverteringstratt**] | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Produkter** | Se vilka produkter som genererar nyckeltal, t.ex. de främsta säljarna eller de mest visade. <p>**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.</p><p>I den här mallen används ordermåttet och produktdimensionen. |
| **Produktprestanda** | Se vilka produkter som ger bäst resultat.<p>**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.</p><p>I den här mallen används måtten för produktvyer, kundvagnstillägg, beställningar, intäkter och enheter. Det använder också produktdimensionen. |
| **Konverteringsfunktioner för kundvagn** | Visa hur många gånger personer har utfört utcheckningshändelser, t.ex. lagt till artiklar i kundvagnen, visat kundvagnen, tagit bort artiklar från kundvagnen och checkat ut. <p>**Detta kan hjälpa dig** att bättre förstå vilka delar av processen som leder till konvertering och vilka som löper större risk att överge kundvagnen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att minska friktionen i vissa steg i utcheckningsprocessen.</p><p>Den här mallen använder |
| **KARTOR** | Visa antalet personer som har lagt till en produkt i kundvagnen.<p>**Detta kan hjälpa dig** att bättre förstå antalet personer som lägger till en produkt i kundvagnen, till skillnad från det totala antalet produkter som läggs till i en kundvagn.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att mäta effektiviteten hos dina produktsidor.</p><p>I den här mallen används Carts-måttet. |
| **Kundvagnsvisningar** | Se hur många gånger kunderna har sett sin kundvagn. <p>**Det här kan hjälpa dig** att bättre förstå utcheckningsupplevelsen i ett försök att minska antalet kundvagnsavhoppningar eller analysera tiden mellan kundvagnstillägg och utcheckning av olika produkter.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, till exempel erbjuda kampanjer för produkter som ligger längst i varukorgar och som löper störst risk att överges.</p><p>I den här mallen används måttet för kundvagnsvyer. |
| **Tillägg i kundvagn** | Se hur många gånger någon har lagt till något i kundvagnen. <p>**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kundintresset för en produkt är tillräckligt högt för att de ska kunna lägga till den i kundvagnen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra produktrekommendationerna för alla kunder. Detta kan göras genom att analysera vilka produkter som ofta läggs till i samma varukorgar och föreslå relaterade produkter som baseras på artiklar som redan finns i varukorgen. |
| **Raderingar i kundvagn** | Se hur många gånger någon har tagit bort något från kundvagnen.<p>**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kunderna inte längre är intresserade av en produkt, eller så kan det hjälpa dig att förstå var det kan finnas problem i utcheckningsprocessen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel ta bort eventuella hinder som kan finnas i utcheckningsprocessen, till exempel en komplicerad användarupplevelse.</p><p>I den här mallen används måttet för kundvagnsborttagning. |
| **Inköpskonverteringstru** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Intäkter** | <!--duplicated in Most popular section-->Visa det monetära beloppet för produkter som köpts i alla order.<p>**Detta kan hjälpa dig** att bättre förstå vilka dimensionsobjekt som har bidragit till intäkterna genom att kombinera intäktsmåtten med valfri dimension. Du kan till exempel se de främsta kampanjerna (med hjälp av spårningskoddimensionen) som har bidragit till intäkterna. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel justera kampanjer som inte uppfyller de intäktsmål du kan förvänta dig.</p><p>I den här mallen används intäktsmåttet. |
| **Beställningar** | <!--duplicated in Most popular section-->Visa det totala antalet inköpshändelser som har gjorts på din webbplats. <p>**Det här kan hjälpa dig** att bättre förstå vilka dimensionsobjekt som har bidragit till en ordning genom att kombinera Orders-måttet med valfri dimension. Du kan till exempel se de främsta kampanjerna (med hjälp av spårningskoddimensionen) som har bidragit till inköp.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel justera kampanjer som inte uppfyller de inköpsmål som du skulle kunna förvänta dig. </p><p>I den här mallen används måttet för beställningar. |

### Webb: Målgrupp {#web-audience}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--countryGeoReport"
>title="Se det land som besökarna kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå vad de populäraste länderna besökarna kommer från när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i dessa länder, eller se till att webbplatsupplevelsen är optimal i länder som har olika primära språk.<br/>Den här mallen använder dimensionen Länder."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--stateGeoReport"
>title="Visa det tillstånd (i USA) som folk från webbplatsen har sitt ursprung i. Detta liknar mallen Geo Regions, förutom att den är specifik för USA."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste amerikanska delstatsbesökarna som kommer från de som besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa lägen.<br/>Den här mallen använder dimensionen USA."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--regionGeoReport"
>title="Visa det geografiska område som personer som besöker webbplatsen kommer från. En region är ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. "
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de här regionerna, eller se till att webbplatsupplevelsen är optimal i regioner som har olika primära språk. <br/>Den här mallen använder dimensionerna ID(variabler/geocountry) och Region. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--cityGeoReport"
>title="Se den stad som folk från webbplatsen kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste städer som besökarna kommer från när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa städer. <br/>Den här mallen använder dimensionen Städer"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dmaGeoReport"
>title="Se vilka områden i USA som besökarna kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de mest framgångsrika regionerna. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--languageRankedReport"
>title="Se vilka språk besökarna föredrar att se innehåll på."
>abstract="**Det här kan hjälpa dig** att bättre förstå besökarnas vanligaste språk.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som fokuslokaliseringsaktiviteter eller marknadsföringsaktiviteter för de vanligaste språken.<br/>Den här mallen använder språkdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-technology-template"
>title="Teknik - översikt"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserRankedReport"
>title="Visa namn och version för de webbläsare som användarna använder mest för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder.<br/>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen.<br/>Den här mallen använder webbläsardimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--browserTypeRankedReport"
>title="Visa namnen på de organisationer som har skapat de vanligaste webbläsarna som användarna använder för att komma åt webbplatsen. Detta skiljer sig från webbläsarmallen på så sätt att olika versioner av samma webbläsare inte listas som separata dimensionsobjekt."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder <br/>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen. <br/>Den här mallen använder dimensionen för webbläsartypen. "

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Första kontra Upprepa användare**] | Visa en jämförelse av förstagångsbesökare för att upprepa besökare. <p>**Detta kan hjälpa dig** att bättre förstå hur effektiv din webbplats är när det gäller att behålla kundlojaliteten, eller hur ofta du skaffar nya kunder.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att erbjuda incitament för framtida köp till förstagångsbesökare för att locka dem att återvända.</p><p>Den här mallen använder </p> |
| **Person-ID/namnområde** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder  </p> |
| **Platsöversikt** | Visa en översikt över besökarnas plats i en kartvisualisering.<p>**Det här kan hjälpa dig** att bättre förstå var besökarna finns som besöker din webbplats. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringsresurser på de platser där du ser störst intresse och möjlighet.</p><p>Den här mallen använder  </p> |
| **Geografiska länder** | Se det land som besökarna kommer ifrån.<p>**Det här kan hjälpa dig** att bättre förstå vad de populäraste länderna besökarna kommer från när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i dessa länder, eller se till att webbplatsupplevelsen är optimal i länder som har olika primära språk.</p><p>Den här mallen använder dimensionen Länder. </p> |
| **Geo USA-lägen** | Visa det tillstånd (i USA) som folk från webbplatsen har sitt ursprung i. Detta liknar mallen Geo Regions, förutom att den är specifik för USA.<p>**Det här kan hjälpa dig** att bättre förstå de populäraste amerikanska delstatsbesökarna som kommer från de som besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa lägen.</p><p>I den här mallen används dimensionen USA. </p> |
| **Geo-regioner** | Visa det geografiska område som personer som besöker webbplatsen kommer från. En region är ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. <p>**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de här regionerna, eller se till att webbplatsupplevelsen är optimal i regioner som har olika primära språk. </p><p>I den här mallen används dimensionerna ID (variabler/geoland) och Region. </p> |
| **Geo-städer** | Se den stad som folk från webbplatsen kommer ifrån. <p>**Det här kan hjälpa dig** att bättre förstå de populäraste städer som besökarna kommer från när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa städer. </p><p>Den här mallen använder dimensionen Städer </p> |
| **Geo US DMA** | Se vilka områden i USA som besökarna kommer ifrån.<p>**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de mest framgångsrika regionerna. </p><p>Den här mallen använder </p> |
| **Språk** | Se vilka språk besökarna föredrar att se innehåll på. <p>**Det här kan hjälpa dig** att bättre förstå besökarnas vanligaste språk.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som fokuslokaliseringsaktiviteter eller marknadsföringsaktiviteter för de vanligaste språken.</p><p>Den här mallen använder dimensionen Språk.</p> |
| **Tekniköversikt** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder </p> |
| **Webbläsare** | Visa namn och version för de webbläsare som användarna använder mest för att komma åt webbplatsen.<p>**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen.</p><p>Den här mallen använder dimensionen Webbläsare. </p> |
| **Webbläsartyper** | Visa namnen på de organisationer som har skapat de vanligaste webbläsarna som användarna använder för att komma åt webbplatsen. Detta skiljer sig från webbläsarmallen på så sätt att olika versioner av samma webbläsare inte listas som separata dimensionsobjekt.<p>**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder</p><p>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen. </p><p>Den här mallen använder dimensionen för webbläsartyp. </p> |

### Webb: Förvärv {#web-acquisition}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--marketing-channel-overview-template"
>title="När du använder anpassad attribuering visar den här mallen hur besökare kommer till din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka av era marknadsföringskanaler som är mest effektiva.<br/>**Baserat på vad du lär dig kan du** göra många saker, som att investera mer i effektiva marknadsföringskanaler och ta bort från mindre effektiva marknadsföringskanaler.<br/>Den här mallen använder dimensionerna ID(variabler/marketingchannel) och Intäktsmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelRankedReport"
>title="Visa den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver den inledande trafiken till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.<br/>Den här mallen använder dimensionen Första beröringskanalen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--firstouchChannelDetailRankedReport"
>title="Visa information om den första marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.<br/>Den här mallen använder dimensionen Första beröringskanaldetalj."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--campaignConversionReport"
>title="Kampanjkonverteringstratt"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--retail-campaign-performance-template"
>title="Visa detaljerad information om hur era marknadsföringskampanjer fungerar."
>abstract="**Det här kan hjälpa dig** att bättre förstå olika indikatorer för att lyckas med kampanjer, t.ex. intäkter, produktvisningar, beställningar och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter. <br/>I den här mallen används måtten Intäktssiffror, Produktvyer, Cart Additions, Orders och Units. Den använder även spårningskoddimensionen och referensdomändimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--web-acquisition-template"
>title="Se hur er webbplats får besökare."
>abstract="**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.<br/>Den här mallen använder Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik. <br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.<br/>Den här mallen använder dimensionen Sök nyckelord."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken. <br/>Den här mallen använder dimensionen Söknyckelord - Betald. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.<br/>Den här mallen använder söknyckelordet - naturlig dimension. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchRankedReport"
>title="Visa sökmotorerna som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik. <br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.<br/>Den här mallen använder dimensionen Sökmotor. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchPaidRankedReport"
>title="Visa sökmotorerna som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen. <br/>Den här mallen använder sökmotorn - betaldimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--searchNaturalRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.<br/>Den här mallen använder sökmotorn - naturlig dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainRankedReport"
>title="Visa vilka domäner som användare klickar igenom för att nå din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som genererar mest trafik till din. (En länk måste finnas på den externa platsen och en besökare måste klicka på den för att dimensionsposten ska kunna visas.)<br/>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande toppdomänerna. <br/>Den här mallen använder dimensionen Refererande domän."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referringDomainOriginalRankedReport"
>title="Visa den första refererande domänen som personer klickat igenom för att nå din webbplats. (När det har angetts innehåller det samma värde för hela besökar-ID:t.)"
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som ursprungligen kör trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande huvuddomänerna. <br/>Den här mallen använder dimensionen Ursprunglig referensdomän."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerRankedReport"
>title="Visa vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. (En länk måste finnas på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.)"
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka specifika URL:er som genererar mest trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de översta URL:erna. <br/>Den här mallen använder dimensionen Refererande domän.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--referrerTypeRankedReport"
>title="Visa vilka generiska kanaler besökarna klickade igenom för att komma till er webbplats. Adobe bibehåller reglerna för varje kanal. Möjliga kanaler är sökmotorer, sociala nätverk, andra webbplatser, hårddisk eller e-post."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilken typ av referenter som leder flest trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från en viss kanal.<br/>Den här mallen använder dimensionen Refererartyp."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Översiktsrapport för marknadsföringskanaler**] | När du använder anpassad attribuering visar den här mallen hur besökare kommer till din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå vilka av era marknadsföringskanaler som är mest effektiva.</p><p>**Baserat på vad du lär dig kan du** göra många saker, som att investera mer i effektiva marknadsföringskanaler och ta bort från mindre effektiva marknadsföringskanaler.</p><p>Den här mallen använder dimensionerna ID (variabler/marketingchannel) och Intäktsmått.</p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Första beröringsmarknadsföringskanalen**] | Visa den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). <p>**Detta kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver den inledande trafiken till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>I den här mallen används dimensionen Första beröringskanalen.</p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Information om den första beröringskanalen**] | Visa information om den första marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>Den här mallen använder dimensionen Första beröringskanalen Detalj.</p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Senaste Touch Marketing Channel**] | Visa den senaste marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard).<p>**Det här kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver trafik till din webbplats som resulterar i konverteringar.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>I den här mallen används dimensionen Sista beröringskanalen.  </p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Information om senaste beröringskanal**] | Visa information om den senaste marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard)<p>**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva. </p><p>I den här mallen används dimensionen Senaste beröringskanaldetalj. </p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Kampanjer (spårningskod)**] | Visa namnen på spårningskoderna på din webbplats. Du kan placera länkar med olika parametervärden för frågesträngar på olika platser på Internet.<p>**Detta kan hjälpa dig** att bättre förstå vilka länkar som var mest framgångsrika när det gäller att köra trafik till din webbplats. Att lägga till spårningskodfrågesträngar är vanligt i e-postmeddelanden, annonser, inlägg i sociala medier och andra marknadsföringsaktiviteter som används i organisationen</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter.</p><p>Den här mallen använder spårningskoddimensionen. </p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Kampanjkonverteringsfunktion**] | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder  </p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Kampanjresultat**] | Visa detaljerad information om hur era marknadsföringskampanjer fungerar.<p>**Det här kan hjälpa dig** att bättre förstå olika indikatorer för att lyckas med kampanjer, t.ex. intäkter, produktvisningar, beställningar och så vidare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter. </p><p>I den här mallen används måtten Intäkter, Produktvyer, Cart Additions, Orders och Units. Den använder även spårningskoddimensionen och referensdomändimensionen. </p> |
| **Webbförvärv** | Se hur er webbplats får besökare.<p>**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.</p><p>I den här mallen används Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension.  </p> |
| **Sök nyckelord-alla** | Visa söknyckelorden som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt. <p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik. </p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.</p><p>Den här mallen använder dimensionen Sök nyckelord. </p> |
| **Sök efter nyckelord - betald** | Visa söknyckelorden som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken. </p><p>Den här mallen använder dimensionen Söknyckelord - Betald. </p> |
| **Sök nyckelord - naturligt** | Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.</p><p>Den här mallen använder dimensionen Sök nyckelord - naturligt. </p> |
| **Sökmotorer - alla** | Visa sökmotorerna som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt. <p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.</p><p>Den här mallen använder dimensionen Sökmotor. </p> |
| **Sökmotorer - betald** | Visa sökmotorerna som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen. </p><p>I den här mallen används dimensionen Sökmotor - betald. </p> |
| **Sökmotorer - Naturliga** | Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.</p><p>Den här mallen använder sökmotorn - naturlig dimension. </p> |
| **Refererande domäner** | Visa vilka domäner som användare klickar igenom för att nå din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som genererar mest trafik till din. (En länk måste finnas på den externa platsen och en besökare måste klicka på den för att dimensionsposten ska kunna visas.)</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande toppdomänerna. </p><p>Den här mallen använder dimensionen Refererande domän. </p> |
| **Ursprungliga referensdomäner** | Visa den första refererande domänen som personer klickat igenom för att nå din webbplats. (När det har angetts innehåller det samma värde för hela besökar-ID:t.)<p>**Det här kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som ursprungligen kör trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande huvuddomänerna. </p><p>Den här mallen använder dimensionen Ursprunglig referensdomän. </p> |
| **Referenter** | Visa vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. (En länk måste finnas på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.)  <p>**Det här kan hjälpa dig** att bättre förstå vilka specifika URL:er som genererar mest trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de översta URL:erna. </p><p>Den här mallen använder dimensionen Refererande domän </p><p>I den här mallen används referensdimensionen. </p> |
| **Refererartyper** | Visa vilka generiska kanaler besökarna klickade igenom för att komma till er webbplats. Adobe bibehåller reglerna för varje kanal. Möjliga kanaler är sökmotorer, sociala nätverk, andra webbplatser, hårddisk eller e-post.<p>**Det här kan hjälpa dig** att bättre förstå vilken typ av referenter som leder flest trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från en viss kanal.</p><p>Den här mallen använder dimensionen Refererartyp.</p> |

### Mobil: Mobilapp {#mobile-app}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-lifecycle-metrics-app-usage-template"
>title="Användning av mobilappar"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-journeys"
>title="Mobilappsresor"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-key-metrics"
>title="Mätvärden för mobilappar"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-messaging"
>title="Mobilappsmeddelanden"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-performance-template"
>title="Mobilappsprestanda"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobile-app-retention"
>title="Underhåll av mobilappar"
>abstract=""

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Mobilapp Screens**] | Visa information om de mobilskärmar som används vid åtkomst till webbplatsen, t.ex. skärmstorlek, skärmbredd och skärmhöjd. <p>**Detta kan hjälpa dig** att bättre förstå hur andra upplever din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera återgivningen av webbplatsen för de vanligaste skärmstorlekarna.</p><p>Den här mallen använder |
| **Mobilappsåtgärder** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Användning av mobilappar** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Mobilappsresor** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Mobilappsmått** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Mobilappsmeddelanden** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Mobilappsprestanda** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Kvarhållning av mobilapp** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |

### Mobil: Information om mobila enheter {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileCarrierRankedReport"
>title="Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder dimensionen Mobiloperatör."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceNameRankedReport"
>title="Visa märke och modell för mobila enheter som används för att komma åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobila enheter som är populärast bland dina användare.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera återgivningen av din webbplats för de vanligaste mobila enheterna.<br/>Den här mallen använder dimensionen Mobilenhetsnamn."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileDeviceTypeRankedReport"
>title="Visa de mobila enhetstyper som användare använder för att få tillgång till din webbplats, t.ex. telefoner och surfplattor."
>abstract="**Detta kan hjälpa dig** att bättre förstå de olika typer av mobila enheter som används för att komma åt din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera webbplatsen för de typer av mobila enheter som används mest.<br/>Den här mallen använder dimensionen Mobilenhetstyp."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--mobileManufacturerRankedReport"
>title="Se vilka tillverkare som producerar de mobila enheter som användarna använder för att få tillgång till er webbplats, som Apple och Samsung."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka tillverkare som är populärast bland dina användare.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att skräddarsy innehållsleveransen baserat på kapaciteten hos olika tillverkare för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder Mobile Manufacturer-dimensionen."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Mobiloperatör**] | Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.</p><p>I den här mallen används mobiloperatörsdimensionen.</p> |
| **Mobila enheter** | Visa märke och modell för mobila enheter som används för att komma åt din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka mobila enheter som är populärast bland dina användare.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera återgivningen av din webbplats för de vanligaste mobila enheterna.</p><p>Den här mallen använder dimensionen Mobilenhetsnamn.</p> |
| **Typ av mobil enhet** | Visa de mobila enhetstyper som användare använder för att få tillgång till din webbplats, t.ex. telefoner och surfplattor.<p>**Detta kan hjälpa dig** att bättre förstå de olika typer av mobila enheter som används för att komma åt din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera webbplatsen för de typer av mobila enheter som används mest.</p><p>Den här mallen använder dimensionen för mobilenhetstyp.</p> |
| **Tillverkare** | Se vilka tillverkare som producerar de mobila enheter som användarna använder för att få tillgång till er webbplats, som Apple och Samsung.<p>**Det här kan hjälpa dig** att bättre förstå vilka tillverkare som är populärast bland dina användare.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att skräddarsy innehållsleveransen baserat på kapaciteten hos olika tillverkare för att säkerställa en smidig användarupplevelse.</p><p>I den här mallen används Mobile Manufacturer-dimensionen.</p> |

### Tidsdelning

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Minut av timmen**] | Visa antalet händelser, sessioner och personer på din webbplats, uppdelat efter minut. Om du t.ex. har en rapport med en rapporttidsram på en dag grupperas den första minuten i varje timme på dagen i samma dimensionsobjekt.<p>**Detta kan hjälpa dig** att förstå trender på detaljnivå.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>I den här mallen används dimensionen Minut för timme. |
| **Timme på dagen** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter timme på dagen. Om du t.ex. har en rapport som sträcker sig från 1 januari till 7 januari grupperas den första timmen för varje dag i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå när webbplatsen besöks mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel tilldela mer datorresurser till din webbplats under mycket trafik.</p><p>Den här mallen använder dimensionen Timme för dag. |
| **AM/PM** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter AM och PM. Om du till exempel har en rapport som sträcker sig från 1 januari till 7, grupperas AM-timmarna för varje dag i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå när webbplatsen besöks oftast och minst.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel tilldela mer datorresurser till din webbplats under mycket trafik.</p><p>Den här mallen använder AM/PM-dimensionen. |
| **Veckodag** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter veckodag. Om du till exempel har en rapport som sträcker sig över januari, grupperas varje veckodag i samma dimensionsobjekt. <p>**Det här kan hjälpa dig** att bättre förstå vilka veckodagar din webbplats besöker mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.</p><p>Den här mallen använder dimensionen Dag i vecka. |
| **Dag i månaden** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter dag i månaden. Om du till exempel har en rapport som sträcker sig över ett helt år grupperas varje dag i månaden i samma dimensionsobjekt. <p>**Det här kan hjälpa dig** att bättre förstå vilka dagar i varje månad som webbplatsen besöks mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.</p><p>Den här mallen använder dimensionen Dag i månaden. |
| **Dag på året** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter dag på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje dag på året i samma dimensionsobjekt. <p>**Det här kan hjälpa dig** att bättre förstå vilka dagar på året som webbplatsen oftast och oftast besöker.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.</p><p>Den här mallen använder dimensionen Dag på år. |
| **Veckodag/Veckoslut** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter veckodagar och helger. Om du till exempel har en rapport som sträcker sig över januari, grupperas veckodagar och helger i separata dimensionsobjekt. <p>**Detta kan hjälpa dig** att bättre förstå skillnaderna i webbplatstrafik för veckodagar jämfört med helger.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att din kundtjänst är mer intensiv på helger, om rapporten visar att helger är mer än vardagar.</p><p>Den här mallen använder dimensionen Veckodag/Veckoslut. |
| **Vecka på året** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter vecka på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje vecka i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå vilka veckor på året som webbplatsen besöks mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämplig i telefonen under trafikveckor, till exempel under helgdagar.</p><p>Den här mallen använder dimensionen Vecka på året. |
| **Månad på året** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter månad på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje månad i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå vilka månader din webbplats är mest frekvent och sällan besökt.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämplig i telefonen för högtrafikmånader, till exempel under helgerna.</p><p>Den här mallen använder dimensionen Månad på år. |
| **Kvartal på året** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter kvartal på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje kvartal i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå vilka delar av webbplatsen som är mest frekvent och sällan besökta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att starta produkter för att öka antalet historiskt lågtrafikplatser.</p><p>Den här mallen använder dimensionen Kvartal på året. |

### Kanalövergripande

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Översikt över flera kanaler**] | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Jämförelse mellan kanaler** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Avböjning av samtalscenter (Web+Call Center)** | Se hur webbtrafiken påverkar trafiken i callcenter.<p>**Detta kan hjälpa dig** att bättre förstå hur självbetjäningsinnehållet på din webbplats avspeglar trafiken till ditt callcenter.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, till exempel förbättra självbetjäningsinnehållet för att minska trafiken till ditt call center, eller mäta avkastningen på ditt självbetjäningsinnehåll genom att beräkna hur mycket som sparats via färre supportsamtal.</p><p>Den här mallen använder |
| **Webb+App** | Visa webbtrafik och mobiltrafik tillsammans.<p>**Detta kan hjälpa dig** att bättre förstå hur webb- och mobiltrafiken distribueras till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att avsätta mer resurser till din mobilappsupplevelse när den når en viss trafiknivå.</p><p>Den här mallen använder |
| **Online/Offline** | Visa trafik online och offline tillsammans.<p>**Detta kan hjälpa dig** att bättre förstå hur online- och offlinetrafik distribueras till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att avsätta mer resurser till din onlineupplevelse när den når en viss trafiknivå.</p><p>Den här mallen använder |

### Andra kanaler

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Kontrollpanel för samtalscenter**] | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **POS/Offline** | Visa kassor och offlinetransaktionsdata.<p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **E-post/AJO** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |
| **Undersökning** | <p>**Det här kan hjälpa dig** att bättre förstå</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som </p><p>Den här mallen använder |

### AJO {#AJO-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="AJO-kampanjer"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="AJO resor"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="AJO landningssidor"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="AJO - översikt"
>abstract=""

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="AJO prenumerationer"
>abstract=""

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **AJO Campaigns**] | Se viktiga mätvärden för era Journey Optimizer-kampanjer, inklusive e-postkampanjer, experiment, i appen, SMS med mera.<p>**Detta kan hjälpa dig** att bättre förstå detaljer som antalet klick och antalet levererade meddelanden, vilket ger en heltäckande insikt i kampanjens effektivitet och engagemangsnivå.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera dina kampanjer baserat på målpublikens engagemangsnivåer.</p> |
| **AJO Journeys** | Se viktiga mätvärden för era Journey Optimizer-resor, inklusive e-postresor, experimenterande, i appen, SMS med mera.<p>**Detta kan hjälpa dig** att bättre förstå detaljer som antalet klick och antalet levererade meddelanden, vilket ger en heltäckande insikt i hur effektiv din resa är och hur hög engagemanget är.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera dina kampanjer baserat på målpublikens engagemangsnivåer.</p> |
| **AJO landningssidor** | Visa användarbeteende, engagemangsmönster, konverteringsgrader och andra viktiga mätvärden.<p>**Detta kan hjälpa dig** att bättre förstå hur effektiv din landningssida är. </p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera prestanda för landningssidor.</p> |
| **AJO - översiktsrapport** | Se en detaljerad sammanfattning av trafik- och engagemangsmätningar för alla kampanjer och resor i er miljö.<p>**Detta kan hjälpa dig** att bättre förstå hur effektiva era kampanjer och resor är på hög nivå. </p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera kampanjer och resor baserat på målpublikens engagemangsnivåer.</p> |
| **AJO-prenumerationer** | Visa profilernas prenumerationer och avbeställningar som är kopplade till särskilda listor.<p>**Detta kan hjälpa dig** att bättre förstå hur effektiva olika prenumerationskampanjer och -initiativ är när det gäller att öka engagemanget och konverteringarna.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att justera dina prenumerationskampanjer baserat på målpublikens engagemangsnivåer.</p> |


<!-- deleted: 

| [!UICONTROL **Real-Time**] | View the dimensions and metrics that are currently being collected on your site. <p>**This can help you** better understand what is trending on your site.</p><p>**Based on what you learn, you might** respond to and actively manage the performance of your current marketing content and campaigns.</p> <p>This template uses the [Real-time report](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md).</p> | 
| [!UICONTROL **Fallout**] | View where people leave or continue through a predefined sequence of pages.<p>**This can help you** better understand where people are falling out of the user journey.</p><p>**Based on what you learn, you might** do any number of things, like analyze conversion rates through specific processes on your site (such as a purchase or registration process), or analyze correlations between events on your site. (For example, what percentage of people who looked at your privacy policy went on to purchase a product.) You can also use this template to perform side-by-side comparisons of two different segments in the same report.</p> <p>This template uses the [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md).</p> | 
| [!UICONTROL **Cross-device analysis**] | View which devices people used across all points of the journey.<p>**This can help you** better understand how many people interact with your brand, the types of devices they use, and how their use of multiple devices affects their experience. For example, how often do people begin a task on a mobile device and then later move to a desktop to complete a task? What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed? And so forth.</p><p>**Based on what you learn, you might** do any number of things, like optimize certain parts of the user journey for a mobile experience.</p> <p>This template uses the [Flow visualization](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md), [Fallout visualization](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md), [Cohort analysis](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md), [the People metric](/help/components/metrics/people.md), and [the Unique devices metric](/help/components/metrics/unique-devices.md).</p> |
| [!UICONTROL **Web retention**] | View who your loyal users are and what they are doing on your site.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 
| [!UICONTROL **Streaming Media Consumption**] | View  trends and top metrics of media consumption across all digital devices.<p>**This can help you** better understand the number of times the average person visits your site, the frequency with which people return to the site, and the number of days between return visits.</p><p>**Based on what you learn, you might** do any number of things, like analyze what content is most effective at bringing people back to the site.<p>This template uses the [Visits metric](/help/components/metrics/visits.md) and the [Unique visitors metric](/help/components/metrics/unique-visitors.md).</p> | 

-->

<!--

Ignore below this 

| Menu item | Reports under this menu item |
| --- | --- | 
| **[!UICONTROL Most Popular]** | <ul><li>Training Tutorial (Pre-existing Workspace template)</li><li>Pages (What are my top pages?)</li><li>Page views (How many page views am I generating?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Key metrics (How are my most important metrics performing?)</li><li>Site sections (Which sections of my site generated the most page views?)</li><li>Real-Time (What is trending on my site, and why?)</li><li>Next page (What are the next pages my visitors go to?)</li><li>Previous page (What are the previous pages my visitors went to?)</li><li>Campaigns (What campaigns are driving my key metrics?)</li><li>Products (What products are driving my key metrics?)</li><li>Last touch channel (Which last touch channel is performing best?</li><li>Last touch channel detail (Which specific last touch channel is outperforming others?)</li><li>Revenue (How is my revenue performing?)</li><li>Orders (How are my orders performing?)</li><li>Units (How many units am I selling?)</li></ul> | 
| **[!UICONTROL Engagement]** | <ul><li>Key metrics (How are my most important metrics performing?)</li><li>Page views (How many page views am I generating?)</li><li>Pages (What are my top pages?)</li><li>Visits (How many visits am I getting?)</li><li>Visitors (How many visitors am I getting?)</li><li>Time spent per visit (How much time do my users spend per visit?)</li><li>Time prior to event (How much time do my users spend prior to a success event?)</li><li>Site sections (Which sections of my site generated the most page views?</li><li>Web content consumption (Which content is consumed most and is engaging users?)</li><li>Media content consumption (Which content is consumed most and is engaging users?)</li><li>Next and previous page flow (What are/were the next/previous paths my visitors take/took?)</li><li>Fallout (Where am I seeing fallout through my digital properties?)</li><li>Cross-device analysis (Using cross-device analysis in Analysis Workspace)</li><li>Web retention (Who are my loyal users and what do they do?)</li><li>Media audio consumption (What are trends and top metrics of audio consumption?)</li><li>Media recency, frequency, loyalty (Who are my loyal readers?)</li><li>Page analysis > Reloads (Which pages generate the most reloads?)</li><li>Page analysis > Time spent on page (How much time do my users spend on my pages?)</li><li>Entries & exits > Entry pages (What are my top entry pages?)</li><li>Entries & exits > Original entry pages (What page did my visitor originally enter from?)</li><li>Entries & exits > Single-page visits (Which pages generated the most single-page visits?)</li><li>Entries & exits > Exit pages (What are my top exit pages?)</li><li>Page Analysis > Page summary</li></ul> |
| **[!UICONTROL Conversion]** | <ul><li>Products > Products (Which products are driving my key metrics?)</li><li>Products > Product performance (Which products are performing best?)</li><li>Products > Categories (What are my best performing product categories?</li><li>Shopping cart > Carts (How many users added a product to cart?</li><li>Shopping cart > Cart views (How many times did my visitors view their carts?)</li><li>Shopping cart > Cart additions (How often are users adding a product to their cart?)</li><li>Shopping cart > Cart removals (How often are users removing a product from their cart?)</li><li>Purchases > Revenue (How is my revenue performing?)</li><li>Purchases > Orders (How are my orders performing?)</li><li>Purchases > Units (How many units am I selling?)</li><li>[Magento: marketing and commerce](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#commerce)</li></ul> |
| **[!UICONTROL Audience]** |<ul><li>People metric (How many people are interacting with my brand?)</li><li>Visitor profile > Location overview (Which locations are driving the most usage among users)</li><li>Visitor profile > Geosegmentation > Geo Counties, Geo US States, Geo Regions, Geo Cities, Geo US DMA (Which geographies are my users visiting from?)</li><li>Visitor profile > Languages (Which language do my users prefer?)</li><li>Visitor profile > Time zones (Which time zones are my users visiting from?)</li><li>Visitor profile > Domains (Which ISPs are my visitors using to access my site?)</li><li>Visitor profile > Top level domains (Which domains are driving traffic to my site?)</li><li>Visitor profile > Technology > Technology overview (What technologies are people using to access my site?)</li><li>Visitor profile > Technology > Browsers, Browser type, Browser width, Browser height (Which company's browser, browser version, and its width and height, are people using to access my site?)</li><li>Visitor profile > Technology > Operating system, Operating system types (Which OS and which version of it do my visitors use?)</li><li>Visitor profile > Technology > Mobile carrier (Which mobile carriers do my visitors use to access my site?)</li><li>Visitor retention > Return frequency (How much time passes between my user's current visit and previous visits?)</li><li>Visitor retention > Return visits (How many of my visits are returning users?)</li><li>Visitor retention > Visit number (Which visit number bucket drives most of my key metrics)</li><li>Visitor retention > Sales cycle > Customer loyalty (Which loyalty segment do my users belong to?)</li><li>Visitor retention > Sales cycle > Days before first purchase (How many days passed between my users' first visit and their first purchase?)</li><li>Visitor retention > Sales cycle > Days since last purchase (How many days have passed between my users' current visit and their last purchase? )</li><li>Visitor retention > Mobile > Devices and Device types (Which devices and device types are my visitors using?)</li><li>Visitor retention > Mobile > Manufacturer (Which mobile device manufacturer do my visitors use?)</li><li>Visitor retention > Mobile > Screen size, Screen height, Screen width (Which mobile screen size/height/width do my visitors have?)</li><li>Visitor retention > Mobile > [Mobile app usage](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app journeys](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app metrics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app messaging](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app performance](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>Visitor retention > Mobile > [Mobile app retention](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li></ul> |
| **[!UICONTROL Acquisition]** |<ul><li>Marketing channels > First touch channel, First touch channel detail (Which first touch channel, and which specific first touch channel is performing best?)</li><li>Marketing channels > First last channel, First last channel detail (Which last touch channel, and which specific last touch channel is performing best?)</li><li>Campaigns > Campaigns (Which campaigns are driving my key metrics?)</li><li>Campaigns > Campaign performance (What campaigns are driving the most revenue?)</li><li>Campaigns > Tracking code (Which campaign tracking codes perform the best?)</li><li>[Web acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#web)</li><li>[Mobile acquisition](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#mobile)</li><li>[Advertising Analytics: paid search](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/starter-projects.html#advertising)</li><li>Search keywords - all, paid, natural (Which search keywords and paid/natural search keywords drive my key metrics the best?)</li><li>Search engines - all, paid, natural (Which search engines and paid/natural search engines drive my key metrics the best?)</li><li>All search page ranking (Which search page are my users visiting from?)</li><li>Referring domains (Which domains are driving traffic to my site?)</li><li>Original referring domains (What was the first domain users were on before visiting my site?)</li><li>Referrers (Which URLs were my users on before clicking through to my site?)</li><li>Referrer types (Which category do my referring URLs belong to?)</li></ul> |

-->
