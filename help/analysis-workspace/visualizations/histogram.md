---
description: Ett histogram är en ny visualiseringstyp i Analysis Workspace.
title: Histogram
uuid: 8a6bd2c4-da15-4f64-b889-ab9add685046
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 3%

---


# Histogram

>[!NOTE]
>
>Du visar dokumentationen för Analysis Workspace i Customer Journey Analytics. Dess funktionsuppsättning skiljer sig något från [Analysis Workspace i traditionell Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/home.html). [Läs mer …](/help/getting-started/cja-aa.md)

Ett histogram liknar ett stapeldiagram, men det grupperar numren i intervall (bucket). Analysen automatiserar &quot;låsningen&quot; av nummer i intervall, men du kan ändra inställningarna i [Avancerade inställningar](#section_09D774C584864D4CA6B5672DC2927477).

## Bygg ett histogram {#section_74647707CC984A1CB6D3097F43A30B45}

Så här skapar du ett histogram:

1. Klicka **[!UICONTROL Visualizations]** i vänster räl.
1. Dra **[!UICONTROL Histogram]** till panelen.
1. Välj ett mått att dra till visualiseringen av histogrammet och klicka på **[!UICONTROL Build]**.

![](assets/histogram.png)

>[!NOTE]
>
>Histogram har endast stöd för standardmått, ej beräknade mått.

Här har vi använt måttet Sidvyer per Unika besökare. Den första (vänstra) haken motsvarar 1 sidvy per unik besökare, den andra haken till två sidvyer osv.

![](assets/histogram2.png)

## Avancerade inställningar {#section_09D774C584864D4CA6B5672DC2927477}

Om du vill justera histograminställningarna klickar du på ikonen Inställningar (&quot;växel&quot;) i det övre högra hörnet. Här följer inställningarna som du kan ändra:

| Inställningar för histogram | Vad gör den? |
|---|---|
| Startar buffert | Anger vilken bucket histogrammet börjar med. &quot;1&quot; är standardvärdet. Du kan ange startnummer från 0 till oändligt (inga negativa tal). |
| Metrisk buffert | Gör att du kan öka/minska antalet dataområden (bucket). Maximalt antal hinkar är 50. |
| Storlek på måttbuffert | Du kan ange storleken på varje hink. Du kan t.ex. ändra bucketstorleken från en sidvy till två sidvisningar. |
| Räkningsmetod | Gör att du kan välja bland [Besökare](https://docs.adobe.com/content/help/en/analytics/components/metrics/unique-visitors.html), [Besök](https://docs.adobe.com/content/help/en/analytics/components/metrics/visits.html)eller Träff. Exempelvis sidvy per besök eller sidvy per besökare eller sidvy per träff. För Träff används &quot;Förekomster&quot; som y-axelmått i en friformstabell. |

<!--Russ or Meike - Check Hit Type link above. -->

**Exempel**:

* Starthastighet: 1. Metrisk buffert: 5. Storlek på måttstork: 2 kommer att resultera i detta histogram: 1-2, 3-4, 5-6, 7-8, 9-10.
* Starthastighet: 0. Metrisk buffert: 3. Storlek på måttstork: Detta histogram ger följande resultat: 0-4, 5-9, 10-14

## Visa och redigera histogramdata {#section_B2CD7CDF0F6B432F928103AE7AAA3617}

Om du vill visa eller ändra datakällan för histogrammet klickar du på punkten bredvid Histogramhuvudet för att gå till **[!UICONTROL Data Source Settings]** > **[!UICONTROL Show Data Source]**.

![](assets/manage-data-source.png)

Förbyggda segment som visas i tabellen är interna segment och visas inte i Segmentväljaren. Klicka på ikonen &quot;i&quot; bredvid segmentnamnet och klicka sedan på **[!UICONTROL Make public]** för att göra segmentet offentligt.

![](assets/prebuilt_segments.png)

Om du vill utforska fler sätt att hantera Freeform-datatabeller och andra visualiseringar, t.ex. genom att göra datauppdelningar, går du [här](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html).
