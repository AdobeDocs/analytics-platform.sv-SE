---
description: I filterverktyget finns en arbetsyta där du kan dra och släppa metriska Dimensioner, filter och händelser för att filtrera personer baserat på behållarhierarkiens logik, regler och operatorer. Med det här integrerade utvecklingsverktyget kan du skapa och spara enkla eller komplexa filter som identifierar personattribut och åtgärder för besök och händelser.
title: Skapa filter
feature: Filters
role: User
source-git-commit: c19309488e0a541b522ca6925c7ca2bdb90f2390
workflow-type: tm+mt
source-wordcount: '1161'
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

![Filterverktyget visar nya filteralternativ som beskrivs i det här avsnittet.](assets/segment_builder_ui_2.png)

| UI-element | Beskrivning |
| --- | --- |
| **[!UICONTROL Title]** | Namnge filtret |
| **[!UICONTROL Description]** | Ange en detaljerad beskrivning av filtret. |
| **[!UICONTROL Tags]** | [Tagga filtret](/help/components/filters/manage-filters.md) du skapar genom att välja från en lista med befintliga taggar eller skapa en ny tagg. |
| **[!UICONTROL Definitions]** | Här är du [skapa och konfigurera filter](/help/components/filters/filters-overview.md), lägger till regler och kapslar in och sekvensbehållare. |
| **[!UICONTROL Include]** | (Översta behållarväljare.) Välj den översta nivån [container](/help/components/filters/filters-overview.md) ( [!UICONTROL Person], [!UICONTROL Session], [!UICONTROL Event]). Standardbehållaren på den översta nivån är händelsebehållaren. |
| **[!UICONTROL Options]** | (kugghjulsikon) | <ul><li>**[!UICONTROL + Add container]**: Gör att du kan lägga till en ny behållare (under behållaren på den översta nivån) i filterdefinitionen.</li><li>**[!UICONTROL Exclude]**: Du kan definiera filtret genom att utesluta en eller flera dimensioner, filter eller mått.</li></ul> |
| **[!UICONTROL Dimensions]** | Komponenter dras och tas bort från listan Dimensioner (orange sidofält). |
| **[!UICONTROL Operator]** | Du kan jämföra och begränsa värden med valda operatorer. (är lika med, är inte lika, innehåller, innehåller alla, osv.) |
| **[!UICONTROL Value]** | Värdet som du angav eller valde för dimensionen, filtret eller mätvärdet. |
| **[!UICONTROL Attribution Models]** | Dessa modeller är bara tillgängliga för dimensioner och avgör vilka värden i en dimension som ska filtreras efter. Dimensioner är särskilt användbara i sekventiella filter.<ul><li>**[!UICONTROL Repeating]** (standard): Inkluderar instanser och beständiga värden för dimensionen.</li><li>**[!UICONTROL Instance]**: Inkluderar instanser för dimensionen.</li><li>**[!UICONTROL Non-repeating instance]**: Inkluderar unika instanser (icke-upprepande) för dimensionen. Detta är den modell som används i Flow när upprepade instanser utesluts.</li></ul>Se till exempel avsnittet Attribution models nedan. |
| **[!UICONTROL And/Or/Then]** | Tilldelar [!UICONTROL AND/OR/THEN] mellan behållare eller regler. Operatorn THEN låter dig [definiera sekventiella filter](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Metric]** | (Grönt sidofält) Mätvärden som har dragits och tagits bort från listan Metrisk. |
| **[!UICONTROL X]** | (Ta bort) Du kan ta bort den här delen av filterdefinitionen. |
| **[!UICONTROL Create audience from filter]** | Genom att skapa en målgrupp från ett filter kan du dela filtret med Adobe Experience Platform för aktivering. [Läs mer …](/help/components/audiences/audiences-overview.md) |
| **[!UICONTROL Search component]** | Söker igenom listan med dimensioner, filter eller mätvärden. |
| **[!UICONTROL Dimensions]** | (Lista) Listan med dimensioner som du kan inkludera i filtret. Klicka på rubriken för att expandera. |
| **[!UICONTROL Metrics]** | Listan med mätvärden som du kan inkludera i filtret. Klicka på rubriken för att expandera. |
| **[!UICONTROL Filters]** | Listan med befintliga filter som du kan ta med i filtret. Klicka på rubriken för att expandera. |
| **[!UICONTROL Data View selector]** | Gör att du kan välja den rapportserie som det här filtret ska sparas under. Du kan fortfarande använda filtret i alla datavyer. |
| **[!UICONTROL Filter Preview]** | Här kan du förhandsgranska nyckelmåtten för att se om du har ett giltigt filter och hur brett filtret är. Representerar den uppdelning av datauppsättningen som du kan förvänta dig att se om du använder det här filtret. Visar 3 koncentriska cirklar och en lista som visar antalet och procentandelen matchningar för [!UICONTROL People], [!UICONTROL Sessions]och [!UICONTROL Reports Run] för ett filter som körs mot en datauppsättning.<p>Diagrammet uppdateras omedelbart när du har skapat eller ändrat filterdefinitionen. |
| **[!UICONTROL Save]** eller **[!UICONTROL Cancel]** | Sparar eller avbryter filtret. Efter klickning **[!UICONTROL Save]** kommer du till Filterhanteraren där du kan hantera filtret. |

