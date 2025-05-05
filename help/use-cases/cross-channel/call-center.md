---
title: Importera callcenter och webbdata
description: Lär dig hur du skapar en datauppsättning som länkar callcenter och webbplatsdata.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: 976f481b6886a4f260f44854a30c47ab0dad7955
workflow-type: tm+mt
source-wordcount: '1124'
ht-degree: 0%

---

# Importera callcenter och webbdata

Customer Journey Analytics har den värdefulla och robusta möjligheten att kombinera datauppsättningar från olika källor till ett enda Workspace-projekt. Använd den här vägledningen när du vill veta hur organisationen kan kombinera webbplatsdata med callcenterdata. Ni kan till exempel förstå vilka åtgärder en kund vidtar, vilket innehåll de ser och vilka termer de söker innan de kontaktar kundsupporten. Sedan kan ni avgöra vilka verktyg för innehåll och självbetjäning som ska förbättras så att kunderna själva kan lösa problem bättre utan att behöva ringa in.

## Förutsättningar

* Den viktigaste komponenten för att kombinera dessa två datauppsättningar är en gemensam identifierare mellan varje datakälla. Exempel är ett kund-ID, en hashad e-post, inloggningsanvändarnamn eller telefonnummer.
* Tillgång till både Adobe Experience Platform och Customer Journey Analytics
* Om datauppsättningen innehåller loggar från ett interaktivt röstsvarssystem rekommenderar Adobe att du endast bearbetar dessa data med uppmaningsinteraktioner innan du importerar dem till plattformen.
* Om datauppsättningen innehåller samtalsloggar rekommenderar Adobe att du inkluderar följande kolumner:
   * Datum/tid då samtalet inleddes
   * Samtalsorsak
   * ID för kundtjänst
   * ID för kundtjänstagent
   * Samtalets längd
   * Anmälningsresultat
   * Anställningskostnad (om sådan finns)
   * Alla ytterligare anropsmetadata som din organisation vill inkludera

## Importera webb- och callcenterdata till plattformen

Importera data till Adobe Experience Platform. Se [Skapa ett schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE) och [Infoga data](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=sv-SE) i Adobe Experience Platform-dokumentationen.

När du importerar data till plattformen kan följande tips hjälpa dig att få bättre insikter i de resulterande rapporterna:

* Kontrollera att den identifierare som används för att länka samman anropscenter- och webbdata är i liknande format.
* Inkludera datakällan i varje datauppsättning. Ta till exempel med en `data_source`-kolumn i varje schema och ange värdet för varje händelse till `"Web"` eller `"Call center"`. <!--mapper-->

## Koppla samman person-ID:n

Customer Journey Analytics kräver en gemensam identifierare för att skapa en [kombinerad datamängd](/help/connections/combined-dataset.md).

* Om dina datauppsättningar redan har en gemensam identifierare för varje händelse i båda datauppsättningarna kan du hoppa över det här steget och fortsätta skapa en anslutning.
* Om någon av dina datauppsättningar bara har en gemensam identifierare för vissa händelser, kan du sammanfoga data med [Stitching](/help/stitching/overview.md) för steg som aktiverar flerkanalsanalys för dessa två datauppsättningar.

## Skapa en anslutning i Customer Journey Analytics

[Skapa en anslutning](/help/connections/create-connection.md) i Customer Journey Analytics.

* Om CCA används finns det en ny sammansatt datauppsättning som du kan använda. Använd det nya sammanslagna ID-fältet som person-ID.
* I annat fall kan du välja både ursprungliga webb- och callcenter-datauppsättningar som ska användas i anslutningen.

## Skapa en datavy

När du har skapat en anslutning kan du [skapa en datavy](/help/data-views/create-dataview.md) som kan användas i Analysis Workspace. Exempel på användbara komponenter:

* En siddimension med senaste berörings- och sessionsbeständighet. Ni kan koppla kundens statistik till den sista sidan som kunden visade innan de ringde in.
* A call metric that uses a Call center reason&#39; schema field to increase instances. Använd [Metrisk borttagning av dubbletter](/help/data-views/component-settings/metric-deduplication.md) så att den bara ökas en gång per session.

## Skapa visualiseringar

Följande visualiseringar kan användas för att få insikter från din sammanslagna datauppsättning.

### Överlappning av datauppsättning

Denna visualisering hjälper er att förstå hur väl CCA sammanfogar data.

