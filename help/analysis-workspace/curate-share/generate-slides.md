---
description: Lär dig generera presentationer i pptx-format från Workspace-rapporter.
keywords: Analysis Workspace
title: Generera presentationer från Workspace-rapporter
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 9e23382800326440ed2a583e80029c9f27bb2494
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 0%

---

# Data storytelling: Generera bildpresentationer från Workspace-rapporter {#generate-powerpoint}

Användare med [nödvändig behörighet](#permission-requirements-to-generate-slides) kan automatiskt generera .pptx-presentationer från Analysis Workspace-projekt. När du skapar dessa bildpresentationer skapar Customer Journey Analytics automatiskt en berättelse utifrån era data genom att identifiera viktiga insikter och konvertera dem till bilder som är klara för intressenter.

Denna funktionalitet minskar den tid och det arbete som krävs för att ta fram resultat från era Workspace-projekt, och gör att ni snabbt kan skapa chefsberättelser och förmedla affärsresultat till intressenter.

Med den här automatiskt genererade databerättelsen kan analytiker fokusera på datautforskandet, medan Customer Journey Analytics strukturerar och formaterar analytikernas resultat för intressenternas konsumtion.

## Förstå dataartiklar i bildpresentationer

Analysis Workspace använder generativ AI för att skapa databerättelser i bildpresentationer. Dessa datamaterial kompletterar en analys av ett visst Workspace-projekt genom att ge ytterligare kontext, lyfta fram viktiga högdagrar och ge idéer för nästa steg. identifiera dolda trender, avvikelser, bidragande faktorer, viktiga faktorer

### Ytterligare värde från datarubriker

Data från olika källor kompletterar en analys av ett visst Workspace-projekt genom att

* Tillhandahåller ytterligare kontext

* Markera viktiga insikter

* Påtala dolda trender, avvikelser och andra bidragande faktorer

* Identifiera nyckeldrivrutiner

* Ge idéer för nästa steg

### Projektelement som formar dataartiklar

Analysis Workspace skapar dataartiklar genom att ta hänsyn till följande projektelement:

* Relationer mellan dimensioner och mätvärden

* De enskilda element som utgör grunden för analysen: mått, mått, filter, tabellstruktur på frihand, visualiseringar och paneler

* Namnen på panelerna, tabellerna och visualiseringarna

* Metrisk ordning i en frihandstabell (för att bestämma prioritet)

* Sammanfattningsnummer och sammanfattningstexter (för att avgöra vilka mätvärden som behöver markeras i dataartikeln)

### Presentationselement i en dataartikel

Databerättelser består av en sammanfattande bild, detaljbilder och avsnittsavgränsare.

**Sammanfattning:** Prioriterar de mest värdefulla insikterna och skapar en övergripande berättelse mellan 1 och 5 meningar i längd.

**Detaljbilder:** Genererar insikter om tabeller, paneler eller visualiseringar i ett Workspace-projekt. Insikterna består av trender, säsongsvariationer, avvikelser och korrelationer.

**Avsnittsavgränsare:** delar insikter med avsnittsavgränsare som är placerade och namngivna.

## Generera en .pptx-presentation baserad på ett Workspace-projekt

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Inkluderade paneler och visualiseringar"
>abstract="Välj paneler och visualiseringar som du vill ta med i presentationen. Du kan inkludera upp till 50 visualiseringar."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Viktiga komponenter"
>abstract="Välj upp till 5 mätvärden och 5 dimensioner från dina visualiseringar som du vill betona i presentationen. De mätvärden du väljer visas i kursiv stil, måtten visas i fet stil och dimensionsobjekten visas i en kontrasterande färg."

<!-- markdownlint-enable MD034 -->

1. Gå till det Workspace-projekt som innehåller de data du vill använda som bas för bildpresentationen.

1. Välj **[!UICONTROL Generate slides]** i det övre högra hörnet på sidan.

   Dialogrutan Generera bilder visas.

   ![Dialogrutan Generera bilder](assets/generate-slides.png)

1. Ange följande information:

   | Alternativ | Beskrivning |
   |---------|----------|
   | **[!UICONTROL Cover title]** | Ange en rubrik för presentationen. Den här rubriken visas på presentationens rubrikbild. |
   | **[!UICONTROL Include presenter name]** | Ange namnet på presentatören. Namnet visas på presentationens rubrikbild, under omslagets rubrik. |
   | **[!UICONTROL Panels and visualizations to include]** | Välj paneler och visualisering som du vill ta med i presentationen. Du kan inkludera upp till 50 visualiseringar.<p>De flesta paneler och visualiseringar stöds. Mer information om paneler och visualisering som inte stöds finns i [Projektelement och funktioner som inte stöds](#unsupported-project-elements-and-features).</p> |
   | **[!UICONTROL Panel and visualization descriptions]** | |
   | **[!UICONTROL Annotations]** | |
   | **[!UICONTROL Emphasize components]** | Välj upp till 5 mätvärden och 5 dimensioner från dina visualiseringar som du vill betona i presentationen.<p>När ingen betoning används visas komponenterna i presentationer enligt följande:<ul><li>**Mätvärden och dimensioner:** Kursiv</li><li>**Dimension-objekt:** Citattecken</li></ul></p><p>När betoning används visas komponenterna i presentationer enligt följande:</p><ul><li>**Mätvärden och dimensioner:** Kursiv och fet</li><li>**Dimension-objekt:** Fet när motsvarande dimension framhävs<p>En färg används också på dimensionsobjektet när dimensionsobjektet är markerat i diagrammet.</p></li></ul> |

1. (Villkorligt) Välj **[!UICONTROL Default theme]** om du snabbt vill generera bilder i färre steg och om ett företagstema inte krävs för bildpresentationen.

   Välj bara den färg du vill använda.

   ![Generera bilder med standardtemat](assets/generate-slides-default-theme.png)

1. (Villkorligt) Välj **[!UICONTROL Upload template]** om bildpresentationen behöver matcha ett företagstema. Det här alternativet kräver att du överför en anpassad mall och använder dina anpassade format.

   ![Generera bilder med en anpassad mall](assets/generate-slides-upload-template.png)

   Gör något av följande om du vill överföra en anpassad mall:

   * (Rekommenderas) Hämta en tom mall och ändra den.

      1. Hämta den här tomma mallen. <!--add link-->

      1. Använd dina anpassade format på den tomma mallen.

      1. Ladda upp mallen igen utan att ändra några malllayoutsnamn.

   * Överför en anpassad mall direkt.

      1. Dra den anpassade mallen från filsystemet till släppområdet.

         eller

         Välj **[!UICONTROL Browse]**, bläddra sedan till och välj din anpassade mall från filsystemet.

         Kontrollera att den överförda filen har mallayouter med följande namn: &quot;Title_Slide&quot;, &quot;Section_Divider&quot;, &quot;Title_Text&quot;, &quot;Title_Chart&quot;, &quot;Title_Two_Content_Mixed&quot;, &quot;Title_Three_Content_Mixed&quot;

         .pptx- och .potx-filer som är upp till 25 MB stora stöds.

1. Välj **[!UICONTROL Export PPT]**.

1. (Rekommenderas) Granska och redigera .ppt-presentationen och gör de ändringar som behövs enligt beskrivningen i följande avsnitt: [Redigera bilder från en tidigare genererad presentation](#edit-slides-from-a-previously-generated-presentation).

## Redigera bilder från en tidigare genererad presentation


## Hämta en genererad PPTX-presentation



## Behörighetskrav för att generera bilder

>[!AVAILABILITY]
>
>Om ni inte har tillgång till bildspel från Workspace kontaktar ni er Adobe återförsäljare.
>
>Den här funktionen är aktiverad som standard för alla användare i organisationer som har den nödvändiga licensieringen.

Administratörer av produktprofiler vars organisationer har licens att generera bilder kan vid behov inaktivera åtkomsten.

I [!UICONTROL Adobe Admin Console] avgör behörigheten [!UICONTROL Reporting Tools] **[!UICONTROL Data storytelling]** åtkomsten till den här funktionen. En [produktprofiladministratör](https://helpx.adobe.com/se/enterprise/using/manage-product-profiles.html) måste följa de här stegen i [!UICONTROL Admin Console] om de vill inaktivera åtkomst:
1. Navigera till **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
1. Välj titeln för den produktprofil som du vill ge åtkomst till [!UICONTROL Data storytelling].
1. Välj **[!UICONTROL Permissions]** i den specifika produktprofilen.
1. Välj ![Redigera](/help/assets/icons/Edit.svg) om du vill redigera **[!UICONTROL Reporting Tools]**.
1. Välj ![AddCircle](/help/assets/icons/RemoveCircle.svg) om du vill ta bort **Data storytelling** från **[!UICONTROL Included permission items]**.

   <!--add screenshot of permission in the admin console-->

1. Välj **[!UICONTROL Save]** om du vill spara behörigheterna.

Mer information finns i [Åtkomst på användarnivå](/help/technotes/access-control.md#user-level-access) i [Åtkomstkontroll](/help/technotes/access-control.md#access-control).

## Projektelement och funktioner som inte stöds {#unsupported}

Följande Analysis Workspace-element och -funktioner som används i ett projekt stöds inte när bilder skapas:

* Attributionspanelen

  Panelen visas som nedtonad när konfigurationsalternativen visas.

  Alla andra paneler kan inkluderas i bilder som genereras från ett Workspace-projekt.

* Vissa visualiseringar

  De flesta visualiseringar kan inkluderas i bilder som skapas från ett Workspace-projekt. Följande visualiseringar kan dock inte inkluderas och visas som nedtonade när konfigurationsalternativen visas:

   * Kohortabell

   * Reseduk

   * Punkt

   * Kombination

   * Spridning

   * Treemap

* Uppdelningar

* Guidade analyser


