---
description: Översikt över hur du använder standardmallar i Analysis Workspace.
title: Använd mallar
feature: Workspace Basics
role: User, Admin
exl-id: d61f215d-9089-4014-9c5a-97f5d7134f34
source-git-commit: d618300480cdc3b4454e5c91e5e5adacc01d0c77
workflow-type: tm+mt
source-wordcount: '19785'
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

   ![Mallflikar](assets/view-prebuilt-templates-full.png)

1. Välj någon av följande flikar i avsnittet [!UICONTROL **Mallar**]:

   * **[!UICONTROL Adobe templates]**: Visar alla mallar från Adobe.

   * **[!UICONTROL _login_company_name _-mallar]**: Visar alla företagsmallar som har skapats för din organisation.

     Endast administratörer kan skapa företagsmallar. Mer information om hur du skapar en företagsmall finns i [Skapa och hantera mallar](/help/analysis-workspace/templates/create-templates.md).

1. Använd något av följande alternativ för att ändra hur du visar de tillgängliga mallarna:

   * Välj om du vill visa mallar i en kolumnvy eller i en kortvy genom att antingen markera kolumnvyn ![VisaKolumn](/help/assets/icons/ViewColumn.svg) eller kortvyikonen ![Kort](/help/assets/icons/Card.svg) .

   * När du använder kortvyn ![Kort](/help/assets/icons/Card.svg) väljer du bland följande sorteringsordning: **[!UICONTROL Most recently used]**, **[!UICONTROL Most popular]**, **[!UICONTROL Alphabetical]**, **[!UICONTROL Categorical]**.

