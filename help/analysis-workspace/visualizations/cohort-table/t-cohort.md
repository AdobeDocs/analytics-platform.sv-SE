---
description: Skapa en kohorttabell och kör en kohortanalys i Analysis Workspace.
keywords: Analysis Workspace
title: Konfigurera en kohorttabell
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
source-git-commit: 38be838fccf896a12da3fbadac50e578081312ba
workflow-type: tm+mt
source-wordcount: '861'
ht-degree: 0%

---

# Konfigurera en kohorttabell

Så här skapar och konfigurerar du en [!UICONTROL Cohort table]:

1. Lägg till en ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Cohort table]**-visualisering. Se [Lägga till en visualisering på en panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Definiera **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]** och **[!UICONTROL Settings]** enligt definitionen i tabellen nedan.

   ![Konfigurera en kohorttabell](assets/cohort-configure.png)

   | Element | Beskrivning |
   |--- |--- |
   | **[!UICONTROL Inclusion criteria]** | Du kan använda upp till 10 inkluderingssegment och upp till 3 inkluderingsvärden. Måttet anger vilken kohort en användare tillhör. Om inkluderingsmåttet till exempel är Order, inkluderas endast användare som lade en order under kohortanalysens tidsintervall i den initiala kohorten.<br>Standardoperatorn mellan mätvärden är AND, men du kan ändra den till OR. Dessutom kan du lägga till numerisk segmentering i dessa mått. Till exempel: `Sessions >= 1`.</br> |
   | **[!UICONTROL Return criteria]** | Du kan använda upp till 10 retursegment och upp till 3 returvärden. Måttet anger om användaren har behållits (kvarhållning) eller inte (bortfall). Om returvärdet till exempel är Videovyer visas bara de användare som visade videor under efterföljande tidsperioder (efter den period då de lades till i en kohort) som sparade. Ett annat mått som kvantifierar kvarhållandet är sessioner. |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B edition"}<br/>**[!UICONTROL Container]** | Som standard är kohortanalysen knuten till personbehållaren. Om det finns fler behållare än den person som är tillgänglig via den kontobaserade anslutningen som stöder Workspace-projektet kan du välja en annan behållare för kohortanalysen i listrutan **[!UICONTROL Container]**. |
   | **[!UICONTROL Granularity]** | Tidsgranulariteten för dag, vecka, månad, kvartal eller år. |
   | **[!UICONTROL Type]** | **[!UICONTROL Retention]** (standard): En **[!UICONTROL Retention]**-kohort mäter hur bra din person kohorter återgår till din egenskap över tid. En bevarandekohort är standardkohorten och anger att användaren ska returnera och upprepa beteendet. En grön färg anger en [!UICONTROL Retention]-kohort i tabellen.<br>**[!UICONTROL Churn]**: En **[!UICONTROL Churn]**-kohort (kallas även attribut eller utfall) mäter hur din personkohort faller bort från din egenskap över tid. Churn är motsatsen till kvarhållande: `Churn = 1 - Retention`. [!UICONTROL Churn] är ett bra mått på hur kantig kunderna är och hur ofta de inte kommer tillbaka. Du kan använda urn för att analysera och identifiera fokusområden: vilka kohortsegment kan behöva lite uppmärksamhet? En röd färg indikerar en [!UICONTROL Churn]-kohort i tabellen (liknar utfallet i **[!UICONTROL Flow]**-visualiseringen).</br> |
   | **[!UICONTROL Settings]** | **[!UICONTROL Rolling calculation]**: Beräkna kvarhållande eller bortfall baserat på föregående kolumn, i stället för kolumnen Inkluderat (standard). [!UICONTROL Rolling Calculation] ändrar beräkningsmetoden för dina returperioder. Vid den normala beräkningen hittas användare som uppfyller returkriterierna och som ingick i inkluderingsperioden. Oavsett om de var i kohorten eller inte under den föregående perioden. I stället hittar [!UICONTROL Rolling Calculation] användare som uppfyller returvillkoret och som var en del av den föregående perioden. Därför segmenterar och fördelar [!UICONTROL Rolling Calculation] de användare som kontinuerligt uppfyller kriterierna för retur under perioden. [!UICONTROL Return]-villkor används för var och en av perioderna som leder fram till den valda perioden. </br><br>**[!UICONTROL Latency Table]**: En [!UICONTROL Latency table] mäter tiden som har gått före och efter det att inkluderingshändelsen inträffade. [!UICONTROL Latency table] är användbart för för-/efteranalys. Du har till exempel en kommande produkt eller kampanj och vill spåra beteendet före och efter lanseringen. I [!UICONTROL Latency table] visas för- och efterhandsbeteendet sida vid sida för att se den direkta effekten. Cellerna före inkludering i [!UICONTROL Latency table] beräknar användare som uppfyller villkoren för [!UICONTROL Inclusion] i inkluderingsperioden och sedan uppfyller villkoren för [!UICONTROL Return] i perioderna före inkluderingsperioden. Observera att [!UICONTROL Latency table] och [!UICONTROL Custom dimension cohort] inte kan användas tillsammans.</br><br>**[!UICONTROL Custom dimension cohort]**: Skapa kohorter baserat på den valda dimensionen i stället för tidsbaserade kohorter (standard). Många kunder vill analysera sina kohorter med något annat än tid, och med den nya funktionen Custom Dimension Cohort kan du skapa kohorter baserat på de mått de väljer. Använd dimensioner, som marknadsföringskanal, kampanj, produkt, sida, region eller någon annan dimension för att visa hur kvarhållandet ändras baserat på de olika värdena för de här dimensionerna. Segmentdefinitionen [!UICONTROL Custom Dimension] för kohort tillämpar endast dimensionsobjektet som en del av inkluderingsperioden, inte som en del av returdefinitionen.</br><br>När du har valt alternativet [!UICONTROL Custom dimension cohort] kan du dra och släppa vilken dimension du vill i släppzonen. Genom att lägga till dimensioner kan du jämföra liknande dimensionsobjekt under samma tidsperiod. Du kan till exempel jämföra hur storstäder fungerar sida vid sida, produkter, kampanjer osv. Tabellen Kohort returnerar de 14 främsta dimensionsobjekten. Du kan emellertid använda ett ![segment](/help/assets/icons/Filter.svg) för att endast visa önskade dimensionsobjekt. [!UICONTROL Custom dimension cohort] kan inte användas med funktionen [!UICONTROL Latency table].</br> |

