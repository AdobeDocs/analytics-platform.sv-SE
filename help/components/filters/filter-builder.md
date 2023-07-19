---
description: I filterverktyget finns en arbetsyta där du kan dra och släppa metriska Dimensioner, filter och händelser för att filtrera personer baserat på behållarhierarkiens logik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla eller komplexa filter som identifierar personattribut och åtgärder för besök och händelser.
title: Skapa filter
feature: Filters
exl-id: 2107f301-4137-4e97-9aa7-07824b842e16
source-git-commit: d045ecf73f7e15940510b764814fb853222e88cc
workflow-type: tm+mt
source-wordcount: '1295'
ht-degree: 1%

---

# Filter Builder

The [!UICONTROL Filter builder] Med kan du skapa enkla eller komplexa filter som identifierar personattribut och åtgärder för besök och händelser. Den innehåller en arbetsyta för att dra och släppa mått, händelser eller andra filter för att filtrera personer baserat på hierarkilogik, regler och operatorer.

Mer information om hur du skapar snabbfilter som bara gäller för det projekt där de skapas finns i [Snabbfilter](/help/components/filters/quick-filters.md).

## Öppna filterverktyget

Du kommer åt filterverktyget på något av följande sätt:

* **Övre navigering**: Klicka **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]**.
* **[!UICONTROL Analysis Workspace]**: Med ett projekt öppet i Analysis Workspace väljer du **[!UICONTROL + Components]** > **[!UICONTROL Create filter]**.
* **[!UICONTROL Report Builder]**: [Arbeta med filter i Report Builder](/help/report-builder/work-with-filters.md).

## Översikt över Builder-kriterier {#section_F61C4268A5974C788629399ADE1E6E7C}

