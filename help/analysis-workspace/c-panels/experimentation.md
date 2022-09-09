---
description: Lär dig hur du kan analysera resultaten av A/B-tester på CJA-panelen Experimentation.
title: Panelen Experimentation
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 41cca39d73773af09981bde10c93c767ebdb77d4
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 0%

---

# Panelen Experimentation

>[!NOTE]
>
>Den här funktionen finns för närvarande i [begränsad testning](/help/release-notes/releases.md).

The **[!UICONTROL Experimentation]** kan analytiker jämföra olika varianter av användarupplevelser, marknadsföring och meddelanden för att avgöra vilket som är bäst för att uppnå ett visst resultat. Ni kan utvärdera lyften och förtroendet för alla A/B-experiment från vilken experimentplattform som helst - online, offline, från Adobe-lösningar, Adobe Journey Optimizer och till och med från BYO (ta fram egna) data.

>[!IMPORTANT]
>
>I det här skedet [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html) (A4T) data som hämtas till Adobe Experience Platform via Analytics Source Connector **inte** analyseras i [!UICONTROL Experimentation] -panelen. Vi förväntar oss en lösning på detta problem under 2023.

## Åtkomstkontroll

Experimentationspanelen kan användas av alla som använder Customer Journey Analytics (CJA). Inga administratörsrättigheter eller andra behörigheter krävs. Installationen (steg 1 och 2 nedan) kräver åtgärder som bara administratörer kan utföra.

## Steg 1: Skapa anslutning för att experimentera med datauppsättningar

Det rekommenderade dataschemat är att experimentdata ska finnas i en [Objektarray](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/array.html?lang=en) som innehåller experimentella data och variantdata i två olika dimensioner. Om du har experimenterat med data i en enda dimension med experiment- och variantdata i en avgränsad sträng kan du använda [delsträng](/help/data-views/component-settings/substring.md) ange i datavyer för att dela upp dem i två för användning på panelen.

Efter att dina experimentdata har [inkapslad](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html) till Adobe Experience Platform, [skapa en anslutning i CJA](/help/connections/create-connection.md) till en eller flera experimentdatauppsättningar.

## Steg 2: Lägga till kontextetiketter i datavyer

I inställningarna för CJA-datavyer kan administratörer lägga till [kontextetiketter](/help/data-views/component-settings/overview.md) till mått eller mätvärden och CJA-tjänster som [!UICONTROL Experimentation] kan använda dessa etiketter för sina ändamål. Två fördefinierade etiketter används för panelen Experimentation:

* [!UICONTROL Experimentation Experiment]
* [!UICONTROL Experimentation Variant]

I datavyn som innehåller experimentella data väljer du två dimensioner, en med experimentella data och en med variantdata. Ge sedan måtten etiketten med **[!UICONTROL Experiment]** och **[!UICONTROL Variant]** etiketter.

![kontextetikett](assets/context-label.png)

Utan dessa etiketter fungerar inte Experimentpanelen eftersom det inte finns några experiment att arbeta med.

## Steg 3: Konfigurera panelen Experimentera

1. I CJA Workspace drar du panelen Experimentation till ett projekt.

![experimentpanel](assets/experiment.png)

>[!IMPORTANT]
>Om de nödvändiga inställningarna i CJA-datavyer inte har slutförts får du det här meddelandet innan du kan fortsätta: &quot;[!UICONTROL Please configure the experiment and variant dimensions in Data Views]&quot;.

1. Konfigurera panelens indatainställningar.

   | Inställning | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | En uppsättning variationer för en upplevelse som exponerats för slutanvändare för att avgöra vilken som är bäst att behålla för all framtid. Ett experiment består av två eller flera varianter, varav en betraktas som kontrollvariant. Den här inställningen är förifylld med de dimensioner som har märkts med  **[!UICONTROL Experiment]** i datavyer och de tre senaste månadernas experimentdata. |
   | **[!UICONTROL Control Variant]** | En av två eller flera förändringar i en slutanvändares upplevelse som jämförs i syfte att identifiera det bättre alternativet. En variant måste väljas som kontroll och endast en variant kan anses vara kontrollvariant. Den här inställningen är förifylld med de dimensioner som har märkts med  **[!UICONTROL Variant]** etikett i datavyer. Den här inställningen hämtar upp de variantdata som är associerade med det här experimentet. |
   | **[!UICONTROL Success Metrics]** | Mätvärden eller mätvärden som en användare jämför varianter med. Den variant som har det mest önskade resultatet för konverteringsmåttet (oavsett om det är högst eller lägst) deklareras som den&quot;bästa varianten&quot; i ett experiment. Du kan lägga till upp till 5 mätvärden. |
   | **[!UICONTROL Normalizing Metric]** | Grunden ([!UICONTROL People], [!UICONTROL Sessions], eller [!UICONTROL Events]) som testet ska köras på. Ett test kan t.ex. jämföra konverteringsgraden för flera variationer där **[!UICONTROL Conversion rate]** beräknas som **[!UICONTROL Conversions per session]** eller **[!UICONTROL Conversions per person]**. |
   | **[!UICONTROL Date Range]** | Datumintervallet ställs in automatiskt baserat på den första träffen i CJA för det valda experimentet. Du kan begränsa eller utöka datumintervallet till en mer specifik tidsram om det behövs. |

