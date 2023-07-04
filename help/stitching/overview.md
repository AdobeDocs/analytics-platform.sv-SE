---
title: Översikt över titlar
description: Översikt över häftning.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
source-git-commit: 73496ea3c8341d9db7e879a4f5ae4f35893c605d
workflow-type: tm+mt
source-wordcount: '1273'
ht-degree: 0%

---

# Översikt över titlar

Identitetssammanfogning (eller helt enkelt sammanfogning) är en kraftfull funktion som ökar en händelsedatamängds lämplighet för flerkanalsanalys. Flerkanalsanalys är ett vanligt användningsfall som Customer Journey Analytics kan hantera, vilket gör det möjligt att smidigt kombinera och köra rapporter på flera datauppsättningar från olika kanaler, baserat på en gemensam identifierare (person-ID).

När du kombinerar datauppsättningar med liknande person-ID:n överförs attribueringen mellan enheter och kanaler. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren stöter på ett problem med sin beställning och ger sedan kundtjänstteamet ett samtal för att hjälpa till att lösa det. Med flerkanalsanalys kan ni attribuera callcenter-händelser till den annons som de ursprungligen klickade på.

Tyvärr är inte alla händelsebaserade datauppsättningar som är en del av din anslutning i Customer Journey Analytics tillräckligt kompletta med data för att stödja denna attribuering. I synnerhet har webbaserade eller mobilbaserade upplevelsedatamängder ofta ingen faktisk person-ID-information tillgänglig för alla händelser.

Med hjälp av häftning kan du skriva in identiteter på nytt i en datamängds rader, så att person-ID (sammanfogat ID) är tillgängligt för varje händelse. Stitching tittar på användardata från både autentiserade och oautentiserade sessioner för att avgöra vilket tillfälligt ID-värde som kan användas som sammanfogat ID. På så sätt kan du lösa olika poster till ett sammanfogat ID för analys på personnivå, i stället för på enhets- eller cookienivå.

Du kan dra nytta av flerkanalsanalys om du kombinerar en eller flera av dina sammanfogade datauppsättningar med andra datauppsättningar, till exempel callcenter-data, som en del av arbetet med att definiera din Customer Journey Analytics-anslutning. Detta förutsätter att dessa andra datauppsättningar redan innehåller ett person-ID på varje rad, som liknar det sammanfogade ID:t.


## Förutsättningar

>[!IMPORTANT]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att utföra flerkanalsanalyser korrekt.

Innan du använder stygn bör du kontrollera att din organisation har förberetts med följande:

* Importera önskade data till Adobe Experience Platform:

   * Information om Adobe Analytics finns på [Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md).
   * Andra typer av data finns i [Skapa ett schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) och [Ingrediera data](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html) i Adobe Experience Platform-dokumentationen.

* Händelsedatauppsättningen i Adobe Experience Platform som du vill använda sammanfogning på måste ha två kolumner som hjälper till att identifiera besökare:

   * A **beständigt ID**, en identifierare som finns på varje rad. Till exempel ett besökar-ID som genererats av ett Adobe Analytics AppMeasurement-bibliotek eller ett ECID som genererats av Adobe Experience Cloud Identity Service.
   * A **tillfälligt ID**, en identifierare som bara finns på vissa rader. Till exempel ett hashas användarnamn eller en e-postadress när en besökare autentiserar. Du kan använda praktiskt taget vilken identifierare som helst. Vid textning tas det här fältet i beaktande för att innehålla den faktiska informationen om person-ID. För bästa resultat av sammanfogning bör ett tillfälligt ID skickas inom datauppsättningens händelser minst en gång för varje beständigt ID.
Om du tänker ta med den här datauppsättningen i en Customer Journey Analytics-anslutning är det bättre att de andra datauppsättningarna också har en liknande gemensam identifierare.

* Stitching inkluderar sammanfogning av autentiserade och oautentiserade användardata. Se till att du följer tillämpliga lagar och bestämmelser, inklusive att erhålla nödvändiga slutanvändarbehörigheter, innan du aktiverar sammanfogning av en händelsedatamängd.


## Använd stygn

