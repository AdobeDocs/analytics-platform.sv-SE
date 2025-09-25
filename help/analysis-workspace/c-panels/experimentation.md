---
description: Lär dig hur du kan analysera resultaten av A/B-tester på panelen Customer Journey Analytics Experimentation.
title: Panelen Experimentation
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
role: User
source-git-commit: b013518d8f1782219dd2cf9e5b5a89b877e3b92d
workflow-type: tm+mt
source-wordcount: '2125'
ht-degree: 0%

---

# Panelen Experimentation {#experimentation-panel}

>[!CONTEXTUALHELP]
>id="workspace_experimentation_button"
>title="Experimentation"
>abstract="Skapa en panel för att jämföra olika användarupplevelser, marknadsförings- och meddelandevarianter. Och för att avgöra vilken variation som är bäst när det gäller att få fram ett visst resultat."

>[!CONTEXTUALHELP]
>id="workspace_experimentation_panel"
>title="Experimentation"
>abstract="Jämför olika användarupplevelser, marknadsförings- och meddelandevarianter för att avgöra vilket som är bäst för att få fram ett visst resultat. Ange experimentet, kontrollvarianten som ska jämföras med, framgångsmåttet och normaliseringsmåttet. Du kan också ange övre och nedre gränser för att få förtroende."


>[!BEGINSHADEBOX]

_I den här artikeln beskrivs panelen Experimentation i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._<br/>_Mer information om hur du analyserar Adobe Target-aktiviteter och -upplevelser finns i [Analytics for Target-panelen](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/a4t-panel) i_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._

>[!ENDSHADEBOX]


På panelen **[!UICONTROL Experimentation]** kan analytiker jämföra olika användarupplevelser, marknadsförings- och meddelandevarianter för att avgöra vilket som är bäst för att få ett visst resultat. Ni kan utvärdera lyften och förtroendet för alla A/B-experiment från vilken experimentplattform som helst: online, offline, från Adobe lösningar som Target eller Journey Optimizer, och till och med från BYO (ta fram egna) data.

Läs mer om [integreringen mellan Adobe Customer Journey Analytics och Adobe Target](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja).

## Åtkomstkontroll {#access}

Panelen Experimentation kan användas av alla Customer Journey Analytics-användare. Inga administratörsrättigheter eller andra behörigheter krävs. Förutsättningarna kräver dock åtgärder som bara administratörer kan utföra.

## Funktioner i beräknade värden

Det finns två avancerade funktioner: Lyft och Förtroende. Mer information finns i [Referens - avancerade funktioner](/help/components/calc-metrics/cm-adv-functions.md).

## Förutsättningar

Om du vill använda panelen för experimenterande måste du uppfylla följande krav:

### Skapa en anslutning för att experimentera med datauppsättningar

Det rekommenderade dataschemat är att experimenteringsdata finns i en [objektarray](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/array) som innehåller experimentella data och variantdata i två olika dimensioner. Båda dimensionerna måste finnas i en **enkel**-objektmatris. Om du har dina experimentella data i en enda dimension (med experimentella data och variantdata i en avgränsad sträng) kan du använda inställningen [delsträng](/help/data-views/component-settings/substring.md) i datavyer för att dela dimensionen i två delar så att den kan användas i panelen.


När dina experimentdata har [importerats](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) till Adobe Experience Platform [skapar du en anslutning i Customer Journey Analytics](/help/connections/create-connection.md) till en eller flera experimentdatauppsättningar.

### Lägga till kontextetiketter i datavyer

I inställningarna för datavyer i Customer Journey Analytics kan administratörer lägga till [kontextetiketter](/help/data-views/component-settings/overview.md) i en dimension eller ett mått, och i Customer Journey Analytics-tjänster som [!UICONTROL Experimentation] kan dessa etiketter användas för deras ändamål. Två fördefinierade etiketter används för panelen Experimentation:

* [!UICONTROL Experimentation Experiment]
* [!UICONTROL Experimentation Variant]

I datavyn som innehåller experimentella data väljer du två dimensioner, en med experimentella data och en med variantdata. Etikettera sedan dimensionerna med etiketterna **[!UICONTROL Experimentation Experiment]** och **[!UICONTROL Experimentation Variant]**.

