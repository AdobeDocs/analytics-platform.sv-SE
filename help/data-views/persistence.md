---
title: Vad är uthållighet i Customer Journey Analytics?
description: Dimensionens beständighet är en kombination av allokering och förfallodatum. Tillsammans avgör de vilka dimensionsvärden som kvarstår.
translation-type: tm+mt
source-git-commit: 09f49cff89d69ae630e917243425967dbf56a9ed
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---


# Persistence

Dimensionens beständighet är en kombination av allokering och förfallodatum. Tillsammans avgör de vilka dimensionsvärden som kvarstår. Adobe rekommenderar att du diskuterar inom organisationen hur flera värden för varje dimension hanteras (allokering) och när dimensionsvärden avbryter bestående data (förfallodatum).

* Som standard använder ett dimensionsvärde den senaste allokeringen. Nya värden skriver över beständiga värden.
* Som standard används en förfallotid på [!UICONTROL Session] för ett dimensionsvärde.

## Allokering

Avgör hur CJA tilldelar kredit för en success-händelse om en variabel tar emot flera värden före händelsen. Värden som stöds är:

* Senaste: Det sista eVar får alltid medarbetare för lyckade händelser tills den eVar förfaller.
* Originalvärde: Den första eVar får alltid erkännande för lyckade händelser tills den eVar går ut.
* Instans: ?

Obs! Genom att växla allokering till eller från Linear förhindrar du att historiska data visas. Blandning av allokeringstyper i rapporteringsgränssnittet kan leda till feldata i rapporter. En linjär fördelning kan t.ex. dela intäkterna med ett antal olika eVar. När du har ändrat tillbaka till Senaste allokering är 100 % av denna intäkt kopplad till det senaste värdet. Den här associationen kan leda till felaktiga slutsatser från användarna.

För att undvika risken för förvirring i rapporteringen gör Analytics att historiska data inte är tillgängliga för gränssnittet. Den kan visas om du bestämmer dig för att ändra tillbaka den angivna eVar till den ursprungliga allokeringsinställningen, men du bör inte ändra eVar allokeringsinställningar bara för att komma åt historiska data. Adobe rekommenderar att du använder en ny eVar när nya allokeringsinställningar är önskade för data som redan registreras, i stället för att ändra allokeringsinställningarna för en eVar som redan har en stor mängd historiska data inbyggda.

## Förfaller

Dimensionen förfaller efter den tidsperiod som du anger. När dimensionsvärdet har gått ut får det inte längre någon kredit för ett mätvärde. Dimensioner kan också konfigureras så att de förfaller enligt mätvärden. Om du t.ex. har en intern kampanj som upphör efter ett besök, får den interna kampanjen endast kredit för inköp eller registreringar som sker under det besök där de aktiverades.

Det finns två sätt att förfalla en eVar:

Du kan ange att eVar ska förfalla efter en angiven tidsperiod eller händelse.
Du kan använda Framtvinga förfallodatum för en eVar genom att återställa den, vilket är användbart när du återanvänder en variabel.
Om du t.ex. ändrar förfallotiden för en eVar från 30 till 90 dagar, kommer de insamlade eVar att finnas kvar så länge den nya förfallotiden varar (i det här fallet 90 dagar). Systemet tittar bara på den aktuella förfalloinställningen och den sista angivna tidsstämpeln för det insamlade eVar för att avgöra förfallodatum. Endast alternativet Återställ förfaller värden och gör det omedelbart.

Ett annat exempel: Om en eVar används i maj för att återspegla interna kampanjer och upphör efter 21 dagar, och i juni används den för att fånga in interna söknyckelord, bör du den 1 juni tvinga fram en förfallotid för, eller återställning av, variabeln. Om du gör det kommer det att bidra till att bevara de interna kampanjvärdena från juni-rapporterna.