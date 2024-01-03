---
title: Visa anteckningar
description: Så här visar du anteckningar i Workspace.
role: User
feature: Components
exl-id: c0e4fb37-b20c-463c-b29a-310ca3adb2c7
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# Visa anteckningar

Anteckningarna visas något annorlunda beroende på om de sträcker sig över en enstaka dag eller ett datumintervall.

## Visa anteckningar i linjediagram eller tabeller

| Datum | Utseende |
| --- | --- |
| **En dag** | ![Visualisering av raddiagram med markerad anteckning](assets/single-day.png)<p>När du hovrar över anteckningen kan du se dess detaljer, redigera den genom att markera pennikonen eller ta bort den:<p> ![Anteckningsinformation med möjlighet att redigera eller ta bort anteckningen.](assets/hover.png) |
| **Datumintervall** | Ikonen ändras och när du håller markören över den visas datumintervallet.<p>![Anteckningsikon för datumintervall](assets/multi-day.png)<p>När du markerar den i linjediagrammet visas anteckningens metadata och du kan redigera eller ta bort den:![](assets/multi-hover.png)<p>I en tabell visas en ikon för varje datum i datumintervallet.<p>![](assets/multi-day-table.png) |
| **Överlappande anteckningar** | På dagar som har fler än en anteckning kopplad till sig visas ikonen i grå färg.<p>![Information om överlappande anteckningar  ](assets/grey.png)<p>När du hovrar över den grå ikonen visas alla överlappande anteckningar:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## Visa anteckningar i en PDF-fil

Eftersom du inte kan hovra över ikoner i en PDF-fil innehåller den här filen (efter exporten) förklaringar längst ned på panelen. Här är ett exempel:

![Markerad vy av en pdf-fil med förklaringar till anteckningar.](assets/ann-pdf.png)

## Visa anteckningar med data som inte är trenddata

Ibland visas anteckningar med data som inte är trenddata, men som är knutna till en viss dimension. I så fall visas de bara i en sammanfattningsanteckning i det nedre högra hörnet. Här är ett exempel:

![](assets/non-date.png)

Sammanfattningsdiagrammet visas i alla visualiseringstyper i hörnet, inte bara i frihandstabeller och sammanfattningsnummer. Det visas också i visualiseringar som [!UICONTROL Donut], [!UICONTROL Flow],[!UICONTROL Fallout],[!UICONTROL Cohort]och så vidare.

![Sammanfattningsdiagram i visualiseringar](assets/ann-summary.png)
