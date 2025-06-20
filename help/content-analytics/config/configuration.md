---
title: Konfigurera Content Analytics
description: En översikt över hur du konfigurerar Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: f149a2bd7f184f4e8f6e67979649e2d9f609d603
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 0%

---

# Konfigurera Content Analytics

I den här artikeln beskrivs hur du konfigurerar Content Analytics på en hög nivå.

Innan du konfigurerar Content Analytics måste du se till att [förutsättningarna](#prerequisites) uppfylls, du har den [åtkomstkontroll](#access-control) som krävs och du är medveten om [begränsningarna](#limitations).


Stegen på hög nivå

![Konfiguration av Content Analytics](../assets/aca-configuration.svg){zoomable="yes"}

1. Använd guiden [guidad konfiguration](guided.md) från Content Analytics för att vägleda dig genom alla steg som krävs för att ställa in förutsättningarna för en konfiguration av Content Analytics. Du kan spara dina konfigurationer när som helst och returnera dem senare.
1. När du känner dig bekväm med konfigurationsvärdena kan du implementera konfigurationen. Den här implementeringen skapar alla nödvändiga artefakter, baserat på vad du har konfigurerat i guiden.
1. Endast när du [manuellt publicerar](manual.md) taggegenskapen distribueras din Content Analytics-konfiguration och datainsamlingen startas.

1. Du kan bara göra vissa mindre ändringar i en implementerad konfiguration med guiden [guidad konfiguration](guided.md). Ändra till exempel [datavyn](/help/data-views/data-views.md).
1. Du kan göra andra ändringar i en implementerad konfiguration med [Adobe Content Analytics-tillägget](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) i den associerade taggegenskapen.
1. Endast när du [manuellt återpublicerar ](manual.md) taggegenskapen distribueras konfigurationsändringarna effektivt och datainsamling, baserat på dina ändringar, startas.


## Förutsättningar

Innan du konfigurerar Content Analytics måste du kontrollera att följande krav uppfylls:

* Du har tillåtit att användaragenten och IP-adressen för den funktionstjänst som används i Content Analytics anges. Den användaragentsträng som ska konfigureras är: <code>AdobeFeaturization/1.0</code>.
* Om du har implementerat [Web SDK med JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library){target="_blank"} för normal beteendedatainsamling måste du kontrollera att du använder standardnamnlegeringen <code>.</code> för JavaScript Library.
* Du har en Customer Journey Analytics-produktadministratörsroll med de extra behörigheterna att hantera anslutningar och hantera datavyer.
* Om du funderar på att samla in Content Analytics-upplevelser ska du kontrollera att du har konfigurerat och uppdaterat [Content Analytics-versionshantering](manual.md#versioning) baserat på ändringar på dina webbsidor.
* Du måste ha [behörighet för datainsamling](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}:
   * [Experience Platform-behörigheter](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Experience Platform Data Collection permissions](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* Du har noga övervägt följande viktiga konfigurationsalternativ:

   * Din webbplats passar för upplevelserapporter. Korrekt erfarenhetsrapportering är bara möjligt när följande villkor är uppfyllda:
      * Sidorna på webbplatsen måste kunna reproduceras med hjälp av sidans URL.
      * Det textinnehåll som visas av en viss användare kan återges med hjälp av sidans URL och är inte beroende av cookies eller andra anpassningsmekanismer.
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

## Begränsningar

Det schema som används för Content Analytics händelsedata ägs av systemet. Ett systemägt schema kan inte ändras vilket innebär:

* Du kan inte inkludera fältgrupper som har stöd för funktioner som geopositionering, robotidentifiering eller enhetssökning.
* Du kan inte lägga till en specifik identifierare som stöder [fältbaserad sammanslagning](/help/stitching/fbs.md).

>[!MORELIKETHIS]
>
>* [Guidad konfiguration](guided.md)
>* [Manuell konfiguration](manual.md)
>* [Åtkomstkontroll](/help/technotes/access-control.md)
>
