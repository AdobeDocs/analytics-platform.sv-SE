---
description: Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.
keywords: Analysis Workspace
title: Dela upp dimensioner
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
solution: Customer Journey Analytics
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---

# Dela upp dimensioner i Workspace

Dela upp dimensioner och dimensionsobjekt i Analysis Workspace.

Dela upp era data på obegränsade sätt för just era behov; bygg frågor med relevanta mått, dimensioner, filter, tidslinjer och andra analysvärden.

1. [Skapa ett projekt](/help/analysis-workspace/home.md) med en datatabell.
1. Högerklicka på ett radobjekt i datatabellen och välj **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Stegresultat som visar Skapa avisering från markering.](assets/fa_data_table_actions.png)

   Du kan dela upp mätvärden efter dimensionsobjekt eller målgruppsfilter över valda tidsperioder. Du kan även gå ned mer i detalj.

   >[!NOTE]
   >
   >Antalet uppdelningar i tabellen är begränsat till 200. Den här gränsen ökar vid export av uppdelningar.

**Video: Dimensioner i Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Video: Dimensioner**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Tillämpa attribueringsmodeller på uppdelningar

Alla uppdelningar i en tabell kan också ha en attribueringsmodell. Den här attribueringsmodellen kan vara densamma eller en annan än den överordnade kolumnen. Du kan till exempel analysera linjära beställningar i dimensionen marknadsföringskanaler, men använda U-formade beställningar på specifika spårningskoder i en kanal. Om du vill redigera attribueringsmodellen som används för en uppdelning håller du muspekaren över nedbrytningsmodellen och klickar på **[!UICONTROL Edit]**:

![Jämförelse av orderattribut som visar brytningsinställningarna](assets/breakdown_settings.png)

Detta är det förväntade beteendet när du tillämpar attribueringsmodeller på uppdelningar eller redigerar dem:

* Om du tillämpar en attribuering när det inte finns några andra attribut gäller attribueringen för hela kolumnträdet.

* Om du lägger till en uppdelning efter att en attribuering har tillämpats, används standardvärdet för den angivna uppdelning som lades till (om den dimensionen har ett standardvärde). I annat fall används den uppdelning som görs från den överordnade kolumnen. Vissa dimensioner har en standardallokering. Tidsdimensioner och Referens använder till exempel samma beröring. Produktdimensionen använder Senaste beröring. Andra dimensioner saknar standardvärde och använder den överordnade kolumnallokeringen.

* Om det redan finns attribut i kolumnträdet påverkas bara den du redigerar om du ändrar attributet.

## Videor

Lägga till mått och mätvärden i ditt projekt i Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Arbeta med dimensioner i en friformstabell:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Dimension uppdelad efter position:

>[!VIDEO](https://video.tv.adobe.com/v/24033)
