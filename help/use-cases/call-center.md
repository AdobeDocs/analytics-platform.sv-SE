---
title: Importera callcenter och webbdata
description: Lär dig hur du skapar en datauppsättning som länkar callcenter och webbplatsdata.
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 0%

---

# Importera callcenter och webbdata

Customer Journey Analytics har den värdefulla och robusta möjligheten att kombinera datauppsättningar från olika källor till ett enda Workspace-projekt. Använd den här vägledningen när du vill veta hur organisationen kan kombinera webbplatsdata med callcenterdata.

## Förutsättningar

* Den viktigaste komponenten för att kombinera dessa två datauppsättningar är en gemensam identifierare mellan varje datakälla. Exempel är ett kund-ID, en hashad e-post, inloggningsanvändarnamn eller telefonnummer.
* Tillgång till både Adobe Experience Platform och Customer Journey Analytics
* Om datauppsättningen innehåller loggar från ett interaktivt röstsvarssystem rekommenderar Adobe att data endast behandlas med uppmaningsinteraktioner innan de importeras till Platform.
* Om datauppsättningen innehåller samtalsloggar rekommenderar Adobe att du inkluderar följande kolumner:
   * Datum/tid då samtalet inleddes
   * Anledning till samtalet
   * ID för kundtjänst
   * ID för kundtjänstagent
   * Samtalets längd
   * Anmälningsresultat
   * Anställningskostnad (om sådan finns)
   * Alla ytterligare anropsmetadata som din organisation vill inkludera

## Importera webb- och callcenterdata till plattformen

Importera data till Adobe Experience Platform. Se [Skapa ett schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html) och [Infoga data](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) i Adobe Experience Platform-dokumentationen.

När du importerar data till plattformen kan följande tips hjälpa dig att få bättre insikter i de resulterande rapporterna:

* Kontrollera att den identifierare som används för att länka samman anropscenter- och webbdata är i liknande format.
* Inkludera datakällan i varje datauppsättning. Ta till exempel med en `data_source`-kolumn i varje schema och ange värdet för varje händelse till `"Web"` eller `"Call center"`. <!--mapper-->

## Koppla samman person-ID:n

CJA kräver en gemensam identifierare för att generera en [kombinerad datamängd](../connections/combined-dataset.md).

* Om dina datauppsättningar redan har en gemensam identifierare för varje händelse i båda datauppsättningarna kan du hoppa över det här steget och fortsätta skapa en anslutning.
* Om någon av dina datauppsättningar bara har en gemensam identifierare för vissa händelser kan du sammanfoga data med hjälp av kanalövergripande analys. Se [Översikt över flerkanalsanalys](/help/connections/cca/overview.md) för steg som aktiverar CCA för dessa två datauppsättningar.

## Skapa en anslutning i CJA

[Skapa en ](/help/connections/create-connection.md) anslutning i CJA.

* Om CCA används finns det en ny sammansatt datauppsättning att använda. Använd det nya sammanslagna ID-fältet som person-ID.
* I annat fall kan du välja både ursprungliga webb- och callcenter-datauppsättningar som ska användas i anslutningen.

## Skapa en datavy

När du har skapat en anslutning kan du [skapa en datavy](/help/data-views/create-dataview.md) som kan användas i Analysis Workspace. <!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## Skapa visualiseringar

Följande visualiseringar kan användas för att få insikter från din sammanslagna datauppsättning.

### Datauppsättningsöverlappning

Denna visualisering hjälper er att förstå hur väl CCA sammanfogar data.

1. Skapa två filter. Variabeln som används i dessa två filter är samma variabel som nämns ovan som återspeglar datakällan för varje händelse. Mer information finns i [Skapa ett filter](/help/components/filters/create-filters.md).
   * Personbehållare där datauppsättnings-ID är lika med dina webbdata
   * Personbehållare där datauppsättnings-ID är lika med dina kundtjänstdata
2. I Analysis Workspace drar du en [Venn](/help/analysis-workspace/visualizations/venn.md)-visualisering till arbetsytan.
3. Dra de två nyskapade filtren till **[!UICONTROL Add Filter]**-området och personmåttet till **[!UICONTROL Add Metric]**-området.

Den resulterande Vennbildningen visar antalet personer i datauppsättningen som innehåller både webb- och callcenterdata. Ju större överlappning, desto fler personer sys ihop. De områden som inte överlappar representerar personer som endast finns i den ena datauppsättningen eller den andra.

### Attribuera callcenter-händelser till webbsidor

I den här frihandstabellen kan du se de översta sidorna som bidrar till att ringa in center-händelser. Kontrollera först att de önskade måtten och mätvärdena har rätt attribueringsmodell:

1. Dra den dimension som innehåller webbsidans namn till en frihandsritabellvisualisering.
1. Ersätt måttet med det anropscentrerade mått som du vill mäta konverteringen med.
1. Klicka på kugghjulsikonen nära måtthuvudet. Klicka på **[!UICONTROL Use non-default attribution model]**.
1. Ange önskad [attribueringsmodell](/help/data-views/configure-dataviews.md#Attribution-model).

Resultatrapporten visar det högsta mätvärdet från kundtjänstdata. <!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
