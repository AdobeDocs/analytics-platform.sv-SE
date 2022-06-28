---
title: Panelen för samtidiga medieanvändare
description: Så här använder och tolkar du panelen Media Concurrent Viewer i Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 29575b51-e319-4156-9834-aa0b671afb31
source-git-commit: a9ba9def94a2f156f6d2d8e59c0155a492c3978c
workflow-type: tm+mt
source-wordcount: '1012'
ht-degree: 1%

---

# Panelen för samtidiga medieanvändare

Media Analytics-kunder kan analysera samtidiga tittare för att förstå var maximal samtidighet har inträffat eller var bortfall har skett för att ge värdefull insikt i kvaliteten på innehåll och tittarengagemang och för att hjälpa till med felsökning eller planering av volym eller skala.

I Analysis Workspace är Concurrent Viewers antalet unika besökare som visar medieströmmarna vid en viss tidpunkt, oavsett antalet sessioner.

Med Media Concurrent Viewers-panelen kan man analysera samtidiga visningsprogram över tiden, med detaljer om maximal samtidighet och möjlighet att dela upp och jämföra.  Om du vill få åtkomst till panelen Medievisningsprogram för samtidiga media går du till en rapportsvit med Media Analytics-komponenter aktiverade. Klicka sedan på panelikonen längst till vänster och dra panelen till ditt Analysis Workspace-projekt.

Här är en videoöversikt av den här panelen:

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## Panelindata {#Input}

Du kan konfigurera panelen Medievisningsprogram för samtidig användning med dessa indatainställningar:

| Inställning | Beskrivning |
|---|---|
| Panelens datumintervall | Panelens datumintervall är som standard Idag.  Du kan redigera den för att visa en enstaka dag eller flera månader i taget. <br> <br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Kornighet | Granularitetsstandardvärdet är Minut. <br> <br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Sammanfattningsnummer för panel | Det finns en sammanfattning av datum- och tidsinformation för samtidiga visningsprogram. Maximal visar detaljer för maximal samtidighet. Minimivärdet visar information om dalvärdet.  Som standard visas bara Maximum, men du kan ändra den till Minimum eller både Maximum och Minimum.<br><br>Om du använder uppdelningar visas ett summeringsnummer för varje. |
| Uppdelning efter serie | Du kan även dela upp visualiseringen efter segment, dimensioner, dimensionsobjekt eller datumintervall. <br><br>- Du kan visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå.<br><br>- När du drar en dimension markeras de översta dimensionsobjekten automatiskt baserat på det valda panelens datumintervall.<br><br>- Om du vill jämföra datumintervall drar du 2 eller fler datumintervall till serieuppdelningsfiltret. |

### Standardvy

![Standardvy](assets/concurrent-viewers-default.png)


### Serieuppdelad vy

![serieuppdelad vy](assets/concurrent-viewers-series-breakdown.png)

## Panelutdata {#Output}

Panelen Media Concurrent Viewer returnerar ett linjediagram och sammanfattningsnummer som innehåller information om maximalt och/eller lägsta antal samtidiga visningsprogram.  Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt.

Du kan när som helst redigera och återskapa panelen genom att klicka på redigeringspennan längst upp till höger.

Om du har valt seriebrytning visas en rad i linjediagrammet och ett sammanfattningsnummer för varje rad:

![samtidiga visningsprogram](assets/concurrent-viewers-output.png)

### Datakälla

Det enda mätvärdet som kan användas i den här panelen är samtidiga visningsprogram:

| Mått | Beskrivning |
|---|---|
| Samtidiga visningsprogram | Antal unika besökare som visar medieströmmar vid en viss tidpunkt, oavsett antalet sessioner.<br><br>Detta skiljer sig från Concurrent Viewer-rapporteringen i avsnittet Rapporter, där Concurrent Active Sessions används.  Använda unika besökskonton för att ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |

Det finns ingen friformstabell i den här vyn.  Om du vill visa datakällan kan du högerklicka på linjediagrammet och hämta som en CSV-fil.  Serieuppdelningar inkluderas.


![samtidiga visningsprogram](assets/concurrent-viewers-download-csv.png)

## Vanliga frågor {#FAQ}

| Fråga | Svar |
|---|---|
| Var är friformsregistret? Hur ser jag datakällan? | Frihandsregistret är inte tillgängligt i den här vyn.  Du kan hämta datakällan genom att högerklicka på linjediagrammet och hämta CSV-filen. |
| Varför ändrades min granularitet? | Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå).  Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet.<br><br>Om du ändrar från ett större datumintervall till ett mindre kommer granulariteten att uppdateras till den lägsta detaljnivån som tillåts när datumintervallet ändras. Om du vill visa en högre granularitet redigerar du panelen och återskapar den. |
| Hur jämför jag videonamn, segment, innehållstyper osv.? | Om du vill jämföra dessa i en enda visualisering drar du segment, dimensioner eller specifika dimensionsobjekt i serieuppdelningsfiltret.<br><br>Vyn är begränsad till tio uppdelningar.  Om du vill visa mer än 10 måste du använda flera paneler. |
| Hur jämför jag datumintervall? | Om du vill jämföra datumintervall i en enda visualisering använder du serieuppdelningarna genom att dra två eller flera datumintervall.  Dessa datumintervall åsidosätter panelens datumintervall. |
| Hur ändrar jag visualiseringstypen? | På den här panelen kan du endast använda linjevisualisering för tidsserien. |
| Kan jag köra avvikelseidentifiering? | Nej.  Anomalsidentifiering är inte tillgängligt för den här panelen. |
| Varför använda unika besökare istället för aktiva sessioner? | Genom att använda unika besökare kan du ta bort oönskade toppar vid visningsgränserna (där sessionerna avslutas och börjar samtidigt). |
| Vad innebär det att ha samtidiga visningsprogram med högre granularitet än en minut? | Med en granularitet som är större än en minut är samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom det tidsintervallet.  På timnivå är till exempel samtidiga visningsprogram summan av unika samtidiga visningsprogram för alla minuter inom timmen. |
| Visar arbetsytan samma information som rapporten Samtidiga visningsprogram? | Nej.  I Analysis Workspace definieras samtidiga visningsprogram som antalet unika besökare som visar medieströmmen vid en viss tidpunkt, oavsett antalet sessioner.<br><br>Detta skiljer sig från Concurrent Viewer-rapporteringen i avsnittet Rapporter, där Concurrent Active Sessions används.  Med unika besökskonton kan du ta bort oönskade toppar vid visningsgränserna, där sessionerna avslutas och börjar samtidigt. |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
