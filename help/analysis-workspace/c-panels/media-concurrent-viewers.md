---
title: Media Concurrent Viewers Panel
description: Lär dig hur du använder och tolkar panelen Media Concurrent Viewer i Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 0%

---

# Panelen Medievisningsprogram för samtidig användning {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Medievisningsprogram för samtidig användning"
>abstract="Skapa en panel för att analysera samtidiga visningsprogram under en viss tidsperiod."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Medievisningsprogram för samtidig användning"
>abstract="Analysera samtidiga visningsprogram över tid, visa samtidighet för toppvärden och dela upp och jämföra dem med segment, dimensioner, dimensionsobjekt eller datumintervall."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Den här artikeln visar panelen Medievisningsprogram för samtidig användning i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_.<br/>_Se [Panelen Medievisningsprogram för samtidiga &#x200B;](https://experienceleague.adobe.com/sv/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) för_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Den genomsnittliga minuten-panelen för media är endast tillgänglig för kunder som har köpt tillägget Streaming Media Collection för Customer Journey Analytics.
>
>Kontakta din Adobe-säljare eller Adobe-kontogrupp om du vill ha mer information.
>

Panelen **[!UICONTROL Media concurrent viewers]** gör det möjligt att analysera samtidiga visningsprogram över tid, med information om maximal samtidighet och möjlighet att dela upp och jämföra.

Ni kan analysera samtidiga visningsprogram för att förstå var maximal samtidighet inträffade eller var bortfall inträffade för att ge värdefull insikt i innehållets och visningsprogrammets kvalitet. Och för att hjälpa till med felsökning eller planering av volym eller skala.

I Analysis Workspace är indikatorn för Concurrent viewers antalet unika personer som visar medieströmmarna vid en viss tidpunkt, oavsett antalet sessioner.


>[!BEGINSHADEBOX]

En demonstrationsvideo finns i ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panelen Medievisningsprogram för samtidig användning](https://video.tv.adobe.com/v/26990/?quality=12&learn=on){target="_blank"} .

{{videoaa}}

>[!ENDSHADEBOX]

## Använd

Så här använder du en **[!UICONTROL Media concurrent viewers]**-panel:

1. Skapa en **[!UICONTROL Media concurrent viewers]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. Se till att du väljer en datavy för panelen som har konfigurerade komponenter från den direktuppspelande mediesamlingen.

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.

### Panelindata

Du kan konfigurera panelen för visningsprogram för parallella media med följande indatainställningar:

| Inställning | Beskrivning |
|---|---|
| **[!UICONTROL Panel date range]** | Panelens datumintervall är som standard Idag.  Du kan redigera den för att visa en enstaka dag eller flera månader i taget. <br> <br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| **[!UICONTROL Granularity]** | Granularitetsstandardvärdet är Minut.<br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| **[!UICONTROL Panel summary numbers]** | Det finns en sammanfattning av datum- och tidsinformation för samtidiga visningsprogram. Maximal visar detaljer för maximal samtidighet. **[!UICONTROL Minimum]** visar information om dalvärdet.  Som standard visas bara Maximum, men du kan ändra den till Minimum eller både Maximum och Minimum.<br><br>Om du använder uppdelningar visas ett summeringsnummer för varje. |
| **[!UICONTROL Series breakdown]** | Du kan även dela upp visualiseringen efter segment, dimensioner, dimensionsobjekt eller datumintervall.<br>Du kan visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå.<br>När du drar en dimension markeras de översta dimensionsobjekten automatiskt baserat på det valda panelens datumintervall.<br>Om du vill jämföra datumintervall drar du 2 eller fler datumintervall till serieuppdelningssegmentet. |

Här är ett exempel på panelen som konfigurerats för **[!UICONTROL Minute]** granularitet, med **[!UICONTROL Maximum only]** sammanfattningsnummer. Och bruten av **[!UICONTROL Other]**, **[!UICONTROL Table]**, **[!UICONTROL Mobile Phone]**, **[!UICONTROL Gaming Console]**, **[!UICONTROL Media Player]**, **[!UICONTROL Set-top Box]**, **[!UICONTROL Television]**.

![Serieuppdelningsvyn i Media Concurrent Viewer med 7 av 10 dimensioner, segment eller datumintervall.](assets/concurrent-viewers-series-breakdown.png)

### Panelutdata

Panelen Media Concurrent Viewer returnerar ett linjediagram och sammanfattningsnummer som innehåller information om maximalt och/eller lägsta antal samtidiga visningsprogram.  Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt.

Välj när som helst ![Redigera medievyn för samtidig användning](/help/assets/icons/Edit.svg) för att redigera och återskapa panelen.

Om du väljer en seriebrytning visas en rad i linjediagrammet och ett sammanfattningsnummer för varje rad:

![Media Concurrent Viewer-utdata.](assets/concurrent-viewers-output.png)

### Datakälla

Det enda mätvärdet som kan användas på den här panelen är **[!UICONTROL Concurrent viewers]**:

| Mått | Beskrivning |
|---|---|
| **[!UICONTROL Concurrent viewers]** | Antalet unika personer som visar medieströmmarna vid en viss tidpunkt, oavsett antalet sessioner. |

Det finns ingen friformstabell i den här vyn.  Om du vill visa datakällan kan du hämta datakällan från snabbmenyn för visualisering av linjediagram och välja **[!UICONTROL Download data as CSV]**.  Serieuppdelningar ingår.

![Alternativen för Concurrent viewers-utdata med&quot;Download data as CSV&quot; markerat.](assets/concurrent-viewers-download-csv.png)

## Vanliga frågor

| Fråga | Svar |
|---|---|
| Var är friformsregistret? Hur ser jag datakällan? | Frihandsregistret är inte tillgängligt i den här vyn.  Du kan hämta datakällan från snabbmenyn för linjediagram och välja **[!UICONTROL Download data as CSV]**. |
| Varför ändrades min granularitet? | Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet.<br><br>När du ändrar från ett större datumintervall till ett mindre uppdateras granulariteten till den lägsta detaljnivån som tillåts när datumintervallet ändras. Om du vill visa en högre granularitet redigerar du panelen och återskapar den. |
| Hur jämför jag videonamn, segment, innehållstyper och andra? | Om du vill jämföra de här objekten i en enda visualisering drar du segment, dimensioner eller specifika dimensionsobjekt i serieuppdelningssegmentet.<br><br>Vyn är begränsad till tio uppdelningar.  Om du vill visa mer än 10 måste du använda flera paneler. |
| Hur jämför jag datumintervall? | Om du vill jämföra datumintervall i en enda visualisering använder du serieuppdelningarna genom att dra två eller flera datumintervall.  Datumintervallen åsidosätter panelens datumintervall. |
| Hur ändrar jag visualiseringstypen? | På den här panelen kan du endast använda linjevisualisering för tidsserien. |
| Kan jag köra avvikelseidentifiering? | Nej.  Anomalsidentifiering är inte tillgängligt för den här panelen. |
| Varför använda unika personer istället för aktiva sessioner? | Genom att använda unika personer kan du ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |
| Vad innebär det att ha samtidiga visningsprogram med högre granularitet än en minut? | Med en granularitet som är större än en minut är samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom det tidsintervallet.  På timnivå är till exempel samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom timmen. |
| Visar arbetsytan samma information som rapporten Samtidiga visningsprogram? | Nej.  I Analysis Workspace definieras mätvärdet för Concurrent viewers som antalet unika personer som visar medieströmmen vid en viss tidpunkt. Oavsett antalet sessioner.<br><br>Det här måttet skiljer sig från Concurrent Viewer-rapportering i avsnittet Rapporter, där Concurrent Active Sessions används. Med unika personkonton kan du ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Skapa en panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>&#x200B;>[Medieuppspelningstid för panelen &#x200B;](media-playback-time-spent.md)
>&#x200B;>[Medie - genomsnittlig minutmålspanel](average-minute-audience-panel.md)
>