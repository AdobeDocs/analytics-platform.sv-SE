---
title: Översikt över flerkanalsanalys
description: Nyckelanpassa person-ID:n från flera datauppsättningar till att sammanfoga personer.
exl-id: 69763313-de27-4487-8e32-8277f1f693d8
solution: Customer Journey Analytics
feature: Cross-Channel Analytics
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '1166'
ht-degree: 0%

---

# Översikt över flerkanalsanalys

**Resa-IQ: Flerkanalsanalys** är en funktion som gör att du kan ändra inmatningen i en datauppsättnings person-ID, vilket möjliggör en sömlös kombination av flera datauppsättningar. CCA undersöker användardata från både autentiserade och oautentiserade sessioner för att generera ett sammanfogat ID. Med flerkanalsanalys kan ni besvara frågor som:

* Hur många börjar sin upplevelse i en kanal och avslutar den i en annan?
* Hur många interagerar med mitt varumärke? Hur många och vilka typer av enheter använder de? Hur överlappar de?
* Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra uppgiften? Kommer kampanjklickningar att leda till konvertering någon annanstans på en enhet?
* Hur förändras min förståelse för kampanjens effektivitet om jag tar hänsyn till resor mellan olika enheter? Hur förändras min kanalanalys?
* Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de?
* Hur skiljer sig beteendet hos användare med flera enheter från dem som har en enda enhet?

När du kombinerar datauppsättningar med liknande person-ID:n överförs attribueringen mellan enheter och kanaler. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren stöter på ett problem med sin beställning och ger sedan kundtjänstteamet ett samtal för att hjälpa till att lösa det. Med Cross-Channel Analytics kan ni attribuera callcenter-händelser till annonsen som de ursprungligen klickade på.

## Förutsättningar

>[!IMPORTANT]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att skapa en CCA-anslutning eller till dåliga resultat när du kombinerar datauppsättningar.

Innan du använder flerkanalsanalys bör du kontrollera att din organisation har förberetts med följande:

* En datauppsättning i Adobe Experience Platform måste ha två kolumner som hjälper till att identifiera personer:
   * A **beständigt ID**, en identifierare som finns på varje rad. Exempel: ett person-ID som genererats av ett Adobe Analytics AppMeasurement-bibliotek.
   * A **tillfälligt ID**, en identifierare som bara finns på vissa rader. Till exempel ett hashas-användarnamn eller en e-postadress när en person autentiseras. Du kan använda praktiskt taget alla identifierare som du vill, förutsatt att de finns minst en gång för samma händelse som ett visst beständigt ID.
* En annan datauppsättning, till exempel callcenter-data, som innehåller ett tillfälligt ID på varje rad. Detta person-ID måste formateras på samma sätt som det tillfälliga ID:t i den andra datauppsättningen.
* Med den här funktionen kan du sammanfoga datauppsättningar som kan omfatta sammanfogning av autentiserade och oautentiserade användardata. Se till att du följer tillämpliga lagar och bestämmelser, inklusive att erhålla nödvändiga slutanvändarbehörigheter, innan du sammanfogar datauppsättningar.

## Begränsningar

>[!IMPORTANT]
>
>Alla ändringar i det globala händelsedatamängdsschemat måste tillämpas även i det nya sammanfogade dataschemat, annars bryts den sammanfogade datauppsättningen.
>
>Om du tar bort källdatauppsättningen avbryts bearbetningen av den sammanfogade datauppsättningen och tas bort av systemet.

Flerkanalsanalys är en banbrytande och robust funktion, men har begränsningar för hur den kan användas.

