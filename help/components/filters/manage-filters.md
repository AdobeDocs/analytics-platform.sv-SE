---
title: Filterhantering
description: Lär dig hantera filter i Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
role: User
source-git-commit: e84010b9ea9e6385574e8b1a04f7eccbba3ebc90
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Filterhantering

Filterhanteraren erbjuder många sätt att strukturera filter, som att dela, tagga, godkänna, kopiera, ta bort och markera som favoriter.

Filterhanteraren visar alla filter som du äger och som har delats med dig. Administratörsnivåanvändare kan se alla filter i organisationen. I den här översikten visas användargränssnittet och funktionerna i filterhanteraren.

![](assets/filter-manager-ui.png)

## Öppna Filterhanteraren

1. I Customer Journey Analytics väljer du fliken **[!UICONTROL Components]** och sedan **[!UICONTROL Filters]**.

## Tillgängliga åtgärder i Filterhanteraren

I Filterhanteraren kan du:

* [Filtrera filterlistan](/help/components/filters/filters-filter.md)

* [Markera filter som favoriter](/help/components/filters/filters-favorite.md)

* [Godkänn filter](/help/components/filters/filters-approve.md)

* [Taggfilter](/help/components/filters/filters-tag.md)

* [Dela filter](/help/components/filters/filters-share.md)

* Exportera ett filter till en CSV-fil.

* [Kopiera filter](/help/components/filters/filters-copy.md)

* Ta bort filter

## Konfigurera kolumner

Du kan konfigurera informationen som visas för varje filter i filterhanteraren genom att konfigurera kolumnerna som visas.

Så här konfigurerar du synliga kolumner i Filterhanteraren:

1. I Customer Journey Analytics väljer du fliken **[!UICONTROL Components]** och sedan **[!UICONTROL Filers]**.

1. I filterhanteraren väljer du ikonen **Anpassa kolumner** ![Anpassa kolumner](assets/customize-columns-icon.png) och markerar sedan de kolumner som du vill ska visas i filterhanteraren.

   Följande kolumner är tillgängliga:

   | Kolumnrubrik | Beskrivning |
   |---|---|
   | Titel och beskrivning | Dessa värden finns i filterverktyget. Om du vill redigera titeln och beskrivningen markerar du titellänken för att öppna filterverktyget. |
   | Favoriter | Visar stjärnikoner bredvid varje filter, så att du kan markera filtren som favoriter. Mer information finns i [Markera filter som favoriter](/help/components/filters/filters-favorite.md). |
   | Datavy | Den här kolumnen anger i vilken datavy filtret senast sparades. |
   | Ägare | Anger vem som äger filtret. Om du inte är administratör kan du bara se filter som du äger eller de som delats med dig. |
   | Taggar (inte incheckad i kolumnväljare, därför visas inte kolumnen) | Taggar som har tillämpats på filtret, antingen av dig eller av personer som delat filtret med dig. |
   | Delas med | Visar enskilda personer eller grupper (endast Admin) eller Alla (endast Admin) som du har delat filtret med. <p>När ett filter delas av dig eller med dig visas en delningsikon bredvid filternamnet.</p> |
   | Ändrat den | Visar datumet då filtret senast ändrades. |
   | Används i | Visar hur många komponenter som filtret används i. <p>Om filtret till exempel används i 40 projekt och 2 varningar visas värdet för den här kolumnen som [!UICONTROL **42 komponenter**].</p> <p>Markera värdet i den här kolumnen för att se hur filtret har delats upp (till exempel [!UICONTROL **Projekt (40)**], [!UICONTROL **Varningar (2)**]).</p><p>Filter kan användas i följande komponenttyper:</p> <ul><li>Beräknade mått</li><li>Projekt</li><li>Schemalagda projekt</li></ul><p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen inkluderar inte användning från API, Report Builder eller Data Warehouse.</li><li>Kolumnen [!UICONTROL **Används i**] visas inte som standard. [Konfigurera kolumner](#configure-columns) så att de visas.</li><li>Om det inte finns några data i den här kolumnen för en viss komponent, men den har datumet [!UICONTROL **Senast använd**], kan komponenten ha använts i en analys utan att sparas.</li><li>Den här informationen är endast tillgänglig för systemadministratörer.</li></ul><p>Du kan använda [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation.</p> |
   | Senast använd | Visar datumet då filtret senast användes i någon av följande komponenttyper: <ul><li>Beräknade mått</li><li>Projekt</li><li>Schemalagda projekt</li><li>Filter</li></ul> <p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen eller om den ska tas bort.</p><p>Tänk på följande när du visar den här kolumnen:</p><ul><li>Den här informationen inkluderar inte användning från API, Report Builder eller Data Warehouse.</li><li>För vissa komponenter kanske den här kolumnen inte innehåller data om komponenten senast användes före september 2023.</li><li>Den här informationen är endast tillgänglig för systemadministratörer.</li></ul><p>Du kan använda [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i din organisation. |

   {style="table-layout:auto"}
