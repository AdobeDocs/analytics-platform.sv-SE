---
description: Hantera befintlig export
keywords: Analysis Workspace
title: Hantera exporter
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: ad43b199d4174894f0e428bcaf1748ca80bddb45
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 0%

---

# Hantera exporter

När du har exporterat en fullständig tabell enligt beskrivningen i [Exportera Customer Journey Analytics-rapporter till molnet](/help/analysis-workspace/export/export-cloud.md)är exporten tillgänglig på [!UICONTROL Exports] på [!UICONTROL Exports] sida.

Du kan bara se de exporter som du skapar.

## Filtrera och söka efter exporter

Om du vill hitta den information du behöver kan du antingen filtrera exportlistan eller söka efter en export.

### Filtrera listan med exporter

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].

1. Välj [!UICONTROL **Export**] -fliken.

1. Välj **Filter** -ikon.

   <!--add screenshot -->

   Du kan filtrera efter följande kriterier:

   | Filter | Beskrivning |
   |---------|----------|
   | [!UICONTROL **Kontotyp**] | Kontotypen som exporten är kopplad till. Följande kontotyper är tillgängliga: <ul><li>[!UICONTROL **AEP Data Landing Zone**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Snowflake**]</li></ul>. |
   | [!UICONTROL **Status**] | Exportstatus. Följande statusar är tillgängliga: <ul><li>[!UICONTROL **Aktiv**]: Anger att en schemalagd export ännu inte har gått ut eller att en engångsexport ännu inte har slutförts. </li><li>[!UICONTROL **Slutförd**]: Anger att en export har exporterats. För schemalagd export innebär detta att tidsplanen har gått ut.</li><li>[!UICONTROL **Misslyckades**]<p>Följande situationer kan leda till en misslyckad export. Hovra över [!UICONTROL **Misslyckades**] status för att se information om felet. <ul><li>Schemalagd exportförfallotid</li><li>Radgränsen för schemalagd export har uppnåtts </li></ul> </p></li></ul> |
   | [!UICONTROL **Frekvens**] | Hur ofta exporten sker. Följande frekvenser är tillgängliga: <ul><li>[!UICONTROL **En gång**]</li><li>[!UICONTROL **Dagligen**]</li><li>[!UICONTROL **Vecka**]</li><li>[!UICONTROL **Månadsvis**]</li><li>[!UICONTROL **Årsvis**]</li></ul> |

   {style="table-layout:auto"}

### Sök efter exporter

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].

1. Välj [!UICONTROL **Export**] -fliken.

1. I sökfältet börjar du skriva in information som är kopplad till den export du söker efter. Du kan söka efter data från alla kolumner som är tillgängliga i tabellen.

## Redigera och exportera

Du kan redigera egenskaper, format, schemaläggning och platsinformation för en export.

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].

1. På [!UICONTROL **Export**] markerar du kryssrutan bredvid den export som du vill redigera.

   Det här alternativet är inte tillgängligt när du väljer flera exporter.

1. Välj [!UICONTROL **Redigera**].

   The [!UICONTROL **Exportera fullständig tabell**] visas.

1. Uppdatera alla tillgängliga alternativ. Information om de olika alternativen finns i [Exportera hela tabeller från Analysis Workspace](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) in [Exportera Customer Journey Analytics-rapporter till molnet](/help/analysis-workspace/export/export-cloud.md).

## Duplicera en export

Du kan duplicera en befintlig export.

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].

1. På [!UICONTROL **Export**] markerar du kryssrutan bredvid den export du vill duplicera.

   Det här alternativet är inte tillgängligt när du väljer flera exporter.

1. Välj [!UICONTROL **Duplicera**].

   En dubblett av exporten skapas. Namnet på den nya exporten matchar namnet på den ursprungliga exporten, med _[!UICONTROL - Copy]_som läggs till i filnamnet.

1. (Valfritt) [Redigera den nya exporten](#edit-an-export), inklusive filnamnet och andra egenskaper som du vill ändra.

## Initiera en export manuellt

Du kan initiera en export manuellt, antingen för en schemalagd export eller en engångsexport som tidigare har slutförts.

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].

1. På [!UICONTROL **Export**] markerar du kryssrutan bredvid den export som du vill köra.

   Det här alternativet är inte tillgängligt när du väljer flera exporter.

1. Välj [!UICONTROL **Exportera nu**].

