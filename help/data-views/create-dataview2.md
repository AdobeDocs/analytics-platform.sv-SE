---
title: Så här skapar du en ny datavy i Customer Journey Analytics.
description: Beskriver alla inställningar som behövs för att skapa nya datavyer.
translation-type: tm+mt
source-git-commit: 6cfab7fc7ce3360b5ea2ed8bdd7f3e0a8e76a24d
workflow-type: tm+mt
source-wordcount: '2314'
ht-degree: 1%

---


# Skapa en ny datavy

När du skapar en datavy måste du antingen skapa mått och mått från schemaelement eller använda standardkomponenter. Genom att skapa mätvärden eller dimensioner får du en enorm flexibilitet. Tidigare var antagandet att om du hade datauppsättningar i Adobe Experience Platform var strängfält dimensioner och numeriska fält var mätvärden. För att kunna ändra något av dessa fält var du tvungen att redigera schemat i Platform. Gränssnittet för datavyer ger nu en friare definition av mått och mått.

## Konfigurera inställningar och behållare för datavyer

1. Gå till fliken **Datavyer** i Customer Journey Analytics.
2. Klicka på **Lägg till** för att skapa en ny datavy och konfigurera dess inställningar.

![](assets/)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| Anslutning | Det här fältet länkar datavyn till anslutningen som du upprättade tidigare, som innehåller en eller flera Adobe Experience Platform-datauppsättningar. |
| Namn | Det är obligatoriskt att ge datavyn ett namn. |
| Beskrivning | En detaljerad beskrivning är inte obligatorisk, men rekommenderas. |
| Tidszon | Välj vilken tidszon du vill att dina data ska visas i. |
| Taggar | Med taggar kan du ordna datavyer i kategorier. |
| Behållare | Du kan byta namn på behållarna här och så här visas de i alla Workspace-projekt som baseras på den här datavyn. Behållare används i filter och utfall/flöde för att definiera hur brett eller smalt omfånget eller sammanhanget är. [Läs mer](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
| Personbehållarens namn är.. | Person (standard). Personbehållaren innehåller alla besök och sidvisningar för besökare inom en viss tidsperiod. Du kan byta namn på detta till &quot;Användare&quot; eller något annat uttryck som du föredrar. |
| Sessionsbehållarens namn är.. | Session (standard). Med sessionsbehållaren kan du identifiera sidinteraktioner, kampanjer eller konverteringar för en viss session. Du kan byta namn på detta till Besök eller något annat uttryck som du föredrar. |
| Händelsebehållarens namn är.. | Händelse (standard). Händelsebehållaren definierar vilka sidhändelser som du vill inkludera eller exkludera från ett filter. |

Därefter ska du skapa mått och mått utifrån schemaelement.

## Skapa mått och dimensioner från schemaelement

1. Klicka på fliken [!UICONTROL Components] i [!UICONTROL Customer Journey Aalytics] > [!UICONTROL Data Views].

![](assets/components-tab.png)

Du kan se [!UICONTROL Connection] längst upp till vänster, som innehåller datauppsättningarna, och dess [!UICONTROL Schema fields] nedan.

1. Dra nu ett schemafält, till exempel [!UICONTROL pageTitle], från den vänstra listen till avsnittet Metrisk eller Dimensioner.

   Du kan dra samma schemafält till mått- eller mätområdena flera gånger och konfigurera samma mått eller mätvärden på olika sätt. I fältet **[!UICONTROL pageTitle]** kan du till exempel skapa en dimension med namnet&quot;Produktsidor&quot; och en annan&quot;Felsidor&quot;. Från **[!UICONTROL pageTitle]**; kan du också skapa mätvärden från ett strängvärde. Du kan till exempel skapa ett eller flera **[!UICONTROL Orders]**-mått med olika attribueringsinställningar och olika include/exclude-värden.

   ![](assets/components-tab-3.png)

1. När du har valt komponenten visas ett antal inställningar till höger. Konfigurera komponenten med de inställningar som beskrivs nedan.

### Konfigurera komponentinställningar

![](assets/component-settings.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Component type] | Obligatoriskt. Gör att du kan ändra en komponent från Mått till Dimension eller tvärtom. |
| [!UICONTROL Component Name] | Obligatoriskt. Här kan du ange vilket eget namn som ska visas i Analysis Workspace. Du kan byta namn på en komponent om du vill ge den ett datavy-specifikt namn. |
| [!UICONTROL Description] | Valfritt, men rekommenderas, för att ge information om komponenten för andra användare. |
| [!UICONTROL Tags] | Valfritt. Gör att du kan tagga komponenten med egna eller färdiga taggar för enklare sökning/filtrering i Analysis Workspace-gränssnittet. |
| [!UICONTROL Field Name] | Schemafältets namn. |
| [!UICONTROL Dataset type] | Obligatoriskt. Ett icke-redigerbart fält som visar vilken datamängdstyp (händelse, sökning eller profil) som komponenten kommer från. |
| [!UICONTROL Dataset] | Obligatoriskt. Ett icke-redigerbart fält som visar vilken typ av fält som komponenten kommer från (t.ex. String, Integer, osv.). Det här fältet kan innehålla flera datauppsättningar, till exempel när du kombinerar flera rapportsviter. |
| [!UICONTROL Schema type] | Avser om komponenten är en sträng, ett heltal osv. |
| [!UICONTROL Component ID] | Obligatoriskt. [CJA API](https://adobe.io/cja-apis/docs) använder det här fältet för att referera till komponenten. Du kan klicka på redigeringsikonen och ändra det här komponent-ID:t. Om du ändrar det här komponent-ID:t bryts alla befintliga arbetsyteprojekt som innehåller den här komponenten.<br>Om du någonsin skapar en annan datavy som använder ett annat fält för en pageTitle-dimension, kan du byta namn på den och göra dimensionen tvärdatavyn kompatibel. |
| Bana | Obligatoriskt. Ett icke-redigerbart fält som visar schemasökvägen som komponenten kommer från. |
| Dölj komponent i rapportering | Standard = av. Gör att du kan strukturera ut komponenten från datavyn när den används i rapporter. Detta påverkar inte behörigheter, bara komponentkurering. Du kan med andra ord dölja komponenten för icke-administratörer i rapporter. Administratörer kan fortfarande komma åt den genom att klicka på [!UICONTROL Show All Components] i ett Analysis Workspace-projekt. |

### Konfigurera formatinställningar

Formatinställningarna gäller endast för mätvärden.

![](assets/format-settings.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Format] | Här kan du ange formatering för ett mätresultat, som decimal, tid, procent eller valuta. |
| [!UICONTROL Decimal Places] | Här kan du ange hur många decimaler ett mätresultat ska visa. |
| [!UICONTROL Show upward trend as] | Här kan du ange om en uppåtgående trend för det här måttet ska anses vara bra (grönt) eller dåligt (rött). |
| [!UICONTROL Currency] | Den här inställningen visas bara om det valda måttformatet är [!UICONTROL Currency]. Det finns en lista med valutaalternativ. Standardvärdet är ingen valuta. På så sätt kan du visa intäkter i valfri valuta vid rapportering. Det här är inte en valutakonvertering, bara ett gränssnittsformateringsalternativ. |

### Konfigurera attributinställningar

![](assets/attribution-settings.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Set attribution] | Här kan du ange de attributinställningar som du vill använda för det här måttet som standard när det används. Den här standardinställningen kan åsidosättas i en frihandstabell eller i ett beräknat mått. |
| [!UICONTROL Attribution model] | Gör att du kan ange en standardattribueringsmodell - bara aktiv när du aktiverar inställningen [!UICONTROL Use Non-default attribution model]. Standardvärdet är [!UICONTROL Last Touch]. Alternativen är: Senaste beröring, första beröring, linjär, deltagande, samma beröring, U-Shaped, J-kurva, omvänd J, tidsfördröjning, anpassad, algoritmisk. Vissa av dessa alternativ skapar ytterligare fält som måste fyllas i, till exempel Anpassad eller Tidsåtgång. Du kan skapa flera mätvärden med samma fält - det innebär att du kan ha ett [!UICONTROL Last touch]-intäktsmått och ett [!UICONTROL First Touch]-intäktsmått, men baserat på samma intäktsfält i schemat. |
| [!UICONTROL Lookback window] | Gör att du kan ange ett standardfönster för sökning till ett mätvärde - bara aktivt när du aktiverar inställningen [!UICONTROL Use Non-default attribution model]. Alternativen är: Person (rapporteringsfönster), session, anpassad. När du har valt Anpassad får du också möjlighet att välja valfritt antal dagar/veckor/månader/osv. (upp till 90 dagar), precis som Attribution IQ. Du kan ha flera mätvärden med samma schemafält, men var och en med ett separat uppslagsfönster. |

### Konfigurera inställningar för Inkludera/exkludera värden

Med den här inställningen kan du ändra de underliggande data som du rapporterar om vid en fråga. Det är inte detsamma som ett filter (kallades tidigare segment). Men filtren kommer att ta hänsyn till denna nya dimension, liksom målning och attribuering.

Du kan t.ex. skapa en dimension utanför pageTitle-fältet, men anropa det som &quot;felsidor&quot; och inkludera alla sidor som [!UICONTROL contains the phrase] &quot;fel&quot;.

![](assets/include-exclude.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Case sensitive] | Standard = På. Den här inställningen skiljer sig något åt för Dimensioner jämfört med mått.<ul><li>**Mått**: Den här inställningen gäller bara för  [!UICONTROL Include/Exclude Values] avsnittet. Du kan ange om filtret du använder ska vara skiftlägeskänsligt.</li><li>**Dimension** : Den här inställningen avgör om data i den här dimensionen ska aggregeras på ett skiftlägeskänsligt eller skiftlägeskänsligt sätt. Detta ändrar hur rapporter/filter/attribueringsinställningar körs för ett strängfält.</li></ul> |
| [!UICONTROL Match] | Här kan du ange vilka värden du vill ta hänsyn till för rapportering före attribuering och segmentering (t.ex. endast använda värden som innehåller frasen &quot;error&quot;). Du kan ange: **[!UICONTROL If all criteria are met]** eller **[!UICONTROL If any criteria are met]**. |
| [!UICONTROL Criteria] | Här kan du ange den matchningslogik som ska användas för en viss filterregel.<ul><li>**Sträng**: Innehåller frasen, Innehåller valfri term, Innehåller alla termer, Innehåller ingen term, Innehåller inte frasen, Lika med, Är inte lika, Börjar med, Slutar med</li><li>**Dubbel/heltal**: är lika med, inte lika med, är större än, är mindre än, är större än eller lika med, är mindre än eller lika med</li><li>**Datum**: är lika med, inte lika med, är senare än, är före, finns i</li></ul> |
| [!UICONTROL Match operand] | Här kan du ange den matchningsoperand som matchningsoperatorn ska användas på.<ul><li>**Sträng**: Textfält</li><li>**Dubbel/heltal**: Textfält med upp-/nedpilar för numeriska värden</li><li>**Datum**: Väljare för daggranularitet (kalender)</li><li>**Datum och tid**: Val för datum- och tidsgranularitet</li></ul> |
| [!UICONTROL Add rule] | Här kan du ange ytterligare en matchningsoperator och -operand. |

### Konfigurera beteendeinställningar

![](assets/behavior-settings.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Count values] | Detta gör att du kan skapa ett antal gånger ett booleskt fält har angetts till `true`; som ett mått. Exempelvis är antalet [!UICONTROL Page Views] där ett booleskt fält med namnet `isPage` är inställt på `true`. |
| [!UICONTROL Count instances] | Här kan du ange om ett numeriskt fält eller ett datumtypsfält som används som ett mätvärde ska räkna tiden som det ställdes in i stället för själva värdet.<br> Om du vill lägga till förekomsterna av ett numeriskt fält och bara vill lägga till antalet gånger som ett fält har angetts, i stället för det faktiska värdet  ** i fältet.<br>Detta är användbart om du till exempel vill skapa ett  [!UICONTROL Orders] mätvärde från ett  [!UICONTROL Revenue] fält. Om intäkten har ställts in vill vi räkna med en enda order i stället för det numeriska intäktsbeloppet. |

### Konfigurera [!UICONTROL No Value Options]-inställningar

[!UICONTROL No Value Options] -inställningarna motsvarar  [!UICONTROL Unspecified] eller  [!UICONTROL None] värden vid rapportering. I datavysningsgränssnittet kan du, komponentvis, bestämma hur du vill att dessa värden ska behandlas i rapporter. Du kan också byta namn på [!UICONTROL No value] till något som passar din miljö bättre, till exempel [!UICONTROL Null], [!UICONTROL Not set] eller andra.

Viktigt: När du ändrar det här fältet till ett anpassat värde behandlas det anpassade värdet som ett giltigt strängvärde. Om du anger värdet &quot;Red&quot; i det här fältet kommer alla förekomster av strängen &quot;Red&quot; som visas i själva data också att hamna under samma radobjekt som du har angett.

Observera också att det du anger i det här fältet kan användas för speciell användargränssnittsbehandling av radobjektet Inget värde i rapporteringen enligt inställningen Inga värdealternativ. (Inte säker på vad detta innebär.)

![](assets/no-value-options.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| Ring [!UICONTROL No value] om det visas... | Här kan du byta namn på **[!UICONTROL No value]** till något annat. |
| Visa inte **[!UICONTROL No value]** som standard | Visar inte det här värdet vid rapportering. |
| Visa **[!UICONTROL No value]** som standard | Visar det här värdet vid rapportering. |
| Behandla **[!UICONTROL No value]** som ett värde | Om du t.ex. har Mobile-enhetstyper som dimension kan du byta namn på **[!UICONTROL No value]**-objektet till &quot;Desktop&quot;. |

### Konfigurera inställningar för beständighet

![](assets/persistence.png)

De här inställningarna liknar eVar i vanliga Adobe Analytics.

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| Ange beständighet | Växla nyckel |
| Allokering | Här kan du ange den allokeringsmodell som används för en dimension för beständighet. Alternativen är: Senaste, Original, Instance, Alla. Om du vill att ett värde ska finnas kvar (liknande eVars i traditionell Analytics) är det här du skulle ange det. Den enda viktiga skillnaden är att den maximala beständighet du kan ange är 90 dagar. [!UICONTROL Never expire] är inte heller ett alternativ. |
| Förfaller | Gör att du kan ange det beständiga fönstret för en dimension. Alternativen är: Session (standard), Person, Time, Metric. Du kanske måste kunna förfalla dimensionen på ett köp (t.ex. interna sökvillkor eller andra användningsfall för varuexponering). Med &quot;Metrisk&quot; kan du ange någon av de definierade måtten som måttets förfallotid för den här dimensionen (t.ex. ett &quot;Inköp&quot;-mått). |

### Konfigurera inställningar för värdepaketering

![](assets/value-bucketing.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| Bucket-värde | Gör att du kan skapa en paketerad version av en numerisk dimension. På så sätt kan du rapportera flera intäktsgrupper eller andra numeriska värden som en dimension i rapporteringen. Du kan skapa upp till fem fickor. |
| Upp till | Här kan du ange gränserna för den första numeriska dimensionskassetten. Detta gäller endast för numeriska mått. |
| Mellan och upp till | Här kan du ange gränserna för efterföljande numeriska dimensionsintervall. |
| Lägg till bucket | Gör att du kan lägga till ytterligare en bucket i en numerisk dimensionsbucketning. |

## Använd standardkomponenter

Förutom att skapa mått och mått från schemaelement kan du även använda standardkomponenter i datavyer.

Standardkomponenter är komponenter som inte genereras från schemafält för datauppsättningar, utan i stället genereras av systemet. Vissa systemkomponenter krävs i en datavy för att underlätta rapportering i Analysis Workspace, medan andra systemkomponenter är valfria.

![](RackMultipart20210326-4-374d6q_html_1100d8d54f8c09ac.png)

Nödvändiga standardkomponenter

| Komponentnamn | Dimension eller mått | Anteckningar |
| --- | --- | --- |
| Personer | Mått | Kallas tidigare [!UICONTROL Unique Visitors] i traditionell analys. Det här måttet baseras på det person-ID som anges i en anslutning. |
| Sessioner | Mått | Kallas tidigare [!UICONTROL Visits] i traditionell analys. Det här måttet baseras på sessionsinställningarna som anges nedan. |
| Händelser | Mått | Kallas tidigare [!UICONTROL Occurrences] i traditionell analys. Det här måttet representerar antalet rader från alla händelsedatamängder i en anslutning. |
| Dag | Dimension |  |
| Vecka | Dimension |  |
| Månad | Dimension |  |
| Kvartal | Dimension |  |
| År | Dimension |  |
| Timme | Dimension |  |
| Minut | Dimension |  |

## Valfria standardkomponenter

Vissa systemkomponenter krävs i en datavy för att underlätta rapportering i Analysis Workspace, medan de nedan är valfria.

| Komponentnamn | Dimension eller mått | Anteckningar |
| --- | --- | --- |
| [!UICONTROL Session Starts] | Mått | Det här måttet räknar antalet händelser som var den första händelsen i en session. Vid användning i en filterdefinition (t.ex. [!UICONTROL Session Starts] existerar&#39;), filtreras ned till den första händelsen i varje session. Observera att detta är ett annat beteende än [!UICONTROL Entries] eftersom det alltid räknar den första händelsen i en session - inte det första värdet som finns för en dimension i en session. |
| [!UICONTROL Session Ends] | Mått | Det här måttet räknar antalet händelser som var den sista händelsen i en session. På liknande sätt som [!UICONTROL Session Starts] kan den även användas i en filterdefinition för att filtrera ned saker till den sista händelsen i varje session. Observera att detta är ett annat beteende än [!UICONTROL Exits] eftersom det alltid räknar den sista händelsen i en session - inte det sista värdet som finns för en dimension i en session. |
| [!UICONTROL Time Spent (seconds)] | Mått | Måttet [!UICONTROL Time Spent] fungerar på liknande sätt som i traditionella Adobe Analytics - vilket ökar tiden mellan två olika värden för en dimension. Men med måtten Session Starts and Session Ends kan kunderna själva konstruera de beräknade värdena [!UICONTROL Time Spent per Person] och [!UICONTROL Time Spent per Session] (se OTB-filter och beräknade värden nedan). |
| [!UICONTROL Time Spent per Event] | Dimension | Det här är faktiskt bara en felsökning av ovanstående mätvärden. Vi erbjuder standardfickor, men du kan ändra bucklarna till vad du vill. |
| Tilldelad tid per session | Dimension |  |
| Tilldelad tid per person | Dimension |  |
| Batch-ID | Dimension |  |
| Datauppsättnings-ID | Dimension |  |
