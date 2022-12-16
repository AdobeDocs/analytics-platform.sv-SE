---
title: Beräkna och hantera din CJA-användning
description: Visar två metoder för att beräkna användningen och en metod för att hantera den.
role: Admin
feature: CJA Basics
source-git-commit: 2bcf1f805a54581f13f7d08b9ef034535d7959b1
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 0%

---


# Beräkna och hantera din CJA-användning

För att förstå hur CJA används kan du använda två metoder:

* Lägg till händelsedataraderna för varje anslutning. (Se **Beräkna anslutningsstorlek** nedan)
* Använd Analysis Workspace för att rapportera om förra månadens händelser. (Se **Skapa ett Workspace-projekt med alla händelsedata** nedan.)

Så här hanterar du CJA-användningen:

* Använd CJA API. (Se **Skapa en rapport i CJA API** nedan.)

## Beräkna anslutningsstorlek {#estimate-size}

Du kan behöva veta hur många rader med händelsedata du har i [!UICONTROL Customer Journey Analytics]. Gör så här för att få en korrekt redovisning av hur din organisation använder händelsedatarader **för var och en av de anslutningar som din organisation har skapat**.

>[!NOTE]
>
>Gör detta den första fredagen i varje månad, eftersom Adobe kör din senaste användningsrapport den dagen.

1. I [!UICONTROL Customer Journey Analytics]klickar du på **[!UICONTROL Connections]** -fliken.

   Nu kan du se en lista över alla dina aktuella anslutningar.

1. Klicka på varje anslutningsnamn för att komma till Anslutningshanteraren.

1. Lägg till **[!UICONTROL Records of event data available]** för varje anslutning som din organisation har skapat. (Beroende på storleken på anslutningen kan det ta en stund innan numret visas.)

   ![händelsedata](assets/event-data.png)

   >[!CAUTION]
   >
   >   Detta antal gäller endast händelsedata, inte profil- eller sökdata. Om du har profil- och sökdata kommer antalet att vara något högre. Det finns dock för närvarande inget sätt att rapportera om användningen av profil- och sökdata i användargränssnittet. Den här funktionen är särpresenterad för 2023.

1. När du har angett summan av alla händelsedatarader ska du slå upp behörigheten&quot;Rader med data&quot; i det Customer Journey Analytics-kontrakt som ditt företag signerade med Adobe.

   Detta ger det maximala antalet rader med data som tillåts i försäljningsordern. Om antalet rader med data som kom från steg 3 är större än det här talet, får du ett överskott.

1. Du kan åtgärda detta på flera sätt:

   * Ändra dina [inställningar för datalagring](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html#set-rolling-window-for-connection-data-retention).
   * [Ta bort oanvända anslutningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
   * [Ta bort en datauppsättning i AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
   * Kontakta kontohanteraren för Adobe om du vill licensiera ytterligare kapacitet.

## Skapa ett Workspace-projekt med alla händelsedata {#workspace-event-data}

1. Innan du skapar projektet i Workspace [skapa en datavy](/help/data-views/create-dataview.md) som hämtar in data från ALLA dina anslutningar och inte har några filter. Med andra ord innehåller den alla era data.

1. I Workspace skapar du ett nytt projekt och hämtar alla händelser (från **[!UICONTROL Metrics]** (listruta) för föregående månad.

   ![Händelser](assets/events-usage.png)

1. gör detta

## Skapa en rapport i CJA API {#api-report}

Använd [CJA-rapporterings-API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) för att köra en rapport om alla dina händelsedata.