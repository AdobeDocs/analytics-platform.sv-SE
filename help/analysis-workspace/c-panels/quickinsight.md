---
description: Quick Insights är ett verktyg för nya Workspace-användare som vägleder dem när de bygger datatabeller och visualiseringar
title: Panelen Snabbinsikter
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 1%

---

# Panelen Snabbinsikter {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_quickinsights_button"
>title="Snabba insikter"
>abstract="Skapa en panel för att snabbt skapa en frihandsritabell och medföljande visualisering för att analysera och hitta insikter snabbare."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_I den här artikeln beskrivs panelen Snabbinsikter i_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**_.<br/>_Se [Panelen Snabbinsikter](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/quickinsight) för_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**-versionen av den här artikeln._

>[!ENDSHADEBOX]


[!UICONTROL Quick Insights] ger vägledning till icke-analytiker och nya användare av [!UICONTROL Analysis Workspace] så att de kan lära sig att snabbt och enkelt svara på affärsfrågor. Det är också ett bra verktyg för avancerade användare som snabbt vill besvara en enkel fråga utan att själva behöva skapa en tabell.

När du börjar använda [!UICONTROL Analysis Workspace] kanske du undrar:

* vilka visualiseringar som skulle vara mest användbara,
* vilka dimensioner och mätvärden som kan underlätta insikter,
* var du kan dra och släppa objekt,
* var ett segment ska skapas,
* med mera.

För att hjälpa till med dessa frågor använder [!UICONTROL Quick insights] en algoritm som ger dig de populäraste dimensionerna, måtten, segmenten och datumintervallen som ditt företag använder. Den här algoritmen baseras på ditt företags användning av datakomponenter i [!UICONTROL Analysis Workspace]. Dimensioner, mätvärden och segment som taggats med [!UICONTROL POPULAR] visas i listrutan, vilket visas här:

![Panelen Snabbinsikter.](assets/popular-tag.png)

[!UICONTROL Quick Insights] hjälper dig

* Bygg en datatabell och en medföljande visualisering på rätt sätt i [!UICONTROL Analysis Workspace].
* Lär dig terminologi och vokabulär för grundläggande komponenter och delar av [!UICONTROL Analysis Workspace].
* Gör enkla uppdelningar av dimensioner, lägg till flera mätvärden eller jämför segment enkelt i en [!UICONTROL Freeform table].
* Ändra eller prova olika visualiseringstyper för att snabbt och intuitivt hitta sökverktyget för din analys.

## Grundläggande nyckelterminologi

Nedan följer några grundläggande termer som du måste känna till. Varje datatabell består av två eller flera byggstenar (komponenter) som du använder för att berätta din databerättelse.

| Byggblock (komponent) | Definition |
|---|---|
| **[!UICONTROL Dimension]** | Dimensioner är beskrivningar eller egenskaper för mätdata som kan visas, delas upp och jämföras i ett projekt. De är icke-numeriska värden och datum som delas upp i dimensionsobjekt. *webbläsare* eller *sida* är till exempel en dimension. |
| **[!UICONTROL Dimension item]** | Dimension-artiklar är enskilda värden för en dimension. Dimensionsobjekten för webbläsardimensionen är till exempel *Chrome*, *Firefox*, *Edge* eller andra. |
| [!UICONTROL Metric] | Mätvärden är kvantitativ information om personaktivitet, t.ex. vyer, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare. |
| **[!UICONTROL Visualization]** | Workspace erbjuder [ett antal visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) för att skapa visuella representationer av dina data. t.ex. stapeldiagram, mundiagram, histogram, linjediagram, kartor, punktdiagram med mera. |
| **[!UICONTROL Dimension Breakdown]** | En dimensionsuppdelning är ett sätt att dela upp en dimension efter andra dimensioner. Du kan till exempel bryta ned USA:s mobilenheter för att få mobilenhetsbesök per delstat. Eller så kan ni bryta ned mobila enheter efter mobilenhetstyper, efter regioner, efter interna kampanjer med mera. |
| **[!UICONTROL Segment]** | Med segment kan du identifiera delmängder av personer baserat på egenskaper eller webbplatsinteraktioner. Du kan till exempel skapa [!UICONTROL People] segment baserat på <li>attribut: webbläsartyp, enhet, antal besök, land, kön eller</li><li>interaktioner: kampanjer, nyckelordssökning, sökmotor eller</li><li>utträde och tävlingsbidrag: personer från Facebook, en definierad landningssida, hänvisande domän, eller</li><li> anpassade variabler: formulärfält, definierade kategorier, kund-ID. |

## Använd

Så här använder du en **[!UICONTROL Quick insights]**-panel:

