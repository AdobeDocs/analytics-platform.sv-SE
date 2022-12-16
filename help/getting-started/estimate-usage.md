---
title: Beräkna och hantera din CJA-användning
description: Visar två metoder för att beräkna användningen och en metod för att hantera den.
role: Admin
feature: CJA Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: e8f5982ae073d4e3dca85b3054fd325cc40ff40a
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 0%

---

# Beräkna och hantera din CJA-användning

För att förstå hur CJA används kan du använda tre metoder:

* Lägg till händelsedataraderna för varje anslutning. (Se **Beräkna anslutningsstorlek** nedan) Det här är ett enkelt sätt att visa data för händelserader, per anslutning, för en viss tidsstämpel.
* Använd Analysis Workspace för att rapportera om förra månadens händelser. (Se **Skapa ett Workspace-projekt med alla händelsedata** nedan.) På så sätt kan ni göra en djupare analys av era användningsdata och av er användningshistorik.
* Använd CJA API för att skapa en automatiserad rapport. (Se **Skapa en rapport i CJA API** nedan.)

Så här hanterar du CJA-användningen:

* Definiera ett rullande datafönster. (Se nedan.)

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

1. I Workspace skapar du ett nytt projekt och hämtar alla händelser (från **[!UICONTROL Metrics]** (nedrullningsbar meny) fram till första fredagen i månaden, med början den första dagen i ditt aktuella CJA-kontrakt.

   ![Händelser](assets/events-usage.png)

   Då får du en bra uppfattning om hur din användning går från månad till månad.

1. Beroende på dina behov kan du gå nedåt efter datauppsättning, osv.


## Skapa en automatiserad rapport i CJA API {#api-report}

1. Använd [CJA-rapporterings-API](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) för att köra en rapport om alla dina händelsedata, **för alla anslutningar**. Konfigurera detta så att rapporten körs

   * var tredje fredag varje månad.
   * till första dagen i ditt CJA-kontrakt.

   Då får du en bra uppfattning om hur din användning går från månad till månad. Då får du det totala antalet rader på alla dina CJA-anslutningar.

1. Använd Excel för att anpassa rapporten ytterligare.

## Definiera ett rullande datafönster {#rolling}

Om du vill hantera din användning [anslutningsgränssnitt](/help/connections/create-connection.md) Med kan du definiera CJA-datalagring som ett rullande fönster på anslutningsnivå i månader (1 månad, 3 månader, 6 månader osv.).

Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader.

Om du låter standardvärdet vara (omarkerat) ersätts kvarhållningsperioden av Adobe Experience Platform datalagringsinställning. Om ni har 25 månaders data i Experience Platform får CJA 25 månaders data genom att fylla på dem. Om du raderade 10 av dessa månader i Platform behåller CJA de återstående 15 månaderna.

Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för rullande datafönster för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar. Om din anslutning innehåller en profil- eller uppslagsdatauppsättning (förutom en eller flera händelsedatamängder) kommer dessa data att lagras under samma tidsperiod.

