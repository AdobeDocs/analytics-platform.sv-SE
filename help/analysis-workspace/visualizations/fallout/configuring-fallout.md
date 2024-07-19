---
description: Lär dig hur du anger kontaktytorna för att skapa en flerdimensionell fallsekvens.
title: Konfigurera en utfallsvisualisering
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 0%

---

# Konfigurera en utfallsvisualisering

Du kan ange kontaktytorna för att skapa en flerdimensionell utfallssekvens. Vanligtvis är en kontaktyta en sida på din webbplats. Kontaktpunkterna är dock inte begränsade till sidor. Du kan t.ex. lägga till händelser, t.ex. enheter, samt unika personer och returbesök. Du kan också lägga till dimensioner, t.ex. en kategori, webbläsartyp eller ett internt sökord.

Du kan också lägga till filter i en kontaktyta. Du kanske vill jämföra filter som iOS- och Android-användare. Dra de önskade filtren högst upp i utfallet och information om dessa filter läggs till i utfallsrapporten. Om du bara vill visa dessa filter, kan du ta bort baslinjen Alla besök.

Det finns ingen begränsning för hur många steg du kan lägga till eller hur många dimensioner som kan användas.

Du kan göra en pthing på eVars, inklusive eVars- och [listVars](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html)-marknadsföring (variabler som kan ha flera värden per händelse, till exempel products, listVars, merchandising eVars och list props). Anta till exempel att någon tittar på skor, skjorta på en sida och på nästa sida tittar de på skjorta, strumpor. Nästa produktflödesrapport från skor blir skjorta och strumpa, INTE skjorta.

1. Dra en [!UICONTROL Fallout]-visualisering från listrutan Visualiseringar till en [!UICONTROL Freeform Table].

1. Dra siddimensionen till friformstabellen och dra sedan en sida (i det här fallet Home - JEsquire) till fältet **[!UICONTROL Add TouchPoint]** som första kontaktyta.

   ![Listrutan Alla besök visar JEsquire som har dragits till fältet Lägg till kontaktpunkt.](assets/fallout1.png)

   Håll muspekaren över en kontaktyta för att se bortfallet och annan information om den nivån, t.ex. namnet på kontaktytan, antalet personer vid den punkten och se hur framgångsrik kontaktytan är (samt jämför framgångssiffran med andra kontaktytor).

   De cirklade siffrorna i den grå delen av fältet visar utfallet mellan kontaktytor (inte det övergripande utfallet till den punkten). Touchpoint % visar det lyckade genombrottet från föregående steg till det aktuella steget i utfallsrapporten.

   Du kan också lägga till en sida i utfallsrapporten, i stället för hela dimensionen. Klicka på högerpilen &quot;>&quot; på siddimensionen för att välja den sida som ska läggas till i utfallsrapporten.

1. Fortsätt lägga till kontaktytor tills sekvensen är klar.

   Du kan **kombinera flera kontaktytor** genom att dra en eller flera ytterligare kontaktytor till en kontaktyta.

   >[!NOTE]
   >
   >Flera filter förenas med AND, men flera objekt som dimensionsobjekt och mått förenas med OR.

   ![Sidan:CamerRoll eller Sida: Kamerans kontaktytor är markerade.](assets/multiple_obj_touchpoint.png)

1. Du kan också **begränsa enskilda kontaktytor till nästa händelse** (till skillnad från&quot;till slut&quot;) i sökvägen. Under varje kontaktyta finns det en väljare med alternativen&quot;Eventual Path&quot; och&quot;Next Hit&quot;, vilket visas här:

   ![Vyn Alla besök visar alternativet för eventuell sökväg markerat. ](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evental sökväg </p> <p>(Standard) </p> </td> 
   <td colname="col2"> <p>Besökare räknas som"så småningom" landar på nästa sida i banan, men inte nödvändigtvis på nästa händelse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nästa </p> </td> 
   <td colname="col2"> <p>Besökare räknas som kommer att landa på nästa sida i banan vid nästa händelse. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utfallsinställningar {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Inställning | Beskrivning |
|--- |--- |
| Utfallsbehållare <ul><li>Besök</li><li>Besökare</li></ul> | Gör att du kan växla mellan Besök och Besök för att analysera personsökningar. Standardvärdet är Visitor.  Dessa inställningar hjälper er att förstå personernas engagemang på personnivå (olika besök) eller begränsa analysen till ett enda besök. |

När du **högerklickar på en kontaktyta** visas följande alternativ:

| Alternativ | Beskrivning |
|--- |--- |
| Trendkontaktyta | Se trenddata för en kontaktyta i ett linjediagram med vissa fördefinierade avvikelseidentifieringsdata. |
| Trend Touchpoint (%) | Trends the total fallout percentage. |
| Trend all touchpoints (%) | Trends all the touchpoint percentage in the fallout (except &quot;All Visits&quot;, if it is included), on the same chart. |
| Bryt ner fallthrough vid den här kontaktytan | Se vad personer gjorde mellan två kontaktytor (den här kontaktytan och nästa kontaktyta) om de fortsatte till nästa kontaktyta. Då skapas en frihandstabell med dina mått. Du kan ersätta dimensioner och andra element i tabellen. |
| Bryt ned bortfallet vid den här kontaktytan | Se vad de som inte klarade sig igenom tratten gjorde direkt efter det valda steget. |
| Skapa filter från kontaktyta | Skapa ett nytt filter från den valda kontaktytan. |
