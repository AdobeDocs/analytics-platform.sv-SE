---
description: Mallar på arbetsytan
title: Mallar
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: tm+mt
source-git-commit: c7bf87b4ff3a7d0da930a22336db762fa3d74393
workflow-type: tm+mt
source-wordcount: '1407'
ht-degree: 3%

---


# Mallar

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan välja om du vill skapa ett projekt från:

* **Tomt projekt (standard)**: Instruktioner finns i [Skapa ett Analysis Workspace-projekt](/help/analysis-workspace/home.md).
* **Standardmall**: De här mallarna skapas av Adobe och levereras med produkten.
* **Anpassad mall**: Dessa mallar kan skapas, delas eller tas bort av användare med administratörsrättigheter eller av icke-administratörer, förutsatt att de har tilldelats [!UICONTROL Analysis Workspace: Save as Template] behörighet i administratörskonsolen. [Läs mer …](https://docs.adobe.com/content/help/en/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Skapa en anpassad mall {#create-custom-template}

Användare med administratörsbehörighet kan omvandla alla projekt de skapar till en anpassad mall. Så här:

1. Öppna projektet.
1. Gå till **[!UICONTROL Project]** > **[!UICONTROL Save As Template]**.

   ![](assets/save_project_template.png)

   Projektet sparas under det aktuella projektnamnet, följt av ordet (mall) inom parentes. Administratörer kan ändra namnet genom att redigera mallen.

   >[!NOTE]
   >
   >Som standard visas projektmallar för alla i organisationen. Du kan ordna dem genom att använda taggar. (Gå till **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]** för att redigera taggar och beskrivningar.)

### Åtgärder som du kan utföra på anpassade mallar

![](assets/custom_templates.png)

| Åtgärd | Beskrivning |
|--- |--- |
| Redigera mall | Gör att en administratör kan redigera mallen genom att ändra dess datakälla, ändra komponenter, visualiseringar, datumintervall osv.  Så här redigerar du en anpassad mall:<ul><li>Ladda upp listan med egna mallar i Analysis Workspace, markera en och klicka på Redigera mall, eller</li><li>Navigera till Komponenter > Projekt i Analytik och filtrera sedan på Mallar. Klicka på namnet på mallen som du vill redigera.</li></ul>**Anmärkning:** När du har redigerat en mall kan du välja mellan två alternativ: Spara, spara som. Så här skiljer sig de åt:<ul><li>**Spara:** Uppdaterar den anpassade mallen för alla användare. När någon annan skapar ett projekt från den här anpassade mallen visas de ändringar du har gjort.</li><li>**Spara som:** Skapar en kopia av den anpassade mallen med dina ändringar. (Du kan se att du är i redigeringsläge när menyalternativet Dela > Dela projekt är inaktiverat.)</li></ul> |
| Sök efter mallar | I dialogrutan Anpassade mallar klickar du på Sökmallar. |
| Sortera mallar | Du kan sortera mallar i alfabetisk ordning, efter relevans och efter skapandedatum.  I dialogrutan Anpassade mallar klickar du på Sortera:. |
| Använd taggar på mall | Öppna mallen och gå till Projekt > Projektinformation och inställningar. Klicka på Lägg till taggar. |
| Ändra mallbeskrivning | Öppna mallen och gå till Projekt > Projektinformation och inställningar. Dubbelklicka på beskrivningen och redigera den. |


## Standardmallar

När du först öppnar en arbetsyta finns mallarna tillgängliga på vänster räls. Analysarbetsytemallar omfattar vanliga användningsfall. De grupperas efter den lodräta version de tillhör och fylls i med olika dimensioner, segment, mått och visualiseringar, beroende på vilket rapportpaket du har valt.

Du kan använda de här förfyllda mallarna som de är eller anpassa dem efter dina behov (t.ex. genom att lägga till eller ersätta mått eller visualiseringar) och spara dem under ett nytt namn.

