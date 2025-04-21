---
description: Lär dig hur du exporterar ett Analysis Workspace-projekt till en molnplats.
keywords: Analysis Workspace
title: Exportera Customer Journey Analytics-rapporter till molnet
feature: Curate and Share
exl-id: 072eadcc-43ff-42e3-86ee-82062fa02eba
role: User
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: tm+mt
source-wordcount: '2285'
ht-degree: 1%

---

# Exportera Customer Journey Analytics-rapporter till molnet {#full-table-export}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-full-table-export"
>title="Skapa fullregisterexporter som liknar Data Warehouse"
>abstract="Fullständig tabellexport är tillgänglig så snart du ser data i Analysis Workspace. Du kan skapa eller schemalägga fullständig tabellexport efter behov.<br><br>Det tar bara några minuter att slutföra skapandet av fullständig tabellexport om du redan vet vilka data som ska inkluderas i exporten."

<!-- markdownlint-enable MD034 -->

Du kan exportera Workspace fullständiga tabeller från Customer Journey Analytics och skicka exporter till angivna molnmål.

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

## Exportera hela tabeller från Analysis Workspace

>[!NOTE]
>
>Läs mer om fullständig tabellexport i avsnittet [Förstå fullständig tabellexport](#understand-full-table-export) innan du exporterar data enligt beskrivningen i det här avsnittet.

Så här exporterar du fullständiga tabeller från Analysis Workspace:

1. Om du inte redan har det konfigurerar du ett exportkonto och en plats enligt beskrivningen i [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md).

1. I Analysis Workspace högerklickar du på friformstabellen som innehåller de data som du vill exportera.

1. Välj [!UICONTROL **Exportera hela tabellen**].

   ![Listrutan Frihandstabell med Exportera fullständig tabell markerad.](assets/export-full-table.png)

1. Ange följande information i dialogrutan [!UICONTROL **Ny fullständig tabellexport**]:

   | Fältnamn | Funktion |
   |---------|----------|
   | Namn | Ange ett namn för exporten. Det här namnet visas i listan över exporter. |
   | Taggar | Du kan lägga till en befintlig tagg i exporten eller skapa en ny tagg och använda den. <p>Om du vill använda en befintlig tagg på exporten markerar du eventuella taggar i listrutan. Alla taggar i ditt företag är tillgängliga för att tillämpa <!-- double-check this -->.</p> <p>Om du vill skapa en ny tagg skriver du namnet på den nya taggen och trycker sedan på Retur.</p><p>Tänk på följande när du lägger till märkord i en export: <ul><li>Taggar som du använder kan filtreras eller sökas efter i exporttabellen.</li> <li>Taggar som används i ett projekt används inte automatiskt vid export av en fullständig tabell, vilket beskrivs i Konfigurera kolumner på exportsidan i [Hantera exporter](/help/components/exports/manage-exports.md). (När [schemalägger ett helt projekt för export](/help/analysis-workspace/export/t-schedule-report.md) används automatiskt alla taggar som används i projektet på exporten.) <!-- Right now we don't have a column for them on the exports table, so this isn't true. Jaden is adding the column. --></li></ul> |
   | Beskrivning | Lägg till en beskrivning till exporten. Du kan välja att visa beskrivningar som en kolumn på [exportsidan](/help/components/exports/manage-exports.md) när du visar exporter. |
   | Datavy | Markera datavyn som innehåller de komponenter som du vill inkludera i exporten. Listrutan Datavy finns i dialogrutans övre vänstra hörn och kan identifieras med datavyikonen![datavyikon](assets/data-view-icon.png).  <p>**Obs!** Om du väljer en datavy som saknar komponenter som redan ingår i datatabellen, uppmanas du att rensa datatabellen och återskapa den med komponenter som ingår i den valda datavyn. </p> |
   | Fönstret Lookback | Välj den tidsram för rapportering som ska inkluderas i varje exportfil. Du kan välja mellan [!UICONTROL **I dag**], [!UICONTROL **I går**], [!UICONTROL **Senaste 7 dagarna**], [!UICONTROL **Senaste 30 dagarna**], [!UICONTROL **Den här veckan**] och [!UICONTROL **Den här månaden**]. <p>Det här alternativet visas inte när [!UICONTROL **exportfrekvensen**] är inställd på [!UICONTROL **Skicka nu (en gång)**]. |
   | Datatabell | Visar friformstabellen som du exporterar. Du kan ändra datatabellen genom att dra komponenter från den vänstra panelen till tabellen. Tabellen uppdateras dynamiskt när du lägger till komponenter på arbetsytan.  <p>Alla segment som har tillämpats på den fullständiga tabellen i projektet visas högst upp i varje enskild kolumn i tabellen.</p> |
   | Rensa | Raderar innehållet i datatabellen. På så sätt kan du börja skapa en ny tabell direkt i dialogrutan Ny fullständig tabellexport. |
   | Exportfrekvens | Ange schemat för hur ofta exporten ska ske. <p>Du kan välja [!UICONTROL **Skicka nu (en gång)**] om du bara vill skicka exporten en gång. När du väljer det här alternativet påbörjas exporten omedelbart.<p>Du kan också välja att skicka exporten enligt ett angivet schema. När du skickar enligt ett schema kan du välja mellan alternativen [!UICONTROL **Dagligen**], [!UICONTROL **Veckovis**], [!UICONTROL **Månadsvis per veckodag**], [!UICONTROL **Månadsvis per dag i månaden**], [!UICONTROL **Årsvis per dag i månaden**] och [!UICONTROL **Årsvis per specifikt datum**]. </p><p>Tänk på följande när du väljer en exportfrekvens:</p><ul><li>Alternativen i fältet [!UICONTROL **Uppslag**] ändras beroende på vad du väljer här.<!-- if they're doing Daily, then we might not let them look back to the last year... --></li><li>Ytterligare konfigurationsfält visas beroende på vilket alternativ du väljer.</li></ul> |
   | Startar | Den dag och tid då den schemalagda exporten ska börja. <p>Det här alternativet är bara tillgängligt när du väljer en schemalagd exportfrekvens.</p> |
   | Slutar på | Den dag och tid då den schemalagda exporten upphör. Den schemalagda exporten körs inte längre efter det datum och den tidpunkt som du angav. <p>Det här alternativet är bara tillgängligt när du väljer en schemalagd exportfrekvens.</p> |
   | Filformat | Välj om exporterade data ska vara i CSV- eller JSON-format. |
   | Konto | Välj det exportkonto i molnet där du vill att data ska skickas. <p>Om du inte redan har konfigurerat ett molnkonto som du vill använda kan du konfigurera ett nytt konto:<ol><li>Välj [!UICONTROL **Lägg till konto**] och ange sedan följande information:<ul><li>[!UICONTROL **Platskontonamn**]: Ange ett namn för platskontot. Det här namnet visas när du skapar en plats </li><li>[!UICONTROL **Beskrivning av platskonto**]: Ange en kort beskrivning av kontot för att skilja det från andra konton av samma kontotyp.</li><li>[!UICONTROL **Kontotyp**]: Välj den typ av molnkonto som du exporterar till. De tillgängliga kontotyperna är Amazon S3 Role ARN, Google Cloud Platform, Azure SAS, Azure RBAC, Snowflake och AEP Data Landing Zone.</li></ul><li>Om du vill slutföra konfigurationen av ditt konto fortsätter du med länken nedan som motsvarar den [!UICONTROL **kontotyp**] du valde:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-accounts.md#aep-data-landing-zone)</li><li>[Amazon S3-roll ARN](/help/components/exports/cloud-export-accounts.md#amazon-s3-role-arn)</li><li>[Google Cloud-plattform](/help/components/exports/cloud-export-accounts.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-accounts.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-accounts.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-accounts.md#snowflake)</li></ul></ol> |
   | Platsnamn | Välj den plats på kontot där du vill att exportdata ska skickas.<p>Om du inte redan har konfigurerat platsen som du vill använda på kontot som du har valt kan du konfigurera en ny plats:<ol><li>Välj [!UICONTROL **Lägg till plats**] och ange sedan följande information: <ul><li>[!UICONTROL **Namn**]: Platsens namn.</li><li>[!UICONTROL **Beskrivning**]: Ange en kort beskrivning av platsen för att skilja den från andra platser på kontot.</li><li>[!UICONTROL **Platskonto**]: Välj det konto där du vill skapa platsen.</li></ul><li>Om du vill slutföra konfigurationen av din plats fortsätter du med länken nedan som motsvarar kontotypen som du valde i fältet [!UICONTROL **Platskonto**]:<ul><li>[AEP Data Landing Zone](/help/components/exports/cloud-export-locations.md#aep-data-landing-zone).</li><li>[Amazon S3-roll ARN](/help/components/exports/cloud-export-locations.md#amazon-s3-role-arn)</li><li>[Google Cloud-plattform](/help/components/exports/cloud-export-locations.md#google-cloud-platform)</li><li>[Azure SAS](/help/components/exports/cloud-export-locations.md#azure-sas)</li><li>[Azure RBAC](/help/components/exports/cloud-export-locations.md#azure-rbac)</li><li>[Snowflake](/help/components/exports/cloud-export-locations.md#snowflake)</li></ul> |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Spara**] om du vill spara exporten.

   Data skickas till molnkontot som du angav med den frekvens som du angav.

1. (Valfritt) När du har skapat exporten, oavsett om du valde att skicka den nu eller enligt ett definierat schema, kan du visa och hantera den på [exportsidan](/help/components/exports/manage-exports.md) och visa den i [exportloggarna](/help/components/exports/manage-export-logs.md).</p>

## Hantera exporter

När data har exporterats från Analysis Workspace kan du redigera, exportera om, duplicera, tagga eller ta bort befintliga exporter enligt beskrivningen i [Hantera exporter](/help/components/exports/manage-exports.md).

## Visa exporterade data och manifestfil

### Exporterade data

Exporterade data är tillgängliga som en komprimerad fil i molndestinationen som du konfigurerade, enligt beskrivningen i [Konfigurera molnexportkonton](/help/components/exports/cloud-export-accounts.md) och [Konfigurera molnexportplatser](/help/components/exports/cloud-export-locations.md).

Filnamnet för den komprimerade filen är följande, beroende på om du väljer CSV eller JSON som filformat:

* `cja-export-{reportInstanceId}-{idx}.csv.gz`

* `cja-export-{reportInstanceId}-{idx}.json.gz`

>[!NOTE]
>
>Du väljer filformatet i fältet [!UICONTROL **Filformat**] när du exporterar tabellen, vilket beskrivs i [Exportera fullständiga tabeller från Analysis Workspace](#export-full-tables-from-analysis-workspace).

### Manifest-fil

En manifestfil med filnamnet `cja-export-{reportInstanceId}-{idx}.json.gz` ingår i alla slutförda exportleveranser som innehåller minst en fil. Manifestfilen gör att du kan bekräfta att alla filer har levererats. Den innehåller följande information:

* En lista över alla filer som levererats

* MD5-kontrollsumman för varje fil

<!-- add in  what the file name, structure, and file format will be -->

## Fördelar med att exportera till molnet

Genom att exportera Customer Journey Analytics-data till molnet kan du:

* Exportera till en delad plats, som Adobe Experience Platform Data Landing Zone, Google Cloud Platform, Microsoft Azure, Amazon S3 eller Snowflake.

* Lagra stora mängder historiska data.

  Denna typ av data kan användas för att upptäcka långsiktiga trender för att få affärsinformation och i slutändan leda till bättre beslutsunderlag.

* Exportera hela tabeller som innehåller tusentals eller miljontals rader (3 miljoner, 30 miljoner, 150 miljoner eller 300 miljoner rader, beroende på licenstyp). Andra exportmetoder tillåter högst 50 000 rader.

* Inkludera beräknade värden i exporterade Customer Journey Analytics-data.

* Strukturera utdata som sammanfogade värden.

* Exportera en gång eller enligt ett schema. (Även tillgängligt med [andra exportalternativ](/help/analysis-workspace/export/export-project-overview.md).)

* Exportera filer i CSV- eller JSON-format. (Även tillgängligt med [andra exportalternativ](/help/analysis-workspace/export/export-project-overview.md).)

* Exportera tabeller som innehåller flera dimensioner.

## Exportkrav {#export-requirements}

### Minimikrav

Se till att tabellerna, miljön och behörigheterna uppfyller följande krav:

* **Tabeller:** Alla tabeller måste innehålla minst en dimension i raden och ett mått i varje kolumn för att kunna hanteras med en export av hela tabeller.

* **Miljö:** Kontrollera att de [IP-adresser](/help/technotes/ip-addresses.md) och [domäner](/help/technotes/domains.md) som används av Customer Journey Analytics tillåts via organisationens brandvägg.

* **Behörigheter:** I Adobe Admin Console måste användarna tilldelas en produktprofil som har behörigheten [!UICONTROL **Fullständig tabellexport**] för att kunna exportera fullständiga tabeller. Information om hur du tilldelar en produktprofil behörighet i Admin Console finns i [Customer Journey Analytics-behörighet i Admin Console](/help/technotes/access-control.md).

  >[!NOTE]
  >
  >  Användare som har tilldelats rollen [Produktadministratör](/help/technotes/access-control.md#product-admin-role) har alltid åtkomst till att exportera fullständiga tabeller. Dessa användare behöver inte tilldelas behörigheten [!UICONTROL **Fullständig tabellexport**].


### Funktioner som inte stöds

Följande funktioner stöds inte och tas automatiskt bort från export i fulltabell:

* Procenttal
* Summor
* Sökfiltrering
* Statiska rader
* Datumjustering
* Mätvärden från sammanfattningsdatauppsättningar
* Dynamiska dimensioner

  Mer information finns i [Dynamiska och statiska dimensionsobjekt i frihandstabeller](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).
* Dimensionerna i den första uppdelningen konverteras och läggs till som en sekundär dimension i raden i den exporterade tabellen. Andra uppdelningar tas inte med i tabellen
* Sortering stöds inte för de flesta datauppsättningar. Data kan sorteras för små datauppsättningar

### Komponenter som inte stöds

Följande komponenter stöds inte och Analysis Workspace uppmanar dig att ta bort dem från tabellen när du exporterar hela tabeller:

* Beräknade mått som använder grundläggande eller avancerade funktioner i metrisk definition (mer information finns i [Grundfunktioner](/help/components/calc-metrics/cm-functions.md) och [Avancerade funktioner](/help/components/calc-metrics/cm-adv-functions.md))
* Komponenter som har begränsats av en administratör från att exporteras (mer information finns i avsnittet *Segment om datastyrningsprinciper i datavyer* i [Etiketter och profiler](/help/data-views/data-governance.md) )
* Alla dimensioner som uppfyller alla följande kriterier:
   * Skapades från ett fält som är en del av en [objektmatris](/help/use-cases/object-arrays.md) (liknar flervärdesvariabler i Adobe Analytics)
   * Har [persistence aktiverat](/help/data-views/component-settings/persistence.md)
   * Använder inte en [bindningsdimension](/help/use-cases/data-views/binding-dimensions-metrics.md)
* Flera dimensioner från fält som refererar till olika [arrayer av objekt](/help/use-cases/object-arrays.md). (Flera dimensioner som refererar till samma array med objekt tillåts.)
* Mer än 5 dimensioner och 5 mätvärden per rapport (upp till 5 dimensioner och 5 mätvärden stöds)
* I tabellkolumner:
   * Datumintervall
   * Mått
* I tabellrader:
   * Beräknade mått
   * Mätvärden
   * Datumintervall
   * Segment

### Attributionsbeteende

Fullständig tabellexport stöder beräknade värden som använder en icke-standardattribueringsmodell (vilket beskrivs i avsnittet *Använd icke-standardattribueringsmodell* i [Kolumninställningar](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)).

Om en attribueringsmodell som inte är standard används i en rapport ignoreras eller behålls allokeringsmodellen som används i rapporten, beroende på om rapporten har en enda dimension eller flera dimensioner:

* **För rapporter som inkluderar metrisk attribuering i en enda dimension:** [Metrisk attribuering](/help/data-views/component-settings/attribution.md) åsidosätter [allokeringsmodellen](/help/data-views/component-settings/persistence.md) på samma sätt som normalt när metrisk attribuering används.

  Exempelvis åsidosätter en första beröring-metrisk attribuering en &quot;senaste&quot; dimensionsallokering.

* **För rapporter som innehåller metrisk attribuering för flera dimensioner samtidigt:** [Måttattribuering](/help/data-views/component-settings/attribution.md) tillämpas utöver dimensionens [allokeringsmodell](/help/data-views/component-settings/persistence.md).

  Till exempel används en första beröring-metrisk attribuering utöver den&quot;senaste&quot; dimensionsallokeringen. Dessutom kommer metrisk attribuering att tillämpas på post-allokerade dimensionsobjektpar som om de vore enskilda dimensionsobjekt, i stället för på varje dimensionsobjekt separat som normalt görs i en frihandsritabell.

  >[!NOTE]
  >
  >Flerdimensionella rapporter stöds bara när data exporteras till molnet, vilket beskrivs i den här artikeln.

## Jämförelse av fullständig tabellexport (i Customer Journey Analytics) till Data Warehouse (i Adobe Analytics)

Om du tidigare använde Data Warehouse för att exportera Adobe Analytics-data kan följande tabell hjälpa dig att förstå skillnaden mellan att exportera fullständiga tabeller i Customer Journey Analytics och att exportera data med Data Warehouse i Adobe Analytics.


| Funktion | Fullständig tabellexport i Customer Journey Analytics | DATA WAREHOUSE i ADOBE ANALYTICS |
|---------|----------|---------|
| Skapa en anpassad rapport | Ja | Ja |
| Beräknade mått | Ja | Nej |
| Segment | Ja | Begränsad |
| Mått | Gräns på 5 | Obegränsad |
| Mätvärden | Gräns på 5 | Obegränsad |
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
