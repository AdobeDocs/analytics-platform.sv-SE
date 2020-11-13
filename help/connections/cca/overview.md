---
title: Översikt över flerkanalsanalys
description: Nyckelanpassa besökar-ID:n igen från flera datauppsättningar för att knyta ihop besökare.
translation-type: tm+mt
source-git-commit: b57895d037f8db3ffc418312b95fc43dd0280dc9
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 0%

---


# Översikt över flerkanalsanalys

**Resa-IQ: Flerkanalsanalys** är en funktion som gör att du kan ändra nyckelord för en datamängds person-ID, vilket möjliggör en sömlös kombination av flera datamängder. CCA undersöker användardata från både autentiserade och oautentiserade sessioner för att generera ett sammanfogat ID. Med flerkanalsanalys kan ni besvara frågor som:

* Hur många börjar sin upplevelse i en kanal och avslutar den i en annan?
* Hur många interagerar med mitt varumärke? Hur många och vilka typer av enheter använder de? Hur överlappar de?
* Hur ofta startar man en uppgift på en mobil enhet och sedan övergår till en stationär dator för att slutföra uppgiften? Kommer kampanjklickningar att leda till konvertering någon annanstans på en enhet?
* Hur förändras min förståelse för kampanjens effektivitet om jag tar hänsyn till resor mellan olika enheter? Hur förändras min kanalanalys?
* Vilka är de vanligaste sökvägarna som användare tar från en enhet till en annan? Var faller de? Var lyckas de?
* Hur skiljer sig beteendet hos användare med flera enheter från dem som har en enda enhet?

När du kombinerar datauppsättningar med liknande person-ID:n överförs attribueringen mellan enheter och kanaler. En användare besöker till exempel först din webbplats via en annons på sin dator. Användaren stöter på ett problem med sin beställning och ger sedan kundtjänstteamet ett samtal för att lösa det. Med flerkanalsanalys kan ni attribuera callcenter-händelser till annonsen som de ursprungligen klickade på.

## Förutsättningar

>[!IMPORTANT]
>
>Om du inte uppfyller alla krav kan det leda till att det inte går att skapa en CCA-anslutning eller till dåliga resultat när du kombinerar datauppsättningar.

Innan du använder flerkanalsanalys bör du kontrollera att din organisation har förberetts med följande:

* En datauppsättning i Adobe Experience Platform måste ha två kolumner som hjälper till att identifiera besökare:
   * Ett **beständigt ID**, en identifierare som finns på varje rad. Till exempel ett besökar-ID som genereras av ett Adobe Analytics AppMeasurement-bibliotek.
   * Ett **tillfälligt ID**, en identifierare som bara finns på vissa rader. Till exempel ett hashas användarnamn eller en e-postadress när en besökare autentiserar. Du kan använda praktiskt taget alla identifierare som du vill, förutsatt att de finns minst en gång för samma händelse som ett visst beständigt ID.
* En annan datauppsättning, till exempel callcenter-data, som innehåller ett tillfälligt ID på varje rad. Detta person-ID måste formateras på samma sätt som det tillfälliga ID:t i den andra datauppsättningen.
* Med den här funktionen kan du sammanfoga datauppsättningar som kan omfatta sammanfogning av autentiserade och oautentiserade användardata. Se till att du följer tillämpliga lagar och bestämmelser, inklusive att erhålla nödvändiga slutanvändarbehörigheter, innan du sammanfogar datauppsättningar.

## Begränsningar

Flerkanalsanalys är en banbrytande och robust funktion, men har begränsningar för hur den kan användas.

* Aktuella återskrivningsfunktioner är begränsade till ett steg (beständigt ID till tillfälligt ID). Återinmatning i flera steg (till exempel beständigt ID till ett tillfälligt ID och sedan till ett annat tillfälligt ID) stöds inte.
* Endast händelsedatamängder stöds. Andra datauppsättningar, till exempel uppslagsdatauppsättningar, stöds inte.
* Anpassade ID-mappningar som används i din organisation stöds inte.
* Adobe Co-op-diagrammet och det privata diagrammet stöds inte.

## Aktivera flerkanalsanalys

När organisationen uppfyller alla krav och förstår sina begränsningar kan du följa de här stegen för att börja använda den i CJA.

1. Importera önskade data till Adobe Experience Platform. Se [Skapa ett schema](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html) och [Infoga data](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) i Adobe Experience Platform-dokumentationen.
1. Kontakta kontohanteraren för Adobe som innehåller följande:
   * En begäran om att aktivera flerkanalsanalys
   * Datauppsättnings-ID för den datauppsättning som du vill ändra inmatning för
   * Kolumnnamnet för det beständiga ID:t för den önskade datauppsättningen (identifierare som visas på varje rad)
   * Kolumnnamnet för det tillfälliga ID:t för den önskade datauppsättningen (länken för personidentifierare mellan datauppsättningar)
   * Din inställning är [repetitionsfrekvens och uppslagslängd](replay.md). Du kan välja att spela upp en gång i veckan med ett 7-dagars uppslagsfönster eller att spela upp varje dag med ett 1-dagars uppslagsfönster.
1. Kontohanteraren för Adobe aktiverar flerkanalsanalys när du tar emot din begäran. När den är aktiverad visas en ny inmatad datauppsättning i Adobe Experience Platform som innehåller en ny person-ID-kolumn. Kontohanteraren för Adobe kan ange det nya datauppsättnings-ID:t och kolumnnamnet för person-ID.
1. [Skapa en ](../create-connection.md) anslutning i CJA med den nya datauppsättningen och andra datauppsättningar som du vill inkludera. Välj rätt person-ID för varje datauppsättning.
1. [Skapa en ](/help/data-views/create-dataview.md) datavy baserad på anslutningen.

<!-- To do: Paragraph on backfill once product and marketing determine the best way forward. -->

När datavyn har konfigurerats är Analysis in CJA precis som alla andra analyser i CJA, förutom att data nu fungerar över alla kanaler och enheter.
