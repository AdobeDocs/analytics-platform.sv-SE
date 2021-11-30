---
title: Komponentinställningar för måttborttagning av dubbletter
description: Räkna bara den första förekomsten av ett mätvärde i rapporter.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 1%

---

# Komponentinställningar för måttborttagning av dubbletter

Med metrisk borttagning av dubbletter kan du konfigurera ett mätvärde så att det bara räknar värden som inte upprepas.

| Inställning | Beskrivning |
| --- | --- |
| Metrisk deduplicering | En kryssruta där du kan aktivera metrisk deduplicering. Inaktiverad som standard. |
| Dedupliceringsomfång | Här kan du bestämma hur långt bakåt den unika kontrollen ska gå.<br>**Session**: Endast den första mätarförekomsten av sessionen räknas.<br>**Person**: Endast den första mätförekomsten i rapporteringsfönstret räknas. |
| Deduplicerings-ID | I stället för att tillämpa borttagning av dubbletter på själva måttet kan du använda metrisk borttagning av dubbletter baserat på en dimension i stället. Värdefull för dimensioner som Inköp-ID för borttagning av dubbletter. |
