---
title: Avbryt rapportbegäranden i Rapporteringsaktivitetshanteraren
description: Lär dig mer om hur du använder Rapporteringsaktivitetshanteraren för att diagnostisera och åtgärda kapacitetsproblem under perioder med hög rapporteringsnivå.
solution: Customer Journey Analytics
feature: Basics
source-git-commit: 57124124254f5ca9eb2a9f63a7478cd288c19b0e
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 0%

---

# Avbryt rapportbegäranden i Rapporteringsaktivitetshanteraren

{{release-limited-testing}}

The [!UICONTROL Reporting Activity Manager] gör det möjligt för administratörer att snabbt diagnostisera och avbryta rapporteringsbegäranden för att åtgärda problem med rapporteringskapaciteten under perioder med hög rapporteringsnivå.

Tänk på följande när du avbryter rapportbegäranden:

* Du kan avbryta specifika begäranden, avbryta alla begäranden från en viss användare eller avbryta alla begäranden som rör ett visst projekt.

* När du avbryter begäranden kan du även välja att begränsa efterföljande begäranden för en viss tidsperiod.

* Du kan inte avbryta en begäran om [!UICONTROL **Användare**] kolumnen i en begäran visas som [!UICONTROL **Okänd**]. När detta inträffar innebär det att användaren befinner sig i ett inloggningsföretag där du inte har administratörsbehörighet.

Mer information om Reporting Activity Manager, inklusive viktiga fördelar och behörighetskrav, finns i [Översikt över Reporting Activity Manager](/help/reporting-activity-manager/reporting-activity-overview.md).

## Avbryt specifika begäranden

Du kan avbryta enskilda begäranden som förbrukar en stor del av rapporteringskapaciteten.

1. I Customer Journey Analytics, gå till **[!UICONTROL Tools]** > **[!UICONTROL Reporting Activity Manager]**.

1. Välj den anslutning där du vill avbryta rapporteringsbegäranden. <!--double-check this step-->

   Mer information om tillgängliga data på den här sidan finns i [Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity.md).

1. Välj [!UICONTROL **Begäranden**] och sedan välja en eller flera förfrågningar.

   <!-- add screenshot -->

1. Välj [!UICONTROL **Avbryt begäranden**].

   The [!UICONTROL **Avbryt _x_ rapportförfrågningar**] visas.

1. I meddelandefältet för annullering visas meddelandet som visas för användarna när deras begäranden avbryts. Ett standardmeddelande har angetts. Du kan uppdatera standardmeddelandet om du vill ha mer information.

