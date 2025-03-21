---
title: Konfigurera innehållsanalys
description: En översikt över hur du konfigurerar Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 17a7a9a602b92693b2ad6db10f60d3e77fef9724
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---

# Konfigurera innehållsanalys

{{draft-aca}}

{{release-limited-testing}}

Konfigurationen av Content Analytics består av följande steg:

![Konfiguration av innehållsanalys](../assets/aca-configuration.svg){zoomable="yes"}

1. Använd guiden [guidad konfiguration](guided.md) från Content Analytics för att vägleda dig genom alla steg som krävs för att ställa in förutsättningarna för en konfiguration av Content Analytics. Du kan spara dina konfigurationer när som helst och returnera dem senare.
1. När du känner dig bekväm med konfigurationsvärdena kan du implementera konfigurationen. Den här implementeringen skapar alla nödvändiga artefakter, baserat på vad du har konfigurerat i guiden.
1. Endast när du [manuellt publicerar](manual.md) taggegenskapen distribueras och aktiveras din Content Analytics-konfiguration.

1. Du kan bara göra vissa mindre ändringar i en implementerad konfiguration med guiden [guidad konfiguration](guided.md). Ändra till exempel [datavyn](/help/data-views/data-views.md).
1. Du kan göra andra ändringar i en implementerad konfiguration med [Adobe Content Analytics-tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) i den associerade taggegenskapen.
1. Endast när du [manuellt återpublicerar ](manual.md) taggegenskapen distribueras och aktiveras konfigurationsändringarna.


## Förutsättningar

Innan du konfigurerar Content Analytics måste du kontrollera att följande krav uppfylls:

* Du har angett användaragenten och IP-adressen som tillåtet för den funktionstjänst som används i Content Analytics. Den användaragentsträng som ska konfigureras är: <code>AdobeFeaturization/1.0</code>.
* Du har en Customer Journey Analytics-produktadministratörsroll med de extra behörigheterna att hantera anslutningar och hantera datavyer.
* Du har de Experience Platform-behörigheter som krävs:

  | Kategori | Behörighet | Beskrivning |
  |---|---|---|
  | [!UICONTROL Data Collection] | Visa datastreams | Skrivskyddad åtkomst till datastreams. |
  | [!UICONTROL Data Collection] | Hantera datastreams | Åtkomst för att läsa, skapa, redigera och ta bort dataströmmar. |
  | [!UICONTROL Data Modeling] | [!UICONTROL View Schemas] | Skrivskyddad åtkomst till scheman och relaterade resurser. |
  | [!UICONTROL Data Modeling] | [!UICONTROL Manage Schemas] | Åtkomst för att läsa, skapa, redigera och ta bort scheman och relaterade resurser. |
  | [!UICONTROL Data Management] | [!UICONTROL View Datasets] | Skrivskyddad åtkomst för datauppsättningar och scheman. |
  | [!UICONTROL Data Management] | [!UICONTROL Manage Datasets] | Åtkomst för att läsa, skapa, redigera och ta bort datauppsättningar. Skrivskyddad åtkomst för scheman. |
  | [!UICONTROL Data Ingestion] | [!UICONTROL Manage Sources] | Tillgång till att läsa, skapa, redigera och inaktivera källor. |
  | [!UICONTROL Identity Management] | [!UICONTROL View Identity Namespaces] | Skrivskyddad åtkomst för identitetsnamnutrymmen. |

* Du har noga övervägt följande viktiga konfigurationsalternativ:

   * Din webbplats passar för upplevelserapporter. Korrekt erfarenhetsrapportering är bara möjligt när följande villkor är uppfyllda:
      * Du kan bara få åtkomst till webbplatsinnehållet via offentliga URL:er. Åtkomst till webbplatsen kräver inte personliga tokens, cookies eller andra mekanismer som inte är tillgängliga via URL:en.
      * Sidorna på din webbplats kan reproduceras med hjälp av sidans URL, och du förstår vilka valfria URL-parametrar som skapar upplevelser.
   * Ni har en tydlig förståelse för vilka sidor ni vill samla in innehållsanalyser och insikter.
   * Ni har en tydlig förståelse för vilka (typer av) resurser ni vill samla in analyser och insikter om innehållsengagemang.


## Åtkomstkontroll

>[!IMPORTANT]
>
>Det finns ingen Content Analytics-behörighet som du kan konfigurera för att aktivera eller inaktivera Content Analytics-åtkomst för enskilda användare eller grupper av användare.
>

Om du vill ge en användare eller grupp av användare åtkomst till Content Analytics måste du ge användaren eller gruppen av användare åtkomst till en eller flera [datavyer som har konfigurerats för Content Analytics](guided.md#data-view).

Den här åtkomsten innebär:

1. Datavyn som aktiveras av Content Analytics ingår som en del av datavybehörigheten för en viss Customer Journey Analytics-produktprofil.
1. Den specifika Customer Journey Analytics-produktprofilen är en av de produktprofiler som tilldelats användaren eller gruppen med användare.

>[!MORELIKETHIS]
>
>* [Guidad konfiguration](guided.md)
>* [Manuell konfiguration](manual.md)
>* [Åtkomstkontroll](/help/technotes/access-control.md)
>
