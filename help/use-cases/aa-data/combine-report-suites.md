---
title: Kombinera rapportsviter med olika scheman
description: Lär dig använda Data Prep för att kombinera rapportsviter med olika scheman
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
feature: Use Cases
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '1321'
ht-degree: 0%

---

# Kombinera rapportsviter med olika scheman

[Analytics-källkopplingen](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html) samlar in rapportsvitsdata från Adobe Analytics i Adobe Experience Platform för användning i Adobe Experience Platform-program, som Real-time Customer Data Platform och Customer Journey Analytics (Customer Journey Analytics). Varje rapportsvit som hämtas in till Adobe Experience Platform konfigureras som ett enskilt källanslutningsdataflöde, och varje dataflöde markeras som en datauppsättning i Adobe Experience Platform datasjön. Analyskällans koppling skapar en datauppsättning per rapportserie.

Customer Journey Analytics-kunder använder [anslutningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html) för att integrera datauppsättningar från Adobe Experience Platform Data Lake i Customer Journey Analytics Analysis Workspace. När du kombinerar rapportsviter i en anslutning måste schemaskillnaderna mellan rapportsviterna dock lösas med Adobe Experience Platform [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html) -funktion. Syftet är att säkerställa att Adobe Analytics-variabler som props och eVars har en konsekvent innebörd i Customer Journey Analytics.

## Schemaskillnader mellan rapportsviter är problematiska

Anta att ert företag vill överföra data från två olika rapportsviter till Adobe Experience Platform för användning av Customer Journey Analytics, och anta att scheman för de två rapportsviterna skiljer sig åt:

| Report Suite A | Report Suite B |
| --- | --- |
| eVar1 = Sökord | eVar1 = Affärsenhet |
| eVar2 = Kundkategori | eVar2 = Sökord |

För enkelhetens skull antar vi att det här är de enda definierade eVars för båda rapportsviterna.

Anta dessutom att du utför följande åtgärder:

- Skapa en anslutning till en Analytics-källa (utan dataförberedelse) som importerar **Report Suite A** till Adobe Experience Platform-datasjön som **datauppsättning A**.
- Skapa en anslutning till en Analytics-källa (utan dataförberedelse) som importerar **Report Suite B** till Adobe Experience Platform-datasjön som **datauppsättning B**.
- Skapa en [Customer Journey Analytics-anslutning](/help/connections/create-connection.md) med namnet **Alla rapportsviter** som kombinerar datauppsättning A och datauppsättning B.
- Skapa en [Customer Journey Analytics-datavy](/help/data-views/create-dataview.md) med namnet **Global vy** som baseras på anslutningen Alla rapportsviter.

Utan att använda Data Prep för att lösa schemaskillnaderna mellan datauppsättning A och datauppsättning B kommer eVarorna i datavyn i den globala vyn att innehålla en blandning av värden:

| Datavy för global vy i Customer Journey Analytics |
| --- |
| eVar1 => en blandning av söktermer och affärsenheter |
| eVar2 => en blandning av kundkategorier och söktermer |

Detta resulterar i meningslösa rapporter för eVar1 och eVar2:

- EVar-fälten innehåller en blandning av värden med olika semantiska betydelser.
- Sökvillkoren fördelas mellan eVar1 och eVar2.
- Det går inte att använda olika attribueringsmodeller för varje sökterm, affärsenhet eller kundkategori.

## Använd Adobe Experience Platform Data Prep för att lösa schemaskillnader mellan olika rapportsviter

Experience Platform Data Prep-funktionen är integrerad med Analytics-källkopplingen och kan användas för att lösa de schemaskillnader som beskrivs i scenariot ovan. Detta resulterar i eVars med enhetlig betydelse i datavyn i Customer Journey Analytics. (Namnkonventionerna nedan kan anpassas efter dina behov.)

1. [Skapa ett nytt schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html) i Adobe Experience Platform innan du skapar källanslutningsdata för Report Suite A och Report Suite B (vi kallar det **Unified Schema** i vårt exempel). Lägg till följande i schemat:

   | &quot;Enhetligt schema&quot; |
   | --- |
   | Klassen **XDM ExperienceEvent** |
   | **Adobe Analytics ExperienceEvent-mall**, fältgrupp |

1. Lägg till en annan fältgrupp i schemat eller [skapa en anpassad fältgrupp](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) och lägg till den i schemat. Vi skapar en ny fältgrupp och kallar den **enhetliga fält**. Sedan lägger vi till följande fält i den nya fältgruppen:

   | Anpassad fältgrupp för enhetliga fält  |
   | --- |
   | Sökterm |
   | Affärsenhet |
   | Kategori |

1. Skapa källanslutningsdataflödet för **Report Suite A** och välj **Unified Schema** för användning i dataflödet. Lägg till anpassade mappningar i dataflödet enligt följande:

   | Report Suite A source field | Målfält från fältgruppen Enhetliga fält |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;sökväg>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;sökväg>_.Customer_category |

   >[!NOTE]
   >
   >XDM-sökvägen för målfälten beror på hur du strukturerar den anpassade fältgruppen.