* Aktuella återskrivningsfunktioner är begränsade till ett steg (beständigt ID till tillfälligt ID). Återinmatning i flera steg (till exempel beständigt ID till ett tillfälligt ID och sedan till ett annat tillfälligt ID) stöds inte.
* Endast händelsedatamängder stöds. Andra datauppsättningar, till exempel uppslagsdatauppsättningar, stöds inte.
* Anpassade ID-mappningar som används i din organisation stöds inte.
* Privat korsenhetsdiagram stöds inte.
* Flerkanalsanalys omformar inte det fält som används för sammanfogning på något sätt. Fältbaserad sammanfogning använder värdet i det angivna fältet så som det finns i den icke-sammanfogade datauppsättningen inom datarjön. Staplingsprocessen är skiftlägeskänslig. Om ibland ordet &#39;Bob&#39; visas i fältet och ibland ordet &#39;BOB&#39; visas, behandlas dessa som två separata personer.
* För Analytics-datauppsättningar som genererats via Analytics Source Connector rekommenderar Adobe att man granskar VISTA-regler eller bearbetningsregler som gäller för det tillfälliga ID-fältet för att säkerställa att inga av dessa regler inför nya former av samma ID. Du bör t.ex. se till att inga VISTA-regler eller bearbetningsregler för endast en del av händelserna introducerar lägre radering till det tillfälliga ID-fältet.
* Fältbaserad sammanfogning varken kombinerar eller sammanfogar fält.
* Det tillfälliga ID-fältet ska innehålla en enda typ av ID (t.ex. ID:n från ett enda namnutrymme). Det tillfälliga ID-fältet ska till exempel inte innehålla en kombination av inloggnings-ID och e-post-ID.
* Om flera händelser inträffar med samma tidsstämpel för samma beständiga ID, men med olika värden i fältet för transient ID, väljer fältbaserad sammanslagning baserat på alfabetisk ordning. Om beständigt ID A har två händelser med samma tidsstämpel och en av händelserna anger Bob och den andra anger Ann, väljer fältbaserad stitling Ann.
* Om en enhet delas av flera personer och det totala antalet övergångar mellan användare överstiger 50 000, upphör CCA att sammanfoga data för den enheten.


## Aktivera flerkanalsanalys

När organisationen uppfyller alla krav och förstår sina begränsningar kan du följa dessa steg för att börja använda programmet i Customer Journey Analytics.

1. Importera önskade data till Adobe Experience Platform. Information om Adobe Analytics finns på [Använda Adobe Analytics rapportsvitsdata i Customer Journey Analytics](/help/getting-started/aa-vs-cja/aa-data-in-cja.md). Andra typer av data finns i [Skapa ett schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) och [Ingrediera data](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html) i Adobe Experience Platform-dokumentationen.
1. Kontakta Adobe kundsupport med följande information:
   * En begäran om att aktivera flerkanalsanalys
   * Datauppsättnings-ID för den datauppsättning som du vill ändra inmatning för
   * Kolumnnamnet för det beständiga ID:t för den önskade datauppsättningen (identifierare som visas på varje rad)
   * Kolumnnamnet för det tillfälliga ID:t för den önskade datauppsättningen (länken för personidentifierare mellan datauppsättningar)
   * Din inställning [spela upp](replay.md) frekvens och uppslagslängd. Du kan välja att spela upp en gång i veckan med ett 7-dagars uppslagsfönster eller att spela upp varje dag med ett 1-dagars uppslagsfönster
   * Namn på sandlåda.
1. Adobe kundsupport kommer att arbeta tillsammans med Adobe-teknik för att möjliggöra flerkanalsanalys när du får din begäran. När den är aktiverad visas en ny inmatad datauppsättning som innehåller en ny person-ID-kolumn i Adobe Experience Platform. Adobe kundsupport kan ange det nya datauppsättnings-ID:t och namn på kolumn för person-ID.
1. När Adobe aktiveras första gången fylls data i bakåt så långt tillbaka som i början av föregående månad (upp till 60 dagar). För att denna efterfyllning ska kunna utföras måste det tillfälliga ID:t finnas i de icke sammanfogade data så långt tillbaka i tiden.
1. [Skapa en anslutning](/help/connections/create-connection.md) i Customer Journey Analytics med den nya datauppsättningen och andra datauppsättningar som du vill inkludera. Välj rätt person-ID för varje datauppsättning.
1. [Skapa en datavy](/help/data-views/create-dataview.md) baserat på anslutningen.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

När datavyn har konfigurerats är analysen i Customer Journey Analytics precis som alla andra analyser i Customer Journey Analytics, förutom att data nu fungerar över alla kanaler och enheter.