![Alternativ för sammanhangsetikett för Experimentation och Experimentation Variant.](assets/context-label.png)

Utan dessa etiketter fungerar inte Experimentpanelen eftersom det inte finns några experiment att arbeta med.

## Använd

Så här använder du en **[!UICONTROL Experimentation]**-panel:

1. Skapa en **[!UICONTROL Experimentation]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).


1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.

   >[!IMPORTANT]
   >
   >Om den nödvändiga konfigurationen i Customer Journey Analytics datavyer inte har slutförts får du det här meddelandet innan du kan fortsätta: [!UICONTROL Please configure the experiment and variant dimensions in Data views].
   >

### Panelindata

Så här använder du panelen Experimentation:

1. Konfigurera panelens indatainställningar:

   ![Experimentationspanelen har dragits till ett projekt.](assets/experiment-input.png)

   | Inställning | Definition |
   | --- | --- |
   | **[!UICONTROL Date Range]** | Datumintervallet för panelen Experimentation anges automatiskt baserat på den första händelsen som togs emot i Customer Journey Analytics för det valda experimentet. Du kan begränsa eller utöka datumintervallet till en mer specifik tidsram om det behövs. |
   | **[!UICONTROL Experiment]** | En uppsättning variationer för en upplevelse som exponerats för slutanvändarna för att avgöra vilken som är bäst att behålla för all framtid. Ett experiment består av två eller flera varianter, varav en betraktas som kontrollvariant. Den här inställningen är förifylld med de dimensioner som har etiketterats med etiketten **[!UICONTROL Experiment]** i datavyer och de senaste sex månadernas experimentdata. |
   | **[!UICONTROL Control variant]** | En av två eller flera förändringar i en slutanvändares upplevelse som jämförs i syfte att identifiera det bättre alternativet. En variant måste väljas som kontroll och endast en variant kan anses vara kontrollvariant. Den här inställningen är förifylld med de dimensioner som har etiketten **[!UICONTROL Variant]** i datavyer. Den här inställningen hämtar upp de variantdata som är associerade med det här experimentet. |
   | **[!UICONTROL Success metrics]** ➊ | Mätvärden eller mätvärden som en användare jämför varianter med. Varianten med det mest önskade resultatet för konverteringsmåttet (oavsett om det är högst eller lägst) deklareras som *varianten* för ett experiment med bästa resultat. Du kan lägga till upp till 5 mätvärden. |
   | **[!UICONTROL Normalizing metric]** ➋ | Grundläggande (**[!UICONTROL Global Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Account]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Opportunity]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL Buying Group]** [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}, **[!UICONTROL People]**, **[!UICONTROL Sessions]** eller **[!UICONTROL Events]**) som testet körs på. Ett test kan till exempel jämföra konverteringsgraden för flera variationer där **[!UICONTROL Conversion rate]** beräknas som sidvy. |
   | **[!UICONTROL Include confidence upper/lower bounds]** | Aktivera det här alternativet om du vill visa övre och nedre gränser för konfidensnivåer. |


1. Välj **[!UICONTROL Build]**.

### Panelutdata

Experimentationspanelen returnerar en mängd data och visualiseringar som hjälper dig att förstå hur dina experiment fungerar bättre. Längst upp på panelen visas [sammanfattningsändringar](../visualizations/summary-number-change.md) som en påminnelse om de panelinställningar du har valt. Du kan när som helst redigera panelen genom att välja redigeringspennan längst upp till höger.