1. Skapa källanslutningsdataflödet för **Report Suite B** och välj **Unified Schema** igen för användning i dataflödet. Arbetsflödet visar att två fält har en konflikt med ett beskrivningsnamn. Detta beror på att beskrivningarna för eVar1 och eVar2 skiljer sig åt i Report Suite B jämfört med i Report Suite A. Men vi vet redan detta, så vi kan ignorera konflikten och använda anpassade mappningar enligt följande:

   | Källfält för Report Suite B | Målfält från fältgruppen Enhetliga fält |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;sökväg>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;sökväg>_.Search_term |

1. Skapa nu en **Alla rapportsviter**-anslutning för Customer Journey Analytics, som kombinerar datauppsättning A och datauppsättning B.

1. Skapa en **global datavy** i Customer Journey Analytics. Ignorera de ursprungliga eVar-fälten och ta endast med fälten från fältgruppen Enhetliga fält.

   **Datavy** i Customer Journey Analytics:

   | Source | Vill du inkludera i datavyn? |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nej |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nej |
   | _\&lt;sökväg>_.Search_term | Ja |
   | _\&lt;sökväg>_.Customer_category  | Ja |
   | _\&lt;sökväg>_.Business_unit | Ja |

Du har nu mappat eVar1 och eVar2 från källrapportsviterna till tre nya fält. Observera att en annan fördel med att använda Data Prep-mappningar är att målfälten nu baseras på semantiskt meningsfulla namn (sökterm, affärsenhet, kundkategori) i stället för de mindre meningsfulla eVar-namnen (eVar1, eVar2).

>[!NOTE]
>
>Den anpassade fältgruppen Enhetliga fält och tillhörande fältmappningar kan när som helst läggas till i befintliga anslutningsdataflöden och datauppsättningar för Analytics-källan. Detta påverkar dock endast data som skickas vidare.

## Mer än bara rapportsviter

Funktionerna hos Data Prep för att kombinera datauppsättningar med olika scheman går utöver rapportsviterna i Analytics. Anta att du har två datauppsättningar som innehåller följande data:

| Datauppsättning A = Rapporteringsserie för analyser via Analytics-källkopplingen |
| --- |
| `eVar1` => Kundkategori |

| Datauppsättning B = Uppgifter om kundtjänst |
| --- |
| Some_field => Kundkategori |

Med Data Prep kan du kombinera kundkategorin i eVar 1 i Analytics-data med kundkategorin i fältet Some_field i call center-data. Här är ett sätt du kan göra det på. Återigen kan namnkonventionen ändras efter dina behov.

1. Skapa ett schema i Adobe Experience Platform. Lägg till följande i schemat:

   | &quot;Utökat schema&quot; |
   | --- |
   | Klassen **XDM Experience Event** |
   | **Adobe Analytics Experience Event Template** - fältgrupp |

1. Skapa en ny fältgrupp och lägg till den i schemat. Lägg till fält i fältgruppen:

   | Anpassad fältgrupp &quot;Kundinformation&quot;  |
   | --- |
   | Customer_category |

1. Skapa dataflödet för **datauppsättning A** och välj **Utökat schema** som ditt schema. Lägg till anpassade mappningar i dataflödet enligt följande:

   | Datamängd Ett källfält | Målfält från fältgruppen Kundinformation |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;sökväg>_.Customer_category |

1. Skapa dataflödet för **datauppsättningen B** och välj **Utökat schema** som ditt schema igen. Lägg till anpassade mappningar i dataflödet enligt följande:

   | Källfält för datauppsättning B | Målfält från fältgruppen Kundinformation |
   | --- | --- |
   | _\&lt;sökväg>_.Some_field | _\&lt;sökväg>_.Customer_category |

1. Skapa en Customer Journey Analytics-anslutning som kombinerar datauppsättning A och datauppsättning B.

1. Skapa en datavy i Customer Journey Analytics med den Customer Journey Analytics-anslutning du just skapade. Ignorera de ursprungliga eVar-fälten och ta endast med fälten från fältgruppen Kundinformation.

   Datavy i Customer Journey Analytics:

   | Source | Vill du inkludera i datavyn? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nej |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nej |
   | _\&lt;sökväg>_.Customer_category | Ja |

## Data Prep vs. komponent-ID

Som beskrivits ovan kan du med Data Prep mappa olika fält till flera Adobe Analytics-rapportsviter. Detta är praktiskt i Customer Journey Analytics när du vill kombinera data från flera datauppsättningar till en enda Customer Journey Analytics-anslutning. Om du tänker behålla rapportsviterna i separata Customer Journey Analytics-anslutningar men vill använda en uppsättning rapporter för alla anslutningar och datavyer, kan du göra rapporter kompatibla genom att ändra det underliggande komponent-ID:t i Customer Journey Analytics, även om scheman är olika. Mer information finns i [Komponentinställningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html).

Att ändra komponent-ID:t är en funktion som endast är Customer Journey Analytics och påverkar inte data från Analytics-källkopplingen som skickas till kundprofilen i realtid och RTCDP.
