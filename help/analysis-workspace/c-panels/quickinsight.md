---
description: Quick Insights är ett verktyg för nya Workspace-användare som vägleder dem när de bygger datatabeller och visualiseringar
title: Panelen Snabbinsikter
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
source-git-commit: 16f1a732260ace8393d7303134fc351740fd1661
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 1%

---

# Panelen Snabbinsikter

[!UICONTROL Quick Insights] ger vägledning till icke-analytiker och nya användare av [!UICONTROL Analysis Workspace] så att de kan lära sig att snabbt och enkelt svara på affärsfrågor. Det är också ett bra verktyg för avancerade användare som snabbt vill besvara en enkel fråga utan att själva behöva skapa en tabell.

När du börjar använda den här [!UICONTROL Analysis Workspace]kan du undra vilka visualiseringar som skulle vara mest användbara, vilka dimensioner och mätvärden som skulle kunna underlätta insikter, var objekt ska dras och släppas, var ett filter ska skapas osv.

För att hjälpa till med detta och baserat på ditt företags användning av datakomponenter i [!UICONTROL Analysis Workspace], [!UICONTROL Quick Insights] använder en algoritm som ger dig de vanligaste måtten, måtten, filtren och datumintervallen som ditt företag använder. Faktum är att du kommer att se mått, mätvärden och filter taggade som [!UICONTROL Popular] i listrutan enligt följande:

![Panelen Quick Insights.](assets/popular-tag.png)

[!UICONTROL Quick Insights] hjälper dig

* Skapa en datatabell och en visualisering i [!UICONTROL Analysis Workspace].
* Lär dig terminologi och vokabulär för grundläggande komponenter och delar av [!UICONTROL Analysis Workspace].
* Gör enkla uppdelningar av dimensioner, lägg till flera mätvärden eller jämför enkelt filter i en [!UICONTROL Freeform table].
* Ändra eller prova olika visualiseringstyper för att snabbt och intuitivt hitta sökverktyget för din analys.

## Grundläggande nyckelterminologi

Nedan följer några grundläggande termer som du måste känna till. Varje datatabell består av två eller flera byggstenar (komponenter) som du använder för att berätta din databerättelse.

| Byggblock (komponent) | Definition |
|---|---|
| [!UICONTROL Dimension] | Dimensioner är beskrivningar eller egenskaper för mätdata som kan visas, delas upp och jämföras i ett projekt. De är icke-numeriska värden och datum som delas upp i dimensionsobjekt. Till exempel är &quot;webbläsare&quot; eller &quot;sida&quot; dimensioner. |
| [!UICONTROL Dimension item] | Dimensioner är enskilda värden för en dimension. Dimensionsobjekten för webbläsardimensionen är till exempel Chrome, Firefox och Edge. |
| [!UICONTROL Metric] | Mätvärden är kvantitativ information om personaktivitet, t.ex. vyer, klickningar, omladdningar, genomsnittlig tid, enheter, order, intäkter och så vidare. |
| [!UICONTROL Visualization] | Erbjudanden på arbetsytor [ett antal visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) för att skapa visuella representationer av data, som stapeldiagram, dondiagram, histogram, linjediagram, kartor, spridningspartier med mera. |
| [!UICONTROL Dimension Breakdown] | En dimensionsuppdelning är ett sätt att bokstavligen dela upp en dimension med andra dimensioner. I det här exemplet kan du bryta ned USA efter mobila enheter för att få mobilenhetsbesök per delstat, eller så kan du bryta ned mobila enheter efter mobilenhetstyper, efter regioner, efter interna kampanjer osv. |
| [!UICONTROL filter] | Med filter kan du identifiera delmängder av personer baserat på egenskaper eller webbplatsinteraktioner. Du kan till exempel skapa [!UICONTROL Visitor] filter baserade på attribut: webbläsartyp, enhet, antal besök, land, kön eller baserat på interaktioner: kampanjer, nyckelordssökning, sökmotor eller baserad på utgångar och poster: personer från Facebook, en definierad landningssida, referensdomän eller baserad på anpassade variabler: formulärfält, definierade kategorier, kund-ID. |

## Kom igång med Quick Insights

1. Logga in på Customer Journey Analytics med de inloggningsuppgifter som du har fått.
1. Gå till [!UICONTROL Workspace] och klicka **[!UICONTROL Create New Project]** och sedan klicka **[!UICONTROL Quick Insights]**. (Du kan även komma åt den här panelen via **[!UICONTROL Panel]** menyn i den vänstra listen.)

   ![I vyn Alla mallar markeras alternativet Snabbinsikter.](assets/qibuilder.png)

   ![Panelerna visar alternativet Snabb insikt.](assets/qi-panel.png)

