---
title: Översikt över målgruppsanalys
description: Läs om hur du analyserar målgrupper från RTCDP i Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 3654d452f2bc4fec5f53854307536b3b8679eac3
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 2%

---

# Översikt över målgruppsanalys

<!-- add hidden text in this article when this feature releases: /help/components/audiences/audiences-overview.md -->

>[!NOTE]
>
>Målgruppsanalys skiljer sig från målgruppspublicering, som gör att ni kan skapa och publicera målgrupper som identifieras i Customer Journey Analytics till Adobe Experience Platform för kundanpassning och personalisering. Mer information om målgruppspublicering finns i [Översikt över målgruppspublicering](/help/components/audiences/audiences-overview.md).

Med hjälp av målgruppsanalys kan ni importera målgruppsmedlemskapsdata från Experience Platform-profildatauppsättningar till en Customer Journey Analytics-anslutning. Publiken blir tillgänglig som nya dimensioner för användning i Analysis Workspace.

I följande diagram och tillhörande tabell visas hur en målgruppsanalyskonfiguration i Customer Journey Analytics gör målgruppsdata från Experience Platform tillgängliga i Analysis Workspace:

![Översikt över målgruppsanalys](assets/audience-analysis-overview.png)

| Nummer | Funktion | Funktion |
|---------|----------|---------|
| 1 | Konfigurering av målgruppsanalys | Konfigurationsgränssnittet i Customer Journey Analytics används för att konfigurera målgruppsanalys. |
| 2 | Sandbox | Måste innehålla den profildatauppsättning som du vill lägga till i anslutningen. |
| 3 | Profildatamängd | Måste innehålla de målgruppsdata från Experience Platform som du vill analysera. Den här profildatauppsättningen läggs till i anslutningen som du väljer. |
| 4 | Kopplingsprincip | Sammanslagningsprincipen som är kopplad till de Experience Platform-målgrupper som du vill analysera. |
| 5 | Profildata | Profildata som är associerade med den sammanfogningsprincip som du väljer. Dessa data är tillgängliga i Experience Platform datamängder. |
| 6 | Ny datauppsättning för sökning | Innehåller egna namn för de nya målgruppsdimensionerna som skapas. Uppslagsdatauppsättningen skapas automatiskt och läggs till i anslutningen tillsammans med den profildatauppsättning som du väljer. |
| 7 | Anslutning | Anslutningen där du vill lägga till den valda profildatauppsättningen. |
| 8 | Nya målgruppsdimensioner | Nya målgruppsdimensioner <!--and metrics?--> som representerar de Experience Platform-målgrupper som ingår i den profildatauppsättning som du har valt och som är tillgängliga för rapportering i Analysis Workspace. Dessa dimensioner skapas automatiskt. |
| 9 | Datavyer | De datavyer som du väljer och som är kopplade till anslutningen. Detta är de datavyer som du vill använda när du analyserar Experience Platform målgruppsdata inom Analysis Workspace. Dessa datavyer konfigureras automatiskt med Experience Platform målgruppsdata för rapportering. |
| 10 | Analysis Workspace | Det område i Customer Journey Analytics där du skapar rapporter som innehåller de målgrupper i Experience Platform som är intresserade. |

## Konfigurera målgruppsanalys

När du konfigurerar målgruppsanalys väljer du den sandlåda och sammanfogningsprincip som är kopplad till de Experience Platform-målgrupper som du vill analysera. Customer Journey Analytics skapar en ny uppslagsdatauppsättning och lägger sedan automatiskt till uppslagsdatauppsättningen och profildatauppsättningen till den anslutning du väljer.

Mer information finns i [Konfigurera målgruppsanalys](/help/connections/audience-analysis/audience-analysis-configure.md).

## Analysera målgruppsdata i Customer Journey Analytics

Med målgruppsdata i Customer Journey Analytics kan ni få användbara insikter om hur målgruppsmedlemmarna beter sig i olika kanaler.

Du kan till exempel spåra beteendet hos enskilda kunder som ingick i samma e-postkampanj. Med målgruppen i Customer Journey Analytics kan du se följande typer av information om varje målgruppsmedlem:

* Klickningar från e-postmeddelandet till webbplatsen som till slut resulterade i ett köp

* Målgruppsmedlemmar som till slut gjorde ett butiksköp

Mer information finns i [Analysera Experience Platform-målgrupper i Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).










