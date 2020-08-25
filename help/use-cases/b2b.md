---
title: (B2B) Lägg till kontonivådata som en uppslagsuppdatamängd
description: Lär dig hur du lägger till kontobaserade data som en uppslagsdatamängd till CJA
translation-type: tm+mt
source-git-commit: de5717d42fbe29554351a789cce594ac9ad47ee1
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 0%

---


# (B2B) Lägg till kontonivådata som en uppslagsuppdatamängd

Detta B2B-användningsfall visar hur du anger dina data på kontonivå i stället för på personnivå för analys. Kontoanalys kan besvara frågor som t.ex.

* Vilket företagsnamn matchas med det här kontot?
* Hur många anställda är associerade med det här kontot/företaget?
* Vilka roller är representerade på det här kontot?
* Hur fungerar detta konto i sin helhet med avseende på en specifik marknadsföringskampanj jämfört med ett annat konto?
* Är vissa roller (t.ex. IT Manager) på ett konto annorlunda än samma roll på ett annat konto?

Du gör allt detta genom att ta med informationen på kontonivå som en [sökning](/help/getting-started/cja-glossary.md) datamängd (liknande klassificeringar i traditionell Adobe Analytics).

Du skapar först ett uppslagsschema i Adobe Experience Platform och skapar sedan en uppsättning av uppslagstabelldata genom att mata in .csv-baserade kontodata. Sedan fortsätter du för att skapa en anslutning-CJA som kombinerar olika datauppsättningar, inklusive den sökning som du skapade. Sedan skapar du en datavy och kan slutligen använda alla dessa data på arbetsytan.

>[!NOTE]
>
>Uppslagstabeller kan vara upp till 1 GB i storlek.

## 1 Skapa uppslagsschema (Experience Platform)

