---
title: Konfigurera inställningar för Report Builder i Customer Journey Analytics
description: Beskriver hur du anger inställningar för offlineläge, språk, aktuellt läge och felsökning.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: 9efad7c7808a7a68bc25fc5f1700f4e4f8e18614
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 0%

---

# Inställningar för Report Builder

Använd rutan **Inställningar** om du vill konfigurera programnivåinställningar, t.ex. det språk som visas i användargränssnittet eller om du vill arbeta i offlineläge eller inte. Inställningarna används omedelbart och ställs in för alla framtida sessioner tills de ändras.

Så här ändrar du inställningarna för Report Builder

1. Klicka på ikonen **Inställningar** .

1. Gör ändringar i Aktivera offlineläge, välj ett språk eller aktivera inställningarna för felsökningsloggen.

1. Klicka på **Använd**.

   ![Report Builder datumintervallfönster med knappen Avbryt och använd.](./assets/image38.png)

## Offline-läge

Data hämtas inte när du skapar och redigerar ett datablock i offlineläge. I stället används simuleringsdata så att du snabbt kan skapa och redigera ett datablock utan att vänta på att begäran ska köras. När du är online igen uppdaterar kommandot *Uppdatera datablock* eller *Uppdatera alla datablock* de datablock som du har skapat med aktuella data.

Aktivera offline-läge

1. Klicka på ikonen **Inställningar** .

1. Välj **Aktivera offlineläge**.

1. Ange ett positivt heltal i fältet **Visa mätdata som**.

1. Klicka på **Använd**.

## Språk

Du kan välja språk för användargränssnittet i Report Builder. Alla Adobe Analytics-språk som stöds finns tillgängliga.

Välj det språk som ska användas i användargränssnittet i Report Builder

1. Klicka på Inställningar.

1. Välj ett språk i listrutan **Språk**.

   ![Datumintervallfönstret Report Builder visar språklistan med engelska markerat.](./assets/image39.png)

1. Klicka på **Använd.**

## Felsökning

Använd felsökningsinställningen för att logga alla klient-/serverdata till en lokal fil. Använd det här alternativet för att lösa supportärenden.

Om du vill aktivera felsökningsalternativet väljer du **Logga Report builder-begäran till den lokala filen**.
