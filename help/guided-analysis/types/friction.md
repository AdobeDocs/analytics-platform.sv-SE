---
title: Bildvy
description: Jämför konverteringsgrader mellan steg.
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Guided Analysis
keywords: produktanalys
role: User
source-git-commit: a8ead81a8de8dcab4c12cbbe9cba56c4ce8417a3
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# [!UICONTROL Friction] visa

The **[!UICONTROL Friction]** ger en visuell representation av en viktig användarresa i din produkt. Den vågräta axeln representerar varje steg som en användare måste gå igenom. Den lodräta axeln representerar procentandelen användare eller sessioner i varje steg. Alla steg måste utföras i den slutliga ordningen, men kan inträffa när som helst i rapportfönstret.

>[!VIDEO](https://video.tv.adobe.com/v/3421663/?learn=on)

## Användningsexempel

Exempel:

* **Konverteringsanalys**: Du kan analysera konverteringar i varje steg i tratten. Genom att spåra antalet användare som går från ett steg till nästa kan ni identifiera flaskhalsar som har ovanliga eller oönskade konverteringsgrader. Den här informationen är värdefull för att förstå var du kan förbättra produkten och få omedelbara resultat.
* **Optimering av introduktion**: Optimera produktens introduktionsprocess genom att undersöka användarbeteenden kring viktiga händelser. Du kan identifiera vilka steg som användare kämpar med eller misslyckas med.
* **Engagemang och engagemang**: Förstå hur användarna interagerar med specifika funktioner i produkten. Genom att analysera användarnas utveckling genom funktionsrelaterade steg kan du utvärdera hur många funktioner som används och identifiera områden där användarna kan överge eller underanvända vissa funktioner. Du kan sedan använda den här informationen för att fokusera på funktionsförbättringar för att öka användningen.
* **Kampanjutvärdering**: Mät effektiviteten i marknadsföringskampanjer. Ni kan skapa ett segment som fokuserar på användare som berörde en viss kampanj och jämföra deras konverteringsprocess med andra kampanjer eller inom den övergripande produkten.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL View]**: Växla mellan den här vytypen och [Konverteringstrender](conversion-trends.md).
* **[!UICONTROL Steps]**: De händelsetyper som du vill spåra. Varje stapel i diagrammet representerar ett steg. Du kan ta med upp till tio steg.
* **[!UICONTROL Counted as]**: Det omfång som du vill ska tillämpas på tratten. Alternativen inkluderar [!UICONTROL Sessions] och [!UICONTROL Users].
   * [!UICONTROL Sessions]: Alla steg måste inträffa i samma session för att räknas.
   * [!UICONTROL Users]: Alla steg måste inträffa i det valda rapportfönstret för att räknas.
* **[!UICONTROL Segments]**: De segment som du vill jämföra tratten mellan. Varje markerat segment delar upp varje steg i flera staplar. Varje färg representerar ett eget segment. Du kan inkludera upp till tre segment.

## Diagraminställningar

I vyn Friktion finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Chart type]**: Den typ av visualisering som du vill använda. Alternativen inkluderar [!UICONTROL Steps].
* **[!UICONTROL Conversion from]**: Anger procentberäkningen från steg till steg. Alternativ för beräkning av konvertering från [!UICONTROL First step] eller [!UICONTROL Previous step].

## Tidsjämförelse

{{apply-time-comparison}}

![Jämförelse av friktionstid](../assets/friction-compare.png){style="border:1px solid gray"}

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa data efter. Den här inställningen påverkar inte vyer som inte är trendade, till exempel Bild.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
