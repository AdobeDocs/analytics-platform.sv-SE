---
title: Konfigurera innehållsanalys
description: En översikt över hur du konfigurerar Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: cea253d3b1da080e6735989d59cc6eda44afc203
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---

# Konfigurera innehållsanalys

>[!WARNING]
>
>Den här artikeln är ett preliminärt inofficiellt utkast till en kommande slutversion och ingår i Content Analytics-dokumentationen. Allt innehåll kan ändras och inga rättsliga skyldigheter kan härledas från den aktuella versionen av den här artikeln.
>

{{release-limited-testing}}


Om du vill konfigurera innehållsanalys för din organisation använder du [den guidade konfigurationen](guided.md) för innehållsanalys. Konfigurationsguiden vägleder dig genom alla steg som krävs för att ställa in förutsättningarna för en automatisk konfiguration av innehållsanalys.

## Förutsättningar

Innan du konfigurerar Content Analytics bör du kontrollera att följande krav är uppfyllda:

* Du har angett användaragenten och IP-adressen som tillåtet för den funktionstjänst som används i Content Analytics. Användaragentsträngen är `AdobeFeaturization/1.0`.
* Du har en Customer Journey Analytics-produktadministratörsroll med de extra behörigheterna att hantera anslutningar och hantera datainsamlingar. Följande Experience Platform-behörigheter krävs:

  | Kategori | Behörighet | Beskrivning |
  |---|---|---|
  | [!UICONTROL Data Collection] | Visa datastreams | Skrivskyddad åtkomst till datastreams. |
  | [!UICONTROL Data Collection] | Hantera datastreams | Åtkomst att läsa, skapa, redigera och ta bort datastreams. |
  | [!UICONTROL Data Modeling] | [!UICONTROL View Schemas] | Skrivskyddad åtkomst till scheman och relaterade resurser. |
  | [!UICONTROL Data Modeling] | [!UICONTROL Manage Schemas] | Åtkomst för att läsa, skapa, redigera och ta bort scheman och relaterade resurser. |
  | [!UICONTROL Data Management] | [!UICONTROL View Datasets] | Skrivskyddad åtkomst för datauppsättningar och scheman. |
  | [!UICONTROL Data Management] | [!UICONTROL Manage Datasets] | Åtkomst för att läsa, skapa, redigera och ta bort datauppsättningar. Skrivskyddad åtkomst för scheman. |
  | [!UICONTROL Data Ingestion] | [!UICONTROL Manage Sources] | Tillgång till att läsa, skapa, redigera och inaktivera källor. |
  | [!UICONTROL Identity Management] | [!UICONTROL View Identity Namespaces] | Skrivskyddad åtkomst för identitetsnamnutrymmen. |

* Du har noga övervägt följande viktiga konfigurationsalternativ:

   * Är din webbplats lämplig för upplevelserapporter? Korrekt erfarenhetsrapportering är bara möjligt när följande villkor är uppfyllda:
      * Webbplatsinnehållet styrs endast av URL-adresser.
      * Sidorna på din webbplats kan reproduceras med hjälp av sidans URL, och du förstår vilka valfria URL-parametrar som skapar upplevelser.
   * Ni har en tydlig förståelse för vilka sidor ni vill samla in innehållsanalyser och insikter.
   * Ni har en tydlig förståelse för vilka (typer av) resurser ni vill samla in analyser och insikter om innehållsengagemang.


>>
[!MORELIKETHIS]
>>
* [Åtkomstkontroll](/help/technotes/access-control.md)
>


