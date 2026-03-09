---
title: Sessionsinställningar
description: Läs mer om inställningarna i en datavy som du kan använda för att definiera längden på en session och utlösaren för att initiera en ny session
solution: Customer Journey Analytics
feature: Data Views
exl-id: 25710bf1-ec85-4a7d-a404-54549013cc2c
role: Admin
source-git-commit: 81e08ecb593b6ba789c479d0e648cbe7ba0a82d6
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---

# Sessionsinställningar {#session-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_settings_datapreview"
>title="Förhandsgranska data"
>abstract="Jämför data i den här datavyn med anslutningsdata. Procentandelen för förhandsgranskning baseras på det totala antalet i anslutningen från de **senaste 90 dagarna**.<br><br/>Om förhandsgranskningen inte läses in kan anslutningen fortfarande återfyllas."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-enable MD034 -->


I Customer Journey Analytics kan ni definiera en session på vilket sätt som helst för att matcha hur människor interagerar med era digitala upplevelser. Du konfigurerar sessionsinställningar i en datavy.

Definitioner av sessionsinställningar är icke-förstörande och ändrar inte underliggande data. Du kan skapa flera datavyer (där var och en har en egen specifik sessionsinställningsdefinition) som grund för dina Workspace-projekt.

Så här definierar du kontexten för en session i en datavy:

1. Välj **[!UICONTROL Data views]**, eventuellt från **[!UICONTROL Data management]**, i huvudnavigeringen för Customer Journey Analytics-gränssnittet.

1. Skapa en ny eller redigera en befintlig datavy. Mer information finns i [Skapa eller redigera en datavy](create-dataview.md).

1. Välj fliken **[!UICONTROL Settings]**. Under [!UICONTROL Session settings]:

   1. Ange ett värde för **[!UICONTROL Session timeout]** i [!UICONTROL minute(s)], [!UICONTROL hour(s)], [!UICONTROL day(s)] eller [!UICONTROL week(s)]. Sessionstimeout avgör hur lång tid en session kan vara ledig (inga händelser inträffar) innan en ny session startas.

      Använd en kort tidsgräns för sessioner (till exempel 30 minuter) om du är intresserad av att analysera huvudsakligen online-interaktioner. Om du till exempel analyserar om profiler som besöker din onlinebutik har lagt till produkter i kundvagnen eller till och med köpt online.

      Använd en lång tidsgräns för sessioner (t.ex. 3 månader) om du kombinerar online- och offlinedata och vill analysera om kunder som har köpt en eller flera av dina produkter har ringt till din kontaktgrupp inom de första tre månaderna efter köpet.

   1. Välj ett segment på den nedrullningsbara menyn **[!UICONTROL Add segments]** om du vill segmentera en datavy. Du kan också dra och släppa ett segment från ![Segmentering](/help/assets/icons/Segmentation.svg) **[!UICONTROL Segments]** i den vänstra rutan på **[!UICONTROL _Släpp ett segment här_]**.

      Endast de segment visas som delas, som du har åtkomst till, och som kan utvärderas baserat på de komponenter du har definierat för datavyn.

   1. Välj ett mått i listrutan **[!UICONTROL Start new session with a metric]** . Du kan också dra och släppa ett mått från ![Event](/help/assets/icons/Event.svg) **[!UICONTROL Metrics]** i den vänstra rutan på **[!UICONTROL _Släpp ett mätresultat här_]**. Det valda måttet definierar början på en ny session. Du kan definiera mer än ett mått.

      Du kan använda alla typer av mätvärden för att definiera en ny session. Tänk dig att du vill definiera en ny session varje gång en profil startar din mobilapp. I **[!UICONTROL Data view]** > **[!UICONTROL Components]** definierar du en komponent av typen metrisk, med namnet **[!UICONTROL Launch]**, baserat på ett **[!UICONTROL appInteraction]** **[!UICONTROL Name]** schemafält. Du anger sedan måttkomponenten **[!UICONTROL Launch]** så att endast värdet räknas när värdet matchar `launch`.

      ![Komponenten för mått för appinteraktion startar](assets/component-launches.png)

      Sedan drar och släpper du eller väljer måttet **[!UICONTROL Launch]** som måttenhet för att definiera en ny session.

      ![Sessionsinställningar startas](assets/session-settings-launches-metric.png)



1. Välj **[!UICONTROL Save]** eller **[!UICONTROL Save and finish]** om du vill spara definitionen av sessionsinställningarna.
