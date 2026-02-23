---
title: Funnel-analys
description: Jämför konverteringsgrader mellan steg.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---

# [!UICONTROL Funnel]-analys {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="Tratt"
>abstract="Jämför konverteringsgrader mellan steg."

<!-- markdownlint-enable MD034 -->

Analysen ![ConversionTrnel ](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL Funnel]**ger en visuell representation av en viktig användarresa i din produkt. Den vågräta axeln representerar varje steg som en användare måste gå igenom. Den lodräta axeln representerar procentandelen användare eller sessioner i varje steg. Alla steg måste utföras i den slutliga ordningen, men kan inträffa när som helst i rapportfönstret.

>[!BEGINSHADEBOX]

Se ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Funnel-friktionsanalys](https://video.tv.adobe.com/v/3421663/?quality=12&learn=onn){target="_blank"} för en demonstrationsvideo.

>[!ENDSHADEBOX]


## Användningsexempel

Användningsexempel för den här analysen är:

* **Konverteringsanalys**: Du kan analysera konverteringar i varje steg i funnel, till exempel en utcheckning (butik), kontoregistrering, prenumerationsflöde eller någon annan viktig process i produktupplevelsen. Genom att spåra antalet användare som går från ett steg till nästa kan ni identifiera flaskhalsar som har ovanliga eller oönskade konverteringsgrader. Denna information är värdefull för att förstå var ni kan förbättra er produktresa och få omedelbara resultat.
* **Experimentationsanalys**: Du kan jämföra konverteringsgrader i en funnel som har valfria steg eller steg där ett A/B-experiment körs. Den här informationen kan hjälpa dig att avgöra vilken variant av funnel som leder till den högsta konverteringsgraden så att du kan uppmuntra fler användare på den vägen.
* **Integreringsoptimering**: Optimera startprocessen för din produkt genom att undersöka användarbeteenden runt viktiga händelser. Du kan identifiera vilka steg som användare kämpar med eller misslyckas med.
* **Funktionens införande och engagemang**: Förstå hur användarna interagerar med specifika funktioner i produkten. Genom att analysera användarnas utveckling genom funktionsrelaterade steg kan ni se hur många användare som har kommit igång och identifiera områden där användarna kan komma att underanvända vissa funktioner. Du kan sedan använda den här informationen för att fokusera på funktionsförbättringar för att öka användningen.
* **Marknadskanalernas effektivitet**: Mät marknadsföringskanalernas effektivitet. Du kan skapa ett segment som fokuserar på användare som interagerade med olika marknadsföringskanaler, till exempel betalsökningar, webbannonser, naturlig sökning eller direktsökning. Sedan kan ni jämföra deras resor för att se vilken kanal som leder till de bästa produktresultaten.

## Gränssnitt

I [Gränssnitt](../overview.md#interface) finns en översikt över gränssnittet för guidad analys. Följande inställningar är specifika för den här analysen:

### Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan den här analysen och [Konverteringstrender](conversion-trends.md).
* **[!UICONTROL Steps]**: De kontaktytor för händelsen som du vill spåra. Varje stapel i diagrammet representerar ett steg. Du kan ta med upp till tio steg.
   * [!UICONTROL Compare]: I varje steg finns ett alternativ för att jämföra flera händelser i ett enda funnel-steg och skapa en&quot;forked funnel&quot;. Med den här funktionen kan du jämföra friktionen för två resor sida vid sida utan att skapa två separata analyser. Det är användbart när det finns stegalternativ eller när ett A/B-experiment körs i funnel. Se [Funnel](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel) i Customer Journey Analytics självstudiekurser för en video som förklarar hur du jämför resurser.
* **[!UICONTROL Counted as]**: Det omfång som du vill tillämpa på funnel. Alternativen är [!UICONTROL Sessions] och [!UICONTROL Users].
   * [!UICONTROL Sessions]: Alla steg måste inträffa inom samma session för att räknas.
   * [!UICONTROL Users]: Alla steg måste inträffa i det valda rapportfönstret för att räknas.
* **[!UICONTROL Segments]**: Segmenten som du vill jämföra funnel med. Varje markerat segment delar upp varje steg i flera staplar. Varje färg representerar ett eget segment. Du kan inkludera upp till tre segment.

### Diagraminställningar

Analysen av [!UICONTROL Funnel] innehåller följande diagraminställningar som kan justeras i menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen är [!UICONTROL Steps].
* **[!UICONTROL Conversion from]**: Anger procentberäkningen från steg till steg. Du kan använda alternativen för att beräkna konverteringen från [!UICONTROL First step] eller [!UICONTROL Previous step].

### Tidsjämförelse

{{apply-time-comparison}}



### Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Den här inställningen påverkar inte icke-trendanalyser som [Funnel](funnel.md).
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
