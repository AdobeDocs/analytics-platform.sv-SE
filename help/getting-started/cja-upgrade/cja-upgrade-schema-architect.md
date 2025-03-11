---
title: Skapa ett schema som kan användas med Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---

# Skapa ett schema som kan användas med Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Arkitekt a schema"
>abstract="Diskutera behovet av datainsamling inom organisationen och fastställ hur du vill skapa ett schema för användning i Adobe Experience Platform. Det här steget visas eftersom du vill använda den rekommenderade processen att använda ett schema som är anpassat till din organisation. Att utföra det här steget korrekt är avgörande eftersom ett schema som alla team i organisationen anpassar sig efter gör det betydligt enklare att få in data.<br><br>Den beräknade tiden för att sammanföra alla relevanta parter i organisationen så att de följer ett enhetligt schema är 1-2 månader. Den här tidsramen är mycket beroende av hur många team som behövs för att samordna och hur många dimensioner + mått som ska justeras efter."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe rekommenderar att du skapar ett anpassat XDM-schema (Experience Data Model) som kan användas med Web SDK när du uppgraderar från Adobe Analytics till Customer Journey Analytics. Du kan också använda Adobe Analytics standardschema, som använder fältgruppen Adobe Analytics ExperienceEvent.

Ett anpassat XDM-schema möjliggör ett smidigt schema som är anpassat efter organisationens behov och de plattformsspecifika program som du använder. Till skillnad från det Adobe Analytics-standardschema som använder fältgruppen Adobe Analytics ExperienceEvent behöver du inte gå igenom tusentals oanvända fält för att hitta det fält som behöver uppdateras när du behöver ändra ett anpassat XDM-schema.

Mer information om de här schemaalternativen finns i [Välja schema för Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

Granska följande avsnitt när du börjar skapa XDM-schemat.

## Undvik Adobe Analytics-begränsningar i XDM-schemat

Customer Journey Analytics underliggande arkitektur ger mycket större flexibilitet än Adobe Analytics. Att skapa ett nytt XDM-schema är ett viktigt sätt att låsa upp den flexibiliteten. När du uppgraderar till Customer Journey Analytics bör du se till att du inte överför onödiga Adobe Analytics-begränsningar till ditt schema.

>[!NOTE]
>
>Följande information är inte fullständig ännu. Den kommer att vara fullständig inom den närmaste framtiden.

| Adobe Analytics dataarkitektur | XDM-schemaarkitektur |
|---------|----------|
| Enskilda mätvärden läggs till i Analytics-dataarkitekturen.<br/>I Adobe Analytics har du till exempel olika eVar för varje händelse. | Skapa enskilda mått i datavyn i stället för i XDM-schemat. Det ger större flexibilitet om du behöver göra ändringar vid ett senare tillfälle.<br/>I Customer Journey Analytics har du till exempel en enda händelse i schemat och använder create-händelser i datavyn. |
| Props och eVars krävs för att skapa anpassade variabler. |  |

## Identifiera ert datateam och andra intressenter i hela organisationen

>[!NOTE]
>
>Den här informationen är inte tillgänglig än. Den kommer att finnas tillgänglig inom den närmaste framtiden.

## Överväg andra Adobe Experience Platform-program som används i er organisation

>[!NOTE]
>
>Den här informationen är inte tillgänglig än. Den kommer att finnas tillgänglig inom den närmaste framtiden.