## Skapa ett filter {#build-filters}

1. Dra bara en Dimension, ett filter eller en metrisk händelse från den vänstra rutan till den [!UICONTROL Definitions] fält.

   ![](assets/drag_n_drop_dimension.png)

1. Ange [operator](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-operators.html) i listrutan.
1. Ange eller välj ett värde för det markerade objektet.
1. Lägg till ytterligare behållare om det behövs, med **[!UICONTROL And]**, **[!UICONTROL Or]**, eller **[!UICONTROL Then]** regler.
1. När du har placerat behållarna och angett reglerna ser du resultatet av filtret i valideringsdiagrammet längst upp till höger. Valideraren anger det procentuella och absoluta antalet sidvisningar, besök och unika personer som matchar filtret som du skapade.
1. Under **[!UICONTROL Tags]**, [tag](/help/components/filters/filters-tag.md) behållaren genom att markera en befintlig tagg eller skapa en ny.
1. Klicka **[!UICONTROL Save]** för att spara filtret.

   Du kommer till [Filterhantering](/help/components/filters/manage-filters.md), där du kan tagga, dela och hantera filtret på flera sätt.

## Lägg till behållare {#containers}

Du kan [skapa ett ramverk med behållare](/help/components/filters/filters-overview.md) och sedan placera logiska regler och operatorer mellan.

1. Klicka på **[!UICONTROL Options > Add container]**.

   En ny [!UICONTROL **Händelse**] behållaren öppnas utan [!UICONTROL **Händelse**] (Sidvy) identifierad.

   ![](assets/new_container.png)

1. Ändra behållartypen efter behov.
1. Dra en Dimension, ett filter eller en händelse från den vänstra rutan till behållaren.
1. Fortsätt lägga till nya behållare på den översta nivån **[!UICONTROL Options]** > **[!UICONTROL Add container]** längst upp i definitionen eller lägg till behållare från en behållare till kapslingslogik.

   **ELLER**

   Markera en eller flera regler och klicka sedan på **[!UICONTROL Options]** > **[!UICONTROL Add container from selection]**. Detta gör om markeringen till en separat behållare.

## Använd datumintervall {#date-ranges}

Du kan skapa filter som innehåller rullande datumintervall för att få svar på frågor om pågående kampanjer eller evenemang.

Du kan till exempel enkelt skapa ett filter som innehåller&quot;alla som har köpt något de senaste 60 dagarna&quot;.

Du skapar en sessionsbehållare och lägger till [!UICONTROL Last 60 days] tidsintervall och mått [!UICONTROL Orders is greater than or equal to 1], med operatorn AND.

Här är en video om hur du använder rullande datumintervall i filter:

>[!VIDEO](https://video.tv.adobe.com/v/25403/?quality=12)

## Staplingsfilter {#stack}

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

1. Ange en rubrik och beskrivning för filtret.

1. Klicka **[!UICONTROL Show filters]** för att visa en lista med filter i den vänstra navigeringen.

1. Dra de filter som du vill stapla till filterdefinitionsytan.

1. Välj [!UICONTROL **Spara**].

## Attributionsmodeller {#attribution}

![](assets/attribution-models.jpg)

**Exempel: Händelsefilter där eVar1 = A**

| Exempel | A | A | A (beständig) | B | A | C |
|---|---|---|---|---|---|---|
| Upprepande | X | X | X | - | X | - |
| Instance | X | X | - | - | X | - |
| Icke upprepande instans | X | - | - | - | X | - |