Du får också en textsammanfattning som anger om experimentet är slutgiltigt eller inte och som sammanfattar resultatet. Slutsatsen baseras på statistisk signifikans (se [Statistisk metod](#adobes-statistical-methodology)). Du kan se sammanfattningssiffror för den mest högpresterande varianten med största lyft och förtroende.

För varje framgångsmått som du har valt visas en [frihandstabell](../visualizations/freeform-table/freeform-table.md)-visualisering och en [linje](../visualizations/line.md)-visualisering.

![Experimentationsutdata visar en friformstabell och en konverteringsgrad.](assets/experiment-output.png)


>[!NOTE]
>
>Den här panelen stöder för närvarande inte analys av A/A-tester.

#### Tolka resultaten

1. **Experimentationen är klar**: Varje gång du visar experimenteringsrapporten analyseras de data som samlats in i experimentet fram till den här tidpunkten. Analysen deklarerar att ett experiment är avgörande när den giltiga *anytime*-förtroendet korsar ett tröskelvärde på 95 % för *minst en* av varianterna. Med mer än två armar tillämpas en Benjamini-Hochberg-korrigering för korrigering vid testning av flera hypoteser.

2. **Mest högpresterande variant**: När ett experiment har deklarerats som entydigt markeras varianten med den högsta konverteringsgraden som den mest presterande varianten. Observera att den här varianten antingen måste vara kontroll- eller baslinjevarianten, eller en av varianterna som korsar det giltiga konfidensintervallet på 95 % *någon gång* (med korrigeringar av Benjamini-Hochberg tillämpade).

3. **Konverteringsgrad**: Den konverteringsgrad som visas är en kvot mellan det genomförda måttet ➊ och det normaliserande måttvärdet ➋. Observera att det här värdet kan vara större än 1 om mätvärdet inte är binärt (1 eller 0 för varje enhet i experimentet)

4. **Lyft**: Sammanfattningen av expertrapporten visar Lyft över baslinjen, vilket är ett mått på den procentuella förbättringen av konverteringsgraden för en given variant över baslinjen. Definierat exakt är det skillnaden i prestanda mellan en given variant och baslinjen, dividerat med baslinjens prestanda, uttryckt i procent.

5. **Förtroende**: Det förtroende som visas varje gång är ett sannolikhetsmått för hur mycket bevis det finns för att en given variant är densamma som kontrollvarianten. Ett högre förtroende tyder inte på att kontrollvarianten och icke-kontrollvarianten har samma prestanda. Förtroendet är en sannolikhet (uttryckt i procent) att du skulle ha observerat en mindre skillnad i konverteringsgraden mellan en given variant och kontrollen. I själva verket finns det ingen skillnad i de faktiska underliggande konverteringssatserna. Värdet för *p* är 1 - *p*.

>[!NOTE]
>
>En fullständig beskrivning av resultaten bör omfatta alla tillgängliga bevis (t.ex. experimentdesign, provstorlekar, konverteringsgrader, förtroende med mera), och inte bara en förklaring om huruvida resultatet är slutgiltigt eller inte. Även om resultatet ännu inte är entydigt kan det fortfarande finnas övertygande bevis för att en variant skiljer sig från en annan (t.ex. att konfidensintervallen nästan inte överlappar varandra). Helst bör alla statistiska uppgifter, tolkade på ett kontinuerligt spektrum, vara beslutsunderlag.

## Adobe statistiska metod {#statistics}

Adobe har antagit en statistisk metod baserad på [Anytime Valid Confidence Sequences](https://arxiv.org/abs/2103.06476) för att den statistiska slutsatsen ska vara enkel att tolka och säker.

En konfidenssekvens är en *sekventiell*-analog för ett konfidensintervall. Tänk dig att du upprepar dina experiment hundra gånger för att förstå vad en förtroendesekvens är. Och beräkna en uppskattning av medelvärdet för affärsmätningen (till exempel öppningsfrekvensen för ett e-postmeddelande) och dess associerade 95-procentiga konfidenssekvens för *varje ny användare* som deltar i experimentet.

En 95-procentig konfidenssekvens innehåller det &quot;sanna&quot; värdet av företagsmätningen i 95 av de 100 experiment som du utförde. (Ett 95-procentigt konfidensintervall kunde endast beräknas en gång per experiment för att ge samma 95-procentiga täckningsgaranti, inte för varje enskild ny användare). Med hjälp av förtroendesekvenser kan du därför övervaka försök kontinuerligt, utan att öka antalet falska positiva fel, det vill säga de tillåter&quot;sökning&quot; vid resultat.

## Tolka icke-slumpmässiga dimensioner {#non-randomized}

Med Customer Journey Analytics kan analytiker välja vilken dimension som helst som experiment. Men hur tolkar man en analys där den dimension som väljs som försöksprodukt inte är en som är slumpmässig?

Ta till exempel en annons som en person ser. Du kan vara intresserad av att mäta förändringen i vissa mätvärden (till exempel medelintäkt) om du bestämmer dig för att visa personer *och B* i stället för *och A*. Orsakseffekten av att visa annonser B i stället för annonser A är av central betydelse för att fatta beslut om marknadsföring. Denna orsakseffekt kan mätas som den genomsnittliga intäkten för hela populationen, om du ersatte status quo för att visa och A med den alternativa strategin att visa och B.

A/B-tester är den guldbaserade standarden inom branschen för att objektivt mäta effekterna av sådana ingrepp. Den kritiska orsaken till varför ett A/B-test ger upphov till en uppskattning av orsakssamband beror på slumpgenereringen av personer för att få en av de möjliga varianterna.

Tänk på en dimension som inte uppnås genom slumpgenerering, till exempel USA:s tillstånd för personen. Personerna kommer främst från två delstater, New York och Kalifornien. De genomsnittliga intäkterna från försäljningen av ett vinterklädmärke kan vara olika i de två delstaterna på grund av skillnaderna i det regionala vädret. I en sådan situation kan vädret vara den verkliga orsaken till försäljningen av kläder på vintern, och inte det faktum att personernas geografiska läge är olika.

Experimenteringspanelen i Customer Journey Analytics gör att du kan analysera data som genomsnittliga intäktsskillnader mellan olika tillstånd. I en sådan situation har produktionen ingen orsaksmässig tolkning. En sådan analys kan dock fortfarande vara av intresse. Den ger en uppskattning (tillsammans med mått på osäkerhet) av skillnaden i de genomsnittliga intäkterna för delstaterna.  Det här värdet kallas även *Statistisk hypotestestning*. Resultatet av denna analys kan vara intressant, men inte nödvändigtvis åtgärdbart. Det beror helt enkelt på att du inte har slumpat ut och ibland inte kan göra personer slumpmässiga till ett av dimensionens möjliga värden.

Följande bild kontrasterar dessa situationer:

![Ett diagram som visar observationsdata och den slumpmässiga utvärderingen.](assets/randomize.png)

När du vill mäta effekten av intervention X på resultatet Y, är det möjligt att den verkliga orsaken till båda är den förvirrande faktorn C. Om data inte uppnås genom slumpgenerering av personer på X är effekten svårare att mäta, och analysen redogör uttryckligen för C. Slumpmässigt bryter X beroendet av C, vilket gör att vi kan mäta X:s effekt på Y utan att behöva oroa oss för andra variabler.

## Använd beräknade mätvärden i experimenterande {#use-in-experimentation}

>[!NOTE]
>
>För organisationer som använder både Customer Journey Analytics och Adobe Journey Optimizer gäller informationen i det här avsnittet även för experimentfunktioner i Journey Optimizer.

Alla beräknade värden är inte kompatibla med panelen Experimentation.

Beräknade mått som innehåller någon av följande mått eller konstanter är inte kompatibla med panelen Experimentation:

* Basmått från en [sammanfattningsdatauppsättning](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/summary-data)
* Basvärden som delas av varandra eller multipliceras tillsammans (till exempel `Revenue`/`Orders`)
* Konstanter som har lagts till eller subtraherats från ett basmått (till exempel `Revenue+50`)
* Något av följande basmått:
   * Folk

Beräknade mätvärden som inte är kompatibla med panelen Experimentation har värdet [!UICONTROL **Everywhere i Customer Journey Analytics (exklusive experiment)**] i fältet [!UICONTROL **Produktkompatibilitet**] när det beräknade mätvärdet skapas. Mer information om hur du skapar beräknade mått finns i [Bygg mått](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md).

## Använda beräknade värden på panelen Experimentera

I det här blogginlägget finns information om [hur du använder beräknade värden på panelen Experimentation](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).

>[!MORELIKETHIS]
>[Mastering Adobe Customer Journey Analytics Experimentation](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/mastering-adobe-customer-journey-analytics-experimentation-your/ba-p/732338)
>
