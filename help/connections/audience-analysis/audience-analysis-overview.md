---
title: Målgruppsanalys - översikt
description: Läs om hur du analyserar målgrupper från RTCDP i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 1e962f52-6b56-4671-afea-d58dae67e8a8
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 1%

---

# Översikt över målgruppsanalys

>[!NOTE]
>
>Förstå skillnaden mellan målgruppsanalys och publikpublicering:
>
>* **Målgruppsanalys**: Gör att du kan importera målgruppsmedlemskapsdata från Experience Platform-profildatauppsättningar till en Customer Journey Analytics-anslutning.
>* **Målgruppspublicering**: Gör att du kan skapa och publicera målgrupper som identifieras i Customer Journey Analytics till Adobe Experience Platform för kundanpassning och personalisering. Mer information om målgruppspublicering finns i [Översikt över målgruppspublicering](/help/components/audiences/audiences-overview.md).

Med hjälp av målgruppsanalys kan ni importera målgruppsmedlemskapsdata från Experience Platform-profildatauppsättningar till en Customer Journey Analytics-anslutning. Publiken blir tillgänglig som nya dimensioner för användning i Analysis Workspace.

I följande diagram och tillhörande tabell visas hur en målgruppsanalyskonfiguration i Customer Journey Analytics gör Experience Platform målgruppsdata tillgängliga i Analysis Workspace:

![Översikt över målgruppsanalys](assets/audience-analysis-overview.png)

| Nummer | Funktion | Funktion |
|---------|----------|---------|
| 1 | Konfigurering av målgruppsanalys | Konfigurationsgränssnittet i Customer Journey Analytics används för att konfigurera målgruppsanalys. |
| 2 | Sandbox | Måste innehålla den profildatauppsättning som du vill lägga till i anslutningen. |
| 3 | Profildatamängd | Måste innehålla de målgruppsdata från Experience Platform som du vill analysera. Den här profildatauppsättningen läggs till i anslutningen som du väljer. |
| 4 | Kopplingsprincip | Sammanslagningsprincipen som är kopplad till de Experience Platform-målgrupper som du vill analysera. |
| 5 | Profildata | Profildata som är associerade med den sammanfogningsprincip som du väljer. Dessa data är tillgängliga i Experience Platform datamängder. |
| 6 | Ny datauppsättning för sökning | Innehåller egna namn för de nya målgruppsdimensionerna som skapas. <p>Uppslagsdatauppsättningen skapas automatiskt och läggs till i anslutningen tillsammans med den profildatauppsättning som du väljer.</p> |
| 7 | Anslutning | Anslutningen där du vill lägga till den valda profildatauppsättningen. |
| 8 | Nya målgruppsdimensioner | Nya målgruppsdimensioner <!--and metrics?--> som representerar de Experience Platform-målgrupper som ingår i den profildatauppsättning som du har valt och som är tillgängliga för rapportering i Analysis Workspace. Dessa dimensioner skapas automatiskt. |
| 9 | Datavyer | De datavyer som du väljer och som är kopplade till anslutningen. Detta är de datavyer som du vill använda när du analyserar Experience Platform målgruppsdata inom Analysis Workspace. Dessa datavyer konfigureras automatiskt med Experience Platform målgruppsdata för rapportering. |

## Konfigurera målgruppsanalys

När du konfigurerar målgruppsanalys väljer du den sandlåda och sammanfogningsprincip som är kopplad till de Experience Platform-målgrupper som du vill analysera. Customer Journey Analytics skapar en ny uppslagsdatauppsättning och lägger sedan automatiskt till uppslagsdatauppsättningen och profildatauppsättningen till den anslutning du väljer.

>[!IMPORTANT]
>
>Målgruppsdata bearbetas om och genereras varje kväll, vilket gör målgruppsdata korrekta för analys bara för föregående dag (&quot;igår&quot;).
>
>Målgrupperna är tillgängliga i Customer Journey Analytics datavyer dagen efter att du har skapat konfigurationen för målgruppsanalys.

Mer information finns i [Konfigurera målgruppsanalys](/help/connections/audience-analysis/audience-analysis-configure.md).

## Hantera konfigurationer för målgruppsanalys

Ni kan hantera konfigurationer för målgruppsanalys efter att de har skapats. Du kan visa, redigera och ta bort konfigurationer.

Information om hur du hanterar befintliga konfigurationer för målgruppsanalys finns i [Hantera konfigurationer för målgruppsanalys](/help/connections/audience-analysis/audience-analysis-manage.md).

## Analysera målgruppsdata i Customer Journey Analytics

Med målgruppsdata i Customer Journey Analytics kan ni få användbara insikter om hur målgruppsmedlemmarna beter sig i olika kanaler.

Du kan till exempel spåra beteendet hos enskilda kunder som ingick i samma e-postkampanj. Med målgruppen i Customer Journey Analytics kan du se följande typer av information om varje målgruppsmedlem:

* Klickningar från e-postmeddelandet till webbplatsen som till slut resulterade i ett köp

* Målgruppsmedlemmar som till slut gjorde ett butiksköp

Mer information finns i [Analysera Experience Platform-målgrupper i Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

## Målgruppsanalysroll och behörighetskrav

Följande Customer Journey Analytics-roller och Experience Platform-behörigheter krävs för målgruppsanalys:

| Funktion | Customer Journey Analytics roll- eller behörighetskrav | Experience Platform behörighetskrav |
|---------|----------|----------|
| [Skapa konfigurationer för målgruppsanalys](/help/connections/audience-analysis/audience-analysis-configure.md) | Systemadministratör | <ul><li>Datauppsättningar: Läsbehörigheter</li><li>Scheman: Läs, Skriv</li><li>Identitetsnamnutrymmen: Läs</li></ul> |
| [Visa målgruppsanalysdimensioner i datavyn](/help/connections/audience-analysis/audience-analysis-configure.md#view-audience-dimensions-in-the-data-view) | Produktprofiladministratör för den produktprofil som datavyn har tilldelats <p>Mer information finns i [Åtkomstkontroll](/help/technotes/access-control.md).</p> | Ej tillämpligt |
| Använd målgruppsanalysdimensioner i Analysis Workspace | Åtkomst till en datavy där målgruppsanalysdimensionerna lades till | Ej tillämpligt |

## Gränser för målgruppsanalys

Tänk på följande gränser när [målgruppsanalys](/help/connections/audience-analysis/audience-analysis-configure.md) konfigureras:

* En enda sandlåda har stöd för upp till 100 konfigurationer för målgruppsanalys.

* En anslutning kan bara kopplas till en målgruppsanalyskonfiguration.
