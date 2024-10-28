---
title: Översikt över produktanvändning
description: Få insikter och rapporter om hur er organisation använder Customer Journey Analytics.
source-git-commit: 7d22c512e8e96963b288567704d2245e64411b10
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Översikt över produktanvändning

{{release-limited-testing}}

Produktanvändningen ger er möjlighet att visa analysdata om hur organisationen använder Customer Journey Analytics. Det är tillgängligt för alla organisationer som använder Customer Journey Analytics. När den är aktiverad skapas och sammanfogas följande Adobe Experience Platform-komponenter automatiskt. Dessa komponenter ägs av systemet, är skrivskyddade och kan inte redigeras.

* Ett schema i Adobe Experience Platform
* En datauppsättning i Adobe Experience Platform
* En anslutning i Customer Journey Analytics
* En datavy i Customer Journey Analytics

Alla datainsamlingar och inställningar konfigureras automatiskt när de är aktiverade. Varje gång en användare gör en åtgärd i Analysis Workspace spåras den åtgärden och är tillgänglig för rapportering.

>[!IMPORTANT]
>
>Den här funktionen är viktig för dina avtalsenliga radbegränsningar i Adobe Experience Platform. Se till att din organisation kan hantera data som genereras av den här funktionen innan du aktiverar den.

## Tillgängliga dimensioner

När du aktiverar produktanvändning är följande dimensioner tillgängliga. Om du vill ändra några dimensionsinställningar skapar du en kopia av den systemägda datavyn och använder den kopierade datavyn i Analysis Workspace.

| Dimension | Beskrivning |
| --- | --- |
| Åtgärdsnamn | Den typ av åtgärd som användaren vidtagit. Du kan använda den här dimensionen som önskat mått genom att skapa en kopia i datavyinställningarna. |
| Attributmodell som används | Den typ av attribueringsmodell som komponenten använder. |
| Komponent | Ett härlett fält som innehåller komponenttypen och komponentnamnet. |
| Komponenttyp | Komponenttypen som läggs till, tas bort eller ändras. |
| Inloggningsanvändare | Användaren som utförde åtgärden. |
| Använd panel | Panelen där komponenten lades till, togs bort eller ändrades. |
| Projektnamn | Projektets egna namn. |
| Projekttyp | Projekttypen. |
| Användar-ID | Det användar-ID som utlöste händelsen. |
| Visualisering används | Den visualisering som lades till, togs bort eller ändrades. |

Produktanvändningen spårar inte enskilda projektkomponenter när ett projekt bara öppnas eller visas. Användaråtgärden för att öppna ett projekt spåras emellertid.