1. Skapa två segment. Variabeln som används i de här två segmenten är samma variabel som nämns ovan som återspeglar datakällan för varje händelse. Mer information finns i [Skapa ett segment](/help/components/filters/create-filters.md).
   * Personbehållare där datauppsättnings-ID är lika med dina webbdata
   * Personbehållare där datauppsättnings-ID är lika med dina kundtjänstdata
2. Dra en [Vennbildvisualisering](/help/analysis-workspace/visualizations/venn.md) till arbetsytan i Analysis Workspace.
3. Dra de två nyskapade segmenten till området **[!UICONTROL Add Segment]** och personmåttet till området **[!UICONTROL Add Metric]**.

I den resulterande Venndatavisualiseringen visas antalet personer i datauppsättningen som innehåller både webb- och callcenterdata. Ju större överlappning, desto fler personer sys ihop. De områden som inte överlappar representerar personer som endast finns i den ena datauppsättningen eller den andra.

### Attribuera callcenter-händelser till webbsidor

I den här frihandstabellen kan du se de översta sidorna som bidrar till att ringa in center-händelser. Kontrollera först att de önskade måtten och mätvärdena har rätt attribueringsmodell:

1. Dra den dimension som innehåller webbsidans namn till en frihandsritabellvisualisering.
1. Ersätt mätvärdet med det anropscentrerade mått som du vill mäta.
1. Klicka på kugghjulsikonen nära måtthuvudet. Klicka på **[!UICONTROL Use non-default attribution model]**.
1. Ange önskad [attributmodell](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md). Exempel: en Time Decay-modell med en halveringstid på 15 minuter och ett Lookback-fönster för session. Den här attribueringsmodellen ger meriter till sidorna som leder fram till samtalet till ert callcenter.

Den resulterande rapporten visar de översta sidorna som driver samtal till ert callcenter. <!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

Du kan öka insikterna ytterligare med den här tabellen genom att dela upp samtal utifrån orsak eller kategori.

1. Klicka på den högra markören under dimensionen Anropsorsak i komponentlistan. Den här åtgärden visar enskilda dimensionsvärden.
2. Dra önskade dimensionsvärden under anropsmåttet, som segmenterar mätvärdena för varje anropsorsak.
3. Upprepa för varje samtalsorsak som du vill fördjupa dig i. Använd segmentet Alla sessioner för att visa den sammanställda summan.

<!-- screenshot -->

### Flödesvisualisering

Ni kan få insikt i vad en kund försökte göra innan de använde callcenterkanalen. Denna flödesvisualisering hjälper er att förstå de vanligaste resorna en kund tar för att nå ert callcenter. Med den här insikten kan ni fastställa de mest effektiva förbättringarna av er webbplats så att kunderna inte är lika benägna att ringa in.

1. Klicka på fliken **[!UICONTROL Visualizations]** till vänster och dra en flödesvisualisering till arbetsytan.
2. Klicka på fliken **[!UICONTROL Components]** till vänster och leta upp dimensionen Anledning till samtal.
3. Klicka på den högra markören bredvid den här dimensionen. Den här åtgärden visar enskilda dimensionsvärden.
4. Dra det önskade måttobjektet för anropsorsaken till mittplatsen för flödesvisualiseringen.
5. Flödesvisualiseringen fyller automatiskt i tidigare och nästa anropsorsaker. Ersätt den föregående samtalsorsaken med webbplatsens siddimension.
6. Klicka på kugghjulsikonen i det övre högra hörnet av flödesvisualiseringen och ändra flödesbehållaren till **[!UICONTROL Session]**.

### Histogram

Hur många har ringt en gång, två gånger eller ringt 6+ gånger? En del av dem besöker aldrig webbplatsen. Använd histogramvisualisering för att avgöra hur många som hamnar i varje hink. För personer som aldrig besöker webbplatsen, se hur vi kan uppmuntra dem att själva använda webbtjänsten.

1. Klicka på fliken **[!UICONTROL Visualizations]** till vänster och dra en histogramvisualisering till arbetsytan.
2. Klicka på fliken **[!UICONTROL Components]** till vänster och dra anropsmåtten till histogramvisualiseringen.
3. Klicka på **[!UICONTROL Show advanced settings]** i mitten av visualiseringen och anpassa önskade intervall.
4. Klicka på **[!UICONTROL Build]**.

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of segments - facets to their business. Segments were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really segments)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential segments, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
