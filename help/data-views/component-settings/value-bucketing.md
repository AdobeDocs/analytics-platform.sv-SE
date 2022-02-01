---
title: Inställningar för värdepaketeringskomponenter
description: Kombinera numeriska värden i en dimension.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: c36dddb31261a3a5e37be9c4566f5e7ec212f53c
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 1%

---

# [!UICONTROL Value Bucketing] komponentinställningar

När du skapar eller redigerar en datavy kan du med värdeberäkning kombinera numeriska värden som baseras på ett intervall. Den är bara tillgänglig för dimensioner med datatyperna Heltal eller Dubbelt schema.

Värdeberäkning är värdefull när du vill gruppera intervall i stället för att behandla varje unikt nummer som en separat dimensionspost. Till exempel visas en hink på Mellan 5 och upp till 10 som ett radobjekt på 5 till 10 i Analysis Workspace.

![Värdebuckning](../assets/value-bucketing.png)

Om du vill ha flexibiliteten att kunna rapportera om både en fast och en icke-paketerad dimension, drar du två kopior av komponenten till listan med tillgängliga dimensioner. Aktivera blockering för en dimension och inaktivera den för en annan.

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Bucket value] | En kryssruta där du kan aktivera bucketning. |
| [!UICONTROL Less than] | Den övre gränsen för den första dimensionsmarkeringen. |
| [!UICONTROL Including] [!UICONTROL and less than] | Gränser för efterföljande bucklor. |
| [!UICONTROL Greater than or equal to] | Den nedre gränsen för den sista dimensionskassetten. |
| [!UICONTROL Add bucket] | Gör att du kan lägga till ytterligare en bucket i en numerisk dimensionsbucketning. Du kan lägga till upp till 20 bucklor i en enda dimension. |
