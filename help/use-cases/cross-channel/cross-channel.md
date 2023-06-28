---
title: Reseanalys över flera kanaler
description: Analysera och extrahera insikter från kundinteraktioner under hela kundresan.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: cf6da1f126933f17e05fb458f52dff93c1601891
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 0%

---

# Flerkanalsanalys

Flerkanalsanalys ger en samlad bild av kundernas beteende i olika kanaler genom att sammanföra data från olika webb-, mobil- och offlineegenskaper. Du kan till exempel använda den här konsoliderade vyn för att analysera kundinteraktioner på både dator och mobil för att förstå kundbeteendet och få insikter för att optimera digitala kundupplevelser. Ni kan också analysera kundinteraktioner över alla kanaler, inklusive digitala och offlinekanaler som supportinteraktioner och köp i butiken, för att bättre förstå och optimera kundresan.

## Arbetsflöde

![Flerkanalsarkitektur](../assets/cca-architecture.png)

## Implementeringssteg

1. [Skapa scheman](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html) för data som ska importeras.
1. [Skapa datauppsättningar](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) för data som ska importeras.
1. [Infoga data i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html):
   1. Händelsebaserade data ![event](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) från webbplats eller mobilapp via Edge Network eller Analytics Data Connector.
   2. Profildata ![profil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (t.ex. från ett CRM-system, callcenter-program, lojalitetsprogram).
   3. Sökdata ![sökning](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (t.ex. produktnamn, kategori från ett produktinformationssystem).

1. Använd ett gemensamt namnområdes-ID för alla datauppsättningar. Använd [Stitlar](../../stitching/overview.md) för att lyfta fram händelsebaserade datauppsättningar ![datauppdatering](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) när det gäller att tillhandahålla ett gemensamt ID på varje rad. Observera att Customer Journey Analytics för närvarande inte använder profiltjänsten eller identitetstjänsten Experience Platform för sammanfogning.
1. Utför alla anpassade dataförberedelser för att säkerställa en gemensam nyckel över tidsseriens datauppsättningar som ska importeras till Customer Journey Analytics.
1. Ge sökdata ett primärt ID som kan kopplas till ett fält i händelsedata. Räknas som rader i licensiering.
1. Ange samma primära ID för profildata som det primära ID:t för händelsedata.
1. [Skapa en anslutning](../../connections/overview.md) att importera relevanta datauppsättningar från Experience Platform till Customer Journey Analytics.
1. [Skapa en datavy](/help/data-views/create-dataview.md) på anslutningen för att välja de mått och mått som ska inkluderas i vyn. Attribution- och allokeringsinställningar konfigureras också i datavyn. Dessa inställningar beräknas vid rapporttillfället.
1. [Skapa ett projekt](/help/analysis-workspace/home.md) för att konfigurera kontrollpaneler och rapporter i Analysis Workspace.

## Överväganden

När du skapar det här arbetsflödet bör du tänka på följande.

* För att kunna analysera data över flera kanaler krävs samma ID-namnutrymme för alla poster.
* Unionsprocessen för att sammanfoga olika datauppsättningar kräver en gemensam primärnyckel för personen/enheten i alla datauppsättningar.
* Sekundära nyckelbaserade föreningar stöds för närvarande inte.
* Häftningsprocessen gör det möjligt att skriva in identiteter på nytt i rader baserat på efterföljande tillfälliga ID-poster, till exempel ett autentiserings-ID. Detta gör det möjligt att lösa olika poster till ett enda ID för analys på personnivå i stället för på enhets- eller cookienivå.
* Objekt och attribut i samma XDM-fält sammanfogas till en dimension i Customer Journey Analytics. Om du vill sammanfoga flera attribut från olika datauppsättningar till samma Customer Journey Analytics-dimension, ska datauppsättningarna referera till samma XDM-fält eller -schema.

