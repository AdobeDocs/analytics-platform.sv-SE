---
title: Redigerare för delad komponent
description: Skapa eller redigera delade dimensioner och mätvärden.
source-git-commit: d2c6605cc440c293aca279c1583bac964055d277
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Redigerare för delad komponent

Med den delade komponentredigeraren kan du skapa eller redigera delade dimensioner och mätvärden. Den delar många gränssnittselement när [skapar eller redigerar en datavy](/help/data-views/create-dataview.md), men dessa gränssnitt är distinkta i syfte:

* Med datavykomponentens redigerare kan du skapa och redigera komponenter som är specifika för den datavyn. Du kan inte redigera delade dimensioner eller mätvärden i datavykomponentens redigerare. I det här gränssnittet kan delade dimensioner och mått identifieras med en ![ikon för delad komponent](/help/assets/icons/CCLibrary.svg) bredvid komponentnamnet.
* Med den delade komponentredigeraren kan du skapa och redigera delade dimensioner och mätvärden. Du kan inte redigera komponenter som tillhör en enskild datavy i den delade komponentredigeraren.

![Komponentredigeraren, bild](assets/component-editor.png)

I det övre högra hörnet finns tre knappar:

* **[!UICONTROL Close]** eller **[!UICONTROL Cancel]**: Om alla ändringar sparas stänger knappen **[!UICONTROL Close]** redigeraren. Om det finns ändringar som inte har sparats stänger knappen **[!UICONTROL Cancel] redigeraren utan att spara ändringarna.
* **[!UICONTROL Save]**: Sparar alla komponenter och håller redigeraren öppen.
* **[!UICONTROL Save and finish]**: Sparar alla komponenter och stänger redigeraren.

Gränssnittet innehåller tre huvudkolumner/avsnitt:

* **Schemafältväljare**: Leta reda på önskade schemafält och dra dem till det inkluderade komponentområdet.
   * **Anslutning**: Den aktiva anslutningen. Ändra den aktiva anslutningen i [hanteraren för delade mått](smd-overview.md).
   * **Listrutan Komponentlista**: Du kan välja mellan att välja [!UICONTROL Schema fields] (nya delade dimensioner och mått) eller [!UICONTROL Metrics & Dimensions] (befintliga delade komponenter).
   * **Sök**: Använd textsökningen ![Sök ikon](/help/assets/icons/Search.svg) för att hitta det önskade schemafältet eller den delade komponenten efter namn. Du kan också använda filtren ![Filterikon](/help/assets/icons/Filter.svg) för att begränsa komponentlistan. Filtret `Is not deprecated` är aktivt som standard.
   * **Skapa härlett fält**: Gör att du kan [skapa ett härlett fält](/help/data-views/derived-fields/derived-fields.md).
* **Inkluderade komponenter**: De komponenter som du konfigurerar att delas. När du skapar delade komponenter kan du dra mer än ett schemafält till det här området för att skapa flera komponenter samtidigt. När du redigerar delade komponenter kan du markera flera komponenter som ska redigeras, som visar alla markerade komponenter i det här området.
* **Komponentinställningar**: När du väljer en komponent i det inkluderade komponentområdet kan alla tillgängliga inställningar konfigureras i den här kolumnen. Se [Komponentinställningar](/help/data-views/component-settings/overview.md) för alla tillgängliga alternativ för mått och mått. Om du håller ned Skift och klickar på flera element i det inkluderade komponentområdet kan du redigera alla vanliga fält samtidigt.
