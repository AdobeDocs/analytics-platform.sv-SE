---
description: 'null'
title: Konfigurera en utfallsvisualisering
uuid: fc117745-baf3-46fb-873d-9307092cc337
translation-type: tm+mt
source-git-commit: e004a2a8ec24113ae8b62a9d30c10fe0eb763460
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 2%

---


# Konfigurera en utfallsvisualisering

Du kan ange kontaktytorna för att skapa en flerdimensionell utfallssekvens. Vanligtvis är en kontaktyta en sida på din webbplats. Kontaktpunkterna är dock inte begränsade till sidor. Du kan till exempel lägga till händelser, som enheter, samt unika besökare och returbesök. Du kan också lägga till dimensioner, t.ex. en kategori, webbläsartyp eller ett internt sökord.

Du kan till och med lägga till segment inom en kontaktyta. Du kanske vill jämföra segment, till exempel iOS- och Android-användare. Dra de önskade segmenten högst upp i utfallet och information om dessa segment läggs till i utfallsrapporten. Om du bara vill visa dessa segment, kan du ta bort baslinjen Alla besök.

Det finns ingen begränsning för hur många steg du kan lägga till eller hur många dimensioner som kan användas.

Du kan göra saker på eVars, t.ex. genom att sälja eVars och [listVars](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html) (variabler som kan ha flera värden per träff, t.ex. products, listVars, merchandising eVars och list props). Anta till exempel att någon tittar på skor, skjorta på en sida och på nästa sida tittar de på skjorta, strumpor. Nästa produktflödesrapport från skor blir skjorta och strumpa, INTE skjorta.

1. Dra en [!UICONTROL Fallout]-visualisering från listrutan Visualiseringar till en [!UICONTROL Freeform Table].

1. Dra siddimensionen till friformstabellen och dra sedan en sida (i det här fallet Home - JEsquire) till **[!UICONTROL Add TouchPoint]**-fältet som första kontaktyta.

   ![](assets/fallout1.png)

   Håll muspekaren över en kontaktyta för att se utfallet och annan information om den nivån, som namnet på kontaktytan, besökarantal vid den punkten, och se hur framgångsrik kontaktytan är (samt jämför framgångssiffran med andra kontaktytor).

   De cirklade siffrorna i den grå delen av fältet visar utfallet mellan kontaktytor (inte det övergripande utfallet till den punkten). Touchpoint % visar det lyckade genombrottet från föregående steg till det aktuella steget i utfallsrapporten.

   Du kan också lägga till en sida i utfallsrapporten, i stället för hela dimensionen. Klicka på högerpilen &quot;>&quot; på siddimensionen för att välja den sida som ska läggas till i utfallsrapporten.

1. Fortsätt lägga till kontaktytor tills sekvensen är klar.

   Du kan **kombinera flera kontaktytor** genom att dra en eller flera ytterligare kontaktytor till en kontaktyta.

   >[!NOTE]
   >
   >Flera segment är sammanfogade med AND, men flera objekt, som dimensionsobjekt och mått, är sammanfogade med OR.

   ![](assets/multiple_obj_touchpoint.png)

1. Du kan också **begränsa enskilda kontaktytor till nästa träff** (till skillnad från&quot;finally&quot;) i banan. Under varje kontaktyta finns det en väljare med alternativen&quot;Eventual Path&quot; och&quot;Next Hit&quot;, vilket visas här:

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evental sökväg </p> <p>(Standard) </p> </td> 
   <td colname="col2"> <p>Besökare räknas som"så småningom" landar på nästa sida i banan, men inte nödvändigtvis på nästa träff. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nästa träff </p> </td> 
   <td colname="col2"> <p>Besökare räknas som kommer att landa på nästa sida i banan vid nästa träff. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bortfallsinställningar {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Inställning | Beskrivning |
|--- |--- |
| Utfallsbehållare <ul><li>Gå in på</li><li>Besökare</li></ul> | Gör att du kan växla mellan Besök och Besök för att analysera besökarbanan. Standardvärdet är Visitor.  Dessa inställningar hjälper er att förstå besökarnas engagemang på besökarnivå (mellan besök) eller begränsa analysen till ett enda besök. |

När du **högerklickar på en kontaktyta** visas följande alternativ:

| Alternativ | Beskrivning |
|--- |--- |
| Trendkontaktyta | Se trenddata för en kontaktyta i ett linjediagram med vissa fördefinierade avvikelseidentifieringsdata. |
| Trend Touchpoint (%) | Trends the total fallout percentage. |
| Trend all touchpoints (%) | Trends all the touchpoint percentage in the fallout (except &quot;All Visits&quot;, if it is included), on the same chart. |
| Bryt ner fallthrough vid den här kontaktytan | Se vad besökarna gjorde mellan två kontaktytor (den här kontaktytan och nästa kontaktyta) om de fortsatte till nästa kontaktyta. Då skapas en frihandstabell med dina mått. Du kan ersätta dimensioner och andra element i tabellen. |
| Bryt ned bortfallet vid den här kontaktytan | Se vad de som inte klarade sig igenom tratten gjorde direkt efter det valda steget. |
| Skapa segment från kontaktyta | Skapa ett nytt segment från den markerade kontaktytan. |
