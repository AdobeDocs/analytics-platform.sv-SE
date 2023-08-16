---
title: Sessionsinställningar
description: Inställningar i en datavy som du kan använda för att definiera längden på en session och utlösaren för att initiera en ny session
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 25ff6feda28f0447927a52f44aed800cdd89e0cb
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 0%

---


# Sessionsinställningar

Sessionsinställningarna i datavyer ändrar hur Customer Journey Analytics beräknar sessioner från data i anslutningen.

I **[!UICONTROL Settings]** Med datavyer kan ni definiera en session på vilket sätt som helst för att matcha hur personer interagerar med era digitala upplevelser. Definitioner av sessionsinställningar är icke-förstörande och ändrar inte underliggande data. Du kan skapa flera datavyer (där var och en har en egen specifik sessionsinställningsdefinition) som grund för dina Workspace-projekt.

Så här definierar du kontexten för en session för en datavy:

1. Välj **[!UICONTROL Data views]** i användargränssnittet i Customer Journey Analytics.

2. Skapa en ny eller redigera en befintlig datavy. Se [Skapa eller redigera en datavy](create-dataview.md) för mer information.

3. Välj **[!UICONTROL Settings]** -fliken. Under [!UICONTROL Session settings]:

   1. Ange ett värde för **[!UICONTROL Session timeout]** in [!UICONTROL minute(s)], [!UICONTROL hour(s)], [!UICONTROL day(s)], eller [!UICONTROL week(s)]. Sessionstimeout avgör hur lång tid en session kan vara ledig (inga händelser inträffar) innan en ny session startas.

      Använd en kort tidsgräns för sessioner (till exempel 30 minuter) om du är intresserad av att analysera huvudsakligen online-interaktioner. Om du till exempel analyserar om profiler som besöker din onlinebutik har lagt till produkter i kundvagnen eller till och med köpt online.

      Använd en lång tidsgräns för sessioner (t.ex. 3 månader) om du kombinerar online- och offlinedata och vill analysera om kunder som har köpt en eller flera av dina produkter har ringt till din kontaktgrupp inom de första tre månaderna efter köpet.


   2. Välj ett mått på menyn **[!UICONTROL Drop a metric here]** lista under **[!UICONTROL Start new session with a metric]**. Du kan också dra och släppa ett mått från den vänstra rutan på panelen **[!UICONTROL Drop a metric field]**. Det valda måttet definierar början på en ny session. Du kan definiera mer än ett mått.

      Du kan använda alla typer av mätvärden för att definiera en ny session. Tänk dig att du vill definiera en ny session varje gång en profil startar din mobilapp. I **[!UICONTROL Data view]** > **[!UICONTROL Components]** definierar du en komponent av typen metrisk, med namnet **[!UICONTROL Launches]**, baserat på en **[!UICONTROL appInteraction]** **[!UICONTROL Name]** schemafält. Du anger mer **[!UICONTROL Launches]** metrisk komponent som endast räknar värdet när värdet matchar `launch`.

      ![Komponenten App Interaction Metric Launches](assets/component-launches.png)

      Sedan drar och släpper du eller väljer **[!UICONTROL Launches]** mått som måttet för att definiera en ny session.

      ![Sessionsinställningar startas](assets/session-settings-launches-metric.png)



4. Välj **[!UICONTROL Save]** eller **[!UICONTROL Save and finish]** för att spara definitionen av sessionsinställningarna.

