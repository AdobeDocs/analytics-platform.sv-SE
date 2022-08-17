---
title: Etiketter och profiler
description: Lär dig hur dataetiketter och principer som definieras i AEP påverkar datavyer och rapporter i CJA.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Etiketter och profiler

När du skapar en datauppsättning i Experience Platform kan du skapa [etiketter för dataanvändning](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) för vissa eller alla element i datauppsättningen. Hittills har dessa etiketter inte exponerats i CJA. I den här versionen kan du visa dessa etiketter och profiler i CJA.

Dessa är av särskilt intresse för CJA:

* The `C8` etikett - **[!UICONTROL No measurement]**. Den här etiketten anger att data inte kan användas för analys på organisationens webbplatser eller i appar.

* The `C12` etikett - **[!UICONTROL No General Data Export]**. Schemafält med den här etiketten kan inte exporteras eller hämtas från CJA (via rapportering, export, API, osv.)

Etikettering i sig innebär inte att dessa dataanvändningsetiketter används. Det är det policyer används för. Du skapar dina profiler via [API för principtjänst](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) i Experience Platform.

Två Adobe-definierade policyer används i CJA och påverkar rapportering och hämtning/delning:

* **[!UICONTROL Enforce Analytics]** policy
* **[!UICONTROL Enforce Download]** policy

## Visa dataetiketter i CJA-datavyer

Dataetiketter som har skapats i Experience Platform visas på tre platser i användargränssnittet för datavyer:

| Plats | Beskrivning |
| --- | --- |
| Informationsknappen i ett schemafält | Om du klickar på den här knappen visas [!UICONTROL Data Usage Labels] gäller för närvarande ett fält:<p>![](assets/data-label-left.png) |
| Höger räl under [Komponentinställningar](/help/data-views/component-settings/overview.md) | Alla [!UICONTROL Data Usage Labels] är listade här:<p>![](assets/data-label-right.png) |
| Lägg till dataetiketter som en kolumn | Du kan lägga till [!UICONTROL Data Usage Labels] som en kolumn till [!UICONTROL Included Components] kolumner i datavyer. Klicka bara på ikonen för kolumnväljaren och välj **[!UICONTROL Data Usage Labels]**:<p>![](assets/data-label-column.png) |

{style=&quot;table-layout:auto&quot;}

## Filtrera på datastyrningsetiketter i datavyer

Klicka på filterikonen i det vänstra spåret i redigeraren för datavyer och filtrera datavykomponenter efter **[!UICONTROL Data Governance]** och typ av **[!UICONTROL Label]**:

![](assets/filter-labels.png)

Klicka **[!UICONTROL Apply]** för att se vilka komponenter som har etiketter kopplade till sig.

## Filtrera på datastyrningsprinciper i datavyer

Du kan kontrollera om en profil är aktiverad som blockerar användningen av vissa CJA-datavytelement för analys eller export.

Klicka igen på filterikonen i den vänstra listen och under **[!UICONTROL Data Governance]**, klicka **[!UICONTROL Policies]**:

![](assets/filter-policies.png)

Klicka **[!UICONTROL Apply]** för att se vilka profiler som är aktiverade.

## Hur aktiverade profiler påverkar datavyer

Om **[!UICONTROL Enforce Analytics]** eller **[!UICONTROL Enforce Download]** profiler är aktiverade. De schemakomponenter som har vissa dataetiketter (till exempel C8 eller C12) kopplade till sig kan inte läggas till i datavyer.

Dessa komponenter är nedtonade i den vänstra listen [!UICONTROL Schema fields] lista:

![](assets/component-greyed.png)

Du kan inte heller spara en datavy som innehåller blockerade fält.

>[!MORELIKETHIS]
>[Hämta känsliga data](/help/analysis-workspace/curate-share/download-send.md)

>[!MORELIKETHIS]
>[Vad är begränsade etiketter i Report Builder?](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/restricted-labels.html?lang=en)

