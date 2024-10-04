---
title: Panelen Mediegenomsnitt för miniatyrmålgrupp
description: Hur man använder och tolkar den minimala målgruppspanelen för media i Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: 1dff53e244e5d231e7075ce087705e33e0978096
workflow-type: tm+mt
source-wordcount: '1754'
ht-degree: 0%

---

# Mediemedelets minutmålspanel {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaminuteaverageaudience_button"
>title="Genomsnittlig minutmålgrupp för media"
>abstract="Skapa en panel för att analysera den genomsnittliga minuten-publiken för visst innehåll, eller under en viss tidsperiod."


<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_mediaaverageminuteaudience_panel"
>title="Genomsnittlig minutmålgrupp för media"
>abstract="Visar prestandan för visst medieinnehåll eller för en anpassad tidsperiod.<br/><br/>**Allmänna parametrar **<br/>**Beräkna mätvärden för**: Välj det mätvärde som ska användas för panelen. Välj **Specifikt innehåll** om du vill analysera den genomsnittliga minuten-publiken för specifikt innehåll eller händelse utifrån innehållets längd. **Välj Anpassad tidsperiod** om du vill analysera hur den genomsnittliga minuten publiken ändras under en anpassad vald tidsperiod.<br/>**Rapporteringsdimension**: Välj att rapportera med **videonamn** för dimensionen **Innehåll-ID**. Endast tillgängligt när du har valt Specifikt innehåll som mätvärde.<br/>**Kornighet**: Välj granularitet för rapporten. Endast tillgängligt när du har valt Anpassad tidsperiod som mått.<br/>**Filtrera innehåll efter (valfritt)**: Välj ett specifikt program, årstid, avsnitt eller välj en anpassad dimension för att filtrera innehållet.<br/><br/>**Avancerade inställningar **<br/>**Tabellinställningar**: Välj om du vill visa beräkningsvärden i tabellen.<br/>**Tidsåtgång för mått**: Välj vilken tid du vill använda för beräkning av specifikt innehåll. Endast tillgängligt när du har valt Specifikt innehåll som mätvärde."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel#specific-content" text="Specifikt innehåll"
>additional-url="https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel#custom-time-period" text="Anpassad tidsperiod"

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>Panelen **[!UICONTROL Media average minute audience]** är bara tillgänglig för kunder som har köpt tillägget Direktuppspelning av mediasamling för Customer Journey Analytics.
>
>Kontakta din säljare eller ditt Adobe-kontoteam på Adobe för mer information.
>

I Analysis Workspace kan den genomsnittliga minuten av publiken ge information om

* hur lång tid som har ägnats åt att visa en viss medieström delat med innehållets längd, eller
* den tid som du har tittat på under en anpassad tidsperiod med vald granularitet.

Med den genomsnittliga minuten-panelen för media kan du förstå hur mycket innehåll som används i genomsnitt genom att jämföra program av alla storlekar och genrer. Du kan till exempel förstå den genomsnittliga förbrukningen när du jämför en 30-minuters webbplats med en 3-timmars sportevenemang.

Dessutom kan du använda panelen för genomsnittlig minutpublik i mediemiljö för att jämföra eller lägga till den digitala genomsnittliga minuten-målgruppen med linjära minutvärden för tv-genomsnitt.

Målgruppspanelen för media i genomsnitt ger följande fördelar jämfört med måttet för genomsnittlig minutpublik:

* Stöder anpassade tidsperioder

* Tillåter att tidsklassificeringen uppdateras efter att vyer har bearbetats (om tidsklassificeringen inte fanns eller behöver korrigeras)

  Om du gör den här uppdateringen när du använder måttet finns inte tidsklassificeringen (om klassificeringen inte fanns). Eller så är tidsklassificeringen inaktuell (om klassificeringen fanns men var felaktig).

## Använd

Så här använder du en **[!UICONTROL Media average minute audience]**-panel:

1. Skapa en **[!UICONTROL Media average minute audience]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. Se till att du väljer en datavy för panelen som har komponenter konfigurerade från tillägget Direktuppspelad mediasamling.


1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.

### Panelindata

Använd de indatainställningar som beskrivs i det här avsnittet för att konfigurera målgruppspanelen för genomsnittlig minuts i media.

