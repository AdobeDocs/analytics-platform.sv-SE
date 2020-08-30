---
description: Skapa en kohort och kör en kohortanalysrapport på Analysis Workspace.
keywords: Analysis Workspace
title: Kör en kohortanalysrapport
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 7862233892e56d1faafed6c14bd527db89ff1a3b
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 0%

---


# Konfigurera ett [!UICONTROL Cohort Analysis] rapportera

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Skapa en kohort och kör en [!UICONTROL Cohort Analysis] rapport i Analysis Workspace.

1. I Analysis Workspace klickar du på **[!UICONTROL Visualizations]** ikonen på vänster räl och dra en **[!UICONTROL Cohort Table]** till arbetsytan.

   ![](assets/cohort-table.png)

1. Definiera **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]** och **[!UICONTROL Settings]** enligt definitionen i tabellen nedan.

| Element | Beskrivning |
| --- | --- |
| **[!UICONTROL Inclusion Criteria]** | Du kan använda upp till 10 inkluderingssegment och upp till 3 integreringsmått. Måttet anger vad en användare placeras i en kohort. Om t.ex. inkluderingsmetersystemet är beställningar, kommer endast användare som beställt en beställning under kohortanalysens tidsintervall att inkluderas i den inledande kohorten. <br> Standardoperatorn mellan måtten är OCH, men du kan ändra den till ELLER. Dessutom kan du lägga till numerisk filtrering till dessa mått. Exempel: &quot;Besök >= 1&quot;. |
| **[!UICONTROL Return Criteria]** | Du kan använda upp till 10 retursegment och upp till 3 returmått. Måttet anger om användaren har behållits (retention) eller inte (churn). Om t.ex. returmåttet är Videovyer, visas endast användare som visade videor under efterföljande tidsperioder (efter den period då de lades till i en kohort) som bevarade. Ett annat mått som kvantifierar kvarhållning är Visits. |
| **[!UICONTROL Granularity]** | Tidsgranularitet för dag, vecka, månad, kvartal eller år. |
| **[!UICONTROL Type]** | **[!UICONTROL Retention]** (standard): En kvarhållandekohort mäter hur väl besökskohorterna återgår till din egendom över tiden. Detta är den standardkohort som vi alltid har haft och som indikerar returnerat och upprepat användarbeteende. A [!UICONTROL Retention] Kohort anges med färgen grön i tabellen. <br> **[!UICONTROL Churn]**: En kyrkohort (även kallad &quot;attributering&quot; eller &quot;utfall&quot;) mäter hur dina besökskohorter faller ur din egendom över tiden. Churn = 1 - Kvarhållning. [!UICONTROL Churn] är ett bra mått på snabbhet och möjligheter genom att visa dig hur ofta kunderna inte kommer tillbaka. Du kan använda kurn för att analysera och identifiera fokusområden: vilka kohortsegment som skulle kunna behöva lite uppmärksamhet. A [!UICONTROL Churn] Kohort indikeras av färgen röd i tabellen (ungefär som utfall i vår **[!UICONTROL Flow]** visualisering). |
| **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]**: Beräkna kvarhållning eller kurva baserat på föregående kolumn i stället för kolumnen Inkluderad (standard). [!UICONTROL Rolling Calculation] ändrar beräkningsmetoden för dina returperioder. Vid den normala beräkningen hittar man oberoende användare som uppfyller returkriterierna och som ingick i inkluderingsperioden, oavsett om de ingick i kohorten för den föregående perioden eller inte. I stället [!UICONTROL Rolling Calculation] hittar användare som uppfyller returkriterierna och som ingick i föregående period. Därför [!UICONTROL Rolling Calculation] filtrerar och trattar de användare som kontinuerligt uppfyller kriterierna för &quot;returnering&quot; över perioden. [!UICONTROL Return] kriterier tillämpas på var och en av de perioder som föregår den valda perioden. <br> **[!UICONTROL Latency Table]**: A [!UICONTROL Latency] Tabellen mäter den tid som förflutit före och efter det att inkluderingshändelsen inträffade. [!UICONTROL Latency] är bra att använda för förhands-/efterhandsanalys. Om du t.ex. har en kommande produkt- eller kampanjstart och vill spåra beteendet före och se hur det fungerar efter, kan du [!UICONTROL Latency] Tabellen visar för- och efterbeteendet sida vid sida för att se den direkta effekten. Cellerna före inkludering i [!UICONTROL Latency] Tabellen beräknas av användare som uppfyller [!UICONTROL Inclusion] kriterierna för införandeperioden och därefter uppfylla [!UICONTROL Return] kriterier under perioderna före inklusionsperioden. Observera att [!UICONTROL Latency] tabeller och [!UICONTROL Custom Dimension] Kohort kan inte användas tillsammans. <br> **[!UICONTROL Custom Dimension Cohort]**: Skapa kohorter baserat på den valda dimensionen i stället för tidsbaserade kohorter (standard). Många kunder vill analysera sina kohorter med något annat än tid, och den nya funktionen för anpassad Dimension-kohort ger dig möjlighet att bygga kohorter baserat på de mått de väljer. Använd dimensioner som marknadsföringskanal, kampanj, produkt, sida, region eller någon annan dimension i Adobe Analytics för att visa hur kvarhållandet ändras baserat på de olika värdena för dessa dimensioner. De [!UICONTROL Custom Dimension] Definitionen av kohort-segment använder dimensionsobjektet endast som en del av inklusionsperioden, inte som en del av returdefinitionen. <br> När du har valt [!UICONTROL Custom Dimension] Alternativet Kohort, du kan dra och släppa vilken dimension du vill i släppzonen. På så sätt kan du jämföra liknande dimensionsobjekt över samma tidsperiod. Du kan t.ex. jämföra prestanda för städer sida vid sida, produkter, kampanjer osv. Det returnerar dina 14 främsta dimensionsobjekt. Du kan dock använda ett filter (komma åt det genom att hovra till höger om dimensionen som drogs på) för att visa endast önskade dimensionsobjekt. A [!UICONTROL Custom Dimension] Kohort kan inte användas med [!UICONTROL Latency] Tabellfunktion. |