1. (Valfritt) Om du vill begränsa framtida begäranden för en viss tidsperiod aktiverar du alternativet att [!UICONTROL **Begränsa efterföljande begäranden**] väljer du sedan något av följande alternativ:

   | Alternativ |  -funktion |
   |---------|----------|
   | [!UICONTROL **Användare &amp; projekt**] | Användare som är associerade med de valda förfrågningarna kommer tillfälligt att begränsas från att köra rapportförfrågningar för associerade projekt. |
   | [!UICONTROL **Användare**] | Användare som är associerade med de valda förfrågningarna hindras tillfälligt från att göra några rapportförfrågningar. |
   | [!UICONTROL **Projekt**] | Projekt som är associerade med de valda förfrågningarna begränsas tillfälligt från alla rapporteringsförfrågningar. |
   | [!UICONTROL **Begränsat för**] | Välj hur länge begäranden ska begränsas. Du kan välja 1 minut (standard), 5 minuter, 10 minuter, 15 minuter eller 30 minuter. <!-- double-check this --><p>Du kan inte ta bort en begränsning tidigt efter att den har angetts.</p> |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Fortsätt med annullering**].

   Ett meddelande visas i Analysis Workspace som informerar användare om att begäran har avbrutits. Mer information om hur detta visas i Analysis Workspace finns i [Upplevelse när användare öppnar en avbruten rapport](#experience-when-users-access-a-cancelled-report).

## Avbryt begäranden från användare

Du kan avbryta alla begäranden som är kopplade till en eller flera användare.

1. I Customer Journey Analytics, gå till **[!UICONTROL Tools]** > **[!UICONTROL Reporting Activity Manager]**.

1. Välj den anslutning där du vill avbryta rapporteringsbegäranden. <!--double-check this step-->

   Mer information om tillgängliga data på den här sidan finns i [Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity.md).

1. Välj [!UICONTROL **Användare**] och sedan en eller flera användare.

   <!-- add screenshot -->

1. Välj [!UICONTROL **Avbryt begäranden**].

   The [!UICONTROL **Avbryt _x_ rapportförfrågningar från x-användare**] visas.

1. I meddelandefältet för annullering visas meddelandet som visas för användarna när deras begäranden avbryts. Ett standardmeddelande har angetts. Du kan uppdatera standardmeddelandet om du vill ha mer information.

1. (Valfritt) Om du vill begränsa framtida begäranden för en viss tidsperiod aktiverar du alternativet att [!UICONTROL **Begränsa efterföljande begäranden**] väljer du sedan något av följande alternativ:

   | Alternativ |  -funktion |
   |---------|----------|
   | [!UICONTROL **Användare &amp; projekt**] | De valda användarna kommer tillfälligt att hindras från att göra några rapportförfrågningar för de associerade projekten. |
   | [!UICONTROL **Användare**] | De valda användarna kommer tillfälligt att hindras från att göra några rapportförfrågningar. |
   | [!UICONTROL **Projekt**] | Projekt som är associerade med de valda användarna kommer att begränsas från alla rapportförfrågningar som görs av alla användare. |
   | [!UICONTROL **Begränsat för**] | Välj hur länge begäranden ska begränsas. Du kan välja 1 minut (standard), 5 minuter, 10 minuter, 15 minuter eller 30 minuter. <!--double-check this--> <p>Du kan inte ta bort en begränsning tidigt efter att den har angetts.</p> |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Fortsätt med annullering**].

   Ett meddelande visas i Analysis Workspace som informerar användare om att begäran har avbrutits. Mer information om hur detta visas i Analysis Workspace finns i [Upplevelse när användare öppnar en avbruten rapport](#experience-when-users-access-a-cancelled-report).

## Avbryt begäranden per projekt

Du kan avbryta alla begäranden som är kopplade till ett eller flera projekt.

1. I Customer Journey Analytics, gå till **[!UICONTROL Tools]** > **[!UICONTROL Reporting Activity Manager]**.

1. Välj den anslutning där du vill avbryta rapporteringsbegäranden. <!--double-check this step-->

   Mer information om tillgängliga data på den här sidan finns i [Visa rapporteringsaktivitet i Rapporteringsaktivitetshanteraren](/help/reporting-activity-manager/reporting-activity.md).

1. Välj [!UICONTROL **Projekt**] och sedan välja ett eller flera projekt.

   <!-- add screenshot -->

1. Välj [!UICONTROL **Avbryt begäranden**].

   The [!UICONTROL **Avbryt _x_ rapportbegäranden från x-projekt**] visas.

1. I meddelandefältet för annullering visas meddelandet som visas för användarna när deras begäranden avbryts. Ett standardmeddelande har angetts. Du kan uppdatera standardmeddelandet om du vill ha mer information.

1. (Valfritt) Om du vill begränsa framtida begäranden för en viss tidsperiod aktiverar du alternativet att [!UICONTROL **Begränsa efterföljande begäranden**] väljer du sedan något av följande alternativ:

   | Alternativ |  -funktion |
   |---------|----------|
   | [!UICONTROL **Användare &amp; projekt**] | De valda projekten kommer tillfälligt att begränsas från alla rapportförfrågningar som görs av associerade användare. |
   | [!UICONTROL **Användare**] | Användare som är associerade med de valda projekten kommer inte att kunna göra några rapportförfrågningar. |
   | [!UICONTROL **Projekt**] | De valda projekten kommer tillfälligt att begränsas från alla rapportförfrågningar som görs av någon användare. |
   | [!UICONTROL **Begränsat för**] | Välj hur länge begäranden ska begränsas. Du kan välja 1 minut (standard), 5 minuter, 10 minuter, 15 minuter eller 30 minuter. <!--double-check this--> <p>Du kan inte ta bort en begränsning tidigt efter att den har angetts.</p> |

   {style="table-layout:auto"}

1. Välj [!UICONTROL **Fortsätt med annullering**].

   Ett meddelande visas i Analysis Workspace som informerar användare om att begäran har avbrutits. Mer information om hur detta visas i Analysis Workspace finns i [Upplevelse när användare öppnar en avbruten rapport](#experience-when-users-access-a-cancelled-report).

## Upplevelse när användare öppnar en avbruten rapport

<!-- Update for CJA and AA -->

I Analysis Workspace visas följande meddelande när användare försöker få åtkomst till en rapport som har avbrutits av en administratör:

![cancel-user-notice](assets/cancel-user-facing.png)