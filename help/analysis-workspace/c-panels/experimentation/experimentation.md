---
description: Lär dig mer om hur du kan analysera resultaten av A/B-tester på CJA Experimentation-panelen.
title: Panelen Experimentation
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
source-git-commit: 69331f1ad3699c4a01d782fe11d4f2212c703190
workflow-type: tm+mt
source-wordcount: '0'
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

Det rekommenderade dataschemat är att experimentdata finns i en Object-array som innehåller experimentella data och variantdata i två olika dimensioner. Om du har experimenterat med data i en enda dimension med experiment- och variantdata i en avgränsad sträng kan du använda [delsträng](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/substring.html?lang=en#) ange i datavyer för att dela upp dem i två för användning på panelen.

Efter att dina experimentdata har [inkapslad](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=en) till Adobe Experience Platform, [skapa en anslutning i CJA](/help/connections/create-connection.md) till en eller flera experimentdatauppsättningar.

## Steg 2: Lägga till kontextetiketter i datavyer

I inställningarna för CJA-datavyer kan administratörer lägga till [kontextetiketter](/help/data-views/component-settings/overview.md) till mått eller mätvärden och CJA-tjänster som [!UICONTROL Experimentation] kan använda dessa etiketter för sina ändamål. Två fördefinierade etiketter används för panelen Experimentation:

* [!UICONTROL Experiment]
* [!UICONTROL Variant]

I datavyn som innehåller experimentella data väljer du två dimensioner, en med experimentella data och en med variantdata. Ge sedan måtten etiketten med **[!UICONTROL Experiment]** och **[!UICONTROL Variant]** etiketter.

![kontextetikett](../assets/context-label.png)

Utan dessa etiketter fungerar inte Experimentpanelen eftersom det inte kommer att finnas några experiment att arbeta med.

## Steg 3: Konfigurera panelen Experimentera

1. I CJA Workspace drar du panelen Experimentation till ett projekt.

![experimentpanel](../assets/experiment.png)

>[!IMPORTANT]
>Om de nödvändiga inställningarna i CJA-datavyer inte har slutförts får du ett meddelande om detta innan du kan fortsätta.

1. Konfigurera panelens indatainställningar.

   | Inställning | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | En uppsättning variationer för en upplevelse som exponerats för slutanvändare för att avgöra vilken som är bäst att behålla för all framtid. Ett experiment består av två eller flera varianter, varav en betraktas som kontrollvariant. Den här inställningen är förifylld med de dimensioner som har märkts med  **[!UICONTROL Experiment]** i datavyer och de tre senaste månadernas experimentdata. |
   | **[!UICONTROL Control Variant]** | En av två eller flera förändringar i en slutanvändares upplevelse som jämförs i syfte att identifiera det bättre alternativet. En variant måste väljas som kontroll och endast en variant kan anses vara kontrollvariant. Den här inställningen är förifylld med de dimensioner som har märkts med  **[!UICONTROL Variant]** etikett i datavyer. Den här inställningen hämtar upp de variantdata som är associerade med det här experimentet. |
   | **[!UICONTROL Success Metrics]** | Mätvärden eller mätvärden som en användare jämför varianter med. Den variant som har det mest önskade resultatet för konverteringsmåttet (oavsett om det är högst eller lägst) deklareras som den&quot;bästa varianten&quot; i ett experiment. Du kan lägga till upp till 5 mätvärden. |
   | **[!UICONTROL Normalizing Metric]** | Grunden ([!UICONTROL People], [!UICONTROL Sessions], eller [!UICONTROL Events]) som testet ska köras på. Ett test kan t.ex. jämföra konverteringsgraden för flera variationer där **[!UICONTROL Conversion rate]** beräknas som **[!UICONTROL Conversions per session]** eller **[!UICONTROL Conversions per person]**. |
   | **[!UICONTROL Date Range]** | Datumintervallet ställs automatiskt in baserat på den första träffen i CJA för det valda experimentet. Detta kan ändras för att begränsa eller utöka datumintervallet till en mer specifik tidsram om det behövs. |

1. Klicka på **[!UICONTROL Build]**.

## Steg 4: Tolka panelutdata

Experimentationspanelen returnerar en mängd data och visualiseringar som hjälper dig att förstå hur dina experiment fungerar bättre. Ett globalt filter läggs till för personer eller sessioner som exponeras för flera varianter. Det går inte att redigera eller ta bort det här filtret. Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt. Du kan när som helst redigera panelen genom att klicka på redigeringspennan längst upp till höger.

Du får också en textsammanfattning som anger om experimentet är slutgiltigt eller inte och som sammanfattar resultatet. Slutsatsen baseras på statistisk signifikans. (Se Statistisk metod nedan.) Den bästa varianten tillhandahålls endast för ett experiment som är entydigt och som väljs baserat på konverteringsgraden för de viktiga varianterna. Du kan se sammanfattningsnummer för den mest högpresterande varianten med högsta lyft och självförtroende.

Textsammanfattnings- och sammanfattningsnumren genereras endast för det första framgångsmåttet som valts i panelindata.

>[!NOTE]
>
>Lyft och förtroende är också avancerade beräknade mätfunktioner i CJA, så att ni kan bygga egna lift- och Confidence-mått.

![experimentera fram](../assets/exp-output1.png)

För varje framgångsmått du valt visas en frihandstabell och en konverteringsgrad:

![experimentera fram](../assets/exp-output2.png)

The [!UICONTROL Line] diagrammet ger dig [!UICONTROL Control] kontra [!UICONTROL Control Variant] prestanda:

![experimentera fram](../assets/exp-output3.png)
>[!NOTE]
>
>Den här panelen stöder för närvarande inte analys av A/A-tester.

## Statistikmetod

Följ.
