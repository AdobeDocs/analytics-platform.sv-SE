---
title: Media Concurrent Viewers panel
description: Så här använder och tolkar du panelen Media Concurrent Viewer i Analysis Workspace.
feature: Panels
exl-id: a442fb9c-165f-4136-95e2-ce92b9280c25
role: User
source-git-commit: e4d4ff530d28e692301ca0671e055a164b9f7035
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# Media Concurrent Viewers panel

Ni kan analysera samtidiga visningsprogram för att förstå var maximal samtidighet inträffade eller var bortfall inträffade för att ge värdefull insikt i innehållets och visningsprogrammets kvalitet och för att hjälpa till med felsökning eller planering av volym eller skala.

I Analysis Workspace är Concurrent Viewer antalet unika personer som visar medieströmmarna vid en viss tidpunkt, oavsett antalet sessioner.

Med Media Concurrent Viewers-panelen kan man analysera samtidiga visningsprogram över tiden, med detaljer om maximal samtidighet och möjlighet att dela upp och jämföra.  Om du vill få åtkomst till panelen Medievisningsprogram för samtidig användning går du till en datavy med komponenter aktiverade från tillägget Direktuppspelad mediasamling. Klicka sedan på panelikonen längst till vänster och dra panelen till ditt Analysis Workspace-projekt.

Här är en videoöversikt av den här panelen:

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## Panelindata {#Input}

Du kan konfigurera panelen Medievisningsprogram för samtidig användning med dessa indatainställningar:

| Inställning | Beskrivning |
|---|---|
| Panelens datumintervall | Panelens datumintervall är som standard Idag.  Du kan redigera den för att visa en enstaka dag eller flera månader i taget. <br> <br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Kornighet | Granularitetsstandardvärdet är Minut. <br> <br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Sammanfattningsnummer för panel | Det finns en sammanfattning av datum- och tidsinformation för samtidiga visningsprogram. Maximal visar detaljer för maximal samtidighet. Minimivärdet visar information om dalvärdet.  Som standard visas bara Maximum, men du kan ändra den till Minimum eller både Maximum och Minimum.<br><br>Om du använder uppdelningar visas ett summeringsnummer för varje. |
| Uppdelning efter serie | Du kan även dela upp visualiseringen med filter, dimensioner, dimensionsobjekt eller datumintervall. <br><br>- Du kan visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå.<br><br>- När du drar en dimension markeras de översta dimensionsobjekten automatiskt baserat på det valda panelens datumintervall.<br><br>- Om du vill jämföra datumintervall drar du 2 eller fler datumintervall till serieuppdelningsfiltret. |

### Standardvy

![Standardvyn för Media Concurrent Viewer.](assets/concurrent-viewers-default.png)


### Serieuppdelad vy

![Serieuppdelningsvyn i Media Concurrent Viewer med 7 av 10 dimensioner, segment eller datumintervall.](assets/concurrent-viewers-series-breakdown.png)

## Panelutdata {#Output}

Panelen Media Concurrent Viewer returnerar ett linjediagram och sammanfattningsnummer som innehåller information om maximalt och/eller lägsta antal samtidiga visningsprogram.  Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt.

Du kan när som helst redigera och återskapa panelen genom att klicka på redigeringspennan längst upp till höger.

Om du har valt seriebrytning visas en rad i linjediagrammet och ett sammanfattningsnummer för varje rad:

![Media Concurrent Viewer-utdata.](assets/concurrent-viewers-output.png)

### Data Source

Det enda mätvärdet som kan användas i den här panelen är samtidiga visningsprogram:

| Mått | Beskrivning |
|---|---|
| Samtidiga visningsprogram | Antal unika personer som visar medieströmmarna vid en viss tidpunkt, oavsett antalet sessioner.<br><br>Det här skiljer sig från Concurrent Viewer-rapportering i avsnittet Rapporter, där Concurrent Active Sessions används.  Med unika personkonton kan du ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |

Det finns ingen friformstabell i den här vyn.  Om du vill visa datakällan kan du högerklicka på linjediagrammet och hämta som en CSV-fil.  Serieuppdelningar inkluderas.


![Alternativen för Concurrent viewers-utdata med&quot;Download data as CSV&quot; markerat.](assets/concurrent-viewers-download-csv.png)

## Vanliga frågor {#FAQ}

| Fråga | Svar |
|---|---|
| Var är friformsregistret? Hur ser jag datakällan? | Frihandsregistret är inte tillgängligt i den här vyn.  Du kan hämta datakällan genom att högerklicka på linjediagrammet och hämta CSV-filen. |
| Varför ändrades min granularitet? | Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet.<br><br>Om du ändrar från ett större datumintervall till ett mindre kommer granulariteten att uppdateras till den lägsta detaljnivån som tillåts när datumintervallet ändras. Om du vill visa en högre granularitet redigerar du panelen och återskapar den. |
| Hur jämför jag videonamn, filter, innehållstyper osv.? | Om du vill jämföra dessa i en enda visualisering drar du filter, dimensioner eller specifika dimensionsobjekt i serieuppdelningsfiltret.<br><br>Vyn är begränsad till tio uppdelningar.  Om du vill visa mer än 10 måste du använda flera paneler. |
| Hur jämför jag datumintervall? | Om du vill jämföra datumintervall i en enda visualisering använder du serieuppdelningarna genom att dra två eller flera datumintervall.  Dessa datumintervall åsidosätter panelens datumintervall. |
| Hur ändrar jag visualiseringstypen? | På den här panelen kan du endast använda linjevisualisering för tidsserien. |
| Kan jag köra avvikelseidentifiering? | Nej.  Anomalsidentifiering är inte tillgängligt för den här panelen. |
| Varför använda unika personer istället för aktiva sessioner? | Genom att använda unika personer kan du ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |
| Vad innebär det att ha samtidiga visningsprogram med högre granularitet än en minut? | Med en granularitet som är större än en minut är samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom det tidsintervallet.  På timnivå är till exempel samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom timmen. |
| Visar arbetsytan samma information som rapporten Samtidiga visningsprogram? | Nej.  I Analysis Workspace definieras samtidiga visningsprogram som antalet unika personer som visar medieströmmen vid en viss tidpunkt, oavsett antalet sessioner.<br><br>Det här skiljer sig från Concurrent Viewer-rapportering i avsnittet Rapporter, där Concurrent Active Sessions används.  Med unika personkonton kan du ta bort oönskade toppar vid visningsgränserna, där sessionerna avslutas och börjar samtidigt. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
