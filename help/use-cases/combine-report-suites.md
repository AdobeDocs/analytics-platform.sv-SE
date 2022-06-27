---
title: Kombinera rapportsviter med olika scheman
description: Lär dig hur du använder Data Prep för att kombinera rapportsviter med olika scheman
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '1335'
ht-degree: 1%

---

# Kombinera rapportsviter med olika scheman

The [Källanslutning för analyser](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) lägger in data från Adobe Analytics i Adobe Experience Platform (AEP) för användning i AEP-program som Real-time Customer Data Platform och Customer Journey Analytics (CJA). Varje rapportsvit som hämtas till AEP konfigureras som ett enskilt källanslutningsdataflöde, och varje dataflöde markeras som en datauppsättning i AEP-datasjön. Analyskällans koppling skapar en datauppsättning per rapportserie.

CJA-kunder använder [anslutningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en) att integrera datauppsättningar från AEP Data Lake i CJA:s Analysis Workspace. När du kombinerar rapportsviter i en anslutning måste schemaskillnaderna mellan rapportsviterna dock lösas med hjälp av AEP:s [Dataprep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) funktionalitet. Syftet är att säkerställa att Adobe Analytics-variabler som props och eVars har en konsekvent innebörd i CJA.

## Schemaskillnader mellan rapportsviter är problematiska

Anta att ditt företag vill överföra data från två olika rapportsviter till AEP för CJA, och anta att scheman för de två rapportsviterna är olika:

| Report Suite A | Report Suite B |
| --- | --- |
| eVar1 = Sökord | eVar1 = Affärsenhet |
| eVar2 = Kundkategori | eVar2 = Sökord |

För enkelhetens skull, låt oss säga att det här är de enda definierade eVars för båda rapportsviterna.

Anta dessutom att du utför följande åtgärder:

- Skapa en anslutning till en Analytics-källa (utan att använda dataförberedelse) som importerar **Report Suite A** till AEP-datasjön som **Datauppsättning A**.
- Skapa en anslutning till en Analytics-källa (utan att använda dataförberedelse) som importerar **Report Suite B** till AEP-datasjön som **Datauppsättning B**.
- Skapa en [CJA-anslutning](/help/connections/create-connection.md) anropad **Alla rapportsviter** som kombinerar datauppsättning A och datauppsättning B.
- Skapa en [CJA-datavy](/help/data-views/create-dataview.md) anropad **Global vy** som baseras på anslutningen Alla rapportsviter.

Utan att använda Data Prep för att lösa schemaskillnaderna mellan datauppsättning A och datauppsättning B kommer eVarorna i datavyn i den globala vyn att innehålla en blandning av värden:

| Datavyn Global vy i CJA |
| --- |
| eVar1 => en blandning av söktermer och affärsenheter |
| eVar2 => en blandning av kundkategorier och söktermer |

Detta resulterar i meningslösa rapporter för eVar1 och eVar2:

- eVar innehåller en blandning av värden med olika semantiska betydelser.
- Sökvillkoren fördelas mellan eVar1 och eVar2.
- Det går inte att använda olika attribueringsmodeller för varje sökterm, affärsenhet eller kundkategori.

## Använd AEP Data Prep för att lösa schemaskillnader mellan rapportsviter

Funktionen Experience Platform Data Prep är integrerad med Analytics Source Connector och kan användas för att lösa de schemaskillnader som beskrivs i scenariot ovan. Detta resulterar i eVars med enhetlig betydelse i CJA-datavyn. (Namnkonventionerna nedan kan anpassas efter dina behov.)

1. Innan du skapar källanslutningsdataflöden för Report Suite A och Report Suite B, [Skapa ett nytt schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) i AEP (vi kallar det **Enhetligt schema** i vårt exempel.) Lägg till följande i schemat:

   | &quot;Enhetligt schema&quot; |
   | --- |
   | **XDM ExperienceEvent** class |
   | **Adobe Analytics ExperienceEvent-mall** fältgrupp |

1. Lägg till en annan fältgrupp till schemat eller [skapa en anpassad fältgrupp](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) och lägg till det i schemat. Vi skapar en ny fältgrupp och kallar den **Enhetliga fält**. Sedan lägger vi till följande fält i den nya fältgruppen:

   | Anpassad fältgrupp &quot;Enhetliga fält&quot;  |
   | --- |
   | Sökterm |
   | Affärsenhet |
   | Kategori |

1. Skapa källanslutningsdataflöde för **Report Suite A**, markera **Enhetligt schema** för användning i dataflödet. Lägg till anpassade mappningar i dataflödet enligt följande:

   | Report Suite A source field | Målfält från fältgruppen Enhetliga fält |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Search_term |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

   >[!NOTE]
   >
   >XDM-sökvägen för målfälten beror på hur du strukturerar den anpassade fältgruppen.

