---
title: Sammanhangsmedvetna sessioner
description: Inställningar i en datavy som du kan använda för att definiera sammanhangsberoende sessioner.
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: 5e4bf2985a0ec75cc0120e2a9549d720077cd5cc
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 1%

---


# Sammanhangsmedvetna sessioner

Sammanhangsberoende sessioner i datavyer ändrar hur Customer Journey Analytics beräknar sessioner från data i anslutningen.

I [!UICONTROL Settings] Med datavyer kan ni definiera en session på vilket sätt som helst för att matcha hur personer interagerar med era digitala upplevelser. Kontextmedvetna sessionsdefinitioner är icke-förstörande och ändrar inte underliggande data. Du kan skapa flera datavyer - var och en med sin specifika kontextmedvetna sessionsdefinition - som grund för dina Workspace-projekt.

Så här definierar du kontexten för en session för en datavy:

1. Välj **[!UICONTROL Data views]** i användargränssnittet i Customer Journey Analytics.

1. Skapa en ny eller redigera en befintlig datavy. Se [Skapa eller redigera en datavy](create-dataview.md) för mer information.

1. Välj **[!UICONTROL Settings]** -fliken. Under [!UICONTROL Session settings]:

   1. Ange ett värde för **[!UICONTROL Session timeout]** in [!UICONTROL minute(s)], [!UICONTROL hour(s)], [!UICONTROL day(s)], eller [!UICONTROL week(s)]. Sessionstimeout avgör hur lång tid en session kan vara ledig (inga händelser inträffar) innan en ny session startas.

   2. Välj ett mått på menyn **[!UICONTROL Drop a metric here]** lista under [!UICONTROL Start new session with a metric]. Du kan också dra och släppa ett mått från den vänstra rutan på panelen **[!UICONTROL Drop a metric field]**. Det valda måttet definierar början på en ny session. Du kan definiera mer än ett mått.

1. Välj **[!UICONTROL Save]** eller **[!UICONTROL Save and finish]** för att spara den kontextmedvetna sessionsdefinitionen.

