---
title: Lägg till kvantmetriska data i Customer Journey Analytics
description: Använd Quantum Metric för datainsamling av användarresor och beteenden, och utnyttja sedan CJA från insamlade data för att få djupare insikter.
role: User, Admin
solution: Customer Journey Analytics
feature: Use Cases
hidefromtoc: true
hide: true
exl-id: ea8795fe-f5aa-458f-9e01-53ff1ffe6372
source-git-commit: 03e9fb37684f8796a18a76dc0a93c4e14e6e7640
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Lägg till kvantmetriska data i Customer Journey Analytics

>[!IMPORTANT]
>
>Källkopplingen för kvantmetrisk källa är för närvarande inte tillgänglig.

CJA frigör rapporttidskontrollen av QM-data, sekventiell dataanalys, avancerad attribuering och annan avancerad rapportering.  QM kan skickas till AEP med antingen QM-källkopplingen eller Quantum Metrics Tags-tillägget.

## Steg 1: Skapa en källanslutning för kvantmetrisk källa

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till [!UICONTROL Experience Platform] > [!UICONTROL Connections] > [!UICONTROL Sources].
1. Lägg till källkopplingen för kvantmetrisk källa och följ anvisningarna för att slutföra.

Mer information finns i [Adobe Experience Platform-källanslutningar](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home).

## Steg 2: Skapa en anslutning i Customer Journey Analytics

Om du skapar en källanslutning för Quantum Metric-data skapas automatiskt en datauppsättning i Adobe Experience Platform. Lägg till den här datauppsättningen i en ny eller befintlig [anslutning](/help/connections/overview.md) i Customer Journey Analytics.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Connections]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.
1. Ge anslutningen ett namn och lägg till datamängden Quantum Metric i anslutningen.
1. Klicka på **[!UICONTROL Save]**.

>[!NOTE]
>Du kan lägga till kvantmätdata i samma anslutning som övriga Customer Journey Analytics-data, men dessa data kan inte sammanfogas utan ett gemensamt person-ID mellan de två datauppsättningarna. Om du vill använda det här beteendet rekommenderar Adobe att du använder [taggtillägget](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/analytics/quantum-metric) i stället för källkopplingen.

## Steg 3: Skapa en datavy i Customer Journey Analytics

Skapa en [datavy](/help/data-views/data-views.md) för att konfigurera mått- och måttinställningar.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Data views]**, eventuellt från **[!UICONTROL Data management]**, på den översta menyn.
1. Välj önskad datavy eller skapa en datavy.
1. Leta upp de önskade kvantmåtten och måtten i schemafältlistan till höger och dra dem till mått- och mätområdet i mitten.
1. Använd den högra rutan för att konfigurera alla önskade dimensioner och mått.

## Steg 4: Börja rapportera och analysera i Customer Journey Analytics

Nu när data är tillgängliga i Customer Journey Analytics kan du börja rapportera data.

1. Logga in på [experience.adobe.com](https://experience.adobe.com).
1. Navigera till Customer Journey Analytics och välj **[!UICONTROL Workspace]** på den översta menyn.
1. Välj ett befintligt projekt eller skapa ett projekt.
1. Analysera data genom att dra valfri Quantum Metric-dimension eller mätvärde till Workspace Canvas.
