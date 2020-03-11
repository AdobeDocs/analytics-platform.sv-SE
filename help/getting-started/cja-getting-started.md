---
title: Komma igång med kundreseanalys
description: Customer Journey Analytics Getting Started.
translation-type: tm+mt
source-git-commit: 12ab54b09caea3b7bb5fbc345ba5e396c198a36c

---


# Komma igång med kundreseanalys

För att implementera kundreseanalys måste ni följa det här arbetsflödet. Vissa initiala uppgifter utförs i Adobe Experience Platform och andra i kundreseanalysen.

| Uppgift | Var utförd | Detaljer |
|---|---|---|
| **Steg 1: Hämta data till Adobe Experience Platform** | Adobe Experience Platform |  |
| **Steg 2: Förbered ditt dataschema** | Adobe Experience Platform | Använd [Adobe Experience Data Model (XDM)](https://www.adobe.io/apis/experienceplatform/home/xdm.html) för att standardisera kundupplevelsedata och definiera scheman för kundupplevelsehantering. |
| **Steg 3: Skapa en datauppsättning baserad på schemat** | Adobe Experience Platform | Data in Platform består av datauppsättningar, som e-postdatauppsättningar, CRM-datauppsättningar, POS-datauppsättningar, Adobe Analytics-datauppsättningen osv. Varje datauppsättning består av ett schema och grupper med data. Du kan skapa en datauppsättning [i Experience Platform](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/creating_a_dataset_tutorial/creating_a_dataset_tutorial.md).<br>Även om schemat för datauppsättningar som kan importeras till kundreseanalys är flexibelt, måste det följa vissa grundläggande regler. Det är bäst att se till att dina data uppfyller dessa krav innan du överför dem till plattformen. (Observera att schemat innehåller både mått och dimensioner.)<br>Det finns tre typer av data som är kompatibla med kundreseanalys:<ul><li>**Händelsedata**: Data som representerar händelser i tid (t.ex. webbbesök, interaktioner, transaktioner, POS-data, undersökningsdata, annonsinformation osv.). Detta är typiska klickströmsdata, med ett kund-ID eller ett cookie-ID, och en tidsstämpel. Med händelsedata kan du använda vilket ID du vill.</li><li>**Uppslagsdata**: Dessa data används för att söka efter värden eller nycklar som finns i dina händelse- eller profildata. Du kan till exempel överföra sökdata som mappar numeriska ID:n i händelsedata till produktnamn.</li><li>**Profildata**: Data som tillämpas på besökare, användare eller kunder i händelsedata. Du kan till exempel överföra CRM-data om dina kunder.</li></ul> |
| **Steg 3: Skapa anslutningar mellan plattformsdatauppsättningar och kundreseanalyser** | Customer Journey Analytics | Se [Skapa en anslutning](/help/connections/create-connection.md). |
| **Steg 4: Skapa datavyer** | Customer Journey Analytics | Se [Skapa en datavy](/help/data-views/create-dataview.md). |
| **Steg 5: Rapportera om dina flerkanalsdata i Workspace** | Customer Journey Analytics | Se [Utför grundläggande analys](/help/projects/perform-basic-analysis.md) och [Utför avancerad analys](/help/projects/perform-adv-analysis.md). |

## Förutsättningar

Customer Journey Analytics är tillgängligt för kunder som

* Är Adobe Analytics [Select-, Prime- eller Ultimate](https://www.adobe.com/analytics/compare-adobe-analytics-packages.html) -kunder, och
* tillhandahålls för [Adobe Experience Platform](https://www.adobe.com/experience-platform.html), och
* Har köpt SKU:n för kundreseanalys

## Förbered ditt dataschema

[Skapa ett schema med Schemaredigeraren](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/schema_editor_tutorial/schema_editor_tutorial.md)

## Steg 1: Hämta data till Adobe Experience Platform

Innan ni kan utnyttja Experience Platform-data i CJA måste ni importera dessa data till Platform. Det finns flera sätt att göra detta:

* Om du vill hämta in dina befintliga Adobe Analytics-data använder du Adobe Analytics Platform Connector.
* Om du vill hämta in andra data använder du filer i CSV- eller Parquet-format för att


## Steg 1 a: Använd era befintliga analysdata i Adobe Experience Platform

Använd Adobe Analytics Platform Connector för att överföra traditionella analysdata till plattformen. Du kan skapa en källanslutning per rapportserie. Se [Skapa en källanslutning med Adobe Analytics](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/sources_tutorial/adobe-analytics-ui-tutorial.md) i dokumentationen för Adobe Experience Platform.

När anslutningen har skapats skapas ett målschema och en datauppsättning automatiskt som innehåller inkommande data. Dessutom sker datainfyllning och inmatning av historiska data i upp till 13 månader. När det första intaget är klart kan du fortsätta med steg x för att skapa en anslutning mellan den här analysdatauppsättningen och kundreseanalysen.

## Steg 1 b: Skapa ett schema




