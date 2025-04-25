---
title: Konfigurera inställningar för Report Builder i Customer Journey Analytics
description: Beskriver hur du anger inställningar för offlineläge, språk, aktuellt läge och felsökning.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: 9794779894fbecb433c16d108c555c5f81a4b491
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 0%

---

# Report Builder-inställningar

Använd rutan **Inställningar** om du vill konfigurera programnivåinställningar, t.ex. det språk som visas i användargränssnittet eller om du vill arbeta i offlineläge eller inte. Inställningarna används omedelbart och ställs in för alla framtida sessioner tills de ändras.

Så här ändrar du Report Builder-inställningar

1. Välj ikonen **Inställningar** .

1. Gör ändringar i [aktivera inaktiverat offlineläge](#off-line-mode), [välj ett språk](#language) eller [aktivera felsökning](#troubleshooting).

1. Välj **[!UICONTROL Apply]**.

   ![Report Builder datumintervallfönster med knappen Avbryt och använd.](./assets/report-builder-settings.png){zoomable="yes"}

## Offline-läge

När du skapar och redigerar ett datablock i offlineläge hämtas inga data. I stället används simuleringsdata så att du snabbt kan arbeta utan att vänta på att begäran ska köras. När du är online igen väljer du ![Uppdatera](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** eller ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** om du vill uppdatera datablocken med aktuella data.

Aktivera offline-läge

1. Välj ![Inställning](/help/assets/icons/Setting.svg).

1. Växla **[!UICONTROL Enable off-line mode]** på.

1. Ange ett positivt heltal i fältet **[!UICONTROL Display metric data]** som.

1. Välj **[!UICONTROL Apply]**.


## Språk

Du kan välja språk för Report Builder-gränssnittet. Alla Customer Journey Analytics-språk som stöds finns tillgängliga.

Så här väljer du vilket språk som ska användas i Report Builder-gränssnittet:

1. Välj ett språk i listrutan **[!UICONTROL Language]**.

1. Välj **Använd.**

## Felsökning

Inställningen **[!UICONTROL Troubleshooting logs]** loggar alla klient-/serverdata till en lokal fil. Använd det här alternativet för att lösa supportärenden.

Om du vill aktivera felsökningsloggar kontrollerar du **[!UICONTROL Log report builder request to local file]**.