1. I sökfältet börjar du skriva namnet på mallen som du vill söka efter och väljer den sedan i listan med mallar.

   eller

   Välj den mallkategori som du vill visa och välj sedan mallen i listan med mallar.

   >[!TIP]
   >
   >Om du vill navigera på menyn med piltangenterna trycker du på snedstreck (/) och sedan på nedpilen. Tryck på Retur för att läsa in den valda mallen.

   En lista över tillgängliga mallar finns i avsnittet [Tillgängliga mallar](#available-templates) nedan.

1. (Valfritt) Du kan visa mallar som innehåller komponenter som inte är tillgängliga i datavyn. (Som standard visas mallar bara om de använder komponenter som är tillgängliga i datavyn.)

   >[!NOTE]
   >
   >Innan du kan använda de här mallarna måste en administratör först lägga till de nödvändiga kontextetiketterna för de saknade komponenterna i datavyn. Mer information finns i [Lägga till saknade komponenter i datavyn för en viss mall](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) i [Använd mallar](/help/analysis-workspace/templates/create-templates.md).
   >
   >Mer information om kontextetiketter finns i [Komponentinställningar](/help/data-views/component-settings/overview.md).

   1. Markera segmentikonen.

   1. Välj **[!UICONTROL Not ready for use]** om du vill visa mallar som kräver ytterligare komponenter.

      ![Använd en mall som saknar komponenter](assets/template-not-ready.png)

1. Välj mallen för att skapa en rapport baserad på den mall du valde.

1. (Villkorligt) Om mallen innehåller komponenter som inte är tillgängliga i datavyn visas dialogrutan Inkompatibel datavy, där det anges att datavyn är inkompatibel med mallen och vilka komponenter som saknas.

   Gör något av följande:

   * Välj en annan datavy i listrutan **[!UICONTROL Change data view]**.

   * Välj **[!UICONTROL Continue anyway]** om du vill visa mallen med de komponenter som saknas.

## Skapa ett projekt baserat på en mall {#use-reports}

En mall kanske inte passar dina behov exakt, men den kan göra att du kommer nära. I dessa fall kan du använda mallen som utgångspunkt för ditt projekt och sedan anpassa den så att den passar dina specifika syften.

Om du navigerar bort från en mall efter att ha gjort ändringar uppmanas du att spara eller ignorera ändringarna. Om du sparar ändringar i en mall sparas mallen som ett nytt projekt.

Så här anpassar du en mall och sparar den som ett projekt:

1. I Customer Journey Analytics väljer du fliken [!UICONTROL **Workspace**].

1. Välj fliken [!UICONTROL **Mallar**].

1. Välj den mall som du vill visa. Välj till exempel mallen [!UICONTROL **Sidor**] under [!UICONTROL **Mest populära**].

   Sidmallen, som den visas i Analysis Workspace, visar två [visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) ([stapeldiagram](/help/analysis-workspace/visualizations/bar.md) och [sammanfattningsnummer](/help/analysis-workspace/visualizations/summary-number-change.md)) samt en [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md). Det mätvärde som används är förekomster.

   <!--update screenshot. The following is AA -->

   ![Sidmallar](assets/pages-report.png)

1. Gör något av följande:

   * Visa mallen.
   * Dra ett eller flera segment till segmentsläppzonen längst upp. Dra till exempel segmentet [!UICONTROL **Mobila kunder**] och visa resultatet.
   * Ändra datumintervallet genom att gå till kalendern längst upp till höger.
   * Lägg in dimensionsanalyser, dra in andra mätvärden och anpassa mallen efter behov.

1. (Valfritt) Spara mallen som ett projekt genom att välja [!UICONTROL **Projekt**] > [!UICONTROL **Spara**].

   Mallen sparas som ett nytt projekt. Den ändrar inte den befintliga mallen. Mer information om hur du sparar projekt finns i [Spara projekt](/help/analysis-workspace/build-workspace-project/save-projects.md).

## Tillgängliga mallar

Så här kommer du åt alla tillgängliga färdiga mallar:

1. I Adobe Analytics väljer du fliken [!UICONTROL **Workspace**] och sedan fliken [!UICONTROL **Mallar**] .

   Fördefinierade mallar ordnas efter kategori.

   <!--add screenshot-->

1. Välj en kategori om du vill visa mallarna i den.

   Följande avsnitt motsvarar de tillgängliga kategorierna och ger information om varje mall.

   * **[[!UICONTROL Most popular]](#most-popular)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Engagement]](#engagement)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Conversion]](#web-conversion)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Audience]](#web-audience)**

   * **[[!UICONTROL Web]** > **[!UICONTROL Acquisition]](#web-acquisition)**

   * **[[!UICONTROL Mobile]** > **[!UICONTROL Mobile App]](#mobile-mobile-app)**

   * **[[!UICONTROL Mobile]** > **[!UICONTROL Mobile Device Information]](#mobile-mobile-device-information)**

   * **[[!UICONTROL Time Parting]](#time-parting)**

   * **[[!UICONTROL Cross-Channel]](#cross-channel)**

   * **[[!UICONTROL Other Channels]](#other-channels)**

   * **[[!UICONTROL AJO]](#ajo)**

### Mest populära {#most-popular}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--unitsOvertimeReport"
>title="Visa det totala antalet enheter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur enhetsförsäljningen ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som köper flest enheter och hur enhetsförsäljningen trendar över tid.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra enhetsförsäljningen före och efter att kampanjen har startats. Du kan också jämföra försäljningen per år under helger.<br/>Den här mallen använder måtten Dag och Enheter."

<!-- markdownlint-enable MD034 -->

<!--both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--training"
>title="Mall för självstudiekurser"
>abstract="Lär dig vanliga Analysis Workspace-termer och steg för att skapa din första analys."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pagesRankedReport"
>title="Identifiera de mest populära och minst populära sidorna."
>abstract="**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.<br/>Den här mallen använder måtten Siddimension och Sidvyer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--pageViewsOvertimeReport"
>title="Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. "
>abstract="**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.<br/>Den här mallen använder måtten Dag och Sidvisning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitsOvertimeReport"
>title="Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.<br/>Den här mallen använder måtten Dag och Besök."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--visitorsOvertimeReport"
>title="Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. "
>abstract="**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.<br/>Den här mallen använder måtten Dag och Unika besökare. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--keyMetricsReport"
>title="Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. <br/>Den här mallen använder måtten Dag, Sidvisning, Besök och Unika besökare."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--siteSectionRankedReport"
>title="Se de populäraste eller mest högpresterande avsnitten på webbplatsen."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.<br>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.<br/>Den här mallen använder dimensionen Platsavsnitt och Visits-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--next-page-report"
>title="Se de vanligaste platserna direkt efter besök på en viss sida."
>abstract="**Det här kan hjälpa dig** att förstå användarbeteendet bättre när du har besökt en viss sida.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om siddesignen eller layouten kan optimeras för att dirigera människor till mer önskade sidor, som en sida för att göra ett köp eller lämna en granskning.<br/>Den här mallen använder måtten Sida och Händelser."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--previous-page-report"
>title="Se de vanligaste platserna där man besöker en viss sida omedelbart."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka sidor som dirigerar mest trafik till en viss sida.<br/>**Baserat på vad du lär dig kan du** göra några saker, som att utvärdera om sidor som inte visas som tidigare sidor behöver mer framträdande länkar till den aktuella sidan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignRankedReport"
>title="Visa länkarna som lyckades mest när det gällde att köra trafik till er webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka spårningskoder (och de länkar de är kopplade till) som var de mest använda för att komma åt din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att justera din strategi för var du lägger till länkar till din webbplats.<br/>Den här mallen använder spårningskoddimensionen och Visits-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productsRankedReport"
>title="Visa antalet order per produkt. Data visas över en tidsperiod."
>abstract="**Detta kan hjälpa dig** att förstå vilka produkter som har störst eller lägst efterfrågan.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera dina marknadsföringsstrategier för att marknadsföra högpresterande produkter eller för att förbättra eller avbryta underpresterande produkter. Du kan också justera produktlagret baserat på din analys av data.<br/>Den här mallen använder produktdimensionen och ordermåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelRankedReport"
>title="Visa de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att förstå vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.<br/>Den här mallen använder dimensionen Senaste beröringskanal och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--lastTouchChannelDetailRankedReport"
>title="Visa information om de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att förstå inte bara vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar, utan även information om dessa marknadsföringskanaler. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.<br/>Den här mallen använder dimensionen Senaste beröringskanaldetalj och det unika besökarmåttet. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--revenueOvertimeReport"
>title="Visa det monetära antalet produkter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att förstå hur intäkterna ökar eller minskar över tid. Du kan kombinera det här måttet med vilken dimension som helst för att lära dig vilka dimensionsobjekt som har bidragit till intäkterna.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel framtida projektintäkter baserade på tidigare trender. Ni kan också lägga till ytterligare en dimension, som spårningskoddimensionen, för att lära er vilka kampanjer som genererar störst intäkter.<br/>Den här mallen använder måtten Dag och Intäkter."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--ordersOvertimeReport"
>title="Visa det totala antalet inköpshändelser. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur intresset för dina produkter och tjänster ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som gör mest beställningar och hur dessa beställningar trendar över tid.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra order före och efter det att kampanjen har startats. Eller så kan du jämföra årsavgiftsbeställningar.<br/>Den här mallen använder måtten Dag och Order."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Utbildning - självstudiekurs**] | Lär dig vanliga Analysis Workspace-termer och steg för att bygga din första analys |
| [!UICONTROL **Sidor**] | <!--duplicated in Engagement section--> Identifiera de mest populära och minst populära sidorna. <p>**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.</p><p>I den här mallen används måtten Siddimension och Sidvisning.</p> |
| [!UICONTROL **Sidvyer**] | <!--duplicated in Engagement section--> Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten Dag och Sidvisning.</p> |
| [!UICONTROL **Webbbesök**] | <!--duplicated in Engagement section--> Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten Dag och Besök.</p> |
| [!UICONTROL **Webbbesökare**] | <!--duplicated in Engagement section--> Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.</p><p>I den här mallen används måtten Dag och Unika besökare.</p> |
| [!UICONTROL **Nyckeltal**] | <!--duplicated in Engagement section--> Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. </p><p>I den här mallen används måtten Dag, Sidvisning, Besök och Unika besökare.</p> |
| [!UICONTROL **Webbplatsavsnitt**] | Se de populäraste eller mest högpresterande avsnitten på webbplatsen. <p>**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.</p> <p>Den här mallen använder dimensionen Platsavsnitt och måttet Besök.</p> |
| [!UICONTROL **Nästa sida**] | Se de vanligaste platserna direkt efter besök på en viss sida. <p>**Det här kan hjälpa dig** att förstå användarbeteendet bättre när du har besökt en viss sida.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om siddesignen eller layouten kan optimeras för att dirigera människor till mer önskade sidor, som en sida för att göra ett köp eller lämna en granskning.</p> <p>I den här mallen används måtten Sida och Händelser.</p> |
| [!UICONTROL **Föregående sida**] | Se de vanligaste platserna där man besöker en viss sida omedelbart. <p>**Det här kan hjälpa dig** att bättre förstå vilka sidor som dirigerar mest trafik till en viss sida.</p><p>**Baserat på vad du lär dig kan du** göra några saker, som att utvärdera om sidor som inte visas som tidigare sidor behöver mer framträdande länkar till den aktuella sidan.</p><p>I den här mallen används måtten Sida och Händelser.</p> |
| [!UICONTROL **Spårningskod**] | Visa länkarna som lyckades mest när det gällde att köra trafik till er webbplats. <p>**Detta kan hjälpa dig** att bättre förstå vilka spårningskoder (och de länkar de är kopplade till) som var de mest använda för att komma åt din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att justera din strategi för var du lägger till länkar till din webbplats.</p><p>I den här mallen används spårningskoddimensionen och Visits-måttet.</p> |
| [!UICONTROL **Produkter**] | Visa antalet order per produkt. Data visas över en tidsperiod. <p>**Detta kan hjälpa dig** att förstå vilka produkter som har störst eller lägst efterfrågan.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera dina marknadsföringsstrategier för att marknadsföra högpresterande produkter eller för att förbättra eller avbryta underpresterande produkter. Du kan också justera produktlagret baserat på din analys av data.</p><p>I den här mallen används måtten Produkt och Order.</p> |
| [!UICONTROL **Senaste beröringskanal**] | Visa de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att förstå vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.</p><p>I den här mallen används måtten Senaste beröringskanal och Unika besökare.</p> |
| [!UICONTROL **Senaste beröringskanaldetalj**] | Visa information om de senaste marknadsföringskanalerna som besökarna matchar under sin engagemangsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att förstå inte bara vilka marknadsföringskanaler som var mest effektiva när det gäller att ta personer till din webbplats som resulterar i konverteringar, utan även information om dessa marknadsföringskanaler. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela mer resurser till högpresterande kanaler eller tilldela färre resurser till underpresterande kanaler.</p><p>I den här mallen används dimensionen Senaste beröringskanaldetalj och det unika besökarmåttet.</p> |
| [!UICONTROL **Intäkter**] | <!--duplicated in Web Conversion section-->Visa det monetära antalet produkter som köpts i alla order. Data visas över en tidsperiod och jämförs med tidigare perioder.<p>**Detta kan hjälpa dig** att förstå hur intäkterna ökar eller minskar över tid. Du kan kombinera det här måttet med vilken dimension som helst för att lära dig vilka dimensionsobjekt som har bidragit till intäkterna.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel framtida projektintäkter baserade på tidigare trender. Ni kan också lägga till ytterligare en dimension, som spårningskoddimensionen, för att lära er vilka kampanjer som genererar störst intäkter.</p><p>I den här mallen används måtten Dag och Intäkter.</p> |
| [!UICONTROL **Beställningar**] | <!--duplicated in Web Conversion section-->Visa det totala antalet inköpshändelser. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur intresset för dina produkter och tjänster ökar eller minskar över tid. Du kan använda ett segment för att lära dig vilka kunder eller geografiska områden som gör mest beställningar och hur dessa beställningar trendar över tid.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra order före och efter det att kampanjen har startats. Eller så kan du jämföra årsavgiftsbeställningar.</p><p>I den här mallen används måtten Dag och Order.</p> |

### Webb: Engagemang {#web-engagement}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--real-time"
>title="Visa de dimensioner och mätvärden som samlas in på din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vad som är trender på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att svara på och aktivt hantera prestandan för ert marknadsföringsinnehåll och era kampanjer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentVisitOvertimeReport"
>title="Se den genomsnittliga tid besökare tillbringar på er webbplats under varje besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.<br/>Den här mallen använder måtten Dag och Tid per besök (sekunder)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timePriorRankedReport"
>title="Visa den genomsnittliga tiden som användare tillbringar före en lyckad händelse."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur lång tid det tar för besökarna att utföra en önskad åtgärd, till exempel göra ett köp.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om ändringar av din webbplats förbättrar besökarens förmåga att snabbt nå en lyckad händelse.<br/>Den här mallen använder dimensionen Tid före händelse och måttet för unika besökare."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--falloutReport"
>title="Visa var personer lämnar eller fortsätter via en fördefinierad sidsekvens."
>abstract="**Det här kan hjälpa dig** att bättre förstå var personer faller bort från användarresan.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera konverteringsgraden via specifika processer på webbplatsen (till exempel en köp- eller registreringsprocess) eller analysera korrelationer mellan händelser på webbplatsen. (Exempel: hur många procent av de personer som tittade på din integritetspolicy gick vidare till att köpa en produkt.) Du kan också använda den här mallen för att utföra jämförelser sida vid sida av två olika segment i samma rapport.<br/>Den här mallen använder utfallsvisualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--cross-device-analysis"
>title="Se vilka enheter som används i alla delar av resan."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur många som interagerar med ert varumärke, vilka typer av enheter de använder och hur deras användning av flera enheter påverkar deras upplevelse. Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra en uppgift? Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de? Och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera vissa delar av användarresan för en mobil upplevelse.<br/>Den här mallen använder värdena för Flödesvisualisering, Utfallsvisualisering, Kohortanalys, Personmått och Unika enheter."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--web-retention"
>title="Se vilka era lojala kunder är och vad de gör på er webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur många gånger den genomsnittliga personen besöker din webbplats, hur ofta personer återvänder till webbplatsen och hur många dagar som förflutit mellan återkomstbesöken.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som är mest effektivt för att ta personer tillbaka till webbplatsen.<br/>Den här mallen använder Visits-måttet och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--audio-consumption-template"
>title="Se trender och de viktigaste mätvärdena för medieanvändning på alla digitala enheter."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur besökare konsumerar ljudinnehåll på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som konsumeras mest.<br/>Den här mallen använder Visits-måttet och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--media-recency-frequency-loyalty"
>title="Se trender och de viktigaste mätvärdena för mediekonsumtion på alla digitala enheter."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur många gånger den genomsnittliga personen besöker din webbplats, hur ofta personer återvänder till webbplatsen och hur många dagar som förflutit mellan återkomstbesöken.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera vilket innehåll som är mest effektivt för att ta personer tillbaka till webbplatsen.<br/>Den här mallen använder Visits-måttet och det unika besökarmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--reloadsRankedReport"
>title="Visa det antal gånger en dimensionsobjekt fanns under en omladdning. En besökare som uppdaterar sin webbläsare är det vanligaste sättet att utlösa en omladdning."
>abstract="**Detta kan hjälpa dig** att identifiera när det kan uppstå problem på en viss sida som skulle uppmana en besökare att läsa in sidan igen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sidor som har problem som behöver åtgärdas.<br/>Den här mallen använder måttet Läs in igen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeSpentPageRankedReport"
>title="Se den genomsnittliga tid besökare tillbringar på er webbplats under varje besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.<br/>Den här mallen använder måtten Dag och Tid per besök (sekunder)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--entryPageOriginalRankedReport"
>title="Visa de populäraste sidorna som andra kommer åt när de besöker webbplatsen för första gången under besökarens livstid."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.<br/>Den här mallen använder måttet för sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--singlePageVisitsRankedReport"
>title="Visa antalet besök som bestod av en enda unik sida."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur mycket tid besökarna spenderar på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att utvärdera om ändringar på din webbplats leder till att besökarna spenderar mer tid på webbplatsen.<br/>Den här mallen använder dimensionen för besök på en sida."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--sitePerformanceOverview"
>title="Visa prestandadata för din Adobe Experience Manager-webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå värdeberäkning från Adobe Experience Manager.<br/>**Beroende på vad du lär dig kan du** göra något annat, som att optimera dina Experience Manager-inställningar."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--formsPerformanceOverview"
>title="Visa prestandadata för din Adobe Experience Manager Forms."
>abstract="**Det här kan hjälpa dig** att bättre förstå värdeberäkning från Adobe Experience Manager.<br/>**Beroende på vad du lär dig kan du** göra något annat, som att optimera dina Experience Manager-inställningar."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--itp-impact"
>title="Visa och analysera effekterna av ITP (Intelligent Tracking Prevention) på datainsamling och rapportering."
>abstract="**Detta kan hjälpa dig** att bättre förstå potentiella dataförluster på grund av cookie-begränsningar som ITP har infört.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att anpassa analysinställningarna för att minimera effekten av ITP."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template_time_spent"
>title="Se den genomsnittliga tid besökarna tillbringar på er webbplats under varje besök, liksom den genomsnittliga tid som användarna tillbringar innan ett lyckat besök. Data visas över en tidsperiod och jämförs med tidigare perioder."
>abstract="**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur lång tid det tar för besökarna att utföra en önskad åtgärd, till exempel göra ett köp.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om ändringar av din webbplats förbättrar besökarens förmåga att snabbt nå en lyckad händelse.<br/>Den här mallen använder måtten Dag och Tid per besök (sekunder), Dag och Antal besök (sekunder)."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-content-consumption"
>title="Se vilket webbinnehåll som konsumeras mest och engagerande användare."
>abstract="**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen.<br/>I den här mallen används måtten Siddimension och Sidvisning, Visits-måttet, det unika besökarmåttet, starthastighetsmåttet, avhoppsfrekvensen, avslutningsmåttet och innehållshastighetsmåttet. Flödesvisualiseringar används också för in-, avslutnings- och toppavsnitt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--media-content-consumption"
>title="Se vilket medieinnehåll som konsumeras mest och engagerande användare."
>abstract="**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen.<br/>I den här mallen används måtten Siddimension och Sidvisning, Visits-måttet, det unika besökarmåttet, starthastighetsmåttet, avhoppsfrekvensen, avslutningsmåttet och innehållshastighetsmåttet. Flödesvisualiseringar används också för in-, avslutnings- och toppsektioner, en Scatterplot-visualisering som visar sidvisningar för de vanligaste sidorna, en Bar-visualisering som visar sidvisningar efter paketerad tid och en Line-visualisering som visar en trendvy över den genomsnittliga tiden som har tillbringats på webbplatsen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--flowreport"
>title="Se de vanligaste platserna där man besöker en viss plats omedelbart efter besök eller omedelbart."
>abstract="**Detta kan hjälpa dig** att förstå hur trafiken flyttas från en viss sida till andra delar av webbplatsen och förstå de sökvägar som användarna tar för att komma fram till en viss sida.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om siddesignen eller layouten kan optimeras för att dirigera människor till mer önskade sidor, som en sida för att göra ett köp eller lämna en granskning. Eller utvärdera om informationen på den aktuella sidan kan ge den riktning eller de åtgärder som folk vill ha när de kommer från föregående sidor. Du kan också bedöma om sidor som inte visas som tidigare sidor behöver mer framträdande länkar till den aktuella sidan.<br/>Den här mallen använder panelen Nästa eller Föregående objekt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--page-summary-report"
>title="Visa viktig information om alla sidor i egenskaperna. Visar sidvyer, en trendlinje, en flödesvisualisering och mycket mer."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur människor interagerar med en viss sida.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera sidans prestanda över en tidsperiod eller bättre förstå vad som driver trafik till sidan.<br/>Den här mallen använder måttet Sidvyer. Det använder även linjevisualisering och Flow-visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--entryPageRankedReport"
>title="Visa de översta sidorna som andra kommer åt när de besöker webbplatsen första gången."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.<br/>Den här mallen använder måttet för sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--exitPageRankedReport"
>title="Visa de översta sidorna som andra kommer åt direkt innan de lämnar din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka sidor som leder personer bort från webbplatsen. <br/>**Baserat på vad du lär dig kan du** göra något av följande, till exempel uppdatera vanliga avslutssidor för att optimera upplevelsen som andra får innan de lämnar webbplatsen, eller inkludera innehåll eller länkar för att uppmuntra andra att stanna kvar på webbplatsen.<br/>Den här mallen använder måttet för sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productUsageOverviewReport"
>title="Se hur Customer Journey Analytics används i er organisation."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur många som använder Customer Journey Analytics, hur ofta de använder det och hur många användartrender de använder över tid. Du kan också se antalet projekt som skapas och information om dessa projekt (till exempel vilka komponenter, visualiseringar och paneler som används mest) samt många andra användningsstatistik.<br/>**Baserat på vad du lär dig kan du** göra flera saker, t.ex. ta bort oanvända projekt eller komponenter, eller tillhandahålla användarutbildning för populära funktioner."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--content-analytics"
>title="Lär dig vilka innehålls- och innehållsattribut som fungerar bäst."
>abstract="**Detta kan hjälpa dig** att lära dig hur ditt innehåll fungerar på detaljnivå. Du kan titta på prestanda för enskilda resurser eller specifika attribut. Content Analytics använder AI för att automatiskt generera attribut och tagga ditt innehåll med dem. [Lär dig mer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics)<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att marknadsföra högpresterande resurser på din hemsida, anpassa innehåll för specifika segment så att det innehåller högpresterande attribut eller rotera bort innehåll som har börjat bli inaktuellt."

<!-- markdownlint-enable MD034 -->


Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Nyckeltal**] | <!--duplicated in Most popular section--> Visa en rapport som visar sidvisningar, besök och unika besökarmått sida vid sida. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att jämföra dessa viktiga mätvärden för att få en mer fullständig bild av antalet unika personer som besöker webbplatsen, antalet gånger som sidorna besöktes och antalet sessioner.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera det genomsnittliga antalet sidor som varje person tittar på när han/hon besöker webbplatsen under en viss vecka eller månad, och hur detta ändrades under vissa tider på året eller före och efter det att marknadsföringskampanjer kördes. </p><p>I den här mallen används måtten Dag, Sidvisning, Besök och Unika besökare.</p> |
| [!UICONTROL **Sidvyer**] | <!--duplicated in Most popular section-->Visa det totala antalet sidvisningar. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten Dag och Sidvisning.</p> |
| [!UICONTROL **Sidor**] | <!--duplicated in Most popular section-->Identifiera de mest populära och minst populära sidorna. <p>**Detta kan hjälpa dig** att bättre förstå din målgrupp och vilken typ av information de är mest intresserade av.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, till exempel justera sidmetadata för att öka synligheten på sidor som visas i mindre grad, eller lägga tid på att förbättra innehållet på de sidor som visas mest.</p><p>I den här mallen används måtten Siddimension och Sidvisning.</p> |
| [!UICONTROL **Besök**] | <!--duplicated in Most popular section-->Visa det totala antalet besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur trafiken på din webbplats kan öka eller minska med tiden.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera effekten av en nyligen lanserad marknadsföringskampanj genom att jämföra webbplatstrafiken före och efter att kampanjen har startats. Eller jämför semestertrafiken år för år.</p><p>I den här mallen används måtten Dag och Besök.</p> |
| [!UICONTROL **Besökare**] | <!--duplicated in Most popular section-->Visa det totala antalet unika besökare. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå hur webbplatsens räckvidd och målgruppsstorlek ökar eller minskar över tid eller jämfört med en tidigare period.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om en nyligen lanserad marknadsföringskampanj lyckades attrahera nya personer till webbplatsen genom att jämföra unika besökare före och efter det att kampanjen startades. Eller så kan du jämföra antalet personer som ska besöka sajten under helger år för år.</p><p>I den här mallen används måtten Dag och Unika besökare.</p> |
| [!UICONTROL **Tidsåtgång**] | Se den genomsnittliga tid besökarna tillbringar på er webbplats under varje besök, liksom den genomsnittliga tid som användarna tillbringar innan ett lyckat besök. Data visas över en tidsperiod och jämförs med tidigare perioder. <p>**Detta kan hjälpa dig** att bättre förstå besökarnas engagemangsnivåer och hur lång tid det tar för besökarna att utföra en önskad åtgärd, till exempel göra ett köp.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om ändringar av din webbplats förbättrar besökarens förmåga att snabbt nå en lyckad händelse.</p><p>I den här mallen används måtten Dag och Tid per besök (sekunder), Dag och Antal besök (sekunder).</p> |
| [!UICONTROL **Webbplatsavsnitt**] | <!--duplicated in Most popular section-->Se de populäraste eller mest högpresterande avsnitten på webbplatsen. <p>**Det här kan hjälpa dig** att bättre förstå vilka avsnitt på webbplatsen som är mest besökta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka produkter eller tjänster som du tillhandahåller och som ger mest intresse.</p> <p>Den här mallen använder dimensionen Platsavsnitt och måttet Besök.</p> |
| [!UICONTROL **Webbinnehållsförbrukning**] | Se vilket webbinnehåll som konsumeras mest och engagerande användare.<p>**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen.</p> <p>I den här mallen används måtten Siddimension och Sidvisning, Visits-mått, Unika besökare, Inmatningshastighet, Studsfrekvens, Exit Rate-mått och Innehållshastighet. Flödesvisualiseringar används också för in-, avslutnings- och toppavsnitt.</p> |
| [!UICONTROL **Medieinnehållsförbrukning**] | Se vilket medieinnehåll som konsumeras mest och engagerande användare.<p>**Det här kan hjälpa dig** att bättre förstå var personer ska gå när de kommer in på webbplatsen, vilka delar av webbplatsen som de flesta besöker och vilka sidor som troligen kommer att leda bort personer från webbplatsen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera vilka sökvägar på webbplatsen som leder personer till de viktigaste sidorna och vilka sidor som är mer benägna att leda personer bort från webbplatsen <!-- not sure about these takeaways... -->.</p> <p>I den här mallen används måtten Siddimension och Sidvisning, Visits-mått, Unika besökare, Inmatningshastighet, Studsfrekvens, Exit Rate-mått och Innehållshastighet. Flödesvisualiseringar används också för in-, avslutnings- och toppsektioner, en Scatterplot-visualisering som visar sidvisningar för de vanligaste sidorna, en Bar-visualisering som visar sidvisningar efter paketerad tid och en Line-visualisering som visar en trendvy över den genomsnittliga tiden som har tillbringats på webbplatsen.</p> |
| [!UICONTROL **Nästa och föregående sidflöde**] | Visa en flödesvisualisering av de vanligaste platserna som folk besöker direkt efter besök och omedelbart innan de besöker en viss sida. <p>**Detta kan hjälpa dig** att förstå hur trafiken flyttas från en viss sida till andra delar av webbplatsen och förstå de sökvägar som användarna tar för att komma fram till en viss sida.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utvärdera om siddesignen eller layouten kan optimeras för att dirigera människor till mer önskade sidor, som en sida för att göra ett köp eller lämna en granskning. Eller utvärdera om informationen på den aktuella sidan kan ge den riktning eller de åtgärder som folk vill ha när de kommer från föregående sidor. Du kan också bedöma om sidor som inte visas som tidigare sidor behöver mer framträdande länkar till den aktuella sidan.</p><p>Den här mallen använder panelen Nästa eller Föregående objekt.</p> |
| **Sidsammanfattning** | Visa viktig information om alla sidor i egenskaperna. Visar sidvyer, en trendlinje, en flödesvisualisering och mycket mer.  <p>**Detta kan hjälpa dig** att bättre förstå hur människor interagerar med en viss sida.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att analysera sidans prestanda över en tidsperiod eller bättre förstå vad som driver trafik till sidan.</p><p>I den här mallen används måttet Sidvyer. Det använder även linjevisualisering och Flow-visualisering.</p> |
| **Startsidor** | Visa de översta sidorna som andra kommer åt när de besöker webbplatsen första gången. <p>**Detta kan hjälpa dig** att bättre förstå vilka sidor som genererar mest trafik till din webbplats eller förstå mer om de första visningar besökarna har på din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera den första upplevelsen som andra personer kommer in på webbplatsen, eller se till att de sidor som de första användarna ser när de kommer in på din webbplats är välkomna och tillhandahåller nödvändiga länkar till andra delar av din webbplats.</p><p>Den här mallen använder måttet Sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering.</p> |
| **Avsluta sidor** | Visa de översta sidorna som andra kommer åt direkt innan de lämnar din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka sidor som leder personer bort från webbplatsen. </p><p>**Baserat på vad du lär dig kan du** göra något av följande, till exempel uppdatera vanliga avslutssidor för att optimera upplevelsen som andra får innan de lämnar webbplatsen, eller inkludera innehåll eller länkar för att uppmuntra andra att stanna kvar på webbplatsen.</p><p>Den här mallen använder måttet Sessioner. Den använder även Bar-visualisering och frihandstabellens visualisering.</p> |
| **Översikt över produktanvändning** | Se hur Customer Journey Analytics används i er organisation. <p>**Det här kan hjälpa dig** att bättre förstå hur många som använder Customer Journey Analytics, hur ofta de använder det och hur många användartrender de använder över tid. Du kan också se antalet projekt som skapas och information om dessa projekt (till exempel vilka komponenter, visualiseringar och paneler som används mest) samt många andra användningsstatistik.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, t.ex. ta bort oanvända projekt eller komponenter, eller tillhandahålla användarutbildning för populära funktioner.</p> |
| **Innehållsanalys** | Lär dig vilka innehålls- och innehållsattribut som fungerar bäst.<p>**Detta kan hjälpa dig** att lära dig hur ditt innehåll fungerar på detaljnivå. Du kan titta på prestanda för enskilda resurser eller specifika attribut. Content Analytics använder AI för att automatiskt generera attribut och tagga ditt innehåll med dem. [Läs mer](/help/content-analytics/content-analytics.md).</p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att marknadsföra högpresterande resurser på din hemsida, anpassa innehåll för specifika segment så att de inkluderar högpresterande attribut eller rotera bort innehåll som har börjat bli inaktuellt.</p> |

### Webb: Konvertering {#web-conversion}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--categoryRankedReport"
>title="Visa antalet besök som är kopplade till varje produktkategori på din webbplats. Detta är användbart för implementeringar som använder variabeln products och vill se mätvärden för produktkategorin. Dimensionen som fyller i den här mallen kan vara tom om du inte har några produkter på webbplatsen."
>abstract="**Det här kan hjälpa dig** att bättre förstå populära eller mest visade produkter. &lt;/br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att mäta effekten av en marknadsföringskampanj för en viss produkt.<br/>Den här mallen använder måtten Kategori och Besök. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--commerce-and-marketing-management"
>title="Visa fördefinierade insikter för återförsäljare om era handelsaktiviteter för att förbättra försäljningen. Detta riktar sig till användare av Adobe Commerce, men kan utnyttjas av alla webbutiker."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur dina handelsaktiviteter bidrar till försäljningssiffror.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera budgeten efter aktiviteter som får störst avkastning."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--productConversionReport"
>title="Visa produktkonvertering i en trattvisualisering som visar kundvagnar, utcheckningar och order. Du kan också se konverteringsprocentsatser, intäktsgenomsnitt, enhetsmedelvärden och ordermedelvärden."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur människor går igenom och släpper under konverteringsprocessen.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att förbättra din webbplats för att underlätta en smidigare utcheckningsprocess."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-products-template"
>title="Se vilka produkter som ger bäst resultat."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.<br/>Den här mallen använder måtten Produktvyer, kundvagnstillägg, Beställningar, Intäkter och Enheter. Det använder också produktdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartConversionReport"
>title="Visa hur många gånger personer har utfört utcheckningshändelser, t.ex. lagt till artiklar i kundvagnen, visat kundvagnen, tagit bort artiklar från kundvagnen och checkat ut."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka delar av processen som leder till konvertering och vilka som löper större risk att överge kundvagnen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att minska friktionen i vissa steg i utcheckningsprocessen.<br/>Den här mallen använder"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartsOvertimeReport"
>title="Visa antalet personer som har lagt till en produkt i kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå antalet personer som lägger till en produkt i kundvagnen, till skillnad från det totala antalet produkter som läggs till i en kundvagn.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att mäta effektiviteten hos dina produktsidor.<br/>Den här mallen använder Carts-måttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartViewsOvertimeReport"
>title="Se hur många gånger kunderna har sett sin kundvagn."
>abstract="**Det här kan hjälpa dig** att bättre förstå utcheckningsupplevelsen i ett försök att minska antalet kundvagnsavhoppningar eller analysera tiden mellan kundvagnstillägg och utcheckning av olika produkter.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, till exempel erbjuda kampanjer för produkter som ligger längst i varukorgar och som löper störst risk att överges.<br/>Den här mallen använder måttet för kundvagnsvyer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartAdditionsOvertimeReport"
>title="Se hur många gånger någon har lagt till något i kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kundintresset för en produkt är tillräckligt högt för att de ska kunna lägga till den i kundvagnen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra produktrekommendationerna för alla kunder. Detta kan göras genom att analysera vilka produkter som ofta läggs till i samma varukorgar och genom att föreslå relaterade produkter baserade på artiklar som redan finns i varukorgen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cartRemovalsOvertimeReport"
>title="Se hur många gånger någon har tagit bort något från kundvagnen."
>abstract="**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kunderna inte längre är intresserade av en produkt, eller så kan det hjälpa dig att förstå var det kan finnas problem i utcheckningsprocessen.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel ta bort eventuella hinder som kan finnas i utcheckningsprocessen, till exempel en komplicerad användarupplevelse.<br/>Den här mallen använder måttet för kundvagnsborttagning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--purchaseConversionReport"
>title="Visa inköpskonvertering i en trattvisualisering som visar sessioner, kundvagnar och order. Du kan också se konverteringsprocentsatser, intäktsgenomsnitt, enhetsmedelvärden och ordermedelvärden."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur människor går igenom och släpper under konverteringsprocessen.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att förbättra din webbplats för att underlätta en smidigare utcheckningsprocess."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Produktkonverteringstratt**] | Visa produktkonvertering i en trattvisualisering som visar kundvagnar, utcheckningar och order. Du kan också se konverteringsprocentsatser, intäktsgenomsnitt, enhetsmedelvärden och ordermedelvärden.<p>**Det här kan hjälpa dig** att bättre förstå hur människor går igenom och släpper under konverteringsprocessen.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att förbättra din webbplats för att underlätta en smidigare utcheckningsprocess.</p> |
| **Produkter** | Se vilka produkter som genererar nyckeltal, t.ex. de främsta säljarna eller de mest visade. <p>**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.</p><p>I den här mallen används ordermåttet och produktdimensionen. |
| **Produktprestanda** | Se vilka produkter som ger bäst resultat.<p>**Detta kan hjälpa dig** att bättre förstå vilka produkter som är mest framgångsrika.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att öka finansieringen av framgångsrika produkter och minska finansieringen av mindre framgångsrika produkter.</p><p>I den här mallen används måtten för produktvyer, kundvagnstillägg, beställningar, intäkter och enheter. Det använder också produktdimensionen. |
| **Konverteringsfunktioner för kundvagn** | Visa hur många gånger personer har utfört utcheckningshändelser, t.ex. lagt till artiklar i kundvagnen, visat kundvagnen, tagit bort artiklar från kundvagnen och checkat ut. <p>**Detta kan hjälpa dig** att bättre förstå vilka delar av processen som leder till konvertering och vilka som löper större risk att överge kundvagnen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att minska friktionen i vissa steg i utcheckningsprocessen.</p> |
| **KARTOR** | Visa antalet personer som har lagt till en produkt i kundvagnen.<p>**Detta kan hjälpa dig** att bättre förstå antalet personer som lägger till en produkt i kundvagnen, till skillnad från det totala antalet produkter som läggs till i en kundvagn.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att mäta effektiviteten hos dina produktsidor.</p><p>I den här mallen används Carts-måttet. |
| **Vyer för kundvagn** | Se hur många gånger kunderna har sett sin kundvagn. <p>**Det här kan hjälpa dig** att bättre förstå utcheckningsupplevelsen i ett försök att minska antalet kundvagnsavhoppningar eller analysera tiden mellan kundvagnstillägg och utcheckning av olika produkter.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, till exempel erbjuda kampanjer för produkter som ligger längst i varukorgar och som löper störst risk att överges.</p><p>I den här mallen används måttet för kundvagnsvyer. |
| **Kundtillägg** | Se hur många gånger någon har lagt till något i kundvagnen. <p>**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kundintresset för en produkt är tillräckligt högt för att de ska kunna lägga till den i kundvagnen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra produktrekommendationerna för alla kunder. Detta kan göras genom att analysera vilka produkter som ofta läggs till i samma varukorgar och föreslå relaterade produkter som baseras på artiklar som redan finns i varukorgen. |
| **Ta bort kundvagn** | Se hur många gånger någon har tagit bort något från kundvagnen.<p>**Detta kan hjälpa dig** att bättre förstå den del av konverteringsprocessen där kunderna inte längre är intresserade av en produkt, eller så kan det hjälpa dig att förstå var det kan finnas problem i utcheckningsprocessen.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel ta bort eventuella hinder som kan finnas i utcheckningsprocessen, till exempel en komplicerad användarupplevelse.</p><p>I den här mallen används måttet för kundvagnsborttagning. |
| **Inköpskonverteringstratt** | Visa inköpskonvertering i en trattvisualisering som visar sessioner, kundvagnar och order. Du kan också se konverteringsprocentsatser, intäktsgenomsnitt, enhetsmedelvärden och ordermedelvärden.<p>**Det här kan hjälpa dig** att bättre förstå hur människor går igenom och släpper under konverteringsprocessen.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att förbättra din webbplats för att underlätta en smidigare utcheckningsprocess.</p> |
| **Intäkter** | <!--duplicated in Most popular section-->Visa det monetära antalet produkter som köpts i alla order.<p>**Detta kan hjälpa dig** att bättre förstå vilka dimensionsobjekt som har bidragit till intäkterna genom att kombinera intäktsmåtten med valfri dimension. Du kan till exempel se de främsta kampanjerna (med hjälp av spårningskoddimensionen) som har bidragit till intäkterna. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel justera kampanjer som inte uppfyller de intäktsmål du kan förvänta dig.</p><p>I den här mallen används intäktsmåttet. |
| **Beställningar** | <!--duplicated in Most popular section-->Visa det totala antalet inköpshändelser som har gjorts på din webbplats. <p>**Det här kan hjälpa dig** att bättre förstå vilka dimensionsobjekt som har bidragit till en ordning genom att kombinera Orders-måttet med valfri dimension. Du kan till exempel se de främsta kampanjerna (med hjälp av spårningskoddimensionen) som har bidragit till inköp.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel justera kampanjer som inte uppfyller de inköpsmål som du skulle kunna förvänta dig. </p><p>I den här mallen används måttet för beställningar. |

### Webb: Målgrupp {#web-audience}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--people"
>title="Se hur många som interagerar med ert varumärke."
>abstract="**Det här kan hjälpa dig** att bättre förstå användningsmönster på din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att mäta hur effektiv marknadsföringen nyligen har varit när det gäller att skapa nya besökare på din webbplats."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--bots"
>title="Visa sidvisningar och trender för robottrafik på din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå mängden robottrafik som filtreras från din rapportering, enligt de båda regler du har konfigurerat.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fortsätta övervaka startaktiviteten för att identifiera nya mönster."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstvsrepeatvisitors"
>title="Visa en jämförelse av förstagångsbesökare för att upprepa besökare."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur effektiv din webbplats är när det gäller att behålla kundlojaliteten, eller hur ofta du skaffar nya kunder.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att erbjuda incitament för framtida köp till förstagångsbesökare för att locka dem att återvända."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--personid"
>title="Visa enskilda användarbeteenden i olika kanaler."
>abstract="**Detta kan hjälpa dig** att bättre förstå hela kundresan och interaktioner över flera kontaktytor.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att anpassa marknadsföringen för att bättre anpassa användarnas preferenser."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--timeZoneRankedReport"
>title="Visa de översta tidszonerna för besökare som kommer åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå i vilka tidszoner besökarna bor.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att justera webbplatsunderhåll vid tidpunkter som påverkar så få personer som möjligt."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--location"
>title="Visa en översikt över besökarnas plats i en kartvisualisering."
>abstract="**Det här kan hjälpa dig** att bättre förstå var besökarna finns som besöker din webbplats. <br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringsresurser på de platser där du ser störst intresse och möjlighet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--domainRankedReport"
>title="Visa de vanligaste domänerna för besökare som kommer åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka organisationer dina besökare kommer ifrån.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel rikta ditt innehåll mot dina största kunder."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--topLevelDomainRankedReport"
>title="Visa de vanligaste domänerna för besökare som kommer åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka organisationer dina besökare kommer ifrån.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel rikta ditt innehåll mot dina största kunder."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserWidthRankedReport"
>title="Visa de vanligaste webbläsarbredderna som andra använder för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarbredderna. Om du gör det kan du maximera kvalitetskontrollen.<br/>Den här mallen använder webbläsardimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--browserHeightRankedReport"
>title="Visa de topphöjder i webbläsaren som andra använder för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarhöjderna. Om du gör det kan du maximera kvalitetskontrollen.<br/>Den här mallen använder webbläsardimensionen. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemRankedReport"
>title="Visa namnet på de operativsystem och den version som andra använder för att komma åt din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste operativsystemen och versionerna som besökarna använder.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de viktigaste operativsystemen och versionerna. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--operatingSystemTypeRankedReport"
>title="Visa namnet på de operativsystem som användarna använder för att komma åt din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste operativsystemen som besökarna använder.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de vanligaste operativsystemen. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnFrequencyRankedReport"
>title="Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder dimensionen Mobiloperatör."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--returnVisitorsOvertimeReport"
>title="Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder dimensionen Mobiloperatör."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--visitNumberRankedReport"
>title="Visa hur många gånger en besökare har besökt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur engagerade besökare är när de återvänder till din webbplats. Detta gäller besökarens livstid, oavsett projektets datumintervall.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att justera marknadsföringsaktiviteter för besökare som ofta är besökare.<br/>Den här mallen använder dimensionen för besöksnumret."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--customerLoyaltyRankedReport"
>title="Visa antalet besökare på din webbplats som har gjort 0 tidigare inköp, 1 tidigare inköp, 2 tidigare inköp eller 3+ tidigare inköp."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur din webbplats påverkar köpbeteendet.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att fokusera på besökare som kommer tillbaka för att göra ett köp, så att du kan uppmuntra till liknande beteende för nya besökare.<br/>Den här mallen använder kundlojalitetsdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysBeforeFirstPurchaseRankedReport"
>title="Se hur många dagar det är mellan första gången en besökare kommer till er webbplats och när de gör ett köp. Om en besökare till exempel gör ett köp en dag efter första besök, tillhör alla efterföljande besök eller evenemang dimensionsposten 1 dag."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur lång tid det tar för besökarna att göra ett köp.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att uppdatera din webbplats för att uppmuntra till snabbare förvärv.<br/>Den här mallen använder dimensionen Dagar före första inköp."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--daysSinceLastPurchaseRankedReport"
>title="Se hur lång tid det tar mellan besökarens aktuella träff och det senaste köpet vid den tidpunkten."
>abstract="**Detta kan hjälpa dig** att förstå besökarnas beteende bättre efter att ha köpt något på webbplatsen.<br/>**Baserat på vad du lär dig kan du** göra något av följande, som att uppdatera din webbplats för att uppmuntra uppföljningsköp.<br/>Den här mallen använder Dagar sedan den senaste inköpsdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenSizeRankedReport"
>title="Visa de populäraste skärmstorlekarna för mobila enheter som användare använder för att komma åt din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra platskvaliteten genom att testa nya versioner av din webbplats med de vanligaste mobilskärmstorlekarna. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenHeightRankedReport"
>title="Visa höjder på mobilskärmen som andra använder för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatskvaliteten genom att testa nya versioner av din webbplats med de vanligaste höjderna för mobilskärmar. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobileScreenWidthRankedReport"
>title="Visa bredder för den övre mobilskärmen som andra använder för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur innehåll visas för besökare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra webbplatskvaliteten genom att testa nya versioner av webbplatsen med de vanligaste mobilskärmsbredderna. Om du gör det kan du maximera kvalitetskontrollen."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--countryGeoReport"
>title="Se det land som besökarna kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå vad de populäraste länderna besökarna kommer från när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i dessa länder, eller se till att webbplatsupplevelsen är optimal i länder som har olika primära språk.<br/>Den här mallen använder dimensionen Länder."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--stateGeoReport"
>title="Visa det tillstånd (i USA) som folk från webbplatsen har sitt ursprung i. Detta liknar mallen Geo Regions, förutom att den är specifik för USA."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste amerikanska delstatsbesökarna som kommer från de som besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa lägen.<br/>Den här mallen använder dimensionen USA."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--regionGeoReport"
>title="Visa det geografiska område som personer som besöker webbplatsen kommer från. En region är ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. "
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de här regionerna, eller se till att webbplatsupplevelsen är optimal i regioner som har olika primära språk. <br/>Den här mallen använder dimensionerna ID(variabler/geocountry) och Region. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--cityGeoReport"
>title="Se den stad som folk från webbplatsen kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste städer som besökarna kommer från när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa städer. <br/>Den här mallen använder dimensionen Städer"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--dmaGeoReport"
>title="Se vilka områden i USA som besökarna kommer ifrån."
>abstract="**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de mest framgångsrika regionerna. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--languageRankedReport"
>title="Se vilka språk besökarna föredrar att se innehåll på."
>abstract="**Det här kan hjälpa dig** att bättre förstå besökarnas vanligaste språk.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som fokuslokaliseringsaktiviteter eller marknadsföringsaktiviteter för de vanligaste språken.<br/>Den här mallen använder språkdimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-technology-template"
>title="Visa information om den teknik som andra använder för att komma åt webbplatsen, t.ex. operativsystem, webbläsare och enheter."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka tekniker som används oftast när du ansluter till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera webbplatsen för de tekniker som används."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserRankedReport"
>title="Visa namn och version för de webbläsare som användarna använder mest för att komma åt webbplatsen."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder.<br/>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen.<br/>Den här mallen använder webbläsardimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--browserTypeRankedReport"
>title="Visa namnen på de organisationer som har skapat de vanligaste webbläsarna som användarna använder för att komma åt webbplatsen. Detta skiljer sig från webbläsarmallen på så sätt att olika versioner av samma webbläsare inte listas som separata dimensionsobjekt."
>abstract="**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder <br/>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen. <br/>Den här mallen använder dimensionen för webbläsartypen. "

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Första och upprepa besökare**] | Visa en jämförelse av förstagångsbesökare för att upprepa besökare. <p>**Detta kan hjälpa dig** att bättre förstå hur effektiv din webbplats är när det gäller att behålla kundlojaliteten, eller hur ofta du skaffar nya kunder.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att erbjuda incitament för framtida köp till förstagångsbesökare för att locka dem att återvända.</p><!-- This template uses the --> |
| **Person-ID** | Visa enskilda användarbeteenden i olika kanaler.<p>**Detta kan hjälpa dig** att bättre förstå hela kundresan och interaktioner över flera kontaktytor.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att anpassa marknadsföringen för att bättre anpassa användarnas preferenser.</p><!-- This template uses the --> |
| **Geografiska länder** | Se det land som besökarna kommer ifrån.<p>**Det här kan hjälpa dig** att bättre förstå vad de populäraste länderna besökarna kommer från när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i dessa länder, eller se till att webbplatsupplevelsen är optimal i länder som har olika primära språk.</p><p>Den här mallen använder dimensionen Länder. </p> |
| **Geo US-lägen** | Visa det tillstånd (i USA) som folk från webbplatsen har sitt ursprung i. Detta liknar mallen Geo Regions, förutom att den är specifik för USA.<p>**Det här kan hjälpa dig** att bättre förstå de populäraste amerikanska delstatsbesökarna som kommer från de som besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa lägen.</p><p>I den här mallen används dimensionen USA. </p> |
| **Geografiska områden** | Visa det geografiska område som personer som besöker webbplatsen kommer från. En region är ett geografiskt område som är mindre än ett land men större än en stad. I vissa länder är en region en stat, provins eller prefektion. I andra områden är det ett land, en avdelning eller en storstadsregion. <p>**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de här regionerna, eller se till att webbplatsupplevelsen är optimal i regioner som har olika primära språk. </p><p>I den här mallen används dimensionerna ID (variabler/geoland) och Region. </p> |
| **Geografiska städer** | Se den stad som folk från webbplatsen kommer ifrån. <p>**Det här kan hjälpa dig** att bättre förstå de populäraste städer som besökarna kommer från när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel använda data för att fokusera på marknadsföringsaktiviteter i dessa städer. </p><p>Den här mallen använder dimensionen Städer. </p> |
| **Geo US DMA** | Se vilka områden i USA som besökarna kommer ifrån.<p>**Det här kan hjälpa dig** att bättre förstå de populäraste regionerna som besökarna kommer ifrån när de besöker din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att använda data för att fokusera på marknadsföringsaktiviteter i de mest framgångsrika regionerna. </p><!-- This template uses the --> |
| **Språk** | Se vilka språk besökarna föredrar att se innehåll på. <p>**Det här kan hjälpa dig** att bättre förstå besökarnas vanligaste språk.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som fokuslokaliseringsaktiviteter eller marknadsföringsaktiviteter för de vanligaste språken.</p><p>Den här mallen använder dimensionen Språk.</p> |
| **Tekniköversikt** | Visa information om den teknik som används för att komma åt webbplatsen, t.ex. operativsystem, webbläsare och enheter. <p>**Detta kan hjälpa dig** att bättre förstå vilka tekniker som används oftast när du ansluter till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera webbplatsen för de tekniker som används.</p> |
| **Webbläsare** | Visa namn och version för de webbläsare som användarna använder mest för att komma åt webbplatsen.<p>**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen.</p><p>Den här mallen använder dimensionen Webbläsare. </p> |
| **Webbläsartyper** | Visa namnen på de organisationer som har skapat de vanligaste webbläsarna som användarna använder för att komma åt webbplatsen. Detta skiljer sig från webbläsarmallen på så sätt att olika versioner av samma webbläsare inte listas som separata dimensionsobjekt.<p>**Detta kan hjälpa dig** att bättre förstå de vanligaste webbläsarna som besökarna använder</p><p>**Baserat på vad du lär dig kan du** göra flera saker, till exempel förbättra webbplatsens kvalitet genom att testa nya versioner av webbplatsen med de vanligaste webbläsarna. Om du gör det kan du maximera kvalitetskontrollen. </p><p>Den här mallen använder dimensionen för webbläsartyp. </p> |

### Webb: Förvärv {#web-acquisition}

<!--AA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--mobile-app-acquisition-template"
>title="Se hur er webbplats får besökare på mobila enheter."
>abstract="**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.<br/>Den här mallen använder Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--advertisingAnalyticsPaidSearch"
>title="Visa alla dina Google- och Bing betalsökdata sida vid sida."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur mycket trafik som skickas till din webbplats och om kunderna konverterar.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att uppskatta kostnadseffektiviteten för en annonskampanj."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa-template--searchEngineRankRankedReport"
>title="Visa vilken sida av sökresultat en besökare klickade igenom till din webbplats. Om din webbplats till exempel visas på den andra sidan av sökresultatet i en sökmotor är dimensionsobjektet för den här variabeln Söksida 2."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur högt dina sidor rankas i sökresultaten.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att förbättra SEO-strategin för att se till att ditt innehåll visas på den första sidan i sökresultaten."

<!-- markdownlint-enable MD034 -->

<!--Both AA and CJA-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--marketing-channel-overview-template"
>title="När du använder anpassad attribuering visar den här mallen hur besökare kommer till din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka av era marknadsföringskanaler som är mest effektiva.<br/>**Baserat på vad du lär dig kan du** göra många saker, som att investera mer i effektiva marknadsföringskanaler och ta bort från mindre effektiva marknadsföringskanaler.<br/>Den här mallen använder dimensionerna ID(variabler/marketingchannel) och Intäktsmåttet."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelRankedReport"
>title="Visa den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver den inledande trafiken till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.<br/>Den här mallen använder dimensionen Första beröringskanalen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--firstouchChannelDetailRankedReport"
>title="Visa information om den första marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard)."
>abstract="**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.<br/>Den här mallen använder dimensionen Första beröringskanaldetalj."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--campaignConversionReport"
>title="Visa antalet klick och utcheckningar för era kampanjer."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur marknadsföringskampanjer driver konverteringsgraden framåt.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att avgöra vilka marknadsföringskampanjer som genererar mest avkastning."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--retail-campaign-performance-template"
>title="Visa detaljerad information om hur era marknadsföringskampanjer fungerar."
>abstract="**Det här kan hjälpa dig** att bättre förstå olika indikatorer för att lyckas med kampanjer, t.ex. intäkter, produktvisningar, beställningar och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter. <br/>I den här mallen används måtten Intäktssiffror, Produktvyer, Cart Additions, Orders och Units. Den använder även spårningskoddimensionen och referensdomändimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--web-acquisition-template"
>title="Se hur er webbplats får besökare."
>abstract="**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.<br/>Den här mallen använder Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik. <br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.<br/>Den här mallen använder dimensionen Sök nyckelord."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken. <br/>Den här mallen använder dimensionen Söknyckelord - Betald. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalKeywordRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.<br/>Den här mallen använder söknyckelordet - naturlig dimension. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchRankedReport"
>title="Visa sökmotorerna som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik. <br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.<br/>Den här mallen använder dimensionen Sökmotor. "

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchPaidRankedReport"
>title="Visa sökmotorerna som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen. <br/>Den här mallen använder sökmotorn - betaldimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--searchNaturalRankedReport"
>title="Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering."
>abstract="**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.<br/>Den här mallen använder sökmotorn - naturlig dimension."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainRankedReport"
>title="Visa vilka domäner som användare klickar igenom för att nå din webbplats."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som genererar mest trafik till din. (En länk måste finnas på den externa platsen och en besökare måste klicka på den för att dimensionsposten ska kunna visas.)<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande domänerna. <br/>Den här mallen använder dimensionen Refererande domän."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referringDomainOriginalRankedReport"
>title="Visa den första refererande domänen som personer klickat igenom för att nå din webbplats. (När det har angetts innehåller det samma värde för hela besökar-ID:t.)"
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som ursprungligen kör trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande huvuddomänerna. <br/>Den här mallen använder dimensionen Ursprunglig referensdomän."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerRankedReport"
>title="Visa vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. (En länk måste finnas på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.)"
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka specifika URL:er som genererar mest trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de översta URL:erna. <br/>Den här mallen använder dimensionen Refererande domän.</p>"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--referrerTypeRankedReport"
>title="Visa vilka generiska kanaler besökarna klickade igenom för att komma till er webbplats. Adobe behåller reglerna för varje kanal. Möjliga kanaler är sökmotorer, sociala nätverk, andra webbplatser, hårddisk eller e-post."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilken typ av referenter som leder flest trafik till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från en viss kanal.<br/>Den här mallen använder dimensionen Refererartyp."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Marknadskanaler**] > [!UICONTROL **Översiktsrapport för kanaler**] | När du använder anpassad attribuering visar den här mallen hur besökare kommer till din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå vilka av era marknadsföringskanaler som är mest effektiva.</p><p>**Baserat på vad du lär dig kan du** göra många saker, som att investera mer i effektiva marknadsföringskanaler och ta bort från mindre effektiva marknadsföringskanaler.</p><p>Den här mallen använder dimensionerna ID (variabler/marketingchannel) och Intäktsmått.</p> |
| [!UICONTROL **Marknadskanaler**] > [!UICONTROL **Första beröringskanalen**] | Visa den första marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard). <p>**Detta kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver den inledande trafiken till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>I den här mallen används dimensionen Första beröringskanalen.</p> |
| [!UICONTROL **Marknadsföringskanaler**] > [!UICONTROL **Första beröringskanalinformationen**] | Visa information om den första marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard).<p>**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>Den här mallen använder dimensionen Första beröringskanalen Detalj.</p> |
| [!UICONTROL **Marknadskanaler**] > [!UICONTROL **Senaste beröringskanal**] | Visa den senaste marknadsföringskanalen som en besökare matchar under besökarens engagemangsperiod (30 dagar som standard).<p>**Det här kan hjälpa dig** att bättre förstå vilka marknadsföringskanaler som driver trafik till din webbplats som resulterar i konverteringar.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva.</p><p>I den här mallen används dimensionen Sista beröringskanalen.  </p> |
| [!UICONTROL **Marknadskanaler**] > [!UICONTROL **Senaste beröringskanalinformation**] | Visa information om den senaste marknadsföringskanalen som en besökare matchar under besökarens insatsperiod (30 dagar som standard)<p>**Detta kan hjälpa dig** att bättre förstå vad som har bidragit till träffmatchningen i en marknadsföringskanal. Om en besökare till exempel kom till din webbplats och matchade med marknadsföringskanalen Betald sökning kan du använda kanalinformationen för att se vilken sökmotor som användes eller vilket nyckelord de sökte efter.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel fokusera marknadsföringen på områden som är mest effektiva. </p><p>I den här mallen används dimensionen Senaste beröringskanaldetalj. </p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Spårningskod**] | Visa namnen på spårningskoderna på din webbplats. Du kan placera länkar med olika parametervärden för frågesträngar på olika platser på Internet.<p>**Detta kan hjälpa dig** att bättre förstå vilka länkar som var mest framgångsrika när det gäller att köra trafik till din webbplats. Att lägga till spårningskodfrågesträngar är vanligt i e-postmeddelanden, annonser, inlägg i sociala medier och andra marknadsföringsaktiviteter som används i organisationen</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter.</p><p>Den här mallen använder spårningskoddimensionen. </p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Kampanjkonverteringstratt**] | Visa antalet klick och utcheckningar för era kampanjer. <p>**Detta kan hjälpa dig** att bättre förstå hur marknadsföringskampanjer driver konverteringsgraden framåt.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att avgöra vilka marknadsföringskampanjer som genererar mest avkastning.</p> |
| [!UICONTROL **Kampanjer**] > [!UICONTROL **Kampanjprestanda**] | Visa detaljerad information om hur era marknadsföringskampanjer fungerar.<p>**Det här kan hjälpa dig** att bättre förstå olika indikatorer för att lyckas med kampanjer, t.ex. intäkter, produktvisningar, beställningar och så vidare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen på de kampanjer som genererar störst intäkter. </p><p>I den här mallen används måtten Intäkter, Produktvyer, Cart Additions, Orders och Units. Den använder även spårningskoddimensionen och referensdomändimensionen. </p> |
| **Webbförvärv** | Se hur er webbplats får besökare.<p>**Detta kan hjälpa dig** att bättre förstå olika faktorer som leder till förvärv, som söknyckelord, refererande domän och så vidare.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera marknadsföringen till de mest effektiva kanalerna.</p><p>I den här mallen används Studsfrekvens-måttet och Bounces-måttet. Det använder också dimensionen Sökmotor, Nyckelordsdimension för sökning, Siddimension för startsida, Dimensionen Referera till domän, Dimensionen Spårningskod och Referensdimension.  </p> |
| **Sök nyckelord - alla** | Visa söknyckelorden som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt. <p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik. </p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.</p><p>Den här mallen använder dimensionen Sök nyckelord. </p> |
| **Söknyckelord - betald** | Visa söknyckelorden som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken. </p><p>Den här mallen använder dimensionen Söknyckelord - Betald. </p> |
| **Sök efter nyckelord - naturligt** | Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå nyckelord som människor använder i sökningar som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra något av följande, som att identifiera och fylla i SEO-luckor mellan nyckelord som används och de som driver webbplatstrafiken.</p><p>Den här mallen använder dimensionen Sök nyckelord - naturligt. </p> |
| **Sökmotorer - alla** | Visa sökmotorerna som besökarna använder för att nå din webbplats, oavsett om det är betalt eller naturligt. <p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.</p><p>Den här mallen använder dimensionen Sökmotor. </p> |
| **Sökmotorer - betalda** | Visa sökmotorerna som besökarna använder för att nå din webbplats, som matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen. </p><p>I den här mallen används dimensionen Sökmotor - betald. </p> |
| **Sökmotorer - naturliga** | Visa söknyckelorden som besökarna använder för att nå din webbplats, vilket inte matchade betald sökningsidentifiering.<p>**Detta kan hjälpa dig** att bättre förstå de sökmotorer som användarna använder och som resulterar i webbplatstrafik.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att fokusera SEO-arbetet på sökmotorer som genererar flest trafik till webbplatsen.</p><p>Den här mallen använder sökmotorn - naturlig dimension. </p> |
| **Refererande domäner** | Visa vilka domäner som användare klickar igenom för att nå din webbplats.<p>**Detta kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som genererar mest trafik till din. (En länk måste finnas på den externa platsen och en besökare måste klicka på den för att dimensionsposten ska kunna visas.)</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande toppdomänerna. </p><p>Den här mallen använder dimensionen Refererande domän. </p> |
| **Ursprungliga refererande domäner** | Visa den första refererande domänen som personer klickat igenom för att nå din webbplats. (När det har angetts innehåller det samma värde för hela besökar-ID:t.)<p>**Det här kan hjälpa dig** att bättre förstå vilka tredjepartswebbplatser som ursprungligen kör trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de refererande huvuddomänerna. </p><p>Den här mallen använder dimensionen Ursprunglig referensdomän. </p> |
| **Referenter** | Visa vilka URL:er besökarna var på när de klickade igenom för att nå din webbplats. (En länk måste finnas på den externa URL:en och en besökare måste klicka på den för att dimensionsobjektet ska kunna visas.)  <p>**Det här kan hjälpa dig** att bättre förstå vilka specifika URL:er som genererar mest trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från de översta URL:erna. </p><p>Den här mallen använder dimensionen Refererande domän </p><p>I den här mallen används referensdimensionen. </p> |
| **Refererartyper** | Visa vilka generiska kanaler besökarna klickade igenom för att komma till er webbplats. Adobe behåller reglerna för varje kanal. Möjliga kanaler är sökmotorer, sociala nätverk, andra webbplatser, hårddisk eller e-post.<p>**Det här kan hjälpa dig** att bättre förstå vilken typ av referenter som leder flest trafik till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att skapa eller justera innehåll för att bättre anpassa sig till intressena hos besökare som kommer från en viss kanal.</p><p>Den här mallen använder dimensionen Refererartyp.</p> |

### Mobil: Mobilapp {#mobile-app}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappscreens"
>title="Visa antalet händelser, sessioner och personer som är associerade med varje skärm i mobilappen."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka skärmar på din webbplats som är populäraste.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra innehåll på de vanligaste skärmarna."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileappactions"
>title="Visa de åtgärder som andra vidtar i din mobilapp."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur andra använder din app och det värde de får av den.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att utveckla funktioner som kompletterar eller förbättrar dem som är populäraste."

<!-- markdownlint-enable MD034 -->

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-lifecycle-metrics-app-usage-template"
>title="Visa antalet användare, starter och första starter för appen samt den genomsnittliga sessionslängden."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur mycket din app används. <br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra appprestanda så att den kan anpassas till användningsmängden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-journeys"
>title="Visa de framträdande användningsmönstren för din mobilapp."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur andra använder din app. <br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra hur användare kan komma från en skärm till en annan och anpassa sig till de vanligaste arbetsflödena."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-key-metrics"
>title="Visa några av de vanligaste mätvärdena för mobilappar."
>abstract="**Detta kan hjälpa dig** att bättre förstå din mobilapps grundläggande prestanda.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att utvärdera programmets övergripande hälsa och prestanda."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-messaging"
>title="Visa prestandadata för meddelanden i appen och push-meddelanden för appen."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur användare använder meddelandefunktioner i appen samt hur effektivt push-meddelanden genererar trafik till din app.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra push-meddelandefunktionen i appen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-performance-template"
>title="Se hur appen fungerar och var användarna har problem."
>abstract="**Detta kan hjälpa dig** att bättre förstå om användare som använder din app stöter på långsamhet eller försämrade prestanda. <br/>**Baserat på vad du lär dig kan du** göra flera saker, som att åtgärda befintliga problem eller förbättra appprestanda innan problem uppstår."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobile-app-retention"
>title="Se vilka användare som är appens mest lojala kunder och vad de gör i appen."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur dina mest lojala kunder använder din app.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra marknadsföringen för de funktioner som dina mest lojala kunder använder."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Skärmar för mobilappar**] | Visa antalet händelser, sessioner och personer som är associerade med varje skärm i mobilappen.<p>**Det här kan hjälpa dig** att bättre förstå vilka skärmar på din webbplats som är populäraste.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra innehåll på de vanligaste skärmarna.</p><p>I den här mallen används ändringsmåtten Händelser, Sessioner, Personer och Procent. Även sidtitelsdimensionen används.</p> |
| **Åtgärder för mobilappar** | Visa de åtgärder som andra vidtar i din mobilapp. <p>**Det här kan hjälpa dig** att bättre förstå hur andra använder din app och det värde som får av den.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra framkallningsfunktioner som kompletterar eller förbättrar dem som är populäraste.</p><p>I den här mallen används ändringsmåtten Händelser, Sessioner, Personer och Procent. |
| **Användning av mobilappar** | Visa antalet användare, starter och första starter för appen samt den genomsnittliga sessionslängden.<p>**Det här kan hjälpa dig** att bättre förstå hur mycket din app används. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra appprestanda så att den kan anpassas till användningsmängden.</p><!-- This template uses the --> |
| **Mobilappsresor** | Visa de framträdande användningsmönstren för din mobilapp. <p>**Detta kan hjälpa dig** att bättre förstå hur andra använder din app. </p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra hur användare kan komma från en skärm till en annan och anpassa sig till de vanligaste arbetsflödena. </p><!-- This template uses the --> |
| **Mätvärden för mobilappar** | Visa några av de vanligaste mätvärdena för mobilappar. <p>**Detta kan hjälpa dig** att bättre förstå din mobilapps grundläggande prestanda.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att utvärdera programmets övergripande hälsa och prestanda.</p><!-- This template uses the --> |
| **Meddelanden för mobilappar** | Visa prestandadata för meddelanden i appen och push-meddelanden för appen.<p>**Det här kan hjälpa dig** att bättre förstå hur användare använder meddelandefunktioner i appen samt hur effektivt push-meddelanden genererar trafik till din app.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra push-meddelandefunktionen i appen.</p><!-- This template uses the --> |
| **Mobilappsprestanda** | Se hur appen fungerar och var användarna har problem. <p>**Detta kan hjälpa dig** att bättre förstå om användare som använder din app stöter på långsamhet eller försämrade prestanda. </p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att åtgärda befintliga problem eller förbättra appprestanda innan problem uppstår.</p><!-- This template uses the --> |
| **Kvarhållande av mobilappar** | Se vilka användare som är appens mest lojala kunder och vad de gör i appen. <p>**Detta kan hjälpa dig** att bättre förstå hur dina mest lojala kunder använder din app.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att förbättra marknadsföringen för de funktioner som dina mest lojala kunder använder.</p><!-- This template uses the --> |

### Mobil: Information om mobila enheter {#mobile-devices}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileCarrierRankedReport"
>title="Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder dimensionen Mobiloperatör."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceNameRankedReport"
>title="Visa märke och modell för mobila enheter som används för att komma åt din webbplats."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka mobila enheter som är populärast bland dina användare.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera återgivningen av din webbplats för de vanligaste mobila enheterna.<br/>Den här mallen använder dimensionen Mobilenhetsnamn."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileDeviceTypeRankedReport"
>title="Visa de mobila enhetstyper som användare använder för att få tillgång till din webbplats, t.ex. telefoner och surfplattor."
>abstract="**Detta kan hjälpa dig** att bättre förstå de olika typer av mobila enheter som används för att komma åt din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera webbplatsen för de typer av mobila enheter som används mest.<br/>Den här mallen använder dimensionen Mobilenhetstyp."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="template--mobileManufacturerRankedReport"
>title="Se vilka tillverkare som producerar de mobila enheter som användarna använder för att få tillgång till er webbplats, som Apple och Samsung."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka tillverkare som är populärast bland dina användare.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att skräddarsy innehållsleveransen baserat på kapaciteten hos olika tillverkare för att säkerställa en smidig användarupplevelse.<br/>Den här mallen använder Mobile Manufacturer-dimensionen."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Mobiloperatör**] | Visa telekommunikationsföretaget som tillhandahåller mobil nätverksanslutning till de mobila enheterna som användarna använder för att få tillgång till din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka mobiloperatörer som är populärast hos din användarbas.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en mängd saker, som att anpassa innehållsleveransen baserat på nätverkskapaciteten för olika operatörer för att säkerställa en smidig användarupplevelse.</p><p>I den här mallen används mobiloperatörsdimensionen.</p> |
| **Enheter** | Visa märke och modell för mobila enheter som används för att komma åt din webbplats.<p>**Det här kan hjälpa dig** att bättre förstå vilka mobila enheter som är populärast bland dina användare.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera återgivningen av din webbplats för de vanligaste mobila enheterna.</p><p>Den här mallen använder dimensionen Mobilenhetsnamn.</p> |
| **Enhetstyp** | Visa de mobila enhetstyper som användare använder för att få tillgång till din webbplats, t.ex. telefoner och surfplattor.<p>**Detta kan hjälpa dig** att bättre förstå de olika typer av mobila enheter som används för att komma åt din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera webbplatsen för de typer av mobila enheter som används mest.</p><p>Den här mallen använder dimensionen för mobilenhetstyp.</p> |
| **Tillverkare** | Se vilka tillverkare som producerar de mobila enheter som användarna använder för att få tillgång till er webbplats, som Apple och Samsung.<p>**Det här kan hjälpa dig** att bättre förstå vilka tillverkare som är populärast bland dina användare.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att skräddarsy innehållsleveransen baserat på kapaciteten hos olika tillverkare för att säkerställa en smidig användarupplevelse.</p><p>I den här mallen används Mobile Manufacturer-dimensionen.</p> |

### Tidsdelning {#time-parting}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--minuteOfHour"
>title="Visa antalet händelser, sessioner och personer på din webbplats, uppdelat efter minut. Om du t.ex. har en rapport med en rapporttidsram på en dag grupperas den första minuten i varje timme på dagen i samma dimensionsobjekt."
>abstract="**Detta kan hjälpa dig** att förstå trender på detaljnivå.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera resurser för topptider, ända ned till minuten.<br/>Den här mallen använder dimensionen Timme i minuter."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--hourOfDay"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter timme på dagen. Om du t.ex. har en rapport som sträcker sig från 1 januari till 7 januari grupperas den första timmen för varje dag i samma dimensionsobjekt."
>abstract="**Det här kan hjälpa dig** att bättre förstå när webbplatsen besöks mest och minst ofta.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel tilldela mer datorresurser till din webbplats under mycket trafik.<br/>Den här mallen använder dimensionen Timme för dag."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--am-pm"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter AM och PM. Om du till exempel har en rapport som sträcker sig från 1 januari till 7, grupperas AM-timmarna för varje dag i samma dimensionsobjekt."
>abstract="***Det här kan hjälpa dig** att bättre förstå när webbplatsen besöks mest och minst ofta.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel tilldela mer datorresurser till din webbplats under mycket trafik.<br/>Den här mallen använder AM/PM-dimensionen."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfWeek"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter veckodag. Om du till exempel har en rapport som sträcker sig över januari, grupperas varje veckodag i samma dimensionsobjekt."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka veckodagar din webbplats besöker mest och minst ofta.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.<br/>Den här mallen använder dimensionen Dag i veckan."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfMonth"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter dag i månaden. Om du till exempel har en rapport som sträcker sig över ett helt år grupperas varje dag i månaden i samma dimensionsobjekt."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka dagar i varje månad som webbplatsen besöks mest och minst ofta.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.<br/>Den här mallen använder dimensionen Dag i månaden."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--dayOfYear"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter dag på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje dag på året i samma dimensionsobjekt."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka dagar på året som webbplatsen oftast och oftast besöker.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.<br/>Den här mallen använder dimensionen Dag på året."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekdayWeekend"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter veckodagar och helger. Om du till exempel har en rapport som sträcker sig över januari, grupperas veckodagar och helger i separata dimensionsobjekt."
>abstract="**Detta kan hjälpa dig** att bättre förstå skillnaderna i webbplatstrafik för veckodagar jämfört med helger.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att din kundtjänst är mer intensiv på helger, om rapporten visar att helger är mer än vardagar.<br/>Den här mallen använder dimensionen Veckodag/Veckoslut."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--weekOfYear"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter vecka på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje vecka i samma dimensionsobjekt."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka veckor på året som webbplatsen besöks mest och minst ofta.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämplig i telefonen under trafikveckor, till exempel under helgdagar.<br/>Den här mallen använder dimensionen Vecka på året."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--monthOfYear"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter månad på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje månad i samma dimensionsobjekt."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka månader din webbplats är mest frekvent och sällan besökt.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämplig i telefonen för högtrafikmånader, till exempel under helgerna.<br/>Den här mallen använder dimensionen Månad på år."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--quarterOfYear"
>title="Visa händelser, sessioner och personer på din webbplats, uppdelade efter kvartal på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje kvartal i samma dimensionsobjekt."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka delar av webbplatsen som är mest frekvent och sällan besökta.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att starta produkter för att öka antalet historiskt lågtrafikplatser.<br/>Den här mallen använder dimensionen Kvartal på året."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Minut av timmen**] | Visa antalet händelser, sessioner och personer på din webbplats, uppdelat efter minut. Om du t.ex. har en rapport med en rapporttidsram på en dag grupperas den första minuten i varje timme på dagen i samma dimensionsobjekt.<p>**Detta kan hjälpa dig** att förstå trender på detaljnivå.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att optimera resurser för topptider, ända ned till minuten.</p><p>I den här mallen används dimensionen Minut för timme.</p> |
| **Timme på dagen** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter timme på dagen. Om du t.ex. har en rapport som sträcker sig från 1 januari till 7 januari grupperas den första timmen för varje dag i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå när webbplatsen besöks mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel tilldela mer datorresurser till din webbplats under mycket trafik.</p><p>Den här mallen använder dimensionen Timme för dag.</p> |
| **AM/PM** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter AM och PM. Om du till exempel har en rapport som sträcker sig från 1 januari till 7, grupperas AM-timmarna för varje dag i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå när webbplatsen besöks mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, till exempel tilldela mer datorresurser till din webbplats under mycket trafik.</p><p>Den här mallen använder AM/PM-dimensionen.</p> |
| **Veckodag** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter veckodag. Om du till exempel har en rapport som sträcker sig över januari, grupperas varje veckodag i samma dimensionsobjekt. <p>**Det här kan hjälpa dig** att bättre förstå vilka veckodagar din webbplats besöker mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.</p><p>Den här mallen använder dimensionen Dag i vecka.</p> |
| **Dag i månaden** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter dag i månaden. Om du till exempel har en rapport som sträcker sig över ett helt år grupperas varje dag i månaden i samma dimensionsobjekt. <p>**Det här kan hjälpa dig** att bättre förstå vilka dagar i varje månad som webbplatsen besöks mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.</p><p>Den här mallen använder dimensionen Dag i månaden.</p> |
| **Dag på året** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter dag på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje dag på året i samma dimensionsobjekt. <p>**Det här kan hjälpa dig** att bättre förstå vilka dagar på året som webbplatsen oftast och oftast besöker.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämpad för telefonsamtalscentret under dagar med hög trafik.</p><p>Den här mallen använder dimensionen Dag på år.&lt;/> |
| **Veckodag/Veckoslut** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter veckodagar och helger. Om du till exempel har en rapport som sträcker sig över januari, grupperas veckodagar och helger i separata dimensionsobjekt. <p>**Detta kan hjälpa dig** att bättre förstå skillnaderna i webbplatstrafik för veckodagar jämfört med helger.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att din kundtjänst är mer intensiv på helger, om rapporten visar att helger är mer än vardagar.</p><p>Den här mallen använder dimensionen Veckodag/Veckoslut.</p> |
| **Vecka på året** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter vecka på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje vecka i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå vilka veckor på året som webbplatsen besöks mest och minst ofta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämplig i telefonen under trafikveckor, till exempel under helgdagar.</p><p>Den här mallen använder dimensionen Vecka på året.</p> |
| **Månad på året** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter månad på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje månad i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå vilka månader din webbplats är mest frekvent och sällan besökt.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som personal som är mer lämplig i telefonen för högtrafikmånader, till exempel under helgerna.</p><p>Den här mallen använder dimensionen Månad på år.</p> |
| **Kvartal på året** | Visa händelser, sessioner och personer på din webbplats, uppdelade efter kvartal på året. Om du till exempel har en rapport som sträcker sig över flera år grupperas varje kvartal i samma dimensionsobjekt.<p>**Det här kan hjälpa dig** att bättre förstå vilka delar av webbplatsen som är mest frekvent och sällan besökta.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att starta produkter för att öka antalet historiskt lågtrafikplatser.</p><p>Den här mallen använder dimensionen Kvartal på året.</p> |

### Kanalövergripande {#cross-channel}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--multiChannelOverview"
>title="Se hur trafiken distribueras över flera kanaler."
>abstract="**Detta kan hjälpa dig** att bättre förstå vilka kanaler som är mest framgångsrika när det gäller trafik och engagemang. <br/>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel fokusera marknadsföringen på de kanaler som ger störst avkastning på investeringen.<br/>Den här mallen använder användar-, sessions- och händelsemått."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--callCenterDeflection"
>title="Se hur webbtrafiken påverkar trafiken i callcenter."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur självbetjäningsinnehållet på din webbplats avspeglar trafiken till ditt callcenter.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, till exempel förbättra självbetjäningsinnehållet för att minska trafiken till ditt call center, eller mäta avkastningen på ditt självbetjäningsinnehåll genom att beräkna hur mycket som sparats via färre supportsamtal.<br/>Den här mallen använder mått för webbsessioner, mobilappssessioner och flerkanalssessioner för Web+App."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--webAppTemplate"
>title="Visa webbtrafik och mobiltrafik tillsammans."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur webb- och mobiltrafiken distribueras till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra flera saker, som att avsätta mer resurser till din mobilappsupplevelse när den når en viss trafiknivå.<br/>Den här mallen använder mått för webbsessioner, mobilappssessioner och flerkanalssessioner för Web+App."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--onlineOffline"
>title="Visa trafik online och offline tillsammans."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur online- och offlinetrafik distribueras till din webbplats.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att avsätta mer resurser till din onlineupplevelse när den når en viss trafiknivå."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Översikt över flera kanaler**] | Se hur trafiken distribueras över flera kanaler. <p>**Detta kan hjälpa dig** att bättre förstå vilka kanaler som är mest framgångsrika när det gäller trafik och engagemang. </p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av det du vill, till exempel fokusera marknadsföringen på de kanaler som ger störst avkastning på investeringen.</p><p>I den här mallen används användar-, sessions- och händelsemätningar.</p> |
| **Webb+App** | Visa webbtrafik och mobiltrafik tillsammans.<p>**Detta kan hjälpa dig** att bättre förstå hur webb- och mobiltrafiken distribueras till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att avsätta mer resurser till din mobilappsupplevelse när den når en viss trafiknivå.</p><p>I den här mallen används mått för webbsessioner, mobilappssessioner och flerkanalssessioner för Web+App.</p> |
| **Online/Offline** | Visa trafik online och offline tillsammans.<p>**Detta kan hjälpa dig** att bättre förstå hur online- och offlinetrafik distribueras till din webbplats.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att avsätta mer resurser till din onlineupplevelse när den når en viss trafiknivå.</p><!-- This template uses the ... --> |
| **Avböjning av samtalscenter** | Se hur webbtrafiken påverkar trafiken i callcenter.<p>**Detta kan hjälpa dig** att bättre förstå hur självbetjäningsinnehållet på din webbplats avspeglar trafiken till ditt callcenter.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, till exempel förbättra självbetjäningsinnehållet för att minska trafiken till ditt call center, eller mäta avkastningen på ditt självbetjäningsinnehåll genom att beräkna hur mycket som sparats via färre supportsamtal.</p><p>I den här mallen används mått för webbsessioner, mobilappssessioner och flerkanalssessioner för Web+App.</p> |

### Andra kanaler {#other-channels}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--callcenterdashboard"
>title="Visa kundtjänstdata, inklusive varför kunderna ringde och antalet gånger."
>abstract="**Det här kan hjälpa dig** att bättre förstå var kunderna har problem och var resurser från callcenter spenderas.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att åtgärda produktproblem som genererar högre kundtjänsttrafik, vilket i slutänden förbättrar produktlönsamheten."

>[!CONTEXTUALHELP]
>id="cja-template--pointOfSale"
>title="Visa transaktionsdata (POS), inklusive intjänade intäkter, utförda order och sålda enheter. Den här mallen innehåller även visualiseringar som visar information om de främsta butikerna, de viktigaste produkterna och de viktigaste produktkategorierna samt online- och offlineförsäljning."
>abstract="**Det här kan hjälpa dig** att bättre förstå vilka produkter som är era mest säljande produkter på olika butiksplatser och online.<br/>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela fler marknadsföringsresurser till produkter och kanaler med höga prestanda."

>[!CONTEXTUALHELP]
>id="cja-template--ajo-email"
>title="Se hur de e-postmeddelanden du utformar och skickar med Adobe Journey Optimizer genererar nya medlemskap, lojalitetsmedlemmar och korsförsäljningsmöjligheter."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur effektiva e-postmeddelanden är som du utformar och skickar med Adobe Journey Optimizer.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att justera din e-poststrategi för en viss e-postkampanj."

>[!CONTEXTUALHELP]
>id="cja-template--survey"
>title="Visa användarengagemang för era undersökningar. Se antalet starter och slutföranden, de vanligaste frågorna och svaren samt antalet första kontra upprepade deltagare."
>abstract="**Det här kan hjälpa dig** att bättre förstå engagemangsnivåerna och frekvensen av lyckade enkäter.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera framtida undersökningar för att ge bättre deltagande."

>[!CONTEXTUALHELP]
>id="cja-template--product-usage"
>title="Se hur er organisation använder Customer Journey Analytics."
>abstract="**Det här kan hjälpa dig** att bättre förstå hur många personer i organisationen som använder Customer Journey Analytics, hur ofta de använder det och att trender över tiden. Du kan även se antalet projekt som skapats och detaljer om dessa projekt. Se vilka komponenter, visualiseringar och paneler som används oftast, bland annat användningsstatistik.<br/>**Baserat på vad du lär dig kan du** göra flera saker, t.ex. ta bort oanvända projekt eller komponenter, eller tillhandahålla användarutbildning för populära funktioner."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Kontrollpanel för samtalscenter**] | Visa kundtjänstdata, inklusive varför kunderna ringde och antalet gånger. <p>**Det här kan hjälpa dig** att bättre förstå var kunderna har problem och var resurser från callcenter spenderas.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att åtgärda produktproblem som genererar högre kundtjänsttrafik, vilket i slutänden förbättrar produktlönsamheten.</p> |
| **Försäljningsställe** | Visa transaktionsdata (POS), inklusive intjänade intäkter, utförda order och sålda enheter. Den här mallen innehåller även visualiseringar som visar information om de främsta butikerna, de viktigaste produkterna och de viktigaste produktkategorierna samt online- och offlineförsäljning. <p>**Det här kan hjälpa dig** att bättre förstå vilka produkter som är era mest säljande produkter på olika butiksplatser och online.</p><p>**Baserat på vad du lär dig kan du** göra ett antal saker, som att tilldela fler marknadsföringsresurser till produkter och kanaler med höga prestanda.</p><p>I den här mallen används måtten för användare, intäkter och order.</p> |
| **Journey Optimizer e-postanalys** | Se hur de e-postmeddelanden du utformar och skickar med Adobe Journey Optimizer genererar nya medlemskap, lojalitetsmedlemmar och korsförsäljningsmöjligheter. <p>**Detta kan hjälpa dig** att bättre förstå hur effektiva e-postmeddelanden är som du utformar och skickar med Adobe Journey Optimizer.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av en rad saker, som att justera din e-poststrategi för en viss e-postkampanj.</p> |
| **Undersökning** | Visa användarengagemang för era undersökningar. Se antalet starter och slutföranden, de vanligaste frågorna och svaren samt antalet första kontra upprepade deltagare.<p>**Det här kan hjälpa dig** att bättre förstå engagemangsnivåerna och frekvensen av lyckade enkäter.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera framtida undersökningar för att ge bättre deltagande.</p><p>I den här mallen används värdena för användare, händelser, undersökningar, slutförda undersökningar och antalet slutförda enkäter.</p> |
| **Översikt över produktanvändning** | Se hur er organisation använder Customer Journey Analytics.<p>**Det här kan hjälpa dig** att bättre förstå hur många personer i organisationen som använder Customer Journey Analytics, hur ofta de använder det och att trender över tiden. Du kan även se antalet projekt som skapats och detaljer om dessa projekt. Se vilka komponenter, visualiseringar och paneler som används oftast, bland annat användningsstatistik.</p><p>**Baserat på vad du lär dig kan du** göra flera saker, t.ex. ta bort oanvända projekt eller komponenter, eller tillhandahålla användarutbildning för populära funktioner.</p> |

### Journey Optimizer {#AJO-templates}

<!--CJA only-->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-campaign"
>title="Se viktiga mätvärden för era Journey Optimizer-kampanjer, inklusive e-postkampanjer, experiment, i appen, SMS med mera."
>abstract="**Detta kan hjälpa dig** att bättre förstå detaljer som antalet klick och antalet levererade meddelanden, vilket ger en heltäckande insikt i kampanjens effektivitet och engagemangsnivå.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera dina kampanjer baserat på målpublikens engagemangsnivåer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-journey"
>title="Se viktiga mätvärden för era Journey Optimizer-resor, inklusive e-postresor, experimenterande, i appen, SMS med mera."
>abstract="**Detta kan hjälpa dig** att bättre förstå detaljer som antalet klick och antalet levererade meddelanden, vilket ger en heltäckande insikt i hur effektiv din resa är och hur hög engagemanget är.<br/>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera dina kampanjer baserat på målpublikens engagemangsnivåer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-landing-page"
>title="Visa användarbeteende, engagemangsmönster, konverteringsgrader och andra viktiga mätvärden."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur effektiv din landningssida är. <br/>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera prestanda för landningssidor."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-channel"
>title="Se en detaljerad sammanfattning av trafik- och engagemangsmätningar för alla kampanjer och resor i er miljö."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur effektiva era kampanjer och resor är på hög nivå. <br/>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera kampanjer och resor baserat på målpublikens engagemangsnivåer."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-template--ajo-subscription"
>title="Visa profilernas prenumerationer och avbeställningar som är kopplade till särskilda listor."
>abstract="**Detta kan hjälpa dig** att bättre förstå hur effektiva olika prenumerationskampanjer och -initiativ är när det gäller att öka engagemanget och konverteringarna.<br/>**Baserat på vad du lär dig kan du** göra något annat, som att justera dina prenumerationskampanjer baserat på målpublikens engagemangsnivåer."

<!-- markdownlint-enable MD034 -->

Följande mallar är tillgängliga:

| Mallnamn | Varför använda den här mallen <!-- What do you do with it? What can it help you learn? and What are the potential actions? -->? |
| --- | --- | 
| [!UICONTROL **Journey Optimizer-kampanjer**] | Se viktiga mätvärden för era Journey Optimizer-kampanjer, inklusive e-postkampanjer, experiment, i appen, SMS med mera.<p>**Detta kan hjälpa dig** att bättre förstå detaljer som antalet klick och antalet levererade meddelanden, vilket ger en heltäckande insikt i kampanjens effektivitet och engagemangsnivå.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera dina kampanjer baserat på målpublikens engagemangsnivåer.</p> |
| **Journey Optimizer-resor** | Se viktiga mätvärden för era Journey Optimizer-resor, inklusive e-postresor, experimenterande, i appen, SMS med mera.<p>**Detta kan hjälpa dig** att bättre förstå detaljer som antalet klick och antalet levererade meddelanden, vilket ger en heltäckande insikt i hur effektiv din resa är och hur hög engagemanget är.</p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera dina kampanjer baserat på målpublikens engagemangsnivåer.</p> |
| **Journey Optimizer landningssidor** | Visa användarbeteende, engagemangsmönster, konverteringsgrader och andra viktiga mätvärden.<p>**Detta kan hjälpa dig** att bättre förstå hur effektiv din landningssida är. </p><p>**Baserat på vad du lär dig kan du** göra flera saker, som att optimera prestanda för landningssidor.</p> |
| **Journey Optimizer - översiktsrapport** | Se en detaljerad sammanfattning av trafik- och engagemangsmätningar för alla kampanjer och resor i er miljö.<p>**Detta kan hjälpa dig** att bättre förstå hur effektiva era kampanjer och resor är på hög nivå. </p><p>**Baserat på vad du lär dig kan du** göra vilket som helst av något som helst, som att justera kampanjer och resor baserat på målpublikens engagemangsnivåer.</p> |
| **Journey Optimizer-prenumerationer** | Visa profilernas prenumerationer och avbeställningar som är kopplade till särskilda listor.<p>**Detta kan hjälpa dig** att bättre förstå hur effektiva olika prenumerationskampanjer och -initiativ är när det gäller att öka engagemanget och konverteringarna.</p><p>**Baserat på vad du lär dig kan du** göra något annat, som att justera dina prenumerationskampanjer baserat på målpublikens engagemangsnivåer.</p> |
