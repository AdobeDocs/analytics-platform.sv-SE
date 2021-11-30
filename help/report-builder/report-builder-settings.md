---
title: Konfigurera inställningar för Report Builder i CJA
description: Beskriver hur du anger inställningar för offlineläge, språk, aktuellt läge och felsökning.
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---

# Inställningar för Report Builder

Använd **Inställningar** om du vill konfigurera inställningar på programnivå, t.ex. det språk som visas i användargränssnittet eller om du vill arbeta i offlineläge eller inte. Inställningarna används omedelbart och ställs in för alla framtida sessioner tills de ändras.

Så här ändrar du inställningarna för Report Builder

1. Klicka på **Inställningar** ikon.

1. Gör ändringar i Aktivera offlineläge, välj ett språk eller aktivera inställningarna för felsökningsloggen.

1. Klicka **Använd**.

   ![](./assets/image38.png)

## Offline-läge

Data hämtas inte när du skapar och redigerar ett datablock i offlineläge. I stället används simuleringsdata så att du snabbt kan skapa och redigera ett datablock utan att vänta på att begäran ska köras. När du är online igen *Uppdatera datablock* kommando eller *Uppdatera alla datablock* kommandot uppdaterar de datablock som du har skapat med verkliga data.

Aktivera offlineläge

1. Klicka på **Inställningar** ikon.

1. Välj **Aktivera offlineläge**.

1. Ange ett positivt heltal i **Visa måttdata som** fält.

1. Klicka **Använd**.

## Språk

Du kan välja språk för användargränssnittet i Report Builder. Alla Adobe Analytics-språk som stöds finns tillgängliga.

Välj det språk som ska användas i användargränssnittet i Report Builder

1. Klicka på Inställningar.

1. Välj ett språk på menyn **Språk** nedrullningsbar meny.

   ![](./assets/image39.png)

1. Klicka **Använd.**

## Felsökning

Använd felsökningsinställningen för att logga alla klient-/serverdata till en lokal fil. Använd det här alternativet för att lösa supportärenden.

Om du vill aktivera alternativet Felsökning väljer du **Logga Report Builder-begäran till lokal fil**.
