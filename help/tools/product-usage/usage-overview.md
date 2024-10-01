---
title: Översikt över produktanvändning
description: Få insikter och rapporter om hur er organisation använder Customer Journey Analytics.
hide: true
hidefromtoc: true
source-git-commit: 8f2a340f59d8cdf97a5309ec20dc36f49b8f1129
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 1%

---

# Översikt över produktanvändning

{{release-limited-testing}}

Produktanvändningen ger er möjlighet att visa analysdata om hur organisationen använder Customer Journey Analytics. Det är tillgängligt för alla organisationer som använder Customer Journey Analytics. När du har aktiverat följande Adobe Experience Platform-komponenter skapas och sammanfogas de automatiskt åt dig:

* Ett schema i Adobe Experience Platform. Schemat är skrivskyddat och kan inte redigeras.
* En datauppsättning i Adobe Experience Platform. Inställningarna för datauppsättningen är skrivskyddade och kan inte redigeras.
* En förbindelse i Customer Journey Analytics. Inställningarna för anslutningen är skrivskyddade och kan inte redigeras.
* En datavy i Customer Journey Analytics. Du kan redigera den här datavyn eller skapa fler datavyer med samma anslutning.

Alla datainsamlingar och inställningar konfigureras automatiskt när de är aktiverade. Varje gång en användare gör en åtgärd i Analysis Workspace spåras den åtgärden och är tillgänglig för rapportering.

>[!IMPORTANT]
>
>Den här funktionen tar hänsyn till era avtalsbaserade databegränsningar i Adobe Experience Platform. Se till att din organisation kan hantera data som genereras av den här funktionen innan du aktiverar den.

## Tillgängliga dimensioner

När du aktiverar produktanvändning är följande dimensioner tillgängliga:

| Dimension | Beskrivning |
| --- | --- |
| Åtgärdsnamn | Den typ av åtgärd som användaren vidtagit. Du kan använda den här dimensionen som önskat mått genom att skapa en kopia i datavyinställningarna. |
| Attributmodell som används | Den typ av attribueringsmodell som den aktuella komponenten använder. |
| Komponent | Ett härlett fält. |
| Komponenttyp | Komponenttypen som läggs till, tas bort eller ändras. |
| Anslutning | Anslutningen som används i projektet. |
| Datavy | Datavyn som används i projektet. |
| Funktion | Funktionen som används i projektet. |
| Identifierare | Den unika identifieraren för händelsen. |
| Inloggningsanvändare | Användaren som utförde åtgärden. |
| Använd panel | Panelen där komponenten lades till, togs bort eller ändrades. |
| Projekt | Ett härlett fält. |
| Projektnamn | Projektets egna namn. |
| Projekttyp | Projekttypen. |
| Användar-ID | Det användar-ID som utlöste händelsen. |
| Visualisering används | Den visualisering som lades till, togs bort eller ändrades. |

Produktanvändningen spårar inte enskilda projektkomponenter när ett projekt bara öppnas eller visas. Användaråtgärden för att öppna ett projekt spåras emellertid.
