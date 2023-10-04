---
description: I Beräknad måtthanterare kan du strukturera mätvärden på många olika sätt, t.ex. dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.
title: Hanterare för beräknade mätvärden
feature: Calculated Metrics
exl-id: 8b257ecc-a596-4b34-ac26-eda16835f1ba
source-git-commit: 34588ccd39d7464387197a0b4bfd6a9e416bd9c0
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 2%

---

# Beräknat måttansvarig

På sidan Beräknade mätvärden kan du strukturera mätvärden på många olika sätt, t.ex. dela, filtrera, tagga, godkänna, kopiera, ta bort och markera som favoriter.

Den beräknade metriska hanteraren visar alla filter som du äger och som har delats med dig. Användare på administratörsnivå kan se alla anpassade värden i organisationen. I den här översikten visas användargränssnittet och funktionerna i hanteraren för beräknade mätvärden.

![](assets/calc-metric-manager.png)

## Få åtkomst till hanteraren för beräknade värden

1. I Customer Journey Analytics väljer du [!UICONTROL **Komponenter**] > [!UICONTROL **Beräknade mått**].

## Tillgängliga åtgärder i hanteraren för beräknade värden

I Calculated Metrics Manager kan du:

* [Filtrera beräknade värden](/help/components/calc-metrics/cm-workflow/cm-filter.md)

* [Markera beräknade värden som favoriter](/help/components/calc-metrics/cm-workflow/cm-favorite.md)

* [Godkänna beräknade mätvärden](/help/components/calc-metrics/cm-workflow/cm-approving.md)

* [Tagga beräknade mätvärden](/help/components/calc-metrics/cm-workflow/cm-tagging.md)

* [Dela beräknade mätvärden](/help/components/calc-metrics/cm-workflow/cm-sharing.md)

* Exportera ett beräknat mått till en CSV-fil.

* [Kopiera beräknade värden](/help/components/calc-metrics/cm-workflow/cm-copy.md)

* Ta bort beräknade värden

## Konfigurera kolumner

Du kan konfigurera informationen som visas för varje beräknat mått i hanteraren för beräknade mått genom att konfigurera kolumnerna som visas.

Så här konfigurerar du synliga kolumner i hanteraren för beräknade mått:

1. I Customer Journey Analytics väljer du **[!UICONTROL Components]** tabbtangenten och sedan välja **[!UICONTROL Calculated metrics]**.

1. Välj alternativet **Anpassa kolumner** icon ![Ikonen Anpassa kolumner](assets/customize-columns-icon.png)markerar du de kolumner som du vill ska visas i Beräknat mått-hanteraren.

   Följande kolumner är tillgängliga:

   | Kolumnrubrik | Beskrivning |
   |---|---|
   | Favoriter | Visar stjärnikoner bredvid varje beräknat mätvärde, så att du kan markera beräknade mätvärden som favoriter. Mer information finns i [Markera beräknade värden som favoriter](/help/components/calc-metrics/cm-workflow/cm-favorite.md). |
   | Titel och beskrivning | Dessa värden finns i verktyget Beräknade mått. Om du vill redigera titeln och beskrivningen markerar du titellänken för att öppna verktyget Beräknade mätvärden. |
   | Rapportsvit | Anger i vilken rapportsvit mätvärdena senast sparades. |
   | Ägare | Anger vem som äger det anpassade måttet. Som icke-administratör kan du bara se mätvärden som du äger eller de som delats med dig. |
   | Taggar | Visar taggar som har tillämpats på måttet, antingen av dig eller av personer som har delat det beräknade måttet med dig. |
   | Delas med | Visar enskilda personer eller grupper (endast admin) eller Alla (endast admin) som du har delat det beräknade måttet med. <p>När ett beräknat mått delas visas en delningsikon bredvid det beräknade måttnamnet.</p> |
   | Ändrat den | Anger det datum då det anpassade måttet senast ändrades. |
   | Används i | Visar hur många komponenter det beräknade måttet används i. <p>Om det beräknade måttet till exempel används i 40 projekt och 2 varningar visas värdet för den här kolumnen som [!UICONTROL **42 komponenter**].</p> <p>Välj värdet i den här kolumnen för att se hur det beräknade mätvärdet används (till exempel [!UICONTROL **Projekt (40)**], [!UICONTROL **Varningar (2)**]).</p><p>Beräknade mätvärden kan användas i följande komponenttyper:</p> <ul><li>Projekt</li><li>Schemalagda projekt</li></ul><p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen, var den används och om den behöver tas bort eller ändras.</p><p>Den här informationen inkluderar inte användning från API, Report Builder eller Data Warehouse.</p><p>Du kan använda [Dataordlista](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i organisationen.</p><p>The [!UICONTROL **Används i**] -kolumnen visas inte som standard. [Konfigurera kolumner](#configure-columns) för att visa den.</p> |
   | Senast använd | Visar datumet då det beräknade måttet senast användes i någon av följande komponenttyper: <ul><li>Beräknade värden</li><li>Projekt</li><li>Schemalagda projekt</li></ul> <p>Den här informationen kan hjälpa dig att avgöra om en komponent är värdefull för användare i organisationen eller om den ska tas bort.</p><p>Denna information inkluderar inte användning från API:t eller Report Builder.</p><p>Du kan använda [Dataordlista](/help/components/data-dictionary/data-dictionary-overview.md) tillsammans med den här informationen för att hjälpa dig att hålla reda på och bättre förstå hur komponenter används i organisationen. |

   {style="table-layout:auto"}
