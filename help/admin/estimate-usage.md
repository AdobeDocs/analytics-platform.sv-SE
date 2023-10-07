---
title: Visa och hantera användningen av Customer Journey Analytics
description: Visar två metoder för att beräkna användningen och en metod för att hantera den.
role: Admin
feature: Basics
exl-id: 7a5d1173-8d78-4360-a97a-1ab0a60af135
source-git-commit: 16f1a732260ace8393d7303134fc351740fd1661
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 0%

---

# Visa och hantera användningen av Customer Journey Analytics

Om du vill visa hur Customer Journey Analytics används kan du använda flera olika metoder:

* Lägg till händelsedataraderna för varje anslutning. Se [Beräkna anslutningsstorlek](#estimate size) nedan. Det här är ett enkelt sätt att se data för händelseraden, per anslutning, för en viss tidsstämpel.
* Se din användning på tre sätt, som beskrivs närmare nedan:
   * Använd Analysis Workspace för att rapportera om förra månadens händelser.
   * Använd Report Builder för att rapportera händelser förra månaden.
   * Använd Customer Journey Analytics-API:t för att skapa en automatiserad rapport.

Så här hanterar du användningen av Customer Journey Analytics:

* Definiera ett rullande datafönster.

## Beräkna anslutningsstorlek {#estimate-size}

Du kan behöva veta hur många rader med händelsedata du har i [!UICONTROL Customer Journey Analytics]. Gör så här för att få en korrekt redovisning av hur din organisation använder händelsedatarader **för var och en av de anslutningar som din organisation har skapat**.

>[!NOTE]
>
>Gör detta den första fredagen i varje månad, eftersom Adobe kör din senaste användningsrapport den dagen.

1. I [!UICONTROL Customer Journey Analytics]klickar du på **[!UICONTROL Connections]** -fliken.

   Nu kan du se en lista över alla dina aktuella anslutningar.

1. Klicka på varje anslutningsnamn för att komma till Anslutningshanteraren.

1. Lägg till **[!UICONTROL Records of event data available]** för varje anslutning som din organisation har skapat. (Beroende på storleken på anslutningen kan det ta en stund innan numret visas.)

   ![Tillgängliga poster med händelsedata.](./assets/event-data.png)

   >[!CAUTION]
   >
   >   Detta antal gäller endast händelsedata, inte profil- eller sökdata. Om du har profil- och sökdata kommer antalet att vara något högre. Det finns dock för närvarande inget sätt att rapportera om användningen av profil- och sökdata i användargränssnittet. Den här funktionen är särpresenterad för 2023.

1. När du har angett summan av alla händelsedatarader ska du slå upp behörigheten&quot;Rader med data&quot; i det Customer Journey Analytics-kontrakt som ditt företag signerade med Adobe.

   Detta ger det maximala antalet rader med data som tillåts i försäljningsordern. Om antalet rader med data som kom från steg 3 är större än det här talet, får du ett överskott.

1. Du kan åtgärda detta på flera sätt:

   * Ändra dina [inställningar för datalagring](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/manage-connections.html#set-rolling-window-for-connection-data-retention).
   * [Ta bort oanvända anslutningar](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
   * [Ta bort en datauppsättning i Adobe Experience Platform](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#implications-of-deleting-data-components).
   * Kontakta kontoteamet på Adobe om du vill licensiera ytterligare kapacitet.

## Skapa ett Workspace-projekt med alla händelsedata {#workspace-event-data}

Med den här metoden kan du göra en djupare analys av dina användningsdata och historiken över din användning.

1. Innan du skapar projektet i Workspace [skapa en datavy](/help/data-views/create-dataview.md) för var och en av anslutningarna, utan att några filter tillämpas.

>[!WARNING]
>
>    Skapa inte en ny anslutning som omfattar alla data bara för att mäta användningen, eftersom det effektivt skulle fördubbla användningen.

1. Skapa nya projekt baserat på varje datavy i arbetsytan och dra in alla händelser (från **[!UICONTROL Metrics]** nedrullningsbar lista) fram till den första fredagen i månaden, med början den första dagen i ditt nuvarande Customer Journey Analytics-kontrakt.

   ![Frihandsregister med händelser.](./assets/events-usage.png)

   Då får du en bra uppfattning om hur din användning går från månad till månad.

1. Beroende på dina behov kan du gå nedåt efter datauppsättning, osv.

## Skapa ett datablock i Report Builder {#arb}

I REPORT BUILDER [skapa ett datablock](/help/report-builder/create-a-data-block.md) för varje datavy och sedan summera dem.

## Skapa en automatiserad rapport i Customer Journey Analytics API {#api-report}

1. Använd [API för Customer Journey Analytics-rapportering](https://developer.adobe.com/cja-apis/docs/api/#tag/Reporting-API) för att köra en rapport om alla dina händelsedata, **för alla anslutningar**. Konfigurera detta så att rapporten körs

   * varje fredag varje månad.
   * till första dagen i ditt nuvarande Customer Journey Analytics-kontrakt.

   Då får du en bra uppfattning om hur din användning går från månad till månad. Då får du det totala antalet rader på alla dina Customer Journey Analytics-anslutningar.

1. Använd Excel för att anpassa rapporten ytterligare.

## Hantera din användning genom att definiera ett rullande datafönster {#rolling}

Om du vill hantera din användning [anslutningsgränssnitt](/help/connections/create-connection.md) Med kan du definiera datalagring i Customer Journey Analytics som ett rullande fönster på anslutningsnivå i månader (1 månad, 3 månader, 6 månader osv.).

Den största fördelen är att du bara lagrar eller rapporterar data som är tillämpliga och användbara och tar bort äldre data som inte längre är användbara. Det hjälper er att hålla er inom avtalsgränserna och minskar risken för överlagringskostnader.

Om du låter standardvärdet vara (omarkerat) ersätts kvarhållningsperioden av Adobe Experience Platform datalagringsinställning. Om du har 25 månaders data i Experience Platform får Customer Journey Analytics 25 månaders data genom förifyllning. Om du raderade 10 av dessa månader i Platform behåller Customer Journey Analytics de återstående 15 månaderna.

Datalagringen baseras på tidsstämplar för händelsedatamängder och gäller endast för händelsedatamängder. Det finns ingen inställning för rullande datafönster för profil- eller uppslagsdatauppsättningar eftersom det inte finns några tillämpliga tidsstämplar. Om din anslutning innehåller någon profil- eller sökdatamängd, eftersom de har förenats med händelsedatamängder, behålls data i Customer Journey Analytics baserat på dina datalagringsinställningar för händelsedatamängdens tidsstämplar.