1. Klicka på **[!UICONTROL Build]**.

## Steg 4: Visa panelutdata

Experimentationspanelen returnerar en mängd data och visualiseringar som hjälper dig att förstå hur dina experiment fungerar bättre. Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt. Du kan när som helst redigera panelen genom att klicka på redigeringspennan längst upp till höger.

Du får också en textsammanfattning som anger om experimentet är slutgiltigt eller inte och som sammanfattar resultatet. Slutsatsen baseras på statistisk signifikans. (Se Statistisk metod nedan.) Du kan se sammanfattningsnummer för den mest högpresterande varianten med högsta lyft och självförtroende.

För varje framgångsmått som du har valt visas en frihandstabell och en konverteringsgrad.

![experimentera fram](assets/exp-output1.png)

The [!UICONTROL Line] diagrammet ger dig [!UICONTROL Control] kontra [!UICONTROL Control Variant] prestanda:

![linjediagramutdata](assets/exp-output2.png)

>[!NOTE]
>
>Den här panelen stöder för närvarande inte analys av A/A-tester.

>[!NOTE]
>
>Lyft och förtroende är också [avancerade beräknade mätfunktioner](/help/components/calc-metrics/cm-adv-functions.md) i CJA, så att ni kan bygga upp egna värden för lyft och förtroende.

## Steg 5: Tolka resultaten

1. **Experiment är slutprodukt**: Varje gång du tittar på experimentrapporten analyserar Adobe de data som har samlats in i experimentet fram till den här tidpunkten och deklarerar ett experiment som&quot;slutgiltigt&quot; när ett giltigt konfidensintervall överskrider ett tröskelvärde på 95 % för *minst en* av varianterna (med en Bonferonni-korrigering tillämpad när det finns mer än två armar, för att korrigera för multipla hypotesstester).

2. **Best Performance Variant**: När ett försök har förklarats vara avgörande betecknas varianten med den högsta konverteringsgraden som&quot;varianten med bästa resultat&quot;. Observera att denna variant antingen måste vara kontrollvarianten eller baslinjevarianten, eller en av varianterna som korsar det 95% som gäller vid varje tidpunkt (när Bonferonni korrigerar).

3. **Konverteringsgrad**: Den konverteringsgrad som visas är ett förhållande mellan framgångsmåttet och det normaliserande måttvärdet. Observera att detta ibland kan vara större än 1 om mätvärdet inte är binärt (1 eller 0 för varje enhet i experimentet)

4. **Lyft**: Sammanfattningen av expertrapporten visar Lyft över baslinjen, som är ett mått på den procentuella förbättringen av konverteringsgraden för en given variant över baslinjen. Definierat exakt är det skillnaden i prestanda mellan en given variant och baslinjen, dividerat med baslinjens prestanda, uttryckt i procent.

5. **Förtroende**: Den Anytime Valid Confidence som visas är ett sannolikhetsmått på hur mycket det finns bevis för att en viss variant är densamma som kontrollvarianten. Ett högre förtroende tyder inte på att kontrollvarianten och icke-kontrollvarianten har samma prestanda. Mer exakt är den säkerhet som visas en sannolikhet (uttryckt i procent) att vi skulle ha observerat en mindre skillnad i konverteringsgraden mellan en viss variant och kontrollen, om det i själva verket inte finns någon skillnad i den verkliga underliggande konverteringsgraden. När det gäller *p*-values, the trust displayed is 1 - *p*-value.

>[!NOTE]
>
>En fullständig beskrivning av resultaten bör beakta alla tillgängliga bevis (dvs. experimentdesign, provstorlekar, konverteringsgrader, konfidensgrad osv.), och inte bara försäkran om att resultatet är slutgiltigt eller inte. Även om ett resultat ännu inte är &quot;entydigt&quot; kan det fortfarande finnas övertygande bevis för att en variant skiljer sig från en annan (t.ex. att konfidensintervallen nästan inte överlappar varandra). I idealfallet bör beslutsfattandet kompletteras med all statistik, tolkad på ett kontinuerligt spektrum.

## Adobe statistisk metod

Adobe har antagit en statistisk metod som bygger på [Sekvenser för alltid giltiga förtroenden](https://doi.org/10.48550/arXiv.2103.06476).

En konfidenssekvens är en sekventiell analog till ett konfidensintervall. För att förstå vad en konfidenssekvens är kan du föreställa dig att du upprepar dina experiment hundra gånger och beräknar en uppskattning av medelvärdet för affärsmätningen (t.ex. öppningsfrekvensen för ett e-postmeddelande) och dess associerade 95-procentiga konfidenssekvens för *alla nya användare* som kommer in i experimentet. En 95-procentig konfidenssekvens kommer att innehålla det &quot;sanna&quot; värdet för affärsmåttet i 95 av de 100 experiment som du utförde. (Ett 95-procentigt konfidensintervall kunde endast beräknas en gång per experiment för att ge samma 95-procentiga garanti. inte med alla nya användare). Med Confidence Sequences kan du därför kontinuerligt övervaka experiment utan att öka andelen falskt positiva fel, dvs. de tillåter&quot;sökning&quot; vid resultat.
