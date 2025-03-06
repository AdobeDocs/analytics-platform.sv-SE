---
title: Konfigurera innehållsanalys
description: En översikt över hur du konfigurerar Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 1%

---

# Konfigurera innehållsanalys

>[!WARNING]
>
>Den här artikeln är ett preliminärt inofficiellt utkast till en kommande slutversion och ingår i Content Analytics-dokumentationen. Allt innehåll kan ändras och inga rättsliga skyldigheter kan härledas från den aktuella versionen av den här artikeln.
>

{{release-limited-testing}}

Konfigurationen av Content Analytics består av följande steg:

![Konfiguration av innehållsanalys](../assets/aca-configuration.svg)

1. Använd guiden [Guidad konfiguration](guided.md) för innehållsanalys för att vägleda dig genom alla steg som krävs för att konfigurera förutsättningarna för en konfiguration av innehållsanalys. Du kan spara dina konfigurationer och returnera dem senare.
1. När du känner dig bekväm med konfigurationsvärdena kan du implementera konfigurationen. Den här implementeringen skapar alla nödvändiga artefakter, baserat på vad du har konfigurerat i guiden. Följande artefakter skapas, uppdateras eller väljs:
   * Anpassad reseanalys
      * En [datavy](/help/data-views/data-views.md) har valts.
      * En [anslutning](/help/connections/overview.md) är markerad och hämtas automatiskt från den valda datavyn.
   * Experience Platform
      * Sandlådan markeras och hämtas automatiskt från anslutningen. Nödvändiga arbetsflöden och tjänster aktiveras i sandlådan.
      * Scheman för innehållsanalys markeras i sandlådan. Om det inte är tillgängligt skapas de nödvändiga scheman.
      * Datauppsättningar för innehållsanalys har valts i sandlådan. Om de inte är tillgängliga skapas de nödvändiga datauppsättningarna.
   * Datainsamling
      * En datastream skapas och en Experience Platform-tjänst konfigureras i datastream för att strömma data till händelsedatauppsättningen för upplevelsen av Content Analytics.
      * En taggegenskap skapas med Adobe Content Analytics-tillägget konfigurerat för rätt sandlåda, datastream och andra konfigurationsalternativ från konfigurationsguiden.
1. Endast när du [manuellt publicerar ](manual.md) taggegenskapen distribueras och aktiveras Content Analytics.

1. Du kan bara göra vissa begränsade ändringar i en implementerad konfiguration med guiden [guidad konfiguration](guided.md). Ändra till exempel [datavyn](/help/data-views/data-views.md).
1. Du kan göra andra ändringar i en implementerad konfiguration med [Adobe Content Analytics-tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) i den associerade taggegenskapen.
1. Endast när du [manuellt återpublicerar ](manual.md) taggegenskapen distribueras och aktiveras konfigurationsändringarna från steg 4 och 5.


Innan du konfigurerar Content Analytics bör du kontrollera att följande krav är uppfyllda:


>[!PREREQUISITES]
>
>* Du har angett användaragenten och IP-adressen som tillåtet för den funktionstjänst som används i Content Analytics. Användaragentsträngen är `AdobeFeaturization/1.0`.
>* Du har en Customer Journey Analytics-produktadministratörsroll med de extra behörigheterna att hantera anslutningar och hantera datainsamlingar. Följande Experience Platform-behörigheter krävs:
>  
>   | Kategori | Behörighet | Beskrivning |
>   |---|---|---|
>   | [!UICONTROL Data Collection] | Visa datastreams | Skrivskyddad åtkomst till datastreams. |
>   | [!UICONTROL Data Collection] | Hantera datastreams | Åtkomst att läsa, skapa, redigera och ta bort datastreams. |
>   | [!UICONTROL Data Modeling] | [!UICONTROL View Schemas] | Skrivskyddad åtkomst till scheman och relaterade resurser. |
>   | [!UICONTROL Data Modeling] | [!UICONTROL Manage Schemas] | Åtkomst för att läsa, skapa, redigera och ta bort scheman och relaterade resurser. |
>   | [!UICONTROL Data Management] | [!UICONTROL View Datasets] | Skrivskyddad åtkomst för datauppsättningar och scheman. |
>   | [!UICONTROL Data Management] | [!UICONTROL Manage Datasets] | Åtkomst för att läsa, skapa, redigera och ta bort datauppsättningar. Skrivskyddad åtkomst för scheman. |
>   | [!UICONTROL Data Ingestion] | [!UICONTROL Manage Sources] | Tillgång till att läsa, skapa, redigera och inaktivera källor. |
>   | [!UICONTROL Identity Management] | [!UICONTROL View Identity Namespaces] | Skrivskyddad åtkomst för identitetsnamnutrymmen. |
>
>* Du har noga övervägt följande viktiga konfigurationsalternativ:
>
>   * Är din webbplats lämplig för upplevelserapporter? Korrekt erfarenhetsrapportering är bara möjligt när följande villkor är uppfyllda:
>   * Webbplatsinnehållet styrs endast av URL-adresser.
>   * Sidorna på din webbplats kan reproduceras med hjälp av sidans URL, och du förstår vilka valfria URL-parametrar som skapar upplevelser.
>* Ni har en tydlig förståelse för vilka sidor ni vill samla in innehållsanalyser och insikter.
>* Ni har en tydlig förståelse för vilka (typer av) resurser ni vill samla in analyser och insikter om innehållsengagemang.
>


>[!MORELIKETHIS]
>
>* [Guidad konfiguration](guided.md)
>* [Manuell konfiguration](manual.md)
>* [Åtkomstkontroll](/help/technotes/access-control.md)
>


