---
title: Content Analytics-rapportering
description: Rapportera om innehållsanalys
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
source-git-commit: b4325135ec05737a75027ded70e96f599eb0220c
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 0%

---

# Översikt över Content Analytics-rapportering

{{release-limited-testing}}

Du rapporterar, gör analyser och får insikter om Content Analytics inom [Analysis Workspace](/help/analysis-workspace/home.md). En specifik Workspace [mall](#template) finns tillgänglig, så du kan omedelbart komma åt ett förifyllt Workspace-projekt med relevanta innehållsinsikter.

Så här börjar du rapportera om innehållsanalys från grunden:

1. [Skapa ett nytt](/help/analysis-workspace/build-workspace-project/create-projects.md) eller [öppna ett befintligt](/help/analysis-workspace/build-workspace-project/open-projects.md)-projekt i Workspace.
1. Se till att du [väljer en datavy](/help/analysis-workspace/c-panels/panels.md#data-view) för Content Analytics-rapportering. Content Analytics-rapportering är bara tillgängligt för datavyer som är [konfigurerade](/help/content-analytics/config/configuration.md) för Content Analytics.
1. Dra en ![tabellvisualisering](/help/assets/icons/Table.svg) [Frihandsritabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) på arbetsytan.
1. Använd [specifika komponenter för innehållsanalys](components.md) och andra generiska [komponenter](/help/components/overview.md) (som filter, datumintervall, anteckningar) för att skapa insikter för innehållsanalyser.

## Miniatyrbilder

Baserat på de dimensioner av innehållsanalysen som du använder i ditt projekt visas miniatyrbilder för resurser och dimensioner.

![Miniatyrbilder för innehållsanalys](../assets/aca-thumbnails.png)

Som standard visas miniatyrbilder för relevanta Content Analytics-dimensioner. Så här konfigurerar du visningen av miniatyrbilder för en Content Analytics-dimension:

* Hovra över en rubrikrad för en Content Analytics-dimension. Till exempel **[!UICONTROL Asset Name]** eller **[!UICONTROL Experience IDs]**.
* Välj ![Inställning](/help/assets/icons/Setting.svg).
* I popup-fönstret **[!UICONTROL Row setting]**, under **[!UICONTROL Settings]**, markerar eller avmarkerar **[!UICONTROL Show Thumbnails]**.


## Förhandsgranskningar

För rader med en Content Analytics-dimension som visar miniatyrbilder kan du öppna ett popup-fönster för förhandsvisning.

Så här öppnar du förhandsgranskningen med följande information:

* Välj ![InfoOutline](/help/assets/icons/InfoOutline.svg). Du ser följande information.

  | Förhandsgranska upplevelse | Förhandsgranska resurs |
  |---|---|
  | ![Förhandsgranskning av upplevelse av innehållsanalys](../assets/aca-experience-preview.png) | ![Förhandsgranskning av innehållsanalysresurser](../assets/aca-asset-preview.png) |
  | Dimensionens namn (till exempel **[!UICONTROL Experience ID])** | Namn på resursdimensionen (till exempel **[!UICONTROL Asset ID])** |
  | **[!UICONTROL Impressions (all time)]**: Antal visningar för upplevelsen. | **[!UICONTROL Impressions (all times)]**: Antal visningar för resursen. |
  | **[!UICONTROL Assets]**: Antal resurser som den här upplevelsen innehåller. <br/>Välj ![Uppdelning](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** för att inspektera resurserna. | **[!UICONTROL Experiences]**: Antal upplevelser där den här resursen visas. <br/>Välj ![Uppdelning](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** för att inspektera resurserna. |
  | **[!UICONTROL First impression]**: Datum för första intryck av upplevelsen. | **[!UICONTROL First impression]**: Datum för första exponering av resursen. |
  | **[!UICONTROL  Most recent impression]**: Datum för det senaste intrycket av upplevelsen. | **[!UICONTROL Most recent impression]**: Datum för det senaste intrycket av resursen. |
  | **[!UICONTROL Experience attributes]**: Upplevelsens [attribut](/help/content-analytics/report/components.md#experience-attributes). | **[!UICONTROL Asset attributes]**: Resursens [attribut](/help/content-analytics/report/components.md#asset-attributes). |


## Mall

Det finns en [mall](/help/analysis-workspace/templates/use-templates.md) för innehållsanalys som hjälper dig att ta reda på vilka innehålls- och innehållsattribut som fungerar bäst. Mallen är en del av [webbkanalen och engagemangets användningsfall](/help/analysis-workspace/templates/use-templates.md#web-engagement) och innehåller detaljerad information om hur innehållet fungerar. Du kan titta på prestanda för enskilda resurser eller specifika attribut.

Baserat på vad du lär dig kan du göra en mängd saker. Som att marknadsföra högpresterande resurser på din hemsida, anpassa innehåll för specifika segment så att det innehåller högpresterande attribut eller rotera innehåll som har börjat bli inaktuellt.

Så här använder du mallen:

1. Välj **[!UICONTROL Workspace]** på huvudmenyn.
1. Kontrollera att du har valt en datavy som är konfigurerad för Content Analytics.
1. Sök efter eller använd filter (**[!UICONTROL Web]** för **[!UICONTROL Channel]** och **[!UICONTROL Engagement]** för **[!UICONTROL Use Case]**s) för att hitta och välja mallen **[!UICONTROL Content analytics]**.
1. Välj **[!UICONTROL Use template]**.
1. I dialogrutan **[!UICONTROL Set up your template]** väljer du ett mått i dialogrutan **[!UICONTROL Select a conversion metric]**. Exempel: **[!UICONTROL Asset CTR]**.
1. Välj **[!UICONTROL Continue]**.

Ett **[!UICONTROL Content Analytics Overview]**-projekt öppnas i [Analysis Workspace](/help/analysis-workspace/home.md). Projektet består av fyra [paneler](/help/analysis-workspace/c-panels/panels.md), där varje panel innehåller [frihandstabeller](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) och [visualiseringar](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) som kan besvara en viss fråga:

* **Vilket innehåll fungerar bäst?**
Panelen hjälper er att förstå vilka upplevelser och vilka resurser i upplevelserna som skapar engagemang och konverteringar. Upplevelserna är en komplett webbsida som spelas in vid en viss tidpunkt. En upplevelse kan innehålla både text och flera enskilda bildresurser. En resurs är en enskild bild.

  Panelen består av följande visualiseringar:

   * **Upplevelser**.

     >[!NOTE]
     >
     >Dessa visualiseringar visas bara när du har [inkluderade upplevelser](/help/content-analytics/config/guided.md#experience-capture-and-definition) i din Content Analytics-konfiguration.
     > 

      * **Upplev CTR**: en [sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md) visualisering, som visar upplevelseindikatorn för aktuell tid.
      * **Top converting experiences**: En [horisontell fältvisualisering](/help/analysis-workspace/visualizations/horizontal-bar.md) som visar de bästa konverteringsupplevelserna baserat på det valda konverteringsmåttet.
      * **De bästa upplevelserna**: En [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (inklusive [miniatyrbilder](#thumbnails) och [förhandsvisningar](#previews)) för de bästa upplevelserna.

   * **Assets**

      * **Resurs-CTR**
En [sammanfattningsändring](/help/analysis-workspace/visualizations/summary-number-change.md) som visar CTR för resurs.
      * **De viktigaste konverteringsresurserna**
En [ vågrät fältvisualisering ](/help/analysis-workspace/visualizations/horizontal-bar.md) som visar de översta konverteringsresurserna baserat på det valda konverteringsmåttet.
      * **Resurser som presterar bäst**
En [ friformstabell ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (inklusive [ miniatyrbilder ](#thumbnails) och [ förhandsvisningar ](#previews) ) för de resurser som presterar bäst.
      * **Assets - vyer jämfört med konvertering.**
En [ punktritningsvisualisering ](/help/analysis-workspace/visualizations/scatterplot.md) som visar en punktdiagram över tillgångsvyer jämfört med tillgångskonverteringar.

* **Vilka resursattribut bidrar till konverteringar?**
Content Analytics använder AI och GenAI för att tilldela alla metadata för resurser automatiskt, som motiv, scener, förgrundsfärger osv. Ett attribut är en AI-tilldelad metadatatagg som beskriver vad som finns i en resurs eller upplevelse. Till exempel: <code>förgrundsfärg: röd</code> är ett automatiskt tilldelat attribut. Med visualiseringarna kan du identifiera vilka attribut i dina resurser som bidrar mest till konverteringen.

  Panelen består av följande visualiseringar:

   * **De viktigaste konverteringsattributen för resurser**
Ett [ vågrätt fält ](/help/analysis-workspace/visualizations/horizontal-bar.md) som visar de översta konverteringsattributen baserat på det valda konverteringsmåttet.
   * **De viktigaste attributen för att konvertera resurser jämfört med tidigare 30 dagar**
En [ vågrät fältvisualisering ](/help/analysis-workspace/visualizations/horizontal-bar.md) som visar de översta konverteringsattributen, jämfört med de föregående 30 dagarna, baserat på det valda konverteringsmåttet.
   * **De viktigaste konverteringarna av resursattributdata**
En [ friformstabell ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) som visar de översta konverteringsattributen baserat på det valda konverteringsmåttet. Markera en rad i tabellen om du vill uppdatera attributtrendvisualiseringen.
   * **Attributtrend**
En [ rad ](/help/analysis-workspace/visualizations/line.md) -visualisering som visar attributtrenden för det markerade översta konverteringstillgångsattributet.
   * **Resursens förgrundsfärg**
Ett exempel på en [ frihandstabell ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) som jämför prestanda för objekt i en attributkategori för en resurs: Förgrundsfärger. Du kan ersätta det här resursattributet med andra dimensioner för tillgångsattributkategorier.

* **Vilka upplevelseattribut bidrar till konverteringarna?**

  >[!NOTE]
  >
  >Den här panelen visas bara när du har [inkluderade upplevelser](/help/content-analytics/config/guided.md#experience-capture-and-definition) i din Content Analytics-konfiguration.
  > 

  Resursattribut fokuserar på bildens visuella egenskaper, men upplevelseattribut fokuserar på texten på sidan. Med visualiseringarna nedan kan du utforska vilka upplevelseattribut som bidrar till konverteringen. Dessa attribut tilldelas också automatiskt med hjälp av AI- och GenAI-modeller.

  Panelen består av följande visualiseringar:

   * **De viktigaste attributen för konvertering av upplevelser**
En [ vågrät fältvisualisering ](/help/analysis-workspace/visualizations/horizontal-bar.md) som visar de viktigaste konverteringsattributen baserat på det valda konverteringsmåttet.
   * **De viktigaste attributen för konvertering jämfört med tidigare 30 dagar**
En [ vågrät fältvisualisering ](/help/analysis-workspace/visualizations/horizontal-bar.md) som visar de viktigaste konverteringsattributen, jämfört med de föregående 30 dagarna, baserat på det valda konverteringsmåttet.
   * **De viktigaste konverteringsattributsdata**
En [ friformstabell ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) som visar de mest konverterade upplevelserna baserat på det valda konverteringsmåttet. Markera en rad i tabellen för att uppdatera radinvisualiseringen.
   * **Rad**
En [ linje ](/help/analysis-workspace/visualizations/line.md) -visualisering som visar trenden för det valda toppattributet för konvertering.
   * **Upplev nyckelord**
En [ friformstabell ](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) som visar nyckelorden för de översta upplevelserna baserat på det valda konverteringsmåttet.

* **Var visas resurser på min webbplats?**
En panel som består av en frihandstabell som innehåller information om var de mest visade resurserna visas på webbplatsen.

  Panelen består av en visualisering:

   * **Var visas de mest visade resurserna?**
Du kan dela upp en resurs efter dimensioner för att få en bättre förståelse för var bilden visas.

     I exemplet [friformstabell](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (inklusive [miniatyrbilder](#thumbnails) och [förhandsvisningar](#previews)) används **[!UICONTROL Asset Perception ID]** i stället för [!UICONTROL Asset Id]. Ibland kan samma bild dupliceras på webbplatsen med en annan bild-URL. Attributet [!UICONTROL Asset Perception ID] hjälper till att gruppera dessa dubbletter under ett enda ID.

     Eftersom resurser kan ändras på en sida, delas varje resurs upp efter **[!UICONTROL Experience Id]** för att identifiera vilken version av sidan som resursen fanns på. Du kan ersätta [!UICONTROL Experience Id] med andra dimensioner som hjälper dig att förstå platsen för en resurs på din plats. Till exempel [!UICONTROL Page name], [!UICONTROL Page URL] eller [!UICONTROL Site section].

     Du kan också växla ut [!UICONTROL Asset Perception ID] med [!UICONTROL Asset Id] för att få en post över var specifika bild-URL:er refereras.


>[!MORELIKETHIS]
>
>[Innehållsanalyskomponenter](components.md)
>[Använd mallar](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
