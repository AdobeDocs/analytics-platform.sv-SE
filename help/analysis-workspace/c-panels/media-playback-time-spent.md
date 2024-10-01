---
title: Medieuppspelningstid spenderad panel
description: Så här använder och tolkar du den mediespelningstid som används i panelen i Analysis Workspace.
feature: Panels
exl-id: de0fdbea-71f0-445b-a1e4-c7e895f142d4
role: User
source-git-commit: 519e7d583edc1eab9b6dd10fec024ac4bb2b93cf
workflow-type: tm+mt
source-wordcount: '1116'
ht-degree: 0%

---

# Medieuppspelningstid som använts på panelen {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaplaybacktimespent_button"
>title="Medieuppspelningstid"
>abstract="Skapa en panel för att analysera videoförbrukningen över tid, med olika granularitetsnivåer och möjlighet att dela upp och jämföra."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaplaybacktimespent_panel"
>title="Medieuppspelningstid"
>abstract="Analysera videoförbrukningen över tid, välj olika detaljrikedom, uppdelad och jämför.<br/><br/>**Kornighet**: Välj en tidsperiod om du vill visa samtidiga visningsprogram efter.<br/>**Panelsammanfattningsnummer (valfritt)**: Alternativ för att visa sammanfattningsnummer med datum- och tidsinformation för varje rad. Maximalt värde visar detaljer för den maximala uppspelningstiden. Minimivärdet visar information om dalvärdet. Summan visar information om den totala uppspelningstiden.<br/>**Serieuppdelning (valfritt)**: Dela upp visualisering efter segment, dimensioner, dimensionsobjekt eller datumintervall. Visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå.<br/>**Tidsformat**: Alternativ för att visa tidsformatet för visualiseringar i timmar eller minuter."

<!-- markdownlint-enable MD034 -->



>[!NOTE]
>
>Den genomsnittliga minuten-panelen för media är endast tillgänglig för kunder som har köpt tillägget Streaming Media Collection för Customer Journey Analytics.
>Kontakta din säljare på Adobe eller Adobe för mer information.
>

Panelen **[!UICONTROL Media playback time spent]** gör det möjligt att analysera uppspelningen över tid, med information om maximal samtidighet och möjlighet att dela upp och jämföra.

I Analysis Workspace är uppspelningstiden den tid som går åt till att visa medieströmmarna vid en viss tidpunkt. Den innehåller paus, buffert och tid att starta.

Kunder som har köpt tillägget Streaming Media Collection kan analysera uppspelningstiden för att få värdefulla insikter om innehållets kvalitet och tittarnas engagemang. Och som hjälp vid felsökning eller planering av volym eller skala.

Den uppspelningstid som spenderas kan hjälpa dig att förstå:

* Där maximal samtidighet inträffade.

* Där bortfall inträffade.

+++ Visa en videodemonstration av den här funktionen.

