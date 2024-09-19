---
title: Lägg till kontodata som en uppslagsdatauppsättning
description: Lär dig hur du lägger till kontodata som en uppslagsdatauppsättning i Customer Journey Analytics
exl-id: d345f680-b657-4b87-9560-a50fc59bb7a7
solution: Customer Journey Analytics
feature: Use Cases
role: User
source-git-commit: cb47ac777958f6aaf26258d4aaed755b7657f36e
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 0%

---

# Lägg till kontodata som en uppslagsdatauppsättning

Det här användningsexemplet från B2B visar hur du lägger till kontodata i en person- och händelsenivåanalys. När du lägger till kontodata kan du svara på frågor som:

* Vilket företagsnamn matchas med det här kontot?
* Vilka roller visas i det här kontot?
* Beter sig vissa roller (t.ex. IT-chef) på ett konto annorlunda än samma roll på ett annat konto?

Om du vill lägga till kontodatainformation lägger du till och använder en [uppslagsuppsättning](/help/technotes/glossary.md) som innehåller den här informationen.

Följande steg ingår:

1. [Skapa ett sökschema](#create-lookup-schema) i Experience Platform.
1. [Skapa en uppslagsdatauppsättning](#create-lookup-dataset) i Experience Platform som gör att du kan importera CSV-baserade kontodata.
1. [Kombinera datauppsättningar i en anslutning](#combine-datasets-in-a-connection) i Customer Journey Analytics, inklusive den sökning som du skapade.
1. [Skapa en datavy](#create-a-data-view-from-this-connection) i Customer Journey Analytics.
1. [Analysera dessa data](#analyze-the-data-in-workspace) i Workspace i Customer Journey Analytics.

>[!NOTE]
>
>Uppslagstabeller kan vara upp till 1 GB stora.
>

## Skapa sökschema

När du skapar ett eget schema för tabellen [lookup](/help/technotes/glossary.md) ser det schemat till att den datauppsättning som används är tillgänglig i Customer Journey Analytics med rätt inställning (posttyp). Det bästa sättet är att [skapa en anpassad schemaklass](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui) som kan återanvändas för alla uppslagstabeller.

![Dialogrutan Skapa ny klass.](../assets/create-new-class.png)

## Skapa datauppsättning för sökning

När schemat har skapats måste du skapa en uppslagsdatauppsättning, baserat på det schemat, i Experience Platform. Den här uppsättningen uppslagsdata innehåller kontoinformationen. Exempel: företagsnamn, totalt antal anställda, domännamn, vilken bransch företaget tillhör, årsomsättning med mera. Se till att data innehåller en personidentifierare som kan matchas med den personidentifierare som används i händelsedata.

1. Gå till **[!UICONTROL Data Management > Datasets]** i Experience Platform.
1. Klicka på **[!UICONTROL + Create dataset]**.
1. Klicka på **[!UICONTROL Create dataset from schema]**.
1. Välj klassen Lookup Schema som du skapade.
1. Klicka på **[!UICONTROL Next]**.
1. Ge datauppsättningen ett namn (till exempel `B2B Info`) och ange en beskrivning.
1. Klicka på **[!UICONTROL Finish]**.

## Ingrediera data

Instruktioner om hur du [mappar en CSV-fil till ett XDM-schema](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) bör vara till hjälp om du använder en CSV-fil.

[Andra metoder](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/home) är också tillgängliga.

Det tar cirka 2 till 4 timmar att introducera data och upprätta sökningen, beroende på storleken på söktabellen.

## Kombinera datauppsättningar i en anslutning

I det här exemplet kombinerar du tre datauppsättningar i en anslutning mellan Customer Journey Analytics:

| Namn på datauppsättning | Beskrivning | Klassen Adobe Experience Platform Schema | Information om datauppsättning |
| --- | --- | --- | --- |
| B2B-komprimering | Innehåller klickströmsdata på händelsenivå på kontonivån. Den innehåller till exempel e-post-ID och motsvarande konto-ID samt marknadsföringsnamn för att köra marknadsföringsannonser. Det innehåller även visningar för dessa annonser per användare. | Baserat på schemaklassen XDM ExperienceEvent | `emailID` används som primär identitet och tilldelas ett `Customer ID`-namnutrymme. Därför visas den som standard **[!UICONTROL Person ID]** i Customer Journey Analytics. ![Impressions](../assets/impressions-mixins.png) |
| B2B-profil | Den här profildatauppsättningen ger dig mer information om användarna på ett konto, t.ex. deras jobbtitel, vilket konto de tillhör, deras LinkedIn-profil osv. | Baserat på schemaklassen XDM Individual Profile | Välj `emailID` som primärt ID i det här schemat. |
| B2B-information | Se&quot;Skapa uppslagsdatauppsättning&quot; ovan. | B2B-konto (anpassad sökschemaklass) | Relationen mellan `accountID` och datauppsättningen B2B-Impressions skapas automatiskt när du ansluter datauppsättningen B2B-information till datauppsättningen B2B-Impression i Customer Journey Analytics, vilket beskrivs i stegen nedan. ![Uppslag](../assets/lookup-mixins.png) |

Så här kombinerar du datauppsättningarna:

1. I Customer Journey Analytics väljer du fliken **[!UICONTROL Connections]**.
1. Markera de datauppsättningar som du vill kombinera.
1. För datauppsättningen B2B-information väljer du den nyckel som används i din uppslagstabell (till exempel `personKey.sourceKey`). Välj sedan dess matchande nyckel (motsvarande dimension), även i din händelsedatamängd (till exempel p`ersonKey.sourceKey`).
1. Klicka på **[!UICONTROL Next]**.
1. Namnge och beskriv anslutningen och konfigurera den enligt [dessa instruktioner](/help/connections/create-connection.md).
1. Klicka på **[!UICONTROL Save]**.

## Skapa en datavy från den här anslutningen

Följ instruktionerna på [skapa datavyer](/help/data-views/create-dataview.md).

* Lägg till alla komponenter (mått och mått) som du behöver från datauppsättningarna. Se till att du konfigurerar dessa mått utifrån detta för mätvärden som kräver borttagning av dubbletter för överräkning (se [Komponentinställningar för metrisk borttagning av dubbletter ](/help/data-views/component-settings/metric-deduplication.md)). Exempel på sådana mått är antalet anställda eller intäkterna.

## Analysera data i Workspace

Nu kan du skapa Workspace-projekt baserat på data från alla tre datauppsättningarna.

Du kan till exempel hitta svar på svaren i inledningen:

* Dela upp e-post-ID efter kontoID för att ta reda på vilket företag ett e-post-ID tillhör.
* Hur många anställda mappas till ett specifikt konto-ID?
* Vilken bransch tillhör ett konto-ID?

>[!MORELIKETHIS]
>
>Mer information finns i [Ett exempel på ett B2B-projekt](example.md).