1. Justera **[!UICONTROL Cohort Table Settings]** genom att klicka på redskapsikonen.

| Fastställande | Beskrivning | | Visa endast procent | Tar bort nummervärdet och visar bara procentvärdet. | | Rund procent till närmaste heltal | Avrundar procentvärdet till närmaste heltal i stället för att visa decimalvärdet. | | Visa genomsnittlig procentrad | Infogar en ny rad överst i tabellen och lägger sedan till medelvärdet för värdena i varje kolumn. |

## Bygg [!UICONTROL Cohort Analysis] rapportera

1. Klicka på **[!UICONTROL Build]**.

   ![Stegresultat](assets/cohort-report.png)

   I rapporten visas besökare som beställt en beställning ( *`Included`* och som återvände till din webbplats vid efterföljande besök. Genom att antalet besök minskar med tiden kan du upptäcka problem och vidta åtgärder.
1. (Valfritt) Skapa ett segment från en markering.

   Markera celler (angränsande eller icke sammanhängande) och högerklicka sedan > **[!UICONTROL Create Segment From Selection]**.

1. I [Filter Builder](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html)redigerar du segmentet ytterligare och klickar sedan på **[!UICONTROL Save]**.

   Det sparade segmentet är tillgängligt för användning i [!UICONTROL Segment] panel i [!UICONTROL Analysis Workspace].
1. Namnge och spara ditt kohortprojekt.
1. (Valfritt) [Kurva och dela](/help/analysis-workspace/curate-share/curate.md) Projektkomponenterna.

   >[!NOTE]
   >
   >Du måste spara projektet innan du kan boka.