Du kan lägga till regeldefinitioner och behållare för att definiera filter. (Information om hur du använder filterverktyget finns i [Öppna filterverktyget](#access-the-filter-builder).)

![](assets/segment_builder_ui_2.png)

1. **[!UICONTROL Title]**: Ge filtret ett namn.
1. **[!UICONTROL Description]**: Ange en beskrivning för filtret.
1. **[!UICONTROL Tags]**: [Tagga filtret](/help/components/filters/manage-filters.md) du skapar genom att välja från en lista med befintliga taggar eller skapa en ny tagg.
1. **[!UICONTROL Definitions]**: Här är du [skapa och konfigurera filter](/help/components/filters/filters-overview.md), lägger till regler och kapslar in och sekvensbehållare.
1. **[!UICONTROL Show]**: (Översta behållarväljare.) Välj den översta nivån [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Session], [!UICONTROL Event]). Standardbehållaren på den översta nivån är händelsebehållaren.
1. **[!UICONTROL Options]**: (kugghjulsikon)

   * **[!UICONTROL + Add container]**: Gör att du kan lägga till en ny behållare (under behållaren på den översta nivån) till filterdefinitionen.
   * **[!UICONTROL Exclude]**: Gör att du kan definiera filtret genom att utesluta en eller flera dimensioner, filter eller mått.

1. **[!UICONTROL Dimensions]**: Komponenter dras och tas bort från listan Dimensioner (orange sidofält).
1. **[!UICONTROL Operator]**: Du kan jämföra och begränsa värden med valda operatorer.
1. **[!UICONTROL Value]**: Värdet som du angav eller valde för dimensionen, filtret eller mätvärdet.
1. **[!UICONTROL Attribution Models]**: Dessa modeller är bara tillgängliga för dimensioner och avgör vilka värden i en dimension som ska filtreras efter. Dimensioner är särskilt användbara i sekventiella filter.

   * **[!UICONTROL Repeating]** (standard): Inkluderar instanser och beständiga värden för dimensionen.
   * **[!UICONTROL Instance]**: Inkluderar instanser för dimensionen.
   * **[!UICONTROL Non-repeating instance]**: Inkluderar unika instanser (icke-upprepande) för dimensionen. Detta är den modell som används i Flow när upprepade instanser utesluts.

   ![](assets/attribution-models.jpg)

   **Exempel: Händelsefilter där eVar1 = A**

   | Exempel | A | A | A (beständig) | B | A | C |
   |---|---|---|---|---|---|---|
   | Upprepande | X | X | X | - | X | - |
   | Instance | X | X | - | - | X | - |
   | Icke upprepande instans | X | - | - | - | X | - |
1. **[!UICONTROL And/Or/Then]**: Tilldelar [!UICONTROL AND/OR/THEN] mellan behållare eller regler. Operatorn THEN gör att du kan [definiera sekventiella filter](/help/components/filters/filters-overview.md).
1. **[!UICONTROL Metric]**: (Grönt sidofält) Mätvärden som har dragits och tagits bort från listan Metrisk.
1. **[!UICONTROL Comparison]** operator: Du kan jämföra och begränsa värden med valda operatorer.
1. **[!UICONTROL Value]**: Värdet som du angav eller valde för dimensionen, filtret eller mätvärdet.
1. **[!UICONTROL X]**: (Ta bort) Du kan ta bort den här delen av filterdefinitionen.
1. **[!UICONTROL Experience Cloud publishing]**: Genom att publicera ett Adobe Analytics-filter på Experience Cloud kan du använda filtret för marknadsföringsaktiviteter i [!DNL Audience Manager] och i andra aktiveringskanaler. [Läs mer …](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html)
1. **[!UICONTROL Audience library]**: Adobe hanterar översättning av persondata till målgruppsfilter. Att skapa och hantera målgrupper liknar alltså att skapa och använda filter, med möjlighet att dela målgruppsfiltret med Experience Cloud. [Läs mer …](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html)
1. **[!UICONTROL Search]**: Söker igenom listan med dimensioner, filter eller mätvärden.
1. **[!UICONTROL Dimensions]**: (Lista) Klicka på rubriken för att expandera.
1. **[!UICONTROL Metrics]**: Klicka på rubriken för att expandera.
1. **[!UICONTROL Filters]**: Klicka på rubriken för att expandera.
1. **[!UICONTROL Data View selector]**: Gör att du kan välja den rapportserie som det här filtret ska sparas under. Du kan fortfarande använda filtret i alla datavyer.
1. **[!UICONTROL Filter Preview]**: Här kan du förhandsgranska nyckelmåtten för att se om du har ett giltigt filter och hur brett filtret är. Representerar den uppdelning av datauppsättningen som du kan förvänta dig att se om du använder det här filtret. Visar 3 koncentriska cirklar och en lista som visar antalet och procentandelen matchningar för [!UICONTROL Event], [!UICONTROL Person]och [!UICONTROL Session] för ett filter som körs mot en datauppsättning. Diagrammet uppdateras omedelbart när du har skapat eller ändrat filterdefinitionen.
1. **[!UICONTROL Product Compatibility]**: En lista över vilka Adobe Analytics-produkter (Analysis Workspace, [!UICONTROL Reports & Analytics], Data warehouse) som det skapade filtret är kompatibelt med. De flesta filter är kompatibla med alla produkter. Alla operatorer och dimensioner är dock inte kompatibla med alla Analytics-produkter, särskilt [data warehouse](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-compatibility.html). Diagrammet uppdateras omedelbart efter att du har ändrat filterdefinitionen.
1. **[!UICONTROL Save]** eller **[!UICONTROL Cancel]**: Sparar eller avbryter filtret. Efter klickning **[!UICONTROL Save]** kommer du till Filterhanteraren där du kan hantera filtret.

Filter med inbäddade datumintervall fungerar fortfarande annorlunda i Analysis Workspace jämfört med [!UICONTROL Reports & Analytics]: I Arbetsyta åsidosätter ett filter med ett inbäddat datumintervall panelens datumintervall. I motsats till [!UICONTROL Reports & Analytics] ger dig skärningspunkten för rapportens datumintervall och filtrets inbäddade datumintervall.

## Skapa ett filter {#build-filters}

1. Dra bara en Dimension, ett filter eller en metrisk händelse från den vänstra rutan till den [!UICONTROL Definitions] fält.

   ![](assets/drag_n_drop_dimension.png)

1. Ange [operator](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html) i listrutan.
1. Ange eller välj ett värde för det markerade objektet.
1. Lägg till ytterligare behållare om det behövs, med **[!UICONTROL And]**, **[!UICONTROL Or]**, eller **[!UICONTROL Then]** regler.
1. När du har placerat behållarna och angett reglerna ser du resultatet av filtret i valideringsdiagrammet längst upp till höger. Valideraren anger det procentuella och absoluta antalet sidvisningar, besök och unika personer som matchar filtret som du skapade.
1. Under **[!UICONTROL Tags]**, [tag](/help/components/filters/manage-filters.md) behållaren genom att markera en befintlig tagg eller skapa en ny.
1. Klicka **[!UICONTROL Save]** för att spara filtret.

   Du kommer till [Filterhanteraren](/help/components/filters/manage-filters.md), där du kan tagga, dela och hantera filtret på flera sätt.

## Lägg till behållare {#section_1C38F15703B44474B0718CEF06639EFD}

Du kan [skapa ett ramverk med behållare](/help/components/filters/filters-overview.md) och sedan placera logiska regler och operatorer mellan.

1. Klicka på **[!UICONTROL Options > Add container]**.

   En ny [!UICONTROL **Händelse**] behållaren öppnas utan [!UICONTROL **Händelse**] (Sidvy) identifierad.

   ![](assets/new_container.png)

1. Ändra behållartypen efter behov.
1. Dra en Dimension, ett filter eller en händelse från den vänstra rutan till behållaren.
1. Fortsätt lägga till nya behållare på den översta nivån **[!UICONTROL Options]** > **[!UICONTROL Add container]** längst upp i definitionen eller lägg till behållare från en behållare till kapslingslogik.

   **ELLER**

   Markera en eller flera regler och klicka sedan på **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. Detta gör om markeringen till en separat behållare.

## Använd datumintervall {#concept_252A83D43B6F4A4EBAB55F08AB2A1ACE}

Du kan skapa filter som innehåller rullande datumintervall för att få svar på frågor om pågående kampanjer eller evenemang.

Du kan till exempel enkelt skapa ett filter som innehåller&quot;alla som har köpt något de senaste 60 dagarna&quot;.

Du skapar en sessionsbehållare och i den lägger du till [!UICONTROL Last 60 days] tidsintervall och mått [!UICONTROL Orders is greater than or equal to 1], med operatorn AND.

Här är en video om hur du använder rullande datumintervall i filter:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Staplingsfilter {#task_58140F17FFD64FF1BC30DC7B0A1B0E6D}

Du kan använda staplingsfilter genom att kombinera villkoren i varje filter med en &#39;and&#39;-operator och sedan använda de kombinerade villkoren. Detta kan du göra i ett Workspace-projekt direkt eller i Filter Builder.

Om du till exempel staplar ett&quot;mobiltelefonanvändarfilter&quot; och ett&quot;USA-geografifilter&quot; returneras data endast för mobiltelefonanvändare i USA.

Tänk på dessa filter som byggstenar eller moduler som du kan inkludera i ett filterbibliotek, så att användarna kan använda dem som de vill. På så sätt kan du dramatiskt minska antalet filter. Anta till exempel att du har 40 filter:

* 20 för mobilanvändare i olika länder (US_mobile, Germany_mobile, France_mobile, Brazil_mobile, osv.)
* 20 för surfplatteanvändare i olika länder (US_tablet, Germany_tablet, France_tablet, Brazil_tablet, osv.)

Genom att använda filterstackning kan du minska antalet filter till 22 och stapla dem efter behov. Du måste skapa följande filter:

* ett filter för mobilanvändare
* ett filter för surfplattor
* 20 filter för olika geografiska områden

>[!NOTE]
>
>När du staplar två filter förenas de som standard med en AND-programsats. Detta kan inte ändras till en OR-sats.

1. Gå till Filterverktyget.

1. Ange en titel och en beskrivning för filtret.

1. Klicka **[!UICONTROL Show filters]** för att visa en lista med filter i den vänstra navigeringen.

1. Dra de filter som du vill stapla till filterdefinitionsytan.

1. Välj [!UICONTROL **Spara**].

