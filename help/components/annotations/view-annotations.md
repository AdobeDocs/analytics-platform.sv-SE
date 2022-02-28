---
title: Visa anteckningar
description: Så här visar du anteckningar i Workspace.
role: User, Admin
feature: Components
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: b4e65903c720ecd9e684f8b7a764e2ba8f74baed
workflow-type: tm+mt
source-wordcount: '228'
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

## Visa anteckningar i ett sammanfattningsdiagram

![](assets/ann-summary.png)

## Visa anteckningar i en PDF-fil

Eftersom du inte kan hovra över ikoner i en PDF-fil innehåller den här filen (efter exporten) förklaringar längst ned på panelen. Här är ett exempel:

![](assets/ann-pdf.png)

## Visa anteckningar som inte är baserade på datum

Ibland är anteckningen inte knuten till ett datum, utan kopplad till en viss dimension. I så fall visas de bara i en sammanfattningsanteckning i det nedre högra hörnet. Här är ett exempel:

![](assets/non-date.png)