## Tagga en export

När du lägger till märkord i en export kan du visa dessa märkord i dialogrutan [!UICONTROL Tags] kolumn på [!UICONTROL Exports] sida. Se [Konfigurera kolumner](#configure-columns) för mer information.

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].

1. På [!UICONTROL **Export**] markerar du kryssrutan bredvid en eller flera exporter som du vill tagga.

1. Välj [!UICONTROL **Redigera taggar**].

1. I [!UICONTROL **Märkesexport**] skriver du namnet på en tagg för att skapa en ny tagg eller väljer en befintlig tagg i listrutan.

   Alla vanliga taggar mellan de markerade exporter visas i taggdialogrutan. <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. Välj [!UICONTROL **Använd taggar**].

## Ta bort en export

Du kan ta bort exporter från exportsidan. Schemalagda exporter som tas bort skickas inte längre.

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].

1. På [!UICONTROL **Export**] markerar du kryssrutan bredvid en eller flera exporter som du vill ta bort.

1. Välj [!UICONTROL **Ta bort**] väljer [!UICONTROL **Ta bort**] när bekräftelsemeddelandet visas.

## Konfigurera kolumner på [!UICONTROL Exports] page

Du kan lägga till eller ta bort kolumner på [!UICONTROL Exports] för att konfigurera vilken information som visas.

Välj en kolumnrubrik om du vill sortera exporten efter den kolumnen. Som standard sorteras exporten efter det datum och den tidpunkt då exporten senast ändrades.

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Export**].

1. På [!UICONTROL **Export**] väljer du **Anpassa tabell** icon ![anpassa tabell](assets/customize-table-icon.png) i det övre högra hörnet av [!UICONTROL Exports] sida.

   Följande kolumner är tillgängliga:

   | Tillgänglig kolumn | Beskrivning |
   |---------|----------|
   | Namn | Namnet på exporten. Användare ger exporterar ett namn när de skapar dem, vilket beskrivs i [Exportera Customer Journey Analytics-rapporter till molnet](/help/analysis-workspace/export/export-cloud.md). |
   | ID | Det ID som automatiskt tilldelas till exporten när den skapas. <!-- True? --> |
   | Datavy name | Namnet på datavyn som är associerad med exporten. Användarna kan välja datavyn när de skapar exporten, vilket beskrivs i [Exportera Customer Journey Analytics-rapporter till molnet](/help/analysis-workspace/export/export-cloud.md). |
   | Status | Exportstatus. Tillgängliga statusvärden är [!UICONTROL Active], [!UICONTROL Complete]och [!UICONTROL Failed].<p> **Obs!** Mer information om felsökning av misslyckade exporter finns i [Felsökning av misslyckade exporter](/help/components/exports/troubleshoot-exports.md).</p> |
   | Taggar | Visar eventuella märkord som används i exporten. Mer information om hur du använder märkord i en export finns i [Tagga en export](#tag-an-export). |
   | Tabellstorlek (senaste sändning) | Storleken på exporten när den senast skickades. |
   | Skapad av | Användaren som skapade exporten. |
   | Skapad | Datum och tid då exporten skapades. <!-- true? --> |
   | Plats | Platsen på kontot där data exporterades. |
   | Konto | Kontot där data exporterades. |
   | Frekvens | Den frekvens som exporten skickas med. Tillgängliga alternativ är [!UICONTROL One time], [!UICONTROL Daily], [!UICONTROL Weekly], [!UICONTROL Monthly by day of the week], [!UICONTROL Monthly by day of the month], [!UICONTROL Yearly by day of the month]och [!UICONTROL Yearly by specific date]. |
   | Skickat | Tiden då exporten skickades. |
   | Senast skickad | Senaste gången som exporten skickades. |
   | Senast ändrad | Den senaste gången som exporten ändrades. Objekt på exportsidan sorteras som standard efter den här kolumnen. |
   | Kontotyp | Typen av molnkonto där data exporterades. Tillgängliga kontotyper är [!UICONTROL Amazon S3 Role ARN], [!UICONTROL Google Cloud Platform], [!UICONTROL Azure SAS], [!UICONTROL Azure RBAC], [!UICONTROL Snowflake]och [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. Kontrollera att alla kolumner som du vill visa är markerade. Markerade kolumner visas på sidan Exportera och visar relevant information.