1. Gå igenom den korta självstudiekursen som lär ut några av de [!UICONTROL Quick Insights panel] grunderna. Eller klicka för att **[!UICONTROL Skip Tutorial]**.
1. Välj dina byggstenar (kallas även komponenter): dimensioner (orange), mått (grönt), filter (blått) eller datumintervall (lila). Du måste välja minst en dimension och ett mått för att en tabell ska kunna skapas automatiskt.

   ![Komponenterna innefattar mått, mått, filter, segment och datumintervall.](assets/qibuilder2.png)

   Du kan välja byggblock på tre olika sätt:
   * Dra och släpp dem från den vänstra listen.
   * Om du vet vad du söker: börja skriva och [!UICONTROL Quick Insights] kommer att fylla i tomten åt dig.
   * Klicka på listrutan och sök i listan.

1. När du har lagt till minst en dimension och ett mått skapas följande för dig:

   * En Freeform-tabell med dimensionen (här, USA) lodrätt och måttet (här, Besök) vågrätt högst upp. Kolla in den här tabellen:

   ![Tabellen Frihand visar måttet lodrätt och måttet vågrätt.](assets/qibuilder3.png)

   * En åtföljande visualisering, i det här fallet en [stapeldiagram](/help/analysis-workspace/visualizations/bar.md). Den visualisering som genereras baseras på den typ av data som du har lagt till i tabellen. Alla tidsbaserade data (som [!UICONTROL Visits] per dag/månad) blir som standard [!UICONTROL Line] diagram. Alla icke-tidsbaserade data (som [!UICONTROL Visits] per [!UICONTROL Device]) används som standard [!UICONTROL Bar] diagram. Du kan ändra visualiseringstypen genom att klicka på listrutepilen bredvid visualiseringstypen.

1. (Valfritt) Detaljera mått och visa dimensionsobjekt genom att klicka på > högerpilen bredvid dimensionen.

1. Försök att lägga till fler förbättringar enligt beskrivningen nedan under Fler tips.

1. Spara projektet genom att klicka på **[!UICONTROL Project > Save]**.

## Fler tips

Andra användbara tips visas i [!UICONTROL Quick Insights Builder], vissa av dem beror på din senaste åtgärd.

* Fyll först i **[!UICONTROL More tips]** självstudiekurs: Öppna den via hjälpen (?) -ikonen bredvid [!UICONTROL Quick Insights] titel. Den här självstudiekursen visar upp till 24 timmar efter att du har skapat ett projekt med minst en dimension och ett mått.

  ![Meddelande från panelen Snabbinformation visas när du klickar på hjälpikonen.](assets/qibuilder4.png)

* **Uppdelning efter**: Du kan använda upp till tre nivåer av uppdelningar på dimensioner för att gå ned till de data du verkligen behöver.

  ![Delnivåer av uppdelningar.](assets/qibuilder5.png)

* **Lägg till fler mätvärden**: Du kan lägga till upp till två mätvärden till genom att använda operatorn AND för att lägga till dem i tabellen.

  ![Flera mätvärden, inklusive besök och enheter.](assets/qibuilder6.png)

* **Lägg till fler filter**: Du kan lägga till ytterligare upp till två filter genom att använda operatorerna AND eller OR för att lägga till dem i tabellen. Se vad som händer med tabellen när du lägger till mobilanvändare eller lojala besökare. De står bredvid varandra, ovanför mätvärdena. Om du lade till mobila användare OCH lojala besökare skulle du se resultat från båda filtren tillsammans, och de skulle staplas ovanpå varandra i tabellen.

  ![Bild som visar tillagda mobilanvändare och lojala besökare.](assets/qibuilder7.png)

## Kända begränsningar

Om du försöker redigera direkt i tabellen orsakar det [!UICONTROL Quick Insights] för att bli osynkroniserad. Du kan återställa den till föregående [!UICONTROL Quick Insights] inställningar genom att klicka på **[!UICONTROL Resync Builder]** längst upp till höger på panelen.

![Panelen Quick Insights med alternativet Resync Builder.](assets/qibuilder9.png)

Du får en varning innan du lägger till något direkt i tabellen:

![Alternativvarning för Synkronisera om Builder.](assets/qibuilder8.png)

Om du skapar direkt kommer tabellen nu att fungera som en traditionell Freeform-tabell, utan de praktiska funktionerna för nya användare.