[Standardmallar i Analysis Workspace på YouTube](https://www.youtube.com/watch?v=aRgYwPneVXg&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&amp;index=6) 2:46)

Här finns tillgängliga mallar och frågor som varje mall kan besvara.

### Utbildning

Med de här standardmallarna kan du använda vanlig terminologi och steg för att bygga din första analys på arbetsytan. De är tillgängliga som en standardmall i modala New Project och ersätter det exempelprojekt som finns i dag för nya användare som inte har andra projekt i sin lista.

* **Självstudiekurs - analys av intern sökning**: Självstudiekursen för intern sökning hjälper dig att förstå vad dina besökare söker efter på webbplatsen eller appen, men inte hitta. Om du analyserar den här typen av data kan du få möjlighet att optimera innehållet.

* **Självstudiekurs - Marknadsföringsanalys**: Den här självstudiekursen visar hur du sammanställer en marknadsföringsanalys för dina chefer, inklusive vilka anpassade dimensioner och mått som är viktiga.

### Reklam

>[!IMPORTANT]
>
>Annonsmallar är bara tillgängliga om rapportsviten är aktiverad för reklammolnet.

* **Betalade sökmotorer**: Den här mallen delar upp annonstrender, annonsplattformar, nyckelord, konton, kampanjer med mera.

### Handel

* **Magento: Marknadsföring och handel**: Den här mallen delar upp din handelskonvertering efter tilldelning av marknadsföringskanaler och ger inblick efter söknyckelord, landningssida, geografisk plats med mera. En videoöversikt finns i >[!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw)

### Media

* **Ljudförbrukning**: Vilket innehåll konsumeras mest och engagerar användarna?
* **Recency - Frequency - Loyalty**: Vilka är mina lojala läsare?

### Mobil

>[!IMPORTANT]
>
>Mobilmallar är bara tillgängliga om rapportsviten är aktiverad för Mobile.

* **Meddelanden:** Fokuserar på prestanda för in-app och push-meddelanden.
* **Plats:** Innehåller en karta med platsdata för visning av visning.
* **Nyckelmått:** Behåll pulsen på nyckelmåtten för appen.
* **Appanvändning:** Hur många appanvändare, starter och första starter har appen och vilken var den genomsnittliga sessionslängden?
* **Förvärv:** Se hur mobila inköpslänkar fungerar.
* **Prestanda:** Hur fungerar appen och var har användarna problem?
* **Behåll:** Vilka är mina lojala användare och vad gör de?
* **Resor:** Vilka är de främsta användningsmönstren för min app?

### Detaljhandel

* **Kampanjprestanda:** Vilka kampanjer är mest inkomstbringande?
* **Produkter:** Vilka produkter fungerar bäst?

### Webb

* **Förvärv:** Vilka är de främsta trafikförarna på min webbplats?
* **Innehållsförbrukning:** Vilka är de bästa platserna som folk går på min webbplats?
* **Behåll:** Vilka typer av användare är det troligt att de kommer att vara lojala användare av min webbplats?
* **Teknik:** Vilken teknik använder folk för att komma åt min webbplats?

### Personer

>[!NOTE]
>
>Mallen Personer och tillhörande personmått är endast tillgänglig för användning som en del av [Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/sv-SE/device-co-op/using/data/people.html).

Den här mallen är baserad på personmåttet, som är en avduplicerad version av måttet Unika besökare. Mätvärdet Personer är ett mått på hur ofta konsumenter som använder flera enheter interagerar med ert varumärke. Med mallen kan du

* Segmentera dina data för USA/Kanada jämfört med resten av världen. Device Co-op är för närvarande endast tillgänglig i Nordamerika.
* Jämför måttet Personer och unika besökare sida vid sida.
* Se &quot;komprimeringshastigheten&quot;, ett beräknat mått som beräknar hur mycket mindre personmåttet är i procent av Unika besökare.
* Jämför de totalsummor för enhetstyp som dina kunder använder
* Se hur många genomsnittliga enheter per person som används.
* Upptäck hur du använder segmentstapling med personmåttet.
* Utforska hur användningen av Experience Cloud ID i din miljö ökar effektiviteten i People-måttet.

### Journey IQ: Mall för korsenhetsanalys

<!--This content is mirrored in the CDA doc.-->

Med den här mallen kan du se viktiga prestandadata för flera enheter. Den är endast tillgänglig för kunder som har tillgång till [Enhetskoppling](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) (CDA).

* **Särskild anmärkning för medlemmar i Coop Graph**: Visar vilken del av rapportsviten som innehåller besökare i regioner där koordinatdiagrammet stöds och regioner där det inte stöds.
* **Identifiering av användare**: Visar hur ofta besökare på webbplatsen identifieras med metoder baserade på korsenhetsanalys.
* **Mått på målgruppens storlek**: Visar en jämförelse mellan Unika enheter och Personer. Andelen av dessa två tal kallas &quot;komprimering mellan enheter&quot;, ett beräknat mått som visas på den här panelen. Komprimeringsmetersystemet är beroende av ett brett spektrum av faktorer:
   * **Använda CoUP-diagram eller privat diagram**: I allmänhet ser organisationer som använder enhetssamspelet oftast bättre komprimeringshastigheter än organisationer som använder det privata diagrammet.
   * **Inloggningshastighet**: Ju fler användare som loggar in på din webbplats, desto mer kan Adobe identifiera och sammanfoga besökare mellan olika enheter. Platser med låg inloggningshastighet har också låg komprimeringshastighet.
   * **Upplev molnidentitetstäckning**: Endast besökare med ett ECID kan sys ihop. En lägre andel besökare på platsen med hjälp av ett ECID-nummer korrelerar till lägre komprimeringstakt.
   * **Användning av flera enheter**: Om besökare på webbplatsen inte använder flera enheter kan du se lägre komprimeringshastigheter.
   * **Rapporteringsgranularitet**: Komprimering per dag är vanligtvis mindre än komprimering per månad eller år. Möjligheten för en person att använda flera enheter blir mindre inom en enda dag än under en hel månad. Segmentering, filtrering eller användning av nedbrytningsdimensioner kan också visa en lägre komprimeringshastighet.
* **Personbaserade segment**: Innehåller en segmentlistruta där du kan visa enhetsspecifika data. På den här panelen uppmuntras till försök med segment för att se hur rapporter påverkas av att inkludera eller utesluta enhetstyper.
* **Analys av körningen mellan enheter**: Tillhandahåller flödes- och utfallsrapporter baserat på enhetstyp.
* **Tilldelning mellan enheter**: Kombinera funktionerna i Journey IQ och Attribution IQ tillsammans.
* **Andra tips och tricks**: Hjälpämnen runt CDA som gör att du kan få ut mer av det.