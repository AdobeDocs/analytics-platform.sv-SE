---
title: Etiketter och profiler
description: Lär dig hur dataetiketter och principer som definieras i Adobe Experience Platform påverkar datavyer och rapporter i Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
source-git-commit: 4f1299595077a1756a6ad0c4f5ef5e0247ab4973
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 0%

---

# Etiketter och profiler

När du skapar en datauppsättning i Experience Platform kan du skapa [dataanvändningsetiketter](https://experienceleague.adobe.com/sv/docs/experience-platform/data-governance/labels/reference) för vissa eller alla element i datauppsättningen. Du kan visa dessa etiketter och profiler i Customer Journey Analytics.

Följande etiketter är av särskilt intresse för Customer Journey Analytics:

* Etiketten `C8` - **[!UICONTROL No measurement]**. Den här etiketten anger att data inte kan användas för analys på organisationens webbplatser eller i appar.

* Etiketten `C12` - **[!UICONTROL No general data export]**. Schemafält med den här etiketten kan inte exporteras eller laddas ned från Customer Journey Analytics (via rapportering, export, API osv.)

>[!NOTE]
>
>Dataanvändningsetiketter sprids inte automatiskt till sammanslagna datauppsättningar. De kan dock läggas till manuellt.

Etikettering i sig innebär inte att dessa dataanvändningsetiketter används. Det är det policyer används för. Du kan skapa principer med [Experience Platform-gränssnittet](https://experienceleague.adobe.com/sv/docs/experience-platform/data-governance/policies/user-guide) eller med [API:t för principtjänsten](https://experienceleague.adobe.com/sv/docs/experience-platform/data-governance/api/overview) i Experience Platform.

Det finns två Adobe-definierade profiler i Experience Platform som kan användas i Customer Journey Analytics och påverka rapportering och dataexport:

* principen **[!UICONTROL Restrict usage analytics and user based measurement]** som använder etiketten `C8` och
* **[!UICONTROL Restrict data export]**-princip, använder etiketten `C12`.

## Visa dataetiketter i datavyer i Customer Journey Analytics

Dataetiketter som du eller andra har skapat i Experience Platform visas på tre platser i användargränssnittet för datavyer:

| Plats | Beskrivning |
| --- | --- |
| Info-knappen i ett schemafält | Om du klickar på den här knappen visas vilket [!UICONTROL Data Usage Labels] som för närvarande gäller för ett fält:<p>![](assets/data-label-left.png) |
| Höger räl under [Komponentinställningar](/help/data-views/component-settings/overview.md) | Alla [!UICONTROL Data Usage Labels] listas här:<p>![](assets/data-label-right.png) |
| Lägg till dataetiketter som en kolumn | Du kan lägga till [!UICONTROL Data Usage Labels] som en kolumn i [!UICONTROL Included Components]-kolumnerna i datavyer. Välj bara ikonen för kolumnväljaren och välj **[!UICONTROL Data Usage Labels]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filtrera på datastyrningsetiketter i datavyer

I redigeraren för datavyer väljer du ikonen [!UICONTROL filter] i det vänstra spåret och filtrerar datavykomponenter efter **[!UICONTROL Data Governance]** och typen av **[!UICONTROL Label]**:

![](assets/filter-labels.png)

Klicka på **[!UICONTROL Apply]** för att se vilka komponenter som har etiketter kopplade till sig.

## Filtrera på datastyrningsprinciper i datavyer

Du kan kontrollera om en princip (till exempel en profil som du har skapat med namnet **[!UICONTROL Enforce Analytics]**) är aktiverad. Och om den policyn blockerar användningen av vissa datavyelement från Customer Journey Analytics för analys eller dataexport.

Välj ikonen [!UICONTROL filter] i den vänstra listen igen och välj **[!UICONTROL Data Governance]** under **[!UICONTROL Policies]**:

![Filtrera inkluderade komponenter efter lista med begränsad användningsanalys och valda användarbaserade mått](assets/filter-policies.png)

Klicka på **[!UICONTROL Apply]** för att se vilka profiler som är aktiverade.

## Hur aktiverade profiler påverkar datavyer

Om en eller flera profiler är aktiverade med C8- eller C12-etiketter, kan de schemakomponenter som har vissa dataetiketter använda inte läggas till i datavyer.

De här komponenterna är nedtonade i den vänstra listan med spår [!UICONTROL Schema fields]:

![Greyed components and the Policies message indicating policies has been applied to this field restrict use of the data](assets/component-greyed.png)

Du kan inte heller spara en datavy som innehåller blockerade fält.

Var försiktig och försök att använda etiketter för åtkomst och datastyrning (via policyer) på fält eller fältgrupper i Experience Platform, som du redan har komponenter definierade för i datavyn. Den här dialogrutan kanske visas.

![Felaktig](assets/violation.png)

Du måste först lösa konflikten (t.ex. ta bort komponenterna från datavyn).


>[!MORELIKETHIS]
>
>[Hämta känsliga data](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[Vad är begränsade etiketter i Report Builder?](https://experienceleague.adobe.com/sv/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