1. Skapa en **[!UICONTROL Quick insights]**-panel. Mer information om hur du skapar en panel finns i [Skapa en panel](panels.md#create-a-panel).

1. När du först använder en **[!UICONTROL Quick insights]**-panel kanske du vill gå igenom den korta [!UICONTROL Intro tutorial] som lär dig grunderna. Välj ![HelpOutline](/help/assets/icons/HelpOutline.svg) bredvid paneltiteln Snabbinsikter och välj **[!UICONTROL Intro tutorial]** i popup-fönstret.

1. Ange [indata](#panel-input) för panelen.

1. Observera [utdata](#panel-output) för panelen.


### Panelindata

Välj byggstenar:

* **[!UICONTROL Analyze]** - ange en dimension (orange)
* **[!UICONTROL by]** - ange ett mått (grönt)
* **[!UICONTROL segment by]** - ange ett segment (blått)
* **[!UICONTROL on]** - ange ett datumintervall (lila).

Du måste välja minst en dimension och ett mått för att visualiseringen ska fungera korrekt.



Du kan ange byggblocken på tre sätt:

* Dra och släpp komponenter från den vänstra panelen.
* Börja skriva i ett av byggblocksfälten. När indata påträffas fylls byggblocksfältet automatiskt i med möjliga värden.
* Ange en listruta för byggblock (till exempel `Country` i **[!UICONTROL Analyze]**) och sök i listan med möjliga värden (med ![Sparrhöger](/help/assets/icons/ChevronRight.svg)) efter det värde du vill använda (till exempel **[!UICONTROL Country code]**).

Välj **[!UICONTROL Clear]** om du vill rensa alla inmatningsfält.


### Panelutdata

1. När du har lagt till minst en dimension och ett mätvärde kan du se resultatet.

   ![Registret Frihand visar dimensionen lodrätt och måttet vågrätt.](assets/quick-insights-output.png)

   * En friformstabell med måtten (landskod) och mått (sessioner), segmenterade efter webbsessioner de senaste 12 månaderna.

   * En åtföljande visualisering, i det här fallet ett [stapeldiagram](/help/analysis-workspace/visualizations/bar.md). Den visualisering som genereras baseras på den typ av data som du har lagt till i tabellen. Alla tidsbaserade data (till exempel [!UICONTROL Sessions] per dag/månad) blir som standard ett [!UICONTROL Line]-diagram. Alla icke-tidsbaserade data (till exempel [!UICONTROL Sessions] per [!UICONTROL Device]) blir som standard ett [!UICONTROL Bar]-diagram. Du kan ändra visualiseringstypen genom att klicka på listrutepilen bredvid visualiseringstypen.

1. Försök lägga till fler förbättringar enligt beskrivningen nedan under [Fler tips](#more-tips)

1. Du kanske vill spara projektet med **[!UICONTROL Project > Save]**.

## Fler tips

Andra användbara tips visas i [!UICONTROL Quick Insights Builder]. Vissa av dem beror på den senaste åtgärden.

* Först kanske du vill slutföra självstudiekursen **[!UICONTROL More tips]**. Den här självstudiekursen visar upp till 24 timmar efter att du har skapat ett projekt med minst en dimension och ett mått. Välj ![HelpOutline](/help/assets/icons/HelpOutline.svg) bredvid paneltiteln Snabbinsikter och välj **[!UICONTROL More tips]** i popup-fönstret.

  ![Meddelande från panelen Snabbinformation visas när du har valt hjälpikonen.](assets/qibuilder4.png)

* Du kan analysera flera dimensioner och mätvärden, kombinera eller jämföra segment och ange ett datumintervall:

  ![Resultat av verktyget för snabb Insights-byggaren](assets/qibuilder-result.png)

   * **[!UICONTROL Analyze]** dimension **[!UICONTROL Broken-Down by]**: Du kan använda upp till tre nivåer av uppdelningar på dimensioner för att gå ned till de data du verkligen behöver. Se ➊, ➋ och ➌.

   * Lägg till fler mätvärden **[!UICONTROL by]**: Du kan lägga till upp till två mätvärden till. Se och..

   * **[!UICONTROL segment by]**: Du kan lägga till upp till två segment till. Du kan till exempel lägga till Bokningar som ett segment och kombinera det segmentet med segmenten Vanliga bokningar och Första gången som du jämför. Se ➏, ➐ och ➑.

   * on: Du kan ange datumintervall. Se ➒.

## Kända begränsningar

Om du försöker redigera direkt i tabellen kan panelen [!UICONTROL Quick Insights] bli osynkroniserad. Välj **[!UICONTROL Resync Builder]** längst upp till höger på panelen om du vill återställa den till de tidigare [!UICONTROL Quick Insights] inställningarna.

Du får en varning innan du lägger till något direkt i tabellen:

![Alternativvarning för omsynkroniseringsverktyget.](assets/qibuilder-outofsync.png)

Om du skapar tabellen direkt fungerar den som en traditionell Freeform-tabell, utan de praktiska funktionerna för nya användare.


>[!MORELIKETHIS]
>
>[Skapa en panel](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>