---
description: Lär dig hur du exporterar en fullständig tabell till en molnplats.
keywords: Analysis Workspace
title: Exportera hela tabeller till molnet
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: c16fc1a239c9ce1b701b3d03539bc9696f1c6489
workflow-type: tm+mt
source-wordcount: '2229'
ht-degree: 1%

---

# Exportera fullständiga tabeller till molnet {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Skapa fullregisterexporter som liknar Data Warehouse"
>abstract="Fullständig tabellexport är tillgänglig så snart du ser data i Analysis Workspace. Du kan skapa eller schemalägga fullständig tabellexport efter behov.<br><br>Det tar bara några minuter att slutföra skapandet av fullständig tabellexport om du redan vet vilka data som ska inkluderas i exporten."

<!-- markdownlint-enable MD034 -->

Du kan exportera Analysis Workspace fullständiga tabeller från Customer Journey Analytics och skicka exporter till angivna molnmål.

Det finns även andra metoder för att exportera Customer Journey Analytics-rapporter, vilket beskrivs i [Översikt över export](/help/analysis-workspace/export/export-project-overview.md).

## Förstå fullständig tabellexport

Du kan exportera fullständiga tabeller från Analysis Workspace till molnleverantörer som Google, Azure, Amazon och Adobe.

[Fördelarna med att exportera fullständiga tabeller till molnet](#advantages-of-exporting-to-the-cloud) är bland annat möjligheten att exportera miljontals rader, inkludera beräknade värden, strukturera data i sammanfogade värden och mycket annat.

Tänk på följande när du exporterar fullständiga tabeller:

* Innan du exporterar till molnet måste du kontrollera att tabellerna, miljön och dina behörigheter uppfyller [exportkraven](#export-requirements).

* Vissa [funktioner](#unsupported-features) och [komponenter](#unsupported-components) stöds inte vid export av fullständiga tabeller till molnet.

Använd följande process när du exporterar fullständiga tabeller till molnet:

1. [Konfigurera ett molnkonto](/help/components/exports/cloud-export-accounts.md)

1. [Konfigurera en plats på kontot](/help/components/exports/cloud-export-locations.md)

1. [Exportera en fullständig tabell från Workspace](#export-full-tables-from-analysis-workspace)

1. [Få åtkomst till data i molnet](#view-exported-data-and-manifest-file) och [Hantera exporter i Adobe](/help/components/exports/manage-exports.md)

![Hela tabellexportprocessen som beskrivs i steg 1 till 4.](assets/export-full-table-process.png)

## Exportera fullständiga tabeller  {#export-from-workspace}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="export-manifest"
>title="Manifest-fil"
>abstract="När det här alternativet är aktiverat inkluderas en manifestfil i alla slutförda exportleveranser. Manifestfilen gör att du kan bekräfta att alla filer har levererats."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Läs mer om fullständig tabellexport i avsnittet [Förstå fullständig tabellexport](#understand-full-table-export) innan du exporterar data enligt beskrivningen i det här avsnittet.

Så här exporterar du fullständiga tabeller från Analysis Workspace:

1. Om du inte redan har det konfigurerar du ett exportkonto och en plats enligt beskrivningen i [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md).

1. I Analysis Workspace väljer du [!UICONTROL **Exportera fullständig tabell**] på snabbmenyn för en friformstabell.

   ![Listrutan Frihandstabell med Exportera fullständig tabell markerad.](assets/export-full-table.png)

1. Ange följande information i dialogrutan [!UICONTROL **Ny fullständig tabellexport**]:

   | Fältnamn | Funktion |
   |---------|----------|
   | Namn | Ange ett namn för exporten. Det här namnet visas i listan över exporter. |
   | Taggar | Du kan lägga till en befintlig tagg i exporten eller skapa en ny tagg och använda den. <p>Om du vill använda en befintlig tagg på exporten markerar du eventuella taggar i listrutan. Alla taggar i ditt företag är tillgängliga för att tillämpa <!-- double-check this -->.</p> <p>Om du vill skapa en ny tagg skriver du namnet på den nya taggen och trycker sedan på Retur.</p><p>Tänk på följande när du lägger till märkord i en export: <ul><li>Taggar som du använder kan filtreras eller sökas efter i exporttabellen.</li> <li>Taggar som används i ett projekt används inte automatiskt vid export av en fullständig tabell, vilket beskrivs i Konfigurera kolumner på exportsidan i [Hantera exporter](/help/components/exports/manage-exports.md). (När [schemalägger ett helt projekt för export](/help/analysis-workspace/export/t-schedule-report.md) används automatiskt alla taggar som används i projektet på exporten.) <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Beskrivning | Lägg till en beskrivning till exporten. Du kan välja att visa beskrivningar som en kolumn på [exportsidan](/help/components/exports/manage-exports.md) när du visar exporter. |
   | Datavy | Markera datavyn som innehåller de komponenter som du vill inkludera i exporten. Listrutan ![Datavy](/help/assets/icons/Data.svg) finns i dialogrutans övre vänstra hörn.  <p>**Obs!** Om du väljer en datavy som saknar komponenter som redan ingår i datatabellen, uppmanas du att rensa och återskapa panelen med komponenter som ingår i den valda datavyn. </p> |
   | Fönstret Lookback | Välj den tidsram för rapportering som ska inkluderas i varje exportfil. Du kan välja mellan [!UICONTROL **Idag**], **[!UICONTROL Yesterday]**, **[!UICONTROL Last 7 days]**, **[!UICONTROL Last 30 days]**, **[!UICONTROL This week]** och **[!UICONTROL This month]**. <p>Det här alternativet visas inte när **[!UICONTROL Export frequency]** är inställd på **[!UICONTROL Send now (one-time)]**. |
   | Datatabell | Visar friformstabellen som du exporterar. Du kan ändra datatabellen genom att dra komponenter från den vänstra panelen till tabellen. Tabellen uppdateras dynamiskt när du lägger till komponenter på arbetsytan.  <p>Alla segment som har tillämpats på den fullständiga tabellen i projektet visas högst upp i varje enskild kolumn i tabellen.</p> |
   | Rensa | Raderar innehållet i datatabellen. På så sätt kan du börja skapa en ny tabell direkt i dialogrutan Ny fullständig tabellexport. |
   | Exportfrekvens | Ange schemat för hur ofta exporten ska ske. <p>Du kan välja [!UICONTROL **Skicka nu (en gång)**] om du bara vill skicka exporten en gång. När du väljer det här alternativet påbörjas exporten omedelbart.<p>Du kan också välja att skicka exporten enligt ett angivet schema. När du skickar ett schema kan du välja mellan alternativen **[!UICONTROL Daily]**, **[!UICONTROL Weekly]**, **[!UICONTROL Monthly by day of the week]**, **[!UICONTROL Monthly by day of the month]**, **[!UICONTROL Yearly by day of the month]** och **[!UICONTROL Yearly by specific date]**. </p><p>Tänk på följande när du väljer en exportfrekvens:</p><ul><li>Alternativen i fältet **[!UICONTROL Lookback window]** ändras beroende på vad du väljer här.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Ytterligare konfigurationsfält visas beroende på vilket alternativ du väljer.</li></ul> |
   | Startar | Den dag och tid då den schemalagda exporten ska börja. <p>Det här alternativet är bara tillgängligt när du väljer en schemalagd exportfrekvens.</p> |
   | Slutar på | Den dag och tid då den schemalagda exporten upphör. Den schemalagda exporten körs inte längre efter det datum och den tidpunkt som du angav. <p>Det här alternativet är bara tillgängligt när du väljer en schemalagd exportfrekvens.</p> |
   | Filformat | Välj om exporterade data ska vara i CSV- eller JSON-format. |
   | Inkludera manifestfil | När det här alternativet är aktiverat inkluderas en manifestfil i alla slutförda exportleveranser. Manifestfilen gör att du kan bekräfta att alla filer har levererats. Den innehåller följande information:<ul><li>En lista över alla filer som levererats</li><li>MD5-kontrollsumman för varje fil</li></ul><p>Exporterade data är tillgängliga som en komprimerad fil i molndestinationen som du konfigurerade, enligt beskrivningen i [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md) och [Konfigurera molnexportplatser](/help/components/exports/cloud-export-locations.md).</p><p>Filnamnet för den komprimerade filen är följande, beroende på om du väljer CSV eller JSON som filformat:</p><ul><li>`cja-export-{reportInstanceId}-{idx}.csv.gz`</li><li>`cja-export-{reportInstanceId}-{idx}.json.gz`</li></ul><p>Du väljer filformatet i fältet **[!UICONTROL *Filformat**] ovan.</p> |
   | Konto | Välj det exportkonto i molnet där du vill att data ska skickas. <p>Om du inte redan har konfigurerat ett molnkonto som du vill använda kan du konfigurera ett nytt konto:<ol><li>Välj **[!UICONTROL Add account]** och ange sedan följande information:<ul><li>**[!UICONTROL Location account name]**: Ange ett namn för platskontot. Det här namnet visas när du skapar en plats </li><li>**[!UICONTROL *ocation account description]**: Ange en kort beskrivning av kontot för att hjälpa till att skilja det från andra konton av samma kontotyp.</li><li>**[!UICONTROL Account type]**: Välj den typ av molnkonto som du exporterar till. De tillgängliga kontotyperna är Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake och AEP Data Landing Zone.</li></ul><li>Om du vill slutföra konfigurationen av ditt konto fortsätter du med länken nedan som motsvarar **[!UICONTROL Account type]** som du har valt:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3-roll ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud-plattform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Plats | Välj den plats på kontot där du vill att exportdata ska skickas.<p>Om du inte redan har konfigurerat platsen som du vill använda på kontot som du har valt kan du konfigurera en ny plats:<ol><li>Välj **[!UICONTROL *dd location]** och ange sedan följande information: <ul><li>**[!UICONTROL Name]**: Platsens namn.</li><li>**[!UICONTROL Description]**: Ange en kort beskrivning av platsen för att hjälpa till att skilja den från andra platser på kontot.</li><li>**[!UICONTROL Location account]**: Välj det konto där du vill skapa platsen.</li></ul><li>Om du vill slutföra konfigurationen av din plats fortsätter du med länken nedan som motsvarar kontotypen som du valde i fältet **[!UICONTROL Location account]**:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3-roll ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud-plattform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Spara**] om du vill spara exporten.

   Data skickas till molnkontot som du angav med den frekvens som du angav.

1. (Valfritt) När du har skapat exporten, oavsett om du valde att skicka den nu eller enligt ett definierat schema, kan du visa och hantera den på [exportsidan](/help/components/exports/manage-exports.md) och visa den i [exportloggarna](/help/components/exports/manage-export-logs.md).</p>

## Hantera exporter

När data har exporterats från Analysis Workspace kan du redigera, exportera om, duplicera, tagga eller ta bort befintliga exporter enligt beskrivningen i [Hantera exporter](/help/components/exports/manage-exports.md).

## Fördelar med fullständig tabellexport {#advantages}

Genom att exportera Customer Journey Analytics-data till molnet kan du:

* Exportera till en delad plats, som Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 eller Snowflake.

* Lagra stora mängder historiska data.

  Den här typen av data kan användas för att upptäcka långsiktiga trender för att ta till vara affärsintelligens och i slutänden leda till bättre beslutsunderlag.

* Exportera hela tabeller som innehåller tusentals eller miljontals rader (3 miljoner, 30 miljoner, 150 miljoner eller 300 miljoner rader, beroende på licenstyp). Andra exportmetoder tillåter högst 50 000 rader.

* Inkludera beräknade värden i exporterade Customer Journey Analytics-data.

* Strukturera utdata som sammanfogade värden.

* Exportera en gång eller enligt ett schema. (Även tillgängligt med [andra exportalternativ](/help/analysis-workspace/export/export-project-overview.md).)

* Exportera filer i CSV- eller JSON-format. (Även tillgängligt med [andra exportalternativ](/help/analysis-workspace/export/export-project-overview.md).)

* Exportera tabeller som innehåller flera dimensioner.

## Minimikrav

Se till att tabellerna, miljön och behörigheterna uppfyller följande krav:

* **Tabeller:** Alla tabeller måste innehålla minst en dimension i raden och ett mått i varje kolumn för att kunna hanteras med en export i en hel tabell.

* **Miljö:** Kontrollera att de [IP-adresser](/help/technotes/ip-addresses.md) och [domäner](/help/technotes/domains.md) som används av Customer Journey Analytics tillåts via organisationens brandvägg.

* **Behörigheter:** I Adobe Admin Console måste användare tilldelas en produktprofil som har behörigheten **[!UICONTROL Full Table Export]** för att kunna exportera fullständiga tabeller. Information om hur du tilldelar en produktprofil behörighet i Admin Console finns i [Customer Journey Analytics-behörighet i Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Användare som har tilldelats rollen [Produktadministratör](/help/technotes/access-control.md#product-admin-role) har alltid åtkomst till att exportera fullständiga tabeller. Dessa användare behöver inte tilldelas behörigheten **[!UICONTROL Full Table Export]**.


## Funktioner som inte stöds

Följande funktioner stöds inte och tas automatiskt bort från export i fulltabell:

* Procenttal
* Summor
* Sökfiltrering
* Statiska rader
* Datumjustering
* Mätvärden från sammanfattningsdatauppsättningar
* Dynamiska dimensionsobjekt

  Dynamiska dimensionsobjekt skapas när du släpper en dimension i en kolumnrubrik i en friformstabell, vilket gör att kolumnen filtreras dynamiskt av de fem övre dimensionsobjekten. I Analysis Workspace uppdateras dessa fem viktigaste dimensionsobjekt varje gång du läser in projektet. Vid en export i fullformat blir dessa dimensionsobjekt statiska. Mer information finns i [Dynamiska och statiska dimensionsobjekt i frihandstabeller](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Dimensioner i den första uppdelningen konverteras och läggs till som en sekundär dimension på raden i den exporterade tabellen. Andra uppdelningar tas inte med i tabellen.
* Sortering stöds inte för de flesta datauppsättningar. Data kan sorteras för små datauppsättningar.

## Komponenter som inte stöds

Följande komponenter stöds inte och Analysis Workspace uppmanar dig att ta bort dem från tabellen när du exporterar hela tabeller:

* Beräknade mått som använder grundläggande eller avancerade funktioner i metrisk definition (mer information finns i [Grundfunktioner](/help/components/calc-metrics/cm-functions.md) och [Avancerade funktioner](/help/components/calc-metrics/cm-adv-functions.md))
* Komponenter som har begränsats av en administratör från att exporteras (mer information finns i avsnittet *Segment om datastyrningsprinciper i datavyer* i [Etiketter och profiler](/help/data-views/data-governance.md) )
* Alla dimensioner som uppfyller alla följande kriterier:
   * Skapas från ett fält som är en del av en [objektmatris](/help/use-cases/object-arrays.md) (liknar flervärdesvariabler i Adobe Analytics).
   * Har [persistence aktiverat](/help/data-views/component-settings/persistence.md).
   * Använder inte en [bindningsdimension](/help/use-cases/data-views/binding-dimensions-metrics.md).
* Flera dimensioner från fält som refererar till olika [arrayer av objekt](/help/use-cases/object-arrays.md). (Flera dimensioner som refererar till samma array med objekt tillåts.)
* Mer än 10 dimensioner och 10 mätvärden per rapport (upp till 10 dimensioner och 10 mätvärden stöds)
* I tabellkolumner:
   * Datumintervall
   * Mått
* I tabellrader:
   * Beräknade mått
   * Mätvärden
   * Datumintervall
   * Segment

## Attributionsbeteende

Fullständig tabellexport stöder beräknade värden som använder en icke-standardattribueringsmodell (vilket beskrivs i avsnittet *Använd icke-standardattribueringsmodell* i [Kolumninställningar](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)).

Om en attribueringsmodell som inte är standard används i en rapport ignoreras eller behålls allokeringsmodellen som används i rapporten, beroende på om rapporten har en enda dimension eller flera dimensioner:

* **För rapporter som inkluderar metrisk attribuering i en enda dimension:** [Metrisk attribuering](/help/data-views/component-settings/attribution.md) åsidosätter [allokeringsmodellen](/help/data-views/component-settings/persistence.md) på samma sätt som normalt när metrisk attribuering används.

  Exempelvis åsidosätter en första beröring-metrisk attribuering en &quot;senaste&quot; dimensionsallokering.

* **För rapporter som innehåller metrisk attribuering för flera dimensioner samtidigt:** [Måttattribuering](/help/data-views/component-settings/attribution.md) tillämpas utöver dimensionens [allokeringsmodell](/help/data-views/component-settings/persistence.md).

  Till exempel används en första beröring-metrisk attribuering utöver den&quot;senaste&quot; dimensionsallokeringen. Dessutom tillämpas metrisk attribuering på post-allokerade dimensionsobjektpar som om de vore enskilda dimensionsobjekt, i stället för på varje dimensionsobjekt separat, som normalt görs i en frihandsritabell.

  >[!NOTE]
  >
  >Flerdimensionella rapporter stöds bara när data exporteras till molnet, vilket beskrivs i den här artikeln.

## Jämförelse med Data Warehouse

Om du tidigare använde Data Warehouse för att exportera Adobe Analytics-data kan följande tabell hjälpa dig att förstå skillnaden mellan att exportera fullständiga tabeller i Customer Journey Analytics och att exportera data med Data Warehouse i Adobe Analytics.


| Funktion | Fullständig tabellexport i Customer Journey Analytics | DATA WAREHOUSE i ADOBE ANALYTICS |
|---------|----------|---------|
| Skapa en anpassad rapport | Ja | Ja |
| Beräknade mått | Ja | Nej |
| Segment | Ja | Begränsad |
| Mått | Gräns 10 | Obegränsad |
| Mätvärden | Gräns 10 | Obegränsad |
| Rapporteringsrader | Gräns på 3 miljoner, 30 miljoner, 150 miljoner eller 300 miljoner, beroende på skikt | Obegränsad |
| Antal rapporter | Obegränsad | Obegränsad |
| Ad hoc-leverans (en gång) | Ja | Ja |
| Schemalägg återkommande leverans | Ja | Ja |
| E-postleverans | Nej | Ja |
| FTP/SFTP | Nej | Stöd för äldre versioner |
| Azure | Ja | Ja |
| Amazon S3 | Ja | Ja |
| Google Cloud Platform | Ja | Ja |
| Snowflake | Ja | Nej |
| Leveransfrekvens | Dagligen | Varje timme |
