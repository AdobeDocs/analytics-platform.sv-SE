---
title: Visa anteckningar
description: Så här visar du anteckningar i Workspace.
role: User, Admin
feature: Components
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: 998cc9e5f8d2ffd3964078dc389f55bb573063b9
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 1%

---

# Visa anteckningar

>[!NOTE]
>
>Den här funktionen är för närvarande i begränsad testning.

Anteckningarna visas något annorlunda beroende på om de sträcker sig över en enstaka dag eller ett datumintervall.

## Visa anteckningar i linjediagram eller tabeller

| Datum | Utseende |
| --- | --- |
| **En dag** | ![](assets/single-day.png)<p>När du hovrar över anteckningen kan du se dess detaljer, redigera den genom att markera pennikonen eller ta bort den:<p> ![](assets/hover.png) |
| **Datumintervall** | Ikonen ändras och när du håller markören över den visas datumintervallet.<p>![](assets/multi-day.png)<p>När du markerar den i linjediagrammet visas anteckningens metadata och du kan redigera eller ta bort den:![](assets/multi-hover.png)<p>I en tabell visas en ikon för varje datum i datumintervallet.<p>![](assets/multi-day-table.png) |
| **Överlappande anteckningar** | På dagar som har fler än en anteckning kopplad till sig visas ikonen i grå färg.<p>![](assets/grey.png)<p>När du hovrar över den grå ikonen visas alla överlappande anteckningar:<p>![](assets/overlap.png) |

## Visa anteckningar i en PDF-fil

Eftersom du inte kan hovra över ikoner i en PDF-fil innehåller den här filen (efter exporten) förklaringar längst ned på panelen. Här är ett exempel:

![](assets/ann-pdf.png)

## Visa anteckningar med icke-trenddata

Ibland visas anteckningar med data som inte är trenddata, men som är knutna till en viss dimension. I så fall visas de bara i en sammanfattningsanteckning i det nedre högra hörnet. Här är ett exempel:

![](assets/non-date.png)

Sammanfattningsdiagrammet visas i alla visualiseringstyper i hörnet, inte bara i frihandstabeller och sammanfattningsnummer. Det visas också i visualiseringar som [!UICONTROL Donut], [!UICONTROL Flow],[!UICONTROL Fallout],[!UICONTROL Cohort]och så vidare.

![](assets/ann-summary.png)