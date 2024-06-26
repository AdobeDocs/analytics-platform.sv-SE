---
title: Panelen Mediegenomsnitt för miniatyrmålgrupp
description: Så här använder och tolkar du panelen Media Average Minute Audience i Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: c55b5534-a9a6-47f1-8b43-c8c0b8686c53
source-git-commit: e4d4ff530d28e692301ca0671e055a164b9f7035
workflow-type: tm+mt
source-wordcount: '1664'
ht-degree: 0%

---

# Mediemedelets minutmålspanel

>[!NOTE]
>
>Den genomsnittliga minuten-panelen för media är endast tillgänglig för kunder som har köpt tillägget Streaming Media Collection för Customer Journey Analytics.
>
>Kontakta din säljare på Adobe eller Adobe Account Team för att köpa tillägget Streaming Media Collection.

I Analysis Workspace är den genomsnittliga minuten den tid som går åt till att visa medieströmmen dividerat med längden på innehållet eller det totala urvalet av period och vald granularitet.

Med den genomsnittliga minuten-målgruppspanelen för media kan du bättre förstå den genomsnittliga användningen av ditt innehåll genom att jämföra program av alla storlekar och genrer. Du kan till exempel förstå den genomsnittliga förbrukningen när du jämför en 30-minuters webbplats med en 3-timmars sportevenemang.

Dessutom kan du använda panelen för genomsnittlig minutpublik i mediemiljö för att jämföra eller lägga till den digitala genomsnittliga minuten-målgruppen med linjära minutvärden för tv-genomsnitt.

Målgruppspanelen för media i genomsnitt ger följande fördelar jämfört med måttet för genomsnittlig minutpublik:

* Stöder anpassade tidsperioder

* Tillåter att tidsklassificeringen uppdateras efter att vyer har bearbetats (om den inte fanns eller behöver korrigeras)

  Om du gjorde detta när du använde måttet finns det antingen inte (om klassificeringen inte fanns) eller så är den inaktuell (om klassificeringen fanns men var felaktig).

## Få åtkomst till den genomsnittliga publiken för media - minut

1. I Analysis Workspace går du till en rapportserie som har komponenter aktiverade från tillägget Direktuppspelning Media Collection.

1. I den vänstra navigeringen väljer du **Panel** -ikon.

   ![Panelikon i vänster navigering](assets/panels-icon.png)

1. Dra [!UICONTROL **Genomsnittlig minutmålgrupp för media**] på arbetsytan i Analysis Workspace.

