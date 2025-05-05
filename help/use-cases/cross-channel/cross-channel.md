---
title: Reseanalys över flera kanaler
description: Analysera och extrahera insikter från kundinteraktioner under hela kundresan.
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Flerkanalsanalys {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-additional-datasets"
>title="Lägg till ytterligare datauppsättningar i anslutningen"
>abstract="När du har lagt till data i en datauppsättning i Adobe Experience Platform kan du lägga till datauppsättningen i anslutningen i Customer Journey Analytics. När du lägger till data från andra kanaler måste du se till att de följer det schema som din organisation använder.<br><br>Varje datauppsättning som du lägger till kräver en enorm mängd arbete, särskilt när det gäller att säkerställa att den unika identifieraren finns för varje händelse och att den övergripande datastrukturen följer organisationens anpassade schema. Om du skapar det här arbetsflödet kan det ta samordningen mellan många team inom organisationen att spridas över flera månader."

<!-- markdownlint-enable MD034 -->

Flerkanalsanalys ger en samlad bild av kundernas beteende i olika kanaler genom att sammanföra data från olika webb-, mobil- och offlineegenskaper. Ni kan till exempel använda den här konsoliderade vyn för att analysera kundinteraktioner på både dator och mobil för att förstå kundbeteenden och få insikter för att optimera digitala kundupplevelser. Ni kan också analysera kundinteraktioner över alla kanaler, inklusive digitala och offlinekanaler som supportinteraktioner och köp i butiken, för att bättre förstå och optimera kundresan.

## Implementeringssteg

![Flöde för implementeringssteg enligt beskrivningen i det här avsnittet.](../assets/cca-architecture.png)

1. [Skapa scheman](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=sv-SE) för data som ska importeras.
1. [Skapa datauppsättningar](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html?lang=sv-SE) för data som ska importeras.
1. [Infoga data i Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html?lang=sv-SE):
   1. Händelsebaserad ![datahändelse](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg) från webbplats eller mobilapp via Edge Network- eller Analytics-källkopplingen.
   2. Profildata ![profil](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg) (till exempel från ett CRM-system, ett callcenter-program, ett lojalitetsprogram).
   3. Uppslagsdata ![uppslag](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) (t.ex. produktnamn, kategori från ett produktinformationssystem).

1. Använd ett gemensamt namnområdes-ID för alla datauppsättningar. Använd [Stitching](../../stitching/overview.md) för att höja upp händelsebaserade datauppsättningar ![datauppdateringar](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg) för att ange ett gemensamt ID för varje rad. Observera att Customer Journey Analytics för närvarande inte använder Experience Platform profil- eller identitetstjänster för sammanfogning.
1. Utför alla anpassade dataförberedelser för att säkerställa en gemensam nyckel över tidsseriedatauppsättningar som ska importeras till Customer Journey Analytics.
1. Ge sökdata ett primärt ID som kan kopplas till ett fält i händelsedata. Räknas som rader i licensiering.
1. Ange samma primära ID för profildata som det primära ID:t för händelsedata.
1. [Skapa en anslutning](../../connections/overview.md) för att importera relevanta datauppsättningar från Experience Platform till Customer Journey Analytics.
1. [Skapa en datavy](/help/data-views/create-dataview.md) på anslutningen för att välja de dimensioner och mått som ska inkluderas i vyn. Attribution- och allokeringsinställningar konfigureras också i datavyn. Dessa inställningar beräknas vid rapporttillfället.
1. [Skapa ett projekt](/help/analysis-workspace/home.md) för att konfigurera instrumentpaneler och rapporter i Analysis Workspace.

## Överväganden

När du skapar det här arbetsflödet bör du tänka på följande.

* För att kunna analysera data över flera kanaler krävs samma ID-namnutrymme för alla poster.
* Unionsprocessen för att sammanfoga olika datauppsättningar kräver en gemensam primärnyckel för personen/enheten i alla datauppsättningar.
* Sekundära nyckelbaserade föreningar stöds för närvarande inte.
* Häftningsprocessen gör det möjligt att skriva in identiteter på nytt i rader baserat på kortvarig ID-information (t.ex. ett autentiserings-ID) från poster som delar samma beständiga ID. Detta gör att olika poster kan matchas till ett sammanfogat ID för analys på personnivå, i stället för på enhets- eller cookienivå.
* Objekt och attribut i samma XDM-fält sammanfogas till en dimension i Customer Journey Analytics. Om du vill sammanfoga flera attribut från olika datauppsättningar till samma Customer Journey Analytics-dimension, ska datauppsättningarna referera till samma XDM-fält eller -schema.

