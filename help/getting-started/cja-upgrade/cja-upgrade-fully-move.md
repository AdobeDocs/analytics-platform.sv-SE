---
title: Utvärdera hur länge du behöver Adobe Analytics efter att du uppgraderat till Customer Journey Analytics
description: Lär dig hur länge du behöver Adobe Analytics efter att du uppgraderat till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: f4440148d26e81938d029d4a077cd787c868f1be
workflow-type: tm+mt
source-wordcount: '927'
ht-degree: 0%

---

# Utvärdera hur länge du behöver Adobe Analytics efter att du uppgraderat till Customer Journey Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Gå helt till Customer Journey Analytics"
>abstract="(Rekommenderas) Customer Journey Analytics är det primära analysverktyget för er organisation. Din organisation kan dock fortfarande behöva Adobe Analytics om den är starkt beroende av funktioner som är exklusiva för verktyget och dessa arbetsflöden inte kan ändras."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Behåll båda analysprodukterna"
>abstract="(Rekommenderas inte) Om du väljer det här alternativet inkluderar ditt avtal med Adobe både Adobe Analytics och Customer Journey Analytics, vilket kan vara dyrare för din organisation över tid."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Den här dokumentationen bör användas som en del av uppgraderingsenkäten för [Adobe Analytics till Customer Journey Analytics](https://gigazelle.github.io/cja-ttv/).

De flesta organisationer kommer till slut att inaktivera Adobe Analytics efter en uppgradering till Customer Journey Analytics. Detta beror på kostnaden och komplexiteten i att underhålla två analysmiljöer.

Adobe rekommenderar dock att du håller Adobe Analytics-miljön igång under en tidsperiod efter implementeringen av Customer Journey Analytics. I följande avsnitt beskrivs orsakerna till detta samt den föreslagna tidpunkten för inaktivering av Adobe Analytics.

## Användning av Adobe Analytics under och efter en uppgradering

När du ska avgöra om och när din organisation ska inaktivera Adobe Analytics bör du tänka på följande användningar av Adobe Analytics under och efter en uppgradering till Customer Journey Analytics:

| Användning av Adobe Analytics under och efter uppgraderingen | Förklaring |
|---------|----------|
| Jämför data sida vid sida | Adobe rekommenderar att du håller Adobe Analytics-miljön igång under en tid efter att den nya Customer Journey Analytics-miljön har körts och att du samlar in data. Detta är det bästa sättet att jämföra data från Customer Journey Analytics sida vid sida med data från Adobe Analytics.<p>Inaktivera inte Adobe Analytics förrän du känner dig trygg med data i Customer Journey Analytics.</p><p>**Obs!** Adobe rekommenderar en ny implementering av Web SDK för din Customer Journey Analytics-miljö, tillsammans med Analytics-källkopplingen för historiska data. [Läs mer](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Behåll historiska data från Adobe Analytics | Adobe rekommenderar att du håller din Adobe Analytics-miljö på plats med Analytics-källkopplingen under en tid efter att din nya Customer Journey Analytics-miljö har körts och att du samlar in data. Detta är det bästa sättet att föra in historiska Adobe Analytics-data i Customer Journey Analytics.<p>När du har samlat in tillräckligt med historiska data i Customer Journey Analytics med den nya Web SDK-implementeringen kan du ta bort källkopplingen för Analytics helt och hållet. Gör detta när du bara kan förlita dig på historiska data som du har samlat in med den nya Customer Journey Analytics Web SDK-implementeringen.</p><p>**Obs!** Adobe rekommenderar en ny implementering av Web SDK för din Customer Journey Analytics-miljö, tillsammans med Analytics-källkopplingen för historiska data. [Läs mer](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p> |
| Använd dataflöden eller andra Adobe Analytics-funktioner | En liten uppsättning funktioner är ännu inte helt tillgängliga i Customer Journey Analytics. Om du behöver ha tillgång till dessa funktioner kan det vara nödvändigt att använda Adobe Analytics tillsammans med Customer Journey Analytics tills dessa funktioner blir tillgängliga. <p>Funktioner som inte är helt tillgängliga i Customer Journey Analytics omfattar dataflöden och bidragsanalys. En fullständig lista över funktioner som ännu inte är tillgängliga finns i [Funktionsstöd i Customer Journey Analytics](/help/getting-started/aa-vs-cja/cja-aa.md).</p> |

## Processen och tidslinjen för att inaktivera Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Inaktivera ett tagghanteringssystem från tredje part"
>abstract="Med Web SDK-data i full funktionalitet arbetar du med tagghanteraren för att ta bort AppMeasurementet från tredjepartssystemet.<br><br>Den beräknade tiden för att utföra det här steget beror på hur enkelt det är att inaktivera AppMeasurementet från tagghanteringsprodukten, liksom på vilken releasecykel din organisation använder för att distribuera och hantera taggar."

<!-- markdownlint-enable MD034 -->

Din befintliga Adobe Analytics-implementering är en viktig del av en lyckad uppgradering till Customer Journey Analytics, vilket beskrivs i avsnittet ovan, [Användning av Adobe Analytics under och efter en uppgradering](#uses-of-adobe-analytics-during-and-after-an-upgrade).

När du inte längre behöver Adobe Analytics för de syften som beskrivs i avsnittet ovan använder du följande information för att ta bort Adobe Analytics:

1. Sluta samla in data med Adobe Analytics.

   När du är nöjd med jämförelserna av dina Adobe Analytics-data och dina Customer Journey Analytics-data kan du sluta samla in data med Adobe Analytics-implementeringen. Nya Adobe Analytics-data flödar inte längre till Customer Journey Analytics via Analytics-källkopplingen.

   Data som ni har samlat in från er Adobe Analytics-miljö före den här punkten är dock fortfarande tillgängliga som historiska data i Customer Journey Analytics via Analytics-källkopplingen.

   Den här processen skiljer sig åt beroende på vilken datainsamlingsmetod du använde för att implementera Adobe Analytics:

+++ AppMeasurement

   [Inaktivera datainsamling för AppMeasurement](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md).

+++

+++ Analystillägg (taggar)

   Inaktivera Analytics-tillägget i taggar.

+++

+++ API

   Inaktivera API-datainsamling.

+++

+++ Tredje part

   Arbeta med tagghanteraren för att ta bort AppMeasurementet från tredjepartssystemet.

+++

1. Ta bort Adobe Analytics som en tjänst från datastream.

   Med Web SDK-data i full funktionalitet arbetar du tillsammans med plattformsadministratören för att ta bort Adobe Analytics som en tjänst från datastreammet.

   Innan du tar bort Adobe Analytics som en tjänst bör du kontrollera att era Analytics-användare använder Customer Journey Analytics och inte Adobe Analytics.

1. Ta bort Analytics-källkopplingen helt.

   När du har samlat in tillräckligt med historiska data i Customer Journey Analytics med den nya Web SDK-implementeringen kan du ta bort källkopplingen för Analytics helt och hållet.

   Gör detta när du inte längre behöver historiska data från din Adobe Analytics-miljö via källkopplingen i Analytics, och du kan bara förlita dig på historiska data som du har samlat in med den nya Web SDK-implementeringen.