1. Om du vill konfigurera panelen fortsätter du med [Panelindata](#panel-inputs).

## Panelindata {#Input}

Använd de indatainställningar som beskrivs i det här avsnittet för att konfigurera målgruppspanelen för genomsnittlig minuts i media.

1. Börja skapa en målgruppspanel för medieminimemin, enligt beskrivningen i [Få åtkomst till den genomsnittliga publiken för media - minut](#access-the-media-average-minute-audience-panel).

1. Konfigurera följande indatainställningar:

   | Inställning | Beskrivning |
   |---------|------------|
   | **Panelens datumintervall** | Panelens standarddatumintervall är [!UICONTROL **Den här månaden**]. Du kan redigera den för att visa en enstaka dag eller flera månader i taget. <br></br> Den här visualiseringen är begränsad till 1 440 datarader (till exempel 24 timmar vid granularitet på minutnivå). Om ett datumintervall och en granularitetskombination resulterar i mer än 1 440 rader uppdateras granulariteten automatiskt för att passa det fullständiga datumintervallet. |
   | [!UICONTROL **Släpp ett segment här (eller någon annan komponent)**] | Precis som andra paneler filtrerar den här inställningen dina markeringar baserat på segment som du har skapat. Detta är ett bra sätt att se på specifika plattformar, liveströmmar eller andra vanliga mediesegment. |
   | [!UICONTROL **Beräkna mått för**] | Välj om du vill se den genomsnittliga minuten-publiken för ett visst innehåll eller om du vill se den genomsnittliga minuten-publiken för en anpassad tidsperiod:<ul><li>**Särskilt innehåll:** Det här alternativet är bara tillgängligt om varaktigheten har uppdaterats med hjälp av klassificeringar. Om längden inte är tillgänglig, eller om du vill visa den genomsnittliga minuten-publiken för en tidsserie med flera innehållsdelar eller innehåll utan en viss tilldelad varaktighet (som under en liveström eller händelse), bör du välja [!UICONTROL **Anpassad tidsperiod**]. (Du kan ange varaktighet med hjälp av klassificeringar antingen före eller efter bearbetningstiden.)</li><li>**Anpassad tidsperiod:** Detta är tillgängligt oavsett om varaktigheten är tillgänglig med hjälp av klassificeringar.</li></ul> <p>Den här inställningen ändrar arbetsflödet och rapportutdata.</p> |

1. Fortsätt med [Specifikt innehåll](#specific-content) eller [Anpassad tidsperiod](#custom-time-period), beroende på vilket alternativ du väljer i dialogrutan [!UICONTROL **Beräkna mått för**] listruta.

### Specifikt innehåll

1. Om du valde [!UICONTROL **Specifikt innehåll**] i [!UICONTROL **Beräkna mått för**] nedrullningsbar meny när [konfigurera panelindata](#panel-inputs)anger du följande konfigurationsalternativ:

   | Inställning | Beskrivning |
   |---------|------------|
   | [!UICONTROL **Rapporteringsdimension**] | När du väljer specifikt innehåll kan du välja rapportutdata och använda antingen video- eller innehålls-ID-fälten för att visa innehållet och dess associerade genomsnittliga minutmålgrupp under den valda tidsperioden. |
   | [!UICONTROL **Filtrera innehåll efter (valfritt)**] | Välj hur du vill filtrera det specifika innehållet, beroende på vilken vy du vill ha eller hur data är strukturerade. <ul>[!UICONTROL **Visa, säsong, avsnitt**]: Visar tillgängliga bildspel i listrutan, som du kan filtrera med hjälp av en sökning (eller genom att dra och släppa visningsnamnet från den vänstra kolumnen). Du kan avsluta markeringen där för att se alla årstiderna i programmet eller filtrera efter enskilda årstider och sedan efter enskilda avsnitt. Den här inställningen visar data för dessa program, säsonger eller avsnitt för den valda tidsperioden.</li><li>[!UICONTROL **Anpassad dimension**]: Om ditt visningsnamn finns under en anpassad dimension kan du hitta det antingen genom att söka i den nedrullningsbara menyn för dimension (valfritt) eller genom att använda den vänstra kolumnsökningen. Dimensionsobjektet fylls automatiskt baserat på det urvalet och behandlas som ett avsnitt.</li><li>[!UICONTROL **Ingen**]: Visar alla videonamn som har genomsnittliga minutdata för det valda urvalet. (Det här alternativet är markerat som standard.)</li></ul> |

1. Fortsätt med [Avancerade inställningar för specifikt innehåll](#specific-content-advanced-settings) för att konfigurera avancerade inställningar.

### Avancerade inställningar för specifikt innehåll

1. Med [!UICONTROL **Specifikt innehåll**] markerat i [!UICONTROL **Beräkna mått för**] nedrullningsbar meny, välja [!UICONTROL **Visa avancerade inställningar**] anger du sedan följande konfigurationsalternativ:

   | Inställning | Beskrivning |
   |---------|------------|
   | Tabellinställningar | Standardinställningen visar beräkningsvärdena i tabellen, som visar täljaren och nämnaren för den genomsnittliga minutmålgruppen som de föregående kolumnerna i tabellen. Om du avmarkerar det här alternativet tas dessa två kolumner bort, så att endast den genomsnittliga minuten-publiken visas bredvid videonamnet eller innehålls-ID:t. |
   | Tidsåtgång för mått | Du kan välja hur lång tid som ska användas som standard, vilket endast inkluderar innehållstid, eller så kan du välja att använda den medietid som har använts, vilket inkluderar innehåll och annonstid tillsammans som täljarberäkning för den genomsnittliga minuten-målgruppen. |

1. Välj [!UICONTROL **Bygge**] för att slutföra skapandet av målgruppspanelen för media i genomsnitt.

1. Fortsätt med [Panelutdata](#panel-output) om du vill ha information om hur man använder den genomsnittliga minuten-målgruppspanelen för media.

### Anpassad tidsperiod

1. Om du valde [!UICONTROL **Anpassad tidsperiod**] i [!UICONTROL **Beräkna mått för**] nedrullningsbar meny när [konfigurera panelindata](#panel-inputs)anger du följande konfigurationsalternativ:

   | Inställning | Beskrivning |
   |---------|------------|
   | Kornighet | Standardgranulariteten är [!UICONTROL **5 minuter**], men du kan välja vilken kornighet som helst som ska användas som nämnare för tidsserien inom den övergripande tidsperioden som valts i kalendervalet. Om du till exempel väljer 12:00 till 12:30 med 5 minuters granularitet returneras den genomsnittliga minuten-publiken över hela halvtimmen samt sex rader med den genomsnittliga minuten-publiken för varje femminutersperiod. Dessa rader används som datapunkter för tidsseriediagrammet. |
   | [!UICONTROL **Filtrera innehåll efter (valfritt)**] | Välj hur du vill filtrera det specifika innehållet, beroende på vilken vy du vill ha eller hur data är strukturerade. <ul>[!UICONTROL **Visa, säsong, avsnitt**]: Visar tillgängliga bildspel i listrutan, som du kan filtrera med hjälp av en sökning (eller genom att dra och släppa visningsnamnet från den vänstra kolumnen). Du kan avsluta markeringen där för att se alla årstiderna i programmet eller filtrera efter enskilda årstider och sedan efter enskilda avsnitt. Den här inställningen visar data för dessa program, säsonger eller avsnitt för den valda tidsperioden.</li><li>[!UICONTROL **Anpassad dimension**]: Om ditt visningsnamn finns under en anpassad dimension kan du hitta det antingen genom att söka i den nedrullningsbara menyn för dimension (valfritt) eller genom att använda den vänstra kolumnsökningen. Dimensionsobjektet fylls automatiskt baserat på det urvalet och behandlas som ett avsnitt.</li><li>[!UICONTROL **Ingen**]: Visar alla videonamn som har genomsnittliga minutdata för det valda urvalet. (Det här alternativet är markerat som standard.)</li></ul> |

1. Fortsätt med [Avancerade inställningar för anpassad tidsperiod](#custom-time-period-advanced-settings) för att konfigurera avancerade inställningar.

### Avancerade inställningar för anpassad tidsperiod

1. Med [!UICONTROL **Anpassad tidsperiod**] markerat i [!UICONTROL **Beräkna mått för**] nedrullningsbar meny, välja [!UICONTROL **Visa avancerade inställningar**] anger du sedan följande konfigurationsalternativ:

   | Inställning | Beskrivning |
   |---------|------------|
   | Tabellinställningar | Standardinställningen visar beräkningsvärdena i tabellen, som visar täljaren och nämnaren för den genomsnittliga minutmålgruppen som de föregående kolumnerna i tabellen. Om du avmarkerar det här alternativet tas de två kolumnerna bort, så att bara den genomsnittliga minuten-målgruppen visas intill tidsperioden. |

1. Välj [!UICONTROL **Bygge**] för att slutföra skapandet av målgruppspanelen för media i genomsnitt.

1. Fortsätt med [Panelutdata](#panel-output) om du vill ha information om hur man använder den genomsnittliga minuten-målgruppspanelen för media.

## Panelutdata

Utdata på panelen varierar beroende på om du väljer [!UICONTROL **Specifikt innehåll**] eller [!UICONTROL **Anpassad tidsperiod**] i [!UICONTROL **Beräkna mått för**] nedrullningsbar meny när [konfigurera panelindata](#panel-inputs).

### Specifikt innehåll

Den genomsnittliga minuten-panelen för media returnerar följande:

* Total genomsnittlig minutmålstid för hela urvalet
* Filter och genomsnittlig minimal publik för de enskilda videoklipp som visas i en tabell
* Innehållstid och videolängd (längd) om den avancerade inställningen har valts

Om du vill redigera och återskapa panelen väljer du ikonen Redigera (penna) längst upp till höger.

![Standardvy](assets/specific-content-panel-output.png)

### Datakälla för specifikt innehåll

Målgruppspanelen för medieminarium använder endast måttet för genomsnittlig minutpublik för att samla in data. Det går inte att använda uppdelningar eller andra mätvärden i panelen.

| Mått | Beskrivning |
|--------|-------------|
| Genomsnittlig målgrupp i minuter | Den tid som har använts för att visa medieströmmen dividerat med videolängden (längden) som levereras via klassificeringar. |

### Anpassad tidsperiod {#custom-time-period-output}

Den genomsnittliga minuten-panelen för media returnerar följande:

* Total genomsnittlig minutmålgrupp för hela urvalet

* Maximal och minimal genomsnittlig minutpublik

* Diagrammet för linjeserien visar den genomsnittliga minuten-publiken för hela markeringen.

* En tabell som visar filtren och den genomsnittliga minuten-publiken för detaljerna, samt hur lång tid och granularitet som använts för varje tidsperiod

  Den här tabellen visas bara om alternativet under avancerade inställningar har anropats [!UICONTROL **Visa beräkningsvärden i registret**] är markerat.

Om du vill redigera och återskapa panelen väljer du ikonen Redigera (penna) längst upp till höger.

![samtidiga visningsprogram](assets/custom-time-period-panel-output.png)

### Datakälla för anpassad tidsperiod

Målgruppspanelen för medieminarium använder endast måttet för genomsnittlig minutpublik för att samla in data. Det går inte att använda uppdelningar eller andra mätvärden i panelen.

| Mått | Beskrivning |
|---|---|
| Genomsnittlig målgrupp i minuter | Den tid det tar att visa medieströmmen dividerat med det totala urvalet eller den valda granulariteten i minuter. |
