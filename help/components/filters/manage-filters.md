---
title: Filterhantering
description: Lär dig hantera filter i Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
feature: Filters
source-git-commit: 8d6dc1d220fc3719b13842e812aaf6ddc55ae47c
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 0%

---

# Filterhantering

Filterhanteraren erbjuder många sätt att strukturera filter, som att dela, tagga, godkänna, kopiera, ta bort och markera som favoriter.

Filterhanteraren visar alla filter som du äger och som har delats med dig. Administratörsnivåanvändare kan se alla filter i organisationen. I den här översikten visas användargränssnittet och funktionerna i filterhanteraren.

![](assets/filter-manager-ui.png)

## Öppna Filterhanteraren

1. I Customer Journey Analytics väljer du **[!UICONTROL Components]** tabbtangenten och sedan välja **[!UICONTROL Filters]**.

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

1. I Customer Journey Analytics väljer du **[!UICONTROL Components]** tabbtangenten och sedan välja **[!UICONTROL Filers]**.

1. I filterhanteraren väljer du **Anpassa kolumner** icon ![Ikonen Anpassa kolumner](assets/customize-columns-icon.png)markerar du de kolumner som du vill ska visas i Filterhanteraren.

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
   | Används i | **Obs!** Den här funktionen är i den begränsade testfasen och är kanske inte tillgänglig än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).<p>Visar i vilken av följande komponenttyper filtret används:</p> <ul><li>Beräknade värden</li><li>Projekt</li><li>Schemalagda projekt</li><li>Filter</li></ul> Om filtret till exempel används i 40 projekt och 2 beräknade värden visas den här kolumnen [!UICONTROL **Beräknade värden (2), projekt (40)**]. <p>Den här informationen kan hjälpa dig att avgöra om ett filter är värdefullt för användare i din organisation eller om det ska tas bort.</p><p>Denna information inkluderar inte användning från API:t eller Report Builder.</p><p>Du kan använda [Dataordlista](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i organisationen. |
   | Senast använd | **Obs!** Den här funktionen är i den begränsade testfasen och är kanske inte tillgänglig än i din miljö. Den här anteckningen tas bort när funktionen är allmänt tillgänglig. Mer information om Customer Journey Analytics finns i [Funktionsreleaser för Customer Journey Analytics](/help/release-notes/releases.md).<p>Visar datumet då filtret senast användes i någon av följande komponenttyper:</p> <ul><li>Beräknade värden</li><li>Projekt</li><li>Schemalagda projekt</li><li>Filter</li></ul> <p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen eller om den ska tas bort.</p><p>Denna information inkluderar inte användning från API:t eller Report Builder.</p><p>Du kan använda [Dataordlista](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i organisationen. |

   {style="table-layout:auto"}
