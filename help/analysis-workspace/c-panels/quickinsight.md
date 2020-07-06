---
description: Quick Insights är ett verktyg för nya Workspace-användare som vägleder dem i arbetet med att skapa datatabeller och visualiseringar
title: Panelen Snabbinsikter
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 2%

---


# Panelen Snabbinsikter

>[!NOTE]
>
>Dokumentationen för Analysis Workspace i Customer Journey Analytics finns nu. Dess funktioner skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

>[!IMPORTANT]
>
>**[!UICONTROL Quick Insights]** Panelen har för närvarande begränsad testning. [Läs mer](https://docs.adobe.com/content/help/sv-SE/analytics/landing/an-releases.html)

[!UICONTROL Quick Insights] ger vägledning till icke-analytiker och nya användare av [!UICONTROL Analysis Workspace] så att de kan lära sig att snabbt och enkelt svara på affärsfrågor. Det är också ett bra verktyg för avancerade användare som snabbt vill besvara en enkel fråga utan att själva behöva skapa en tabell.

När du börjar använda det här [!UICONTROL Analysis Workspace]kan du undra vilka visualiseringar som skulle vara mest användbara, vilka dimensioner och mätvärden som skulle kunna underlätta insikter, var objekt ska dras och släppas, var ett segment ska skapas osv.

För att underlätta detta, och baserat på det egna företagets användning av datakomponenter i [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] utnyttjar en algoritm som ger dig de populäraste dimensionerna, måtten, segmenten och datumintervallen som ditt företag använder. Det är faktiskt så att du ser mått, mått och segment som taggats som [!UICONTROL Popular] i listrutan, vilket visas här:

![](assets/popular-tag.png)

[!UICONTROL Quick Insights] hjälper dig

* Bygg en datatabell och en medföljande visualisering i [!UICONTROL Analysis Workspace].
* Lär dig terminologi och vokabulär för grundläggande komponenter och delar av [!UICONTROL Analysis Workspace].
* Gör enkla uppdelningar av dimensioner, lägg till flera mätvärden eller jämför segment enkelt i en [!UICONTROL Freeform table]bild.
* Ändra eller prova olika visualiseringstyper för att snabbt och intuitivt hitta sökverktyget för din analys.

## Grundläggande nyckelterminologi

Nedan följer några grundläggande termer som du måste känna till. Varje datatabell består av två eller flera byggstenar (komponenter) som du använder för att berätta din databerättelse.

| Byggblock (komponent) | Definition |
|---|---|
| [!UICONTROL Dimension] | Dimensioner är beskrivningar eller egenskaper för mätdata som kan visas, delas upp och jämföras i ett projekt. De är icke-numeriska värden och datum som delas upp i dimensionsobjekt. Till exempel är &quot;webbläsare&quot; eller &quot;sida&quot; dimensioner. |
| [!UICONTROL Dimension item] | Dimensionsobjekt är enskilda värden för en dimension. Dimensionsobjekten för webbläsardimensionen är till exempel Chrome, Firefox och Edge. |
| [!UICONTROL Metric] | Mätvärden är kvantitativ information om besökaraktivitet, t.ex. visningar, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare. |
| [!UICONTROL Visualization] | Workspace erbjuder [ett antal visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) för att skapa visuella representationer av dina data, till exempel stapeldiagram, dondiagram, histogram, linjediagram, kartor, punktdiagram med mera. |
| [!UICONTROL Dimension Breakdown] | En dimensionsuppdelning är ett sätt att bokstavligen dela upp en dimension med andra dimensioner. I det här exemplet kan du bryta ned USA efter mobila enheter för att få mobilenhetsbesök per delstat, eller så kan du bryta ned mobila enheter efter mobilenhetstyper, efter regioner, efter interna kampanjer osv. |
| [!UICONTROL Segment] | Med segment kan du identifiera undergrupper av besökare baserat på egenskaper eller webbplatsinteraktioner. Du kan till exempel skapa [!UICONTROL Visitor] segment baserat på attribut: webbläsartyp, enhet, antal besök, land, kön eller baserat på interaktioner: kampanjer, sökordssökningar, sökmotorer eller baserat på avslutningar och tävlingsbidrag: besökare från Facebook, en definierad landningssida, hänvisande domän eller baserad på anpassade variabler: formulärfält, definierade kategorier, kund-ID. |

## Kom igång med Quick Insights

1. Logga in på Adobe Analytics med de inloggningsuppgifter du har fått.
1. Gå till [!UICONTROL Workspace] och klicka **[!UICONTROL Create New Project]** och klicka sedan **[!UICONTROL Quick Insights]**. (Du kan även öppna den här panelen från menyn i den vänstra listen **[!UICONTROL Panel]** .)

   ![](assets/qibuilder.png)

   ![](assets/qi-panel.png)

1. När du börjar ska du gå igenom den korta självstudiekursen som lär ut några av grunderna [!UICONTROL Quick Insights panel] . Du kan också klicka för att **[!UICONTROL Skip Tutorial]**.
1. Markera dina byggstenar (kallas även komponenter): dimensioner (orange), mått (grönt), segment (blått) eller datumintervall (lila) Du måste välja minst en dimension och ett mått för att en tabell ska skapas automatiskt.

   ![](assets/qibuilder2.png)

   Du kan välja byggblock på tre olika sätt:
   * Dra och släpp dem från den vänstra listen.
   * Om du vet vad du söker: Börja skriva och [!UICONTROL Quick Insights] fyller i tomrummen åt dig.
   * Klicka på listrutan och sök i listan.

1. När du har lagt till minst en dimension och ett mått skapas följande för dig:

   * En Freeform-tabell med dimensionen (här, USA) lodrätt och måttet (här, Besök) vågrätt högst upp. Kolla in den här tabellen:
   ![](assets/qibuilder3.png)

   * En åtföljande visualisering, i det här fallet ett [stapeldiagram](/help/analysis-workspace/visualizations/bar.md). Den visualisering som genereras baseras på den typ av data som du har lagt till i tabellen. Alla tidsbaserade data (till exempel [!UICONTROL Visits] per dag/månad) blir som standard ett [!UICONTROL Line] diagram. Alla icke-tidsbaserade data (till exempel [!UICONTROL Visits] per [!UICONTROL Device]) blir som standard ett [!UICONTROL Bar] diagram. Du kan ändra visualiseringstypen genom att klicka på listrutepilen bredvid visualiseringstypen.


1. (Valfritt) Detaljera mått och visa dimensionsobjekt genom att klicka på > högerpilen bredvid dimensionen.

1. Försök att lägga till fler förbättringar enligt beskrivningen nedan under Fler tips.

1. Spara projektet genom att klicka **[!UICONTROL Project > Save]**.

## Fler tips

Andra användbara tips visas i [!UICONTROL Quick Insights Builder], vissa beroende på den senaste åtgärden.

* Börja med att slutföra **[!UICONTROL More tips]** självstudiekursen: Öppna den via hjälpen (?) -ikonen bredvid [!UICONTROL Quick Insights] titeln. Den här självstudiekursen visar upp till 24 timmar efter att du har skapat ett projekt med minst en dimension och ett mått.

   ![](assets/qibuilder4.png)

* **Uppdelning efter**: Du kan använda upp till tre nivåer av uppdelningar på dimensioner för att gå ned till de data du verkligen behöver.

   ![](assets/qibuilder5.png)

* **Lägg till fler mätvärden**: Du kan lägga till upp till två mätvärden till genom att använda operatorn AND för att lägga till dem i tabellen.

   ![](assets/qibuilder6.png)

* **Lägg till fler segment**: Du kan lägga till upp till två segment till genom att använda operatorerna AND eller OR för att lägga till dem i tabellen. Se vad som händer med tabellen när du lägger till mobilanvändare eller lojala besökare. De står bredvid varandra, ovanför mätvärdena. Om du lade till mobila användare och lojala besökare skulle du se resultat från båda segmenten tillsammans, och de skulle staplas ovanpå varandra i tabellen.

   ![](assets/qibuilder7.png)

## Kända begränsningar

Om du försöker redigera direkt i tabellen kommer panelen att bli osynkroniserad [!UICONTROL Quick Insights] . Du kan återställa den till tidigare [!UICONTROL Quick Insights] inställningar genom att klicka **[!UICONTROL Resync Builder]** längst upp till höger på panelen.

![](assets/qibuilder9.png)

Du får en varning innan du lägger till något direkt i tabellen:

![](assets/qibuilder8.png)

Om du skapar direkt kommer tabellen nu att fungera som en traditionell Freeform-tabell, utan de praktiska funktionerna för nya användare.