Skapa ett eget schema för [sökning](/help/getting-started/cja-glossary.md) tabellen ser till att den datamängd som används är tillgänglig i CJA med rätt inställning (posttyp). Bästa praxis är att [skapa en anpassad schemaklass](https://docs.adobe.com/content/help/en/experience-platform/xdm/tutorials/create-schema-ui.html#create-new-class) Kallas &quot;Uppslag&quot;, tomt för valfritt element, som kan återanvändas för alla uppslagstabeller.

![](assets/create-new-class.png)

## 2 Skapa uppsättningen med uppslagsdata (Experience Platform)

När schemat har skapats måste du skapa en uppslagsdatauppsättning från det schemat i Experience Platform. Den här uppslagsuppsättningen innehåller marknadsföringsinformation på kontonivå, t.ex.: Företagsnamn, totalt antal anställda, domännamn, vilken bransch de tillhör, årliga intäkter, vare sig de är nuvarande kunder i Experience Platform eller inte, vilket försäljningsstadium de befinner sig i, vilket team på kontot använder CJA osv.

>[!IMPORTANT]
>
>CJA stöder inte heltal i uppslagsdatauppsättningar. Om du lägger till heltalsfälten i XDM-schemat för uppslagsdatauppsättningen kan du inte använda dessa heltal som mått eller beräknade mått. Om exempelvis annualRevenue eller TotalEmployees definieras som heltal visas de som &quot;0&quot; vid rapportering i CJA. Om du däremot tilldelar dem som strängar kan du använda dem som uppslagsinformation.

Exempelvis definieras annualRevenue eller totalEmployees som heltal i följande exempel, det är anledningen till att den visar &quot;0&quot; i CJA.

1. Gå till Adobe Experience Platform **[!UICONTROL Data Management > Datasets]**.
1. Klicka på **[!UICONTROL + Create dataset]**.
1. Klicka på **[!UICONTROL Create dataset from schema]**.
1. Välj klassen Lookup Schema som du har skapat.
1. Klicka på **[!UICONTROL Next]**.
1. Ge datamängden ett namn (i vårt exempel B2B Info) och ge en beskrivning.
1. Klicka på **[!UICONTROL Finish]**.

## 3 Ingest-data från Experience Platform

Instruktioner för hur du ska [Koppla en CSV-fil till ett XDM-schema](https://docs.adobe.com/content/help/en/experience-platform/ingestion/tutorials/map-a-csv-file.html) bör vara till hjälp om du använder en CSV-fil.

[Andra metoder](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html) finns också tillgängliga.

Det tar cirka 2 till 4 timmar att gå ombord på data och att konfigurera sökningen, beroende på storleken på uppslagstabellen.

## 4 Kombinera datauppsättningar i en anslutning (Customer Journey Analytics)

I det här exemplet kombinerar vi tre datauppsättningar till en CJA-anslutning:

| Datauppsättningsnamn | Beskrivning | AEP-schemaklass | Datauppsättningsinformation |
|---|---|---|---|
| B2B-komprimering | Innehåller data på kontonivå för klickström, händelsenivå. Den innehåller t.ex. e-post-ID och motsvarande konto-ID samt marknadsföringsnamn för att köra marknadsföringsannonser. Den innehåller även intryck för annonserna, per användare. | Baserat på schemaklassen XDM ExperienceEvent | De `emailID` används som primär identitet och tilldelas en `Customer ID` namnområde. Som ett resultat av detta visas den som standard **[!UICONTROL Person ID]** i Customer Journey Analytics. ![Impression](assets/impressions-mixins.png) |
| B2B-profil | Den här profildatamängden ger dig mer information om användarna i ett konto, till exempel deras jobbtitel, vilket konto de tillhör, deras LinkedIn-profil osv. | Baserat på schemaklassen XDM-individuell profil | Du behöver inte välja `emailID` som primärt ID i det här schemat. Se till att aktivera **[!UICONTROL Profile]**; Om du inte gör det kommer inte CJA att kunna ansluta `emailID` i B2B-profilen med `emailID` i B2B-data om intryckning. (Denna funktion kallas fältbaserad sömnad.) ![Profil](assets/profile-mixins.png) |
| B2B-info | Se &quot;Skapa uppsättningen sökdata&quot; ovan. | B2BAccount (anpassad sökschemaklass) | Förhållandet mellan `accountID` och datauppsättningen B2B Impression har skapats automatiskt genom att datauppsättningen B2B Info ansluts till datauppsättningen B2B Impression i CJA, enligt beskrivningen i stegen nedan. ![Uppslag](assets/lookup-mixins.png) |

Så här kombinerar du datauppsättningarna:

1. I Customer Journey Analytics väljer du **[!UICONTROL Connections]** flik.
1. Markera de datauppsättningar (i vårt exempel de tre ovan) som du vill kombinera.
1. För datamängden B2B-info väljer du `accountID` nyckel som ska användas i uppslagstabellen. Välj sedan dess matchande nyckel (motsvarande dimension), även `accountID` i din händelsedatamängd.
1. Klicka på **[!UICONTROL Next]**.
1. Namnge och beskriv anslutningen och konfigurera den enligt [dessa instruktioner](/help/connections/create-connection.md).
1. Klicka på **[!UICONTROL Save]**.

## 5 Skapa en datavy från den här anslutningen

Följ instruktionerna på [skapa datavyer](/help/data-views/create-dataview.md).

* Lägg till alla komponenter (mått och mått) som du behöver från datauppsättningarna.

## 6 Analysera data på arbetsytan

Du kan nu skapa arbetsyteprojekt baserat på data från alla tre datauppsättningarna.

Du kan till exempel hitta svar på svaren i inledningen:

* Bryt ned e-post-ID:t med konto-ID för att ta reda på vilket företag ett e-post-ID tillhör.
* Hur många anställda mappas till ett specifikt konto-ID?
* Vilken bransch tillhör ett konto-ID?

![](assets/project-lookup.png)
