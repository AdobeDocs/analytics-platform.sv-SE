---
title: Användningsexempel vid dataexport
description: Förstå olika dataexportanvändningsområden för Customer Journey Analytics
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
exl-id: 8b9c164e-01da-4b43-8e2c-99904223cae5
source-git-commit: 40e4c3bd8f3c37e9a6143200b85ffe0ac4bcb2ca
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 0%

---

# Användningsexempel vid dataexport

I det här avsnittet finns exempel på dataexportanvändning och hur du implementerar dessa användningsfall med en eller flera funktioner i Customer Journey Analytics eller Experience Platform. Varje funktion beskrivs närmare i en separat artikel.

## Introduktion

En av de unika skillnaderna mellan Adobe Analytics och Customer Journey Analytics har att göra med behandlingen av data för attribuering och sessioner. Mer information finns i [Jämför databearbetning i Adobe Analytics och Customer Journey Analytics](/help/getting-started/aa-vs-cja/data-processing-comparisons.md).

### Adobe Analytics: tidsattribuering och sessioner.

I Adobe Analytics bearbetas alla händelser live och i ordning efter enhets-ID, vilket gör att Adobe kan generera, lagra och exportera klickströmsdata med beständiga eller tilldelade värden vid insamlingen, inklusive:

* Varaktighet i Dimension (t.ex. kampanjspårningskoder som upphör efter 90 dagar).
* Besök nummer och sessioner.
* Dimensioner, beräknade enligt behandlings- och VISTA-regler.

Detta påverkar exporten av data från Adobe Analytics:

* Databearbetningen är statisk efter den första insamlingen.
* Dataflödena innehåller&quot;post&quot;-kolumner, som avspeglar insamlingstidens bearbetning.


### Customer Journey Analytics: attribuering och sessioner vid frågetiden

I Customer Journey Analytics samlas inte händelser in i ordning och ett person-ID används i stället för ett enhets-ID, vilket gör att Customer Journey Analytics kan uppdatera attribuering och sessioner vid rapporttidpunkten. Den här typen av datainsamling ger flexibilitet, som:

* Stitching kan _spela upp_ data varje dag eller vecka, och associera anonyma händelser med kända händelser. Mer information finns i [Stitching](../../stitching/overview.md).
* Sessionen och beständiga värden ändras varje gång
   * nya data samlas in eller
   * häftning lägger till händelser i en persons historia.

Bearbetningen under rapporttiden påverkar exporten av data från Customer Journey Analytics. Exporter som innehåller beständiga värden kommer inte att matcha Customer Journey Analytics-rapporter och värdena kommer att försvinna över tiden.

För att mätvärdena ska bli enhetliga bör du använda de nya funktionerna i Customer Journey Analytics. I allmänhet överskrider dataexportfunktionen för Experience Platform och Customer Journey Analytics Adobe Analytics dataflöde-funktionaliteten. Experience Platform och Customer Journey Analytics tillhandahåller:

* nya datakällor och bearbetning som omfattas av dataexport

   * innehåller icke-digitala datakällor,
   * tillämpa anpassad attribuering och sessioner baserat på affärsregler, och
   * hålla kundresorna uppdaterade med sammanfogning.

* implementering av skräddarsydda dataexportanvändningsfall

   * exportera data dit ni behöver dem, inklusive Business Intelligence-verktyg (BI) och molndestinationer,
   * synkronisera data med Analysis Workspace via BI-verktyg,
   * behöver inte replikera bearbetningslogiken i era egna system,
   * nytt stöd för beräknade mätvärden, härledda fält och segmentering, och

* bedömning av säkerhet och datastyrning utifrån design

   * övervaka all dataexport per användare och destination,
   * ange gränser för vilka data som är tillgängliga för export, och
   * ange aviseringar om leveransproblem och begränsningar för schemalagda leveransfönster.


## Användningsfall och -funktioner

Vanligtvis stöder dataexport ett antal användningsfall. Varje användningsfall skiljer sig åt när det gäller vilka data som krävs och hur dessa ska hämtas och exporteras. Experience Platform och Customer Journey Analytics tillhandahåller ett antal funktioner som kan lösa de olika användningsområdena, antingen separat eller tillsammans. Tabellen nedan ger en översikt över användningsområdena för dataexport och Experience Platform och Customer Journey Analytics för att implementera dessa användningsfall.

| Användningsexempel vid dataexport | Funktioner för Experience Platform och Customer Journey Analytics |
|---|---|
| **Säkerhetskopiera data**<br/> Behåll en fullständig kopia av dina digitala data för att uppfylla eller följa lagar och förordningar. | **Experience Platform**: [**Exportera datauppsättningar**](export-datasets.md)<br/> Exportera data som samlats in i Experience Platform direkt till molnmål enligt ett schema eller ad hoc.<br/>*För närvarande begränsad version, fullständig version för Customer Journey Analytics-kunder förväntas bli klar i juni 2024.* |
| **Dataverifiering**<br/> Utvärdera klickströmsdata för korrekt datainsamling. | **Experience Platform**: [**Query Service (Data Distiller) &amp; Export datasets**](queryservice-export-datasets.md)<br/> Interactive PostgreSQL interface to execute ad hoc SQL queries using your favorite SQL tool to validate the data in your datasets.<br/><br/>**Customer Journey Analytics**: [**Exportera hela tabellen**](export-full-table.md)<br/> Verifiera bearbetade data från CJA med attribut och sessioner. |
| **Data Lake-, Data Warehouse- eller BI-verktyg**<br/> Använd digitala data i dina egna BI-verktyg eller Data Lake för användning med ytterligare datauppsättningar. | **Customer Journey Analytics**: [**BI-tillägg**](bi-extension.md)<br/> Lägg till Customer Journey Analytics-bearbetade mått i datavisualiseringsverktyg som Power BI och kombinera med ytterligare data för anpassade rapporter <br/><br/>**Experience Platform**: [**Frågetjänst (Data Distiller) och exportdatamängder**](queryservice-export-datasets.md)<br> Generera anpassade klickströmsdata med SQL som ska levereras till molnmål. |
| **Beredskap för AI/ML**<br/> Förbättra artificiell intelligens/Maskinininlärningsmodeller och uppgifter med data från Customer Journey Analytics. | **Customer Journey Analytics**: [**Exportera hela tabellen**](export-full-table.md)<br/> Exportera bearbetade mått och mått för Customer Journey Analytics till molnmål en gång eller återkommande, inklusive beräknade värden och segmentering.<br/><br/>**Experience Platform**: [**Query Service (Data Distiller) och Export datasets**](queryservice-export-datasets.md)<br/> Generera anpassade klickströmsdata med SQL för att utöka AI-/ML-modeller. |
