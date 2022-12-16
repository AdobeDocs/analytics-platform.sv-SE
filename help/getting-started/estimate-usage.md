---
title: Beräkna och hantera din CJA-användning
description: Visar två metoder för att beräkna användningen och en metod för att hantera den.
role: Admin
feature: CJA Basics
source-git-commit: 58d582b693708f883842fb6a18cc57d481f2b2ab
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# Beräkna och hantera din CJA-användning

För att förstå hur CJA används kan du använda två metoder:

* Lägg till händelsedata för varje anslutning (se **Beräkna anslutningsstorlek** nedan)
* Använd Analysis Workspace till...

Så här hanterar du CJA-användningen:

* Använda CJA API

## Beräkna anslutningsstorlek {#estimate-size}

Du kan behöva veta hur många rader med händelsedata du har i [!UICONTROL Customer Journey Analytics]. Gör så här för att få en korrekt redovisning av hur din organisation använder händelsedatarader **för var och en av de anslutningar som din organisation har skapat**.

>[!NOTE]
>
>Gör detta den första fredagen i varje månad, eftersom Adobe kör din senaste användningsrapport den dagen.

1. I [!UICONTROL Customer Journey Analytics]klickar du på **[!UICONTROL Connections]** -fliken.

   Nu kan du se en lista över alla dina aktuella anslutningar.

1. Klicka på varje anslutningsnamn för att komma till Anslutningshanteraren.

1. Lägg till **[!UICONTROL Records of event data available]** för alla anslutningar som skapas. (Beroende på storleken på anslutningen kan det ta en stund innan numret visas.)

   ![händelsedata](assets/event-data.png)

1. När du har angett summan av alla händelsedatarader ska du slå upp behörigheten&quot;Rader med data&quot; i det Customer Journey Analytics-kontrakt som ditt företag signerade med Adobe.

   Detta ger det maximala antalet rader med data som tillåts i försäljningsordern. Om antalet rader med data som kom från steg 3 är större än det här talet, får du ett överskott.

1. Du kan åtgärda detta på flera sätt:

   * Ändra dina [inställningar för datalagring](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html#set-rolling-window-for-connection-data-retention).
   * [Ta bort oanvända anslutningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
   * [Ta bort en datauppsättning i AEP](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
   * Kontakta kontohanteraren för Adobe om du vill licensiera ytterligare kapacitet.