>[!VIDEO](https://video.tv.adobe.com/v/338699)

+++

## Använd

Så här använder du en **[!UICONTROL Media playback time spent]**-panel:

1. Skapa en **[!UICONTROL Media playback time spent]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. Se till att du väljer en datavy för panelen som har komponenter konfigurerade från tillägget Direktuppspelad mediasamling.

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.


### Panelindata

Du kan konfigurera panelen Tid för uppspelning av media med följande indatainställningar:

| Inställning | Beskrivning |
|---|---|
| Panelens datumintervall | Panelens datumintervall är som standard Idag. Du kan redigera den för att visa en enstaka dag eller flera månader i taget.<br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Kornighet | Granularitetsstandardvärdet är Minut.<br>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
| Sammanfattningsnummer för panel | Om du vill visa datum- eller tidsinformation för uppspelningstid finns ett sammanfattningsnummer. Maximal visar detaljer för maximal samtidighet. Minimivärdet visar information om dalvärdet. Summan lägger ihop den totala uppspelningstiden för markeringen. Panelens standardinställning visar bara Maximum, men du kan ändra den till Minimal, Summa eller valfri kombination av de tre.<br>Om du använder uppdelningar visas ett summeringsnummer för varje. |
| Uppdelning efter serie | Du kan även dela upp visualiseringen med filter, dimensioner, dimensionsobjekt eller datumintervall.<p>- Du kan visa upp till 10 rader i taget. Uppdelningarna begränsas till en enda nivå.</p><p>- När du drar en dimension markeras de översta dimensionsobjekten automatiskt baserat på det valda panelens datumintervall.</p>- Om du vill jämföra datumintervall drar du 2 eller fler datumintervall till serieuppdelningsfiltret. |
| Tidsformat | Du kan visa uppspelningstiden i antingen `Hours:Minutes:Seconds` (standard) eller `Minutes` (som visas i heltal, avrundat uppåt till 0,5). |
| Visning av datumsekvens | Om du har placerat minst två datumintervallfilter som serieuppdelningar visas alternativet att välja antingen övertäckning (standard) eller sekventiell. Med Övertäckning visas raderna med en vanlig x-axelstart så att de körs parallellt, medan linjerna visas sekventiellt med den specifika x-axelstarten. Om dataraderna är i linje (till exempel filtret 1 slutar vid 20:44 och filtret 2 börjar vid 20:45) visas raderna i följd. |


![Mediespelbokens tid har använts i standardvyn.](assets/mpts_default_view.png)

### Panelutdata

På panelen Medieuppspelningstid för spenderad tid returneras ett linjediagram och sammanfattningsnummer som innehåller information om den maximala, minimala och/eller sammanlagda uppspelningstiden. Längst upp på panelen finns en sammanfattningsrad som påminner om de panelinställningar du har valt.

Du kan när som helst välja ![Redigera mediespelningstid på ](/help/assets/icons/Edit.svg) för att redigera och återskapa panelen.

Om du väljer seriebrytning visas en rad i linjediagrammet och ett sammanfattningsnummer för varje rad:

![Medieuppspelningstiden för utdata som visar ett linjediagram och en sammanfattning.](assets/mpts_outputs1.png)

### Datakälla

Det enda mätvärdet som kan användas i den här panelen är Använd uppspelningstid.

| Mått | Beskrivning |
|---|---|
| Antal uppspelningstider | Totalt `hours:minutes:seconds` (eller `minutes`) av innehåll som visas under den valda granulariteten, inklusive paus, buffert och tid till start. |

## Vanliga frågor

| Fråga | Svar |
|---|---|
| Var är friformsregistret? Hur ser jag datakällan? | <p></p><p>Frihandsregistret är inte tillgängligt i den här vyn. Om du vill hämta datakällan går du till snabbmenyn i linjediagrammet och väljer alternativet att hämta CSV-filen.</p> |
| <p>Varför ändrades min granularitet?</p> | <p>Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet.</p><p></p><p>Om du ändrar från ett större datumintervall till ett mindre uppdateras granulariteten till den lägsta detaljnivån som tillåts när datumintervallet ändras. Om du vill visa en högre granularitet redigerar du panelen och återskapar den.</p> |
| <p></p><p>Hur jämför jag videonamn, filter, innehållstyper med mera?</p> | <p>Om du vill jämföra dessa i en enda visualisering drar du filter, dimensioner eller specifika dimensionsobjekt i serieuppdelningsfiltret.</p><p></p><p>Vyn är begränsad till tio uppdelningar. Om du vill visa mer än 10 måste du använda flera paneler.</p> |
| Hur jämför jag datumintervall? | Om du vill jämföra datumintervall i en enda visualisering använder du serieuppdelningarna genom att dra två eller flera datumintervall. Dessa datumintervall åsidosätter panelens datumintervall. |
| Hur ändrar jag visualiseringstypen? | <p></p><p>På den här panelen kan du endast använda linjevisualisering för tidsserien.</p> |
| Kan jag köra avvikelseidentifiering? | <p></p><p>Nej. Anomalsidentifiering är inte tillgängligt för den här panelen.</p> |


>[!MORELIKETHIS]
>
>[Skapa en panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Medie - genomsnittlig minutmålspanel](average-minute-audience-panel.md)
>[Panelen för samtidiga visningsprogram för media](media-concurrent-viewers.md)
>