1. Skapa källanslutningsdataflöde för **Report Suite B** väljer **Enhetligt schema** för användning i dataflödet. Arbetsflödet visar att två fält har en konflikt med ett beskrivningsnamn. Detta beror på att beskrivningarna för eVar1 och eVar2 skiljer sig åt i Report Suite B jämfört med dem i Report Suite A. Men vi vet redan detta, så vi kan ignorera konflikten och använda anpassade mappningar enligt följande:

   | Källfält för Report Suite B | Målfält från fältgruppen Enhetliga fält |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\&lt;path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Search_term |

1. Skapa **Alla rapportsviter** anslutning för CJA, som kombinerar datauppsättning A och datauppsättning B.

1. Skapa en **Global vy** datavy i CJA. Ignorera de ursprungliga fälten och ta endast med eVar från fältgruppen Enhetliga fält.

   **Global vy** datavy i CJA:

   | Källfält | Vill du inkludera i datavyn? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nej |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nej |
   | _\&lt;path>_.Search_term | Ja |
   | _\&lt;path>_.Customer_category  | Ja |
   | _\&lt;path>_.Business_unit | Ja |

Du har nu mappat eVar1 och eVar2 från källrapportsviterna till tre nya fält. Observera att en annan fördel med att använda Data Prep-mappningar är att målfälten nu baseras på semantiskt meningsfulla namn (sökterm, affärsenhet, kundkategori) i stället för de mindre meningsfulla eVar (eVar1, eVar2).

>[!NOTE]
>
>Den anpassade fältgruppen Enhetliga fält och tillhörande fältmappningar kan när som helst läggas till i befintliga analysrelaterade källanslutningsdata och datauppsättningar. Detta påverkar dock endast data som skickas vidare.

## Mer än bara rapportsviter

Funktionerna hos Data Prep för att kombinera datauppsättningar med olika scheman går utöver rapportsviterna i Analytics. Anta att du har två datauppsättningar som innehåller följande data:

| Datauppsättning A = Rapporteringsserie för analyser via Analytics Source Connector |
| --- |
| `eVar1` => Kundkategori |

| Datauppsättning B = Uppgifter om kundtjänst |
| --- |
| Some_field => Kundkategori |

Med hjälp av Data Prep kan du kombinera kundkategorin i eVar 1 i Analytics-data med kundkategorin i fältet Some_field i call center-data. Här är ett sätt du kan göra det på. Återigen kan namnkonventionen ändras efter dina behov.

1. Skapa ett schema i AEP. Lägg till följande i schemat:

   | &quot;Utökat schema&quot; |
   | --- | 
   | **XDM Experience Event** class |
   | **Adobe Analytics Experience Event Template** fältgrupp |

1. Skapa en ny fältgrupp och lägg till den i schemat. Lägg till fält i fältgruppen:

   | Anpassad fältgrupp &quot;Kundinformation&quot;  |
   | --- |
   | Customer_category |

1. Skapa dataflöde för **Datauppsättning A**, markera **Utökat schema** som ditt schema. Lägg till anpassade mappningar i dataflödet enligt följande:

   | Datamängd Ett källfält | Målfält från fältgruppen Kundinformation |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\&lt;path>_.Customer_category |

1. Skapa dataflöde för **Datauppsättning B** väljer **Utökat schema** som ditt schema. Lägg till anpassade mappningar i dataflödet enligt följande:

   | Källfält för datauppsättning B | Målfält från fältgruppen Kundinformation |
   | --- | --- |
   | _\&lt;path>_.Vissa_fält | _\&lt;path>_.Customer_category |

1. Skapa en CJA-anslutning som kombinerar datauppsättning A och datauppsättning B.

1. Skapa en datavy i CJA med den CJA-anslutning du just skapade. Ignorera de ursprungliga fälten och ta endast med eVar från fältgruppen Kundinformation.

   Datavy i CJA:

   | Källfält | Vill du inkludera i datavyn? |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | Nej |
   | \_experience.analytics.customDimensions.eVars.eVar2 | Nej |
   | _\&lt;path>_.Customer_category | Ja |

## Data Prep vs. komponent-ID

Som beskrivits ovan kan du med Data Prep mappa olika fält till flera Adobe Analytics-rapportsviter. Detta är användbart i CJA när du vill kombinera data från flera datauppsättningar till en enda CJA-anslutning. Om du tänker behålla rapportsviterna i separata CJA-anslutningar men vill använda en uppsättning rapporter för alla anslutningar och datavyer, kan du göra rapporter kompatibla genom att ändra det underliggande komponent-ID:t i CJA, även om scheman är olika. Se [Komponentinställningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) för mer information.

Ändring av komponent-ID:t är en CJA-funktion och påverkar inte data från Analytics Source Connector som skickas till kundprofilen i realtid och RTCDP.