1. Konfigurera följande indatainställningar:

   | Inställning | Beskrivning |
   |---------|------------|
   | **Panelens datumintervall** | Panelens datumintervall är som standard [!UICONTROL **Den här månaden**]. Du kan redigera den för att visa en enstaka dag eller flera månader i taget. <br></br> Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
   | [!UICONTROL **Släpp ett segment här (eller någon annan komponent)**] | Precis som andra paneler filtrerar den här inställningen dina markeringar baserat på segment som du har skapat. Den här inställningen är ett bra sätt att se på specifika plattformar, liveströmmar eller andra vanliga mediesegment. |
   | [!UICONTROL **Beräkna mått för**] | Välj om du vill se den genomsnittliga minutmålgruppen för [**[!UICONTROL Specific content]**](#specific-content). Eller om du vill se den genomsnittliga minuten-publiken för en [**[!UICONTROL Custom time period]**](#custom-time-period).<br/><br/>Välj [!UICONTROL **Anpassad tidsperiod**]: <ul><li>Om längden inte är tillgänglig, eller </li><li>om du vill visa den genomsnittliga minutmålgruppen för en tidsserie med flera innehållsdelar, eller</li><li>för innehåll utan angiven varaktighet (som under en liveström eller händelse)</li></ul></li></li></ul> <p>Den här inställningen ändrar arbetsflödet och rapportutdata.</p> |

1. Fortsätt med [specifikt innehåll](#specific-content) eller [anpassad tidsperiod](#custom-time-period), beroende på vilket alternativ du väljer i listrutan [!UICONTROL **Beräkna mått för**].

#### Specifikt innehåll

1. Om du valde [!UICONTROL **specifikt innehåll**] i listrutan [!UICONTROL **Beräkna mått för**] när [panelindata](#panel-inputs) konfigureras anger du följande konfigurationsalternativ:

   | Inställning | Beskrivning |
   |---------|------------|
   | [!UICONTROL **Rapporteringsdimension**] | När du väljer specifikt innehåll kan du välja rapportutdata och använda antingen video-ID- eller innehålls-ID-fälten för att visa innehållet och dess associerade genomsnittliga minutmålgrupp. |
   | [!UICONTROL **Filtrera innehåll efter (valfritt)**] | Välj hur du vill filtrera det specifika innehållet, beroende på vilken vy du vill ha eller hur data är strukturerade. <ul>[!UICONTROL **Visa, säsong, avsnitt**]: Visar tillgängliga bildspel i listrutan, som du kan filtrera med hjälp av en sökning (eller genom att dra och släppa bildspelsnamnet från den vänstra kolumnen). Du kan avsluta markeringen där för att se alla årstiderna i programmet eller filtrera efter enskilda årstider och sedan efter enskilda avsnitt. Den här inställningen visar data för dessa program, säsonger eller avsnitt för den valda tidsperioden.</li><li>[!UICONTROL **Anpassad dimension**]: Om ditt visningsnamn finns under en anpassad dimension kan du hitta det antingen genom att söka i listrutan för dimension (valfritt) eller genom att använda den vänstra kolumnsökningen. Dimensionsobjektet fylls automatiskt baserat på det urvalet och behandlas som ett avsnitt.</li><li>[!UICONTROL **Inget**]: Visar alla videonamn som har genomsnittliga minutdata för det valda urvalet. (Det här alternativet är markerat som standard.)</li></ul> |

1. Fortsätt med [Avancerade inställningar för specifikt innehåll](#specific-content-advanced-settings) om du vill konfigurera avancerade inställningar.

#### Avancerade inställningar för specifikt innehåll

1. Välj [!UICONTROL **Specifikt innehåll**] i listrutan [!UICONTROL **Beräkna mått för**] och välj [!UICONTROL **Visa avancerade inställningar**]. Ange sedan följande konfigurationsalternativ:

   | Alternativ | Beskrivning |
   |---------|------------|
   | **[!UICONTROL Table settings]** | Standardalternativet **[!UICONTROL Show calculation values in table]** visar täljaren och nämnaren för den genomsnittliga minutmålgruppen som de föregående kolumnerna i tabellen. Om du avmarkerar det här alternativet tas de två kolumnerna bort. Den genomsnittliga minuten målgruppskolumnen finns kvar i tabellen bredvid videons namn eller innehålls-ID. |
   | **[!UICONTROL Time spent metric]** | Du kan välja standardalternativet **[!UICONTROL Content Time Spent]**, som endast inkluderar innehållstid. Du kan också välja att använda **[!UICONTROL Media Time Spent]**, som inkluderar innehåll och annonstid tillsammans som täljarberäkning för den genomsnittliga minuten-målgruppen. |

1. Välj [!UICONTROL **Build**] om du vill skapa målgruppspanelen för medieminister.

1. Fortsätt med [Panelutdata](#panel-output) om du vill ha information om hur du använder den genomsnittliga minutpanelen för mediefiler.

#### Anpassad tidsperiod

1. Om du valde [!UICONTROL **Anpassad tidsperiod**] i listrutan [!UICONTROL **Beräkna mått för**] när [panelindata](#panel-inputs) konfigureras anger du följande konfigurationsalternativ:

   | Alternativ | Beskrivning |
   |---------|------------|
   | **[!UICONTROL Granularity]** | Standardgranulariteten är [!UICONTROL **5 minuter**], men du kan välja vilken granularitet som helst som används som nämnare för tidsserien under den valda tidsperioden. Om du till exempel väljer 12:00 till 12:30 med 5 minuters granularitet returneras den genomsnittliga minuten-publiken över hela halvtimmen samt sex rader med den genomsnittliga minuten-publiken för varje femminutersperiod. Dessa rader används som datapunkter för tidsseriediagrammet. |
   | [!UICONTROL **Filtrera innehåll efter (valfritt)**] | Välj hur du vill filtrera det specifika innehållet, beroende på vilken vy du vill ha eller hur data är strukturerade. <ul>[!UICONTROL **Visa, säsong, avsnitt**]: Visar tillgängliga bildspel i listrutan, som du kan filtrera med hjälp av en sökning (eller genom att dra och släppa bildspelsnamnet från den vänstra kolumnen). Du kan avsluta markeringen där för att se alla årstiderna i programmet eller filtrera efter enskilda årstider och sedan efter enskilda avsnitt. Den här inställningen visar data för dessa program, säsonger eller avsnitt för den valda tidsperioden.</li><li>[!UICONTROL **Anpassad dimension**]: Om ditt visningsnamn finns under en anpassad dimension kan du hitta det antingen genom att söka i listrutan för dimension (valfritt) eller genom att använda den vänstra kolumnsökningen. Dimensionsobjektet fylls automatiskt baserat på det urvalet och behandlas som ett avsnitt.</li><li>[!UICONTROL **Inget**]: Visar alla videonamn som har genomsnittliga minutdata för det valda urvalet. (Det här alternativet är markerat som standard.)</li></ul> |

1. Fortsätt med [Avancerade inställningar för anpassad tidsperiod](#custom-time-period-advanced-settings) om du vill konfigurera avancerade inställningar.

#### Avancerade inställningar för anpassad tidsperiod

1. Välj [!UICONTROL **Anpassad tidsperiod**] i listrutan [!UICONTROL **Beräkna mått för**] och välj [!UICONTROL **Visa avancerade inställningar**]. Ange sedan följande konfigurationsalternativ:

   | Alternativ | Beskrivning |
   |---------|------------|
   | **[!UICONTROL Table settings]** | Standardinställningen visar beräkningsvärdena i tabellen, som visar täljaren och nämnaren för den genomsnittliga minutmålgruppen som de föregående kolumnerna i tabellen. Om du avmarkerar det här alternativet tas de två kolumnerna bort, så att bara den genomsnittliga minuten-målgruppen visas intill tidsperioden. |

1. Välj [!UICONTROL **Build**] om du vill skapa målgruppspanelen för medieminister.

1. Fortsätt med [Panelutdata](#panel-output) om du vill ha information om hur du använder den genomsnittliga minutpanelen för mediefiler.

### Panelutdata

Utdata från panelen varierar beroende på om du väljer [!UICONTROL **Specifikt innehåll**] eller [!UICONTROL **Anpassad tidsperiod**] i listrutan [!UICONTROL **Beräkna mått för**] när [panelindata ](#panel-inputs) konfigureras.

#### Specifikt innehåll

Den genomsnittliga minuten-panelen för media returnerar följande:

* Total genomsnittlig minutmålstid för hela urvalet
* Filter och genomsnittlig minimal publik för de enskilda videoklippen, som visas i en tabell
* Innehållstid och videolängd (längd) om den avancerade inställningen har valts

Om du vill redigera och återskapa panelen väljer du ![Redigera](/help/assets/icons/Edit.svg) i det övre högra hörnet.

![Standardvy](assets/specific-content-panel-output.png)

#### Datakälla för specifikt innehåll

I den genomsnittliga minuspennan i mediemiljön används endast den genomsnittliga minuspoängen för att samla in data. Det går inte att använda uppdelningar eller andra mätvärden i panelen.

| Mått | Beskrivning |
|--------|-------------|
| **[!UICONTROL Average minute audience]** | Den tid som har använts för att visa medieströmmen dividerat med videolängden (längden) som levereras via klassificeringar. |

#### Anpassad tidsperiod {#custom-time-period-output}

Den genomsnittliga minuten-panelen för media returnerar följande:

* Total genomsnittlig minutmålgrupp för hela urvalet

* Maximal och minimal genomsnittlig minutpublik

* Diagrammet för linjeserien visar den genomsnittliga minuten-publiken för hela markeringen.

* En tabell som visar filtren och den genomsnittliga minuten-publiken för detaljerna, samt hur lång tid och granularitet som använts för varje tidsperiod

  Den här tabellen visas bara om alternativet under de avancerade inställningarna [!UICONTROL **Visa beräkningsvärden i tabellen**] har valts.

Om du vill redigera och återskapa panelen när som helst väljer du ![Redigera den genomsnittliga minuten-målpanelen](/help/assets/icons/Edit.svg) i det övre högra hörnet.


#### Datakälla för anpassad tidsperiod

I den genomsnittliga minuspennan i mediemiljön används endast den genomsnittliga minuspoängen för att samla in data. Det går inte att använda uppdelningar eller andra mätvärden i panelen.

| Mått | Beskrivning |
|---|---|
| **[!UICONTROL Average Minute Audience]** | Den tid det tar att visa medieströmmen dividerat med det totala urvalet eller den valda granulariteten i minuter. |


>[!MORELIKETHIS]
>
> [Skapa en panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Panelen för samtidiga visningsprogram för media](media-concurrent-viewers.md)
> [Medieuppspelningstid för panelen ](media-playback-time-spent.md)
>