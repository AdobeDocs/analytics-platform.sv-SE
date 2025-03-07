---
title: Skapa en datavy i Customer Journey Analytics
description: Läs mer om rekommenderad sökväg när du uppgraderar från Adobe Analytics till Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 832f3f9a-1836-43ac-8185-f22ae0ded3aa
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 0%

---

# Skapa en datavy i Customer Journey Analytics {#upgrade-create-dataview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-dataview"
>title="Skapa en datavy i Customer Journey Analytics"
>abstract="En datavy är en behållare som är specifik för Customer Journey Analytics och som gör att du kan avgöra hur data från en anslutning ska tolkas.<br><br>Det tar några minuter att skapa datavyn i början, men det kan ta flera dagar att konfigurera varje dimension och mätvärde med de önskade komponentinställningarna. Om du ändrar de här inställningarna tillämpas de retroaktivt, så att din organisation kan finjustera dem med tiden."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-views/create-dataview.md -->

När du skapar en datavy måste du antingen skapa mått och mått från schemaelement eller använda standardkomponenter. De flesta schemaelement kan antingen vara en dimension eller ett mått, beroende på företagets behov. När du drar ett schemaelement till en datavy visas alternativ till höger, där du kan justera hur dimensionen eller måtten fungerar i Customer Journey Analytics.

Så här skapar du en datavy:

1. Logga in på [Customer Journey Analytics](https://analytics.adobe.com) och gå till fliken **[!UICONTROL Data views]**.

1. Välj **[!UICONTROL Create new data view]**. Du kan också välja en befintlig datavy i listan över datavyer för att redigera den.

1. På fliken [!UICONTROL **Konfigurera**] anger du ett namn för datavyn och konfigurerar dess grundläggande inställningar, komponenter och kalenderalternativ.

   Mer information om varje fält finns i [Konfigurera](/help/data-views/create-dataview.md#configure) i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).

   ![Konfigurera datavy](assets/dataview-configure.png)

1. Välj fliken [!UICONTROL **Komponenter**].

   På fliken [!UICONTROL **Komponenter**] anger du komponenterna i en datavy, vilket betyder att du kan skapa mått och mått från schemaelement. Du kan också använda standardkomponenter.

   ![Fliken Komponenter](assets/dataview-components.png)

1. Dra schemaelement från den vänstra listen från fliken [!UICONTROL **Komponenter**] till avsnittet [!UICONTROL **Metrisk**] eller [!UICONTROL **Dimensioner**]. Schemaelementen som du lägger till blir mått i datavyn.

   Mer information om vilka alternativ som är tillgängliga när du lägger till komponenter i en datavy finns i [Komponenter](/help/data-views/create-dataview.md#components) i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).

1. Välj fliken [!UICONTROL **Inställningar**]. Härifrån kan du konfigurera filter så att de tillämpas på hela datavyn och konfigurera sessionens tidsgräns och mått.

   Mer information om de alternativ som är tillgängliga när du konfigurerar inställningar för en datavy finns i [Inställningar](/help/data-views/create-dataview.md#settings) i [Skapa eller redigera en datavy](/help/data-views/create-dataview.md).

1. Välj **[!UICONTROL Save]** om du vill spara konfigurationen för datavyn.

1. När alla önskade inställningar har angetts väljer du **[!UICONTROL Save and finish]**.

{{upgrade-final-step}}