När organisationen uppfyller alla krav och förstår [begränsningar](#limitations)kan du följa de här stegen för att börja använda häftning i Customer Journey Analytics:

### Begär support

1. Kontakta Adobe kundsupport med följande information:

   * En begäran om att aktivera sammanfogning.
   * Datauppsättnings-ID för den datauppsättning som du vill ändra inmatning för.
   * Kolumnnamnet för det beständiga ID:t för den önskade datauppsättningen (identifierare som visas på varje rad).
   * Kolumnnamnet för det tillfälliga ID:t för den önskade datauppsättningen (länken för personidentifierare mellan datauppsättningar).
   * Din inställning [spela upp](explained.md) frekvens och uppslagslängd. Du kan välja att spela upp en gång i veckan med ett 7-dagars uppslagsfönster eller att spela upp varje dag med ett 1-dagars uppslagsfönster.
   * Namn på sandlåda.


2. Adobe kundsupport samarbetar med Adobe och gör det möjligt att sy ihop bilder när du får din begäran. När den är aktiverad visas en ny inmatad datauppsättning som innehåller en ny person-ID-kolumn i Adobe Experience Platform. Adobe kundsupport kan ange det nya datauppsättnings-ID:t och namn på kolumn för person-ID.

3. När Adobe aktiveras första gången fylls data i bakåt så långt tillbaka som till början av föregående månad (upp till 60 dagar). Om du vill göra den här bakåtfyllnaden måste det tillfälliga ID:t finnas i de icke sammanfogade data så långt tillbaka i tiden.

4. [Skapa en anslutning](/help/connections/create-connection.md) i Customer Journey Analytics med den nya datauppsättningen och andra datauppsättningar som du vill inkludera. Välj rätt person-ID för varje datauppsättning.

5. [Skapa en datavy](/help/data-views/create-dataview.md) baserat på anslutningen.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

När datavyn har konfigurerats är flerkanalsanalysen i Customer Journey Analytics precis som alla andra analyser i Customer Journey Analytics, förutom att data nu fungerar över alla kanaler och enheter.

<!-- Uncomment once stitching UI is available (for limited testing)..

### Do It Yourself

|Positive|[!BADGE New Feature]{type=Positive before-title="false"}|

{{release-limited-testing-section}}

Alternatively, you can set up and use stitching through the Customer Journey Analytics user interface:

1. Go to the [Create and manage stitched datasets](stitching-ui.md) and follow steps to rekey your dataset.

2. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.

3. [Create a connection](/help/connections/create-connection.md) in Customer Journey Analytics using the newly generated dataset and any other datasets that you want to include. Choose the correct person ID for each dataset.
   
4. [Create a data view](/help/data-views/create-dataview.md) based on the connection.

Once the data view is set up, the cross-channel analysis in Customer Journey Analytics is just like any other analysis in Customer Journey Analytics, except now the data operates across channels and devices.

-->


## Begränsningar

>[!IMPORTANT]
>
>Tillämpa eventuella ändringar som du gör i det globala händelsedatamängdsschemat även på det nya sammanfogade datamängdsschemat, annars bryts den sammanfogade datauppsättningen.
>
>Om du tar bort källdatauppsättningen avbryts bearbetningen av den sammanfogade datauppsättningen och tas bort av systemet.

Stitching är en banbrytande och robust funktion, men har begränsningar för hur den kan användas.

* Aktuella återskrivningsfunktioner är begränsade till ett steg (beständigt ID till tillfälligt ID). Återinmatning i flera steg (till exempel beständigt ID till ett tillfälligt ID och sedan till ett annat tillfälligt ID) stöds inte.
* Endast händelsedatamängder stöds. Andra datauppsättningar, till exempel uppslagsdatauppsättningar, stöds inte.
* Anpassade ID-mappningar som används i din organisation stöds inte.
* Med hjälp av fästfunktionen omvandlas inte det fält som används för sammanfogning på något sätt. Vid Stitching används värdet i det angivna fältet som det finns i den osydda datauppsättningen inom datavjön. Smältningsprocessen är skiftlägeskänslig. Om ibland ordet &#39;Bob&#39; visas i fältet, och ibland ordet &#39;BOB&#39; visas, behandlas dessa id:n som två separata personer.
* Stiting är skiftlägeskänsligt. För datauppsättningar som genererats via Analytics Source Connector rekommenderar Adobe att du granskar alla VISTA-regler eller bearbetningsregler som gäller för det tillfälliga ID-fältet. Denna granskning säkerställer att inga av dessa regler inför nya formulär med samma ID. Du bör t.ex. se till att inga VISTA-regler eller bearbetningsregler för endast en del av händelserna introducerar lägre radering till det tillfälliga ID-fältet.
* När du använder Stitching kombineras eller sammanfogas inte fält.
* Det tillfälliga ID-fältet ska innehålla en enda typ av ID (ID:n från ett enda namnutrymme). Det tillfälliga ID-fältet ska till exempel inte innehålla en kombination av inloggnings-ID och e-post-ID.
* Om flera händelser inträffar med samma tidsstämpel för samma beständiga ID, men med olika värden i fältet för transient ID, väljs ID baserat på alfabetisk ordning. Om beständigt ID A har två händelser med samma tidsstämpel och en av händelserna anger Bob och den andra anger Ann, väljer Ann när de sammanfogar.
* Om en enhet delas av flera personer och det totala antalet övergångar mellan användare överstiger 50 000, slutar Customer Journey Analytics att fästa data för den enheten.

Blanda inte ihop stygn med:

* Sammanfogningen av två eller flera datauppsättningar. Gäller endast en datauppsättning. Sammanfogning av datauppsättningar sker som ett resultat av att du konfigurerar en Customer Journey Analytics-anslutning och väljer samma person-ID för de markerade datauppsättningarna i anslutningen.

* Sammanfogning av två datauppsättningar. I Customer Journey Analytics används ofta en join för uppslag eller klassificeringar i Analysis Workspace. Även om sammanfogning använder sammanfogningsfunktioner innebär själva processen mycket mer än sammanfogningar.

