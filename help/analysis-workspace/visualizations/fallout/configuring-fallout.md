---
description: 'null'
title: Konfigurera en utfallsvisualisering
uuid: fc117745-baf3-46fb-873d-9307092cc337
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 2%

---


# Konfigurera en utfallsvisualisering

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Du kan ange pekpunkterna för att skapa en flerdimensionell utfallssekvens. Vanligtvis är en pekpunkt en sida på webbplatsen. Men det finns inte bara sidor. Du kan t.ex. lägga till evenemang, t.ex. enheter, samt unika besökare och återsändandebesök. Du kan också lägga till dimensioner, t.ex. en kategori, webbläsartyp eller ett internt sökbegrepp.

Du kan till och med lägga till segment i en pekpunkt. Du kan t.ex. vilja jämföra segment, t.ex. iOS- och Android-användare. Dra de önskade segmenten till början av utfallet och information om dessa segment läggs till i utfallsrapporten. Om du bara vill visa dessa segment kan du ta bort baslinjen Alla besök.

Det finns ingen begränsning av antalet steg du kan lägga till eller antalet dimensioner som används.

Du kan göra en målning på eVars, inklusive att marknadsföra eVars och [listaVars](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html) (variabler som kan ha flera värden per träff, t.ex. produkter, listVars, marknadsföringseVars och listprops). Anta till exempel att någon tittar på skor, skjorta på en sida och på nästa sida tittar de på skjortor, sockor. Nästa rapport om produktflödet från skor blir skjortor och strumpor, INTE skjortor.

1. Dra en [!UICONTROL Fallout] visualisering från listrutan Visualiseringar till en [!UICONTROL Freeform Table].

1. Dra siddimensionen till frihandstabellen och dra en sida (i det här fallet Home - JEsquire) till den **[!UICONTROL Add TouchPoint]** fält som första beröringspunkt.

   ![](assets/fallout1.png)

   Hovra över en beröringspunkt för att se utfallet och annan information om den nivån, t.ex. namnet på beröringspunkten, besökarantal vid den tidpunkten, och se framgångssiffran för den beröringspunkten (samt jämföra framgångssiffran med andra beröringspunkter).

   De cirklade talen i den gråa delen av raden visar utfallet mellan pekpunkterna (inte den totala utfallet till den punkten). Touchpoint % visar det lyckade steget från föregående steg till det aktuella steget i utfallsrapporten.

   Du kan också lägga till en enda sida i utfallsrapporten i stället för hela dimensionen. Klicka på högerpilen &quot;>&quot; på siddimensionen för att välja den specifika sida som ska läggas till i utfallsrapporten.

1. Fortsätt lägga till pekpunkter tills sekvensen är klar.

   Du kan **kombinera flera pekpunkter** genom att dra ytterligare en eller flera punkter till en beröringspunkt.

   >[!NOTE]
   >
   >Flera segment är sammanfogade med AND, men flera objekt, t.ex. dimensionsobjekt och mått, är sammanfogade med ELLER.

   ![](assets/multiple_obj_touchpoint.png)

1. Du kan också **begränsa enskilda fästpunkter till nästa träff** (i motsats till &quot;så småningom&quot;) inom banan. Under varje beröringspunkt finns det en selektor med alternativen &quot;Eventual Path&quot; och &quot;Next Träff&quot;, som visas här:

   ![](assets/next-hit-eventually.png)

<table id="table_A91D99D9364B41929CC5A5BC907E8985"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eventuell sökväg </p> <p>(Standard) </p> </td> 
   <td colname="col2"> <p>Besökare räknas som "så småningom" landar på nästa sida i banan, men inte nödvändigtvis på nästa träff. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nästa träff </p> </td> 
   <td colname="col2"> <p>Besökare räknas som kommer att landa på nästa sida i banan vid nästa träff. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utföringsinställningar {#section_0C7C89D72F0B4D6EB467F278AC979093}

| Inställning | Beskrivning |
|--- |--- |
| Fallout-behållare <ul><li>Gå in på</li><li>Besökare</li></ul> | Gör att du kan växla mellan Besök och Besök för att analysera besökspatchen. Standardvärdet är Visitor.  Dessa inställningar hjälper dig att förstå besökarnas engagemang på besöksnivå (mellan besök) eller begränsa analysen till ett enda besök. |
| Visa &quot;Alla besökare&quot; som första beröringspunkt | Du kan avmarkera detta om du hellre inte vill ha &quot;Alla besökare&quot; som första beröringspunkt. |

När du **högerklicka på en beröringspunkt** visas följande alternativ:

| Alternativ | Beskrivning |
|--- |--- |
| Trend-touchpoint | Se trenddata för en touchpoint i ett linjediagram, med vissa förbyggda anomalsidentifieringsdata. |
| Trend-pekpunkt (%) | Trender den totala utfallsprocenten. |
| Trend alla pekpunkter (%) | Trender alla procentsatser för pekpunkter i utfallet (förutom &quot;Alla besök&quot;, om det ingår), i samma diagram. |
| Bryt av felsökning vid denna beröringspunkt | Visa vad besökarna gjorde mellan två beröringspunkter (denna och nästa beröringspunkt) om de fortsatte till nästa beröringspunkt. Då skapas en frihandstabell som visar dina dimensioner. Du kan ersätta dimensioner och andra element i tabellen. |
| Bryt ned utfall vid den här beröringspunkten | Visa vad de som inte klarade sig igenom tratten gjorde omedelbart efter det valda steget. |
| Skapa segment från touchpoint | Skapa ett nytt segment från den markerade kontrollpunkten. |
