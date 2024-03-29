---
title: Etiketter och profiler
description: Lär dig hur dataetiketter och principer som definieras i Adobe Experience Platform påverkar datavyer och rapporter i Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 46d799ad2621d83906908a3f60a59a1027c6518c
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 0%

---

# Etiketter och profiler

När du skapar en datauppsättning i Experience Platform kan du skapa [etiketter för dataanvändning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html) för vissa eller alla element i datauppsättningen. Du kan visa dessa etiketter och profiler i Customer Journey Analytics.

Följande etiketter är av särskilt intresse för Customer Journey Analytics:

* The `C8` etikett - **[!UICONTROL No measurement]**. Den här etiketten anger att data inte kan användas för analys på organisationens webbplatser eller i appar.

* The `C12` etikett - **[!UICONTROL No General Data Export]**. Schemafält med den här etiketten kan inte exporteras eller hämtas från Customer Journey Analytics (via rapportering, export, API, osv.)

>[!NOTE]
>
>Dataanvändningsetiketter sprids inte automatiskt till sammanslagna datauppsättningar. De kan dock läggas till manuellt.

Etikettering i sig innebär inte att dessa dataanvändningsetiketter används. Det är det policyer används för. Du skapar dina profiler med [Experience Platform UI](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html) eller via [API för principtjänst](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html) i Experience Platform.

Två Adobe-definierade policyer används i Customer Journey Analytics och påverkar rapportering och nedladdning/delning:

* **[!UICONTROL Enforce Analytics]** policy
* **[!UICONTROL Enforce Download]** policy

## Visa dataetiketter i datavyer i Customer Journey Analytics

Dataetiketter som har skapats i Experience Platform visas på tre platser i användargränssnittet för datavyer:

| Plats | Beskrivning |
| --- | --- |
| Info-knappen i ett schemafält | Om du klickar på den här knappen visas [!UICONTROL Data Usage Labels] gäller för närvarande ett fält:<p>![](assets/data-label-left.png) |
| Höger räl under [Komponentinställningar](/help/data-views/component-settings/overview.md) | Alla [!UICONTROL Data Usage Labels] är listade här:<p>![](assets/data-label-right.png) |
| Lägg till dataetiketter som en kolumn | Du kan lägga till [!UICONTROL Data Usage Labels] som en kolumn till [!UICONTROL Included Components] kolumner i datavyer. Klicka bara på ikonen för kolumnväljaren och välj **[!UICONTROL Data Usage Labels]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrera på datastyrningsetiketter i datavyer

Klicka på knappen [!UICONTROL filter] ikonen i det vänstra spåret och filtrera datavykomponenterna efter **[!UICONTROL Data Governance]** och typ **[!UICONTROL Label]**:

![](assets/filter-labels.png)

Klicka **[!UICONTROL Apply]** för att se vilka komponenter som har etiketter kopplade till sig.

## Filtrera på datastyrningsprinciper i datavyer

Du kan kontrollera om en profil är aktiverad som blockerar användningen av vissa datavytelement i Customer Journey Analytics för analys eller export.

Klicka igen på [!UICONTROL filter] ikonen i den vänstra listen och under **[!UICONTROL Data Governance]**, klicka **[!UICONTROL Policies]**:

![Filtrera inkluderade komponenter efter lista som visar Enforce Analytics valt](assets/filter-policies.png)

Klicka **[!UICONTROL Apply]** för att se vilka profiler som är aktiverade.

## Hur aktiverade profiler påverkar datavyer

Om **[!UICONTROL Enforce Analytics]** principen är aktiverad. De schemakomponenter som har vissa dataetiketter (till exempel C8) kopplade till sig kan inte läggas till i datavyer.

De här komponenterna är nedtonade i den vänstra listen [!UICONTROL Schema fields] lista:

![Greyed components and the Policies message indicating policies has applied to this field restrict use of the data](assets/component-greyed.png)

Du kan inte heller spara en datavy som innehåller blockerade fält.

>[!MORELIKETHIS]
>[Hämta känsliga data](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>[Vad är begränsade etiketter i Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html)