1. Klicka på **[!UICONTROL Build]**.
1. Om du vill konfigurera om [!UICONTROL Cohort table] väljer du ![Redigera](/help/assets/icons/Edit.svg).

1. (Valfritt) Skapa ett segment eller en målgrupp från en markering.

   Markera celler (angränsande eller icke-angränsande) och högerklicka sedan > **[!UICONTROL Create Segment From Selection]**.

   ![Skapa segment eller målgrupp](assets/retention-createfilter.png)

1. I [Segmentverktyget](/help/components/segments/seg-builder.md) redigerar du segmentet ytterligare och klickar sedan på **[!UICONTROL Save]**.

   Det sparade segmentet kan användas i panelen [!UICONTROL Segment] i [!UICONTROL Analysis Workspace].

## Inställningar

Du kan definiera specifika inställningar för en [!UICONTROL Cohort table].

1. Välj ![Inställning](/help/assets/icons/Setting.svg) om du vill justera [!UICONTROL Cohort table]-inställningarna.

   | Inställning | Beskrivning |
   |---|---|
   | **Visa endast procent** | Tar bort talvärdet och visar bara procentvärdet. |
   | **Avrunda procent till närmaste heltal** | Avrundar procentvärdet till närmaste heltal i stället för att visa decimalvärdet. |
   | **Visa genomsnittlig procentrad** | Infogar en ny rad högst upp i tabellen och lägger sedan till medelvärdet för värdena i varje kolumn. |


>[!MORELIKETHIS]
>
>[Lägg till en visualisering på en panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>&#x200B;>[Visualiseringsinställningar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>&#x200B;>[Snabbmenyn Visualisering ](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

