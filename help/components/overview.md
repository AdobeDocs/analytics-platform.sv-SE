---
title: Vad är komponenter i Customer Journey Analytics?
description: Lär dig vilka komponenter Customer Journey Analytics har och hur du kan använda dem vid rapportering.
exl-id: f9b0b3c2-7c88-4bef-af33-0d309cafe799
solution: Customer Journey Analytics
feature: Components
role: User
source-git-commit: c91ee21a3d4e20e3bdaeb75f2011ede6eee6cba0
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 2%

---

# Komponenter - översikt

Komponenter är funktioner i Customer Journey Analytics som kan användas i visualiseringar (t.ex. Freeform table) eller som komplement till rapporteringsfunktioner.

Så här hanterar du komponenter från Customer Journey Analytics huvudgränssnitt:

1. Välj **[!UICONTROL Components]** i det övre fältet.
1. Välj **[!UICONTROL Components]** om du vill se en översikt över de komponenter som du kan hantera, eller markera komponenten som du vill hantera direkt på menyn.

Du kan hantera följande komponenter:

* [Segment](segments/seg-overview.md): Skapa, hantera, dela och tillämpa kraftfulla, fokuserade målgruppssegment i dina rapporter. Med segment kan du identifiera delmängder av personer baserat på egenskaper eller interaktioner.
* [Beräknade mått](calc-metrics/calc-metr-overview.md): Använd mått och formler som nya komponenter för rapportering
* [Datumintervall](date-ranges/create.md): Anpassa och förfina datumintervall som Analysis Workspace erbjuder.
* [Anteckningar](/help/components/annotations/overview.md): Kommunicera kontextuella datanunkter och insikter till din organisation.
* [Intelligenta aviseringar](/help/components/c-intelligent-alerts/intelligent-alerts.md): Gör att du kan meddelas baserat på ändrade procentsatser eller specifika datapunkter.
* [Schemalagda projekt](/help/analysis-workspace/export/t-schedule-report.md#scheduled-projects-manager): Hantera dina schemalagda projekt.
* [Inställningar](/help/analysis-workspace/user-preferences.md): Hantera inställningarna för Analysis Workspace.
* [Publiker](/help/components/audiences/audiences-overview.md): Skapa och publicera målgrupper från Customer Journey Analytics till [Real-Time Customer Data Platform](https://experienceleague.adobe.com/sv/docs/experience-platform/profile/home) i Experience Platform för målinriktning och personalisering.
* [Exportera](/help/components/exports/manage-export-locations.md): Hantera ditt exportkonto och platser.


## Analysis Workspace-komponenter

Komponenterna i Analysis Workspace består av mått, dimensioner, segment och datumintervall som du kan dra och släppa på paneler och visualiseringar i ditt Workspace-projekt. Anpassade komponenter som du skapar läggs till i panelerna, till exempel ett beräknat mått eller ett anpassat datumintervall.

Om du vill öppna panelen Komponenter väljer du ![Kurva](/help/assets/icons/Curate.svg) **[!UICONTROL Components]** på knapppanelen.

![Panelen Workspace markerar komponentikonen i den vänstra listen](assets/components.png)

Mer information om hur du använder komponenter i ett projekt finns i [Skapa ett projekt](/help/analysis-workspace/home.md).


## Hantera komponenter {#actions}

Du kan snabbt skapa en ny komponent via menyn **[!UICONTROL Components]** i Analysis Workspace. Mer information finns på [Analysis Workspace-menyn](/help/analysis-workspace/home.md#menu).

Du kan hantera komponenter (individuellt eller genom att markera flera).

1. Markera en eller flera komponenter.

1. Välj någon av följande åtgärder på snabbmenyn eller från ![MoreVertical](/help/assets/icons/MoreVertical.svg) Component actions-knappen (längst upp i Komponenter).


   >[!TIP]
   >
   >Du kan markera flera komponenter genom att hålla ned **[!UICONTROL Shift]**, eller genom att hålla ned **[!UICONTROL Command]** (i macOS) eller **[!UICONTROL Ctrl]** (i Windows).


   ![Komponentåtgärdslista med tagg, favorit, godkänn, dela och ta bort.](assets/component-menu.gif){width=100%}

   | Komponentåtgärd | Beskrivning |
   |--- |--- |
   | ![Etikett](/help/assets/icons/Label.svg) [!UICONTROL **Tagg**] | Ordna eller hantera komponenter genom att lägga till taggar i dem. Du kan sedan söka efter tagg i den vänstra panelen genom att välja filtret ![Filter](/help/assets/icons/Filter.svg) eller genom att skriva `#`. Taggar fungerar också som filter i komponenthanterarna. |
   | ![Stjärna](/help/assets/icons/Star.svg) [!UICONTROL **Favorit**] | Lägg till komponenten i listan med favoriter. Precis som med taggar kan du söka efter Favoriter i den vänstra panelen och filtrera efter dem i komponenthanterarna. |
   | ![StarOutline](/help/assets/icons/StarOutline.svg) **[!UICONTROL Un-favorite]** | Ta bort komponenten från favoritlistan. |
   | ![Markering](/help/assets/icons/Checkmark.svg) [!UICONTROL **Godkänn**] | Markera komponenter som godkända för att signalera till användarna att komponenten är godkänd för organisationen. Precis som med taggar kan du söka efter och filtrera efter Godkänd i den vänstra panelen. En ![bock](/help/assets/icons/Checkmark.svg) identifierar godkända komponenter. |
   | ![Dela](/help/assets/icons/ShareAlt.svg) [!UICONTROL **Dela**] | Dela komponenter med användare i organisationen. Det här alternativet är endast tillgängligt för anpassade komponenter, till exempel segment eller beräknade värden. |
   | ![Ta bort](/help/assets/icons/Delete.svg) [!UICONTROL **Ta bort**] | Ta bort komponenter som du inte längre behöver. Det här alternativet är endast tillgängligt för anpassade komponenter, till exempel segment eller beräknade värden. |

Anpassade komponenter kan också hanteras med respektive komponenthanterare. Se till exempel [Hantera segment](/help/components/segments/seg-manage.md).

## Hantera komponentlistan

Du kan söka efter, filtrera och sortera komponentlistan på den vänstra panelen i Analysis Workspace för att hitta en viss komponent.

### Sök

1. Välj ikonen **Komponenter** ![Komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) i den vänstra panelen.

2. I sökfältet börjar du skriva namnet på komponenten som du vill använda i ditt projekt.

   En färg och ikon identifierar komponenttypen. **Dimensioner** ![Dimension-ikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) är orange, **Segment** ![Segmentikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) är blå, **Datumintervall** ![Datumintervallikon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) är lila och **Mätvärden** ![Mätningsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) är gröna.<br/>Adobe-ikonen ![AdobeLogo](/help/assets/icons/AdobeLogoSmall.svg) anger antingen en beräkningsmall eller en segmentmall. Beräkningsikonen ![Beräkningsikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) anger ett beräknat mätvärde som en administratör i organisationen har skapat.

3. Välj komponenten i listrutan.

### Filter

1. Välj ikonen **Komponenter** ![Komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) i den vänstra panelen.

2. Välj **Filtrera** ![Ikonen för dataordlistefilter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) eller ange `#` i sökfältet.

3. Välj något av följande filteralternativ för att filtrera komponentlistan:

   | Ikon | Filteralternativ | Beskrivning |
   |---------|---|----------|
   | ![Markering](/help/assets/icons/Checkmark.svg) | **[!UICONTROL Approved]** | Visa endast komponenter som har markerats som Godkänd av en administratör. |
   | ![Stjärna](/help/assets/icons/Star.svg) | **[!UICONTROL Favorites]** | Visa endast komponenter som finns i din favoritlista. <br/>Mer information om hur du lägger till komponenter i din favoritlista finns i [Hantera komponenter](#manage-components). |
   | ![Dimensioner](/help/assets/icons/Dimensions.svg) | **[!UICONTROL Dimensions]** | Visa endast komponenter som är dimensioner. |
   | ![Händelse](/help/assets/icons/Event.svg) | **[!UICONTROL Metrics]** | Visa endast komponenter som är mätvärden. |
   | ![Segmentering](/help/assets/icons/Segmentation.svg) | **[!UICONTROL Segments]** | Visa endast komponenter som är segment. |
   | ![Kalender](/help/assets/icons/Calendar.svg) | **[!UICONTROL Date ranges]** | Visa endast komponenter som är datumintervall. |
   | ![Etikett](/help/assets/icons/Label.svg) | **[!UICONTROL *Märkordsnamn *]** | Visa bara komponenter med de valda taggarna. Det finns en dedikerad tagg för Adobe Template som är de [beräknade standardmåtten](/help/components/calc-metrics/default-calcmetrics.md) från Adobe. |

   Välj ![CrossSize75](/help/assets/icons/CrossSize75.svg) i ett filter för att ta bort filtret.

4. Du kan sortera komponentlistan enligt beskrivningen i [Sortera komponentlistan](#sort-the-component-list).

### Sortera

<!-- {{release-limited-testing-section}}-->

1. (Valfritt) Tillämpa eventuella filter på komponentlistan enligt beskrivningen i [Filtrera komponentlistan](#filter-the-component-list).

2. Välj ikonen **Komponenter** ![Komponenter](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Curate_18_N.svg) i den vänstra panelen.

3. Välj **Sortera** ![Sortera komponentikonen](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) och välj sedan något av följande filteralternativ för att sortera komponentlistan.

Följande sorteringsalternativ är tillgängliga:

{{components-sort-options}}

## Åtkomstbehörigheter

I Analysis Workspace kan administratörer [kontrollera](/help/analysis-workspace/curate-share/curate.md) vilka komponenter som exponeras för användare vid rapportering.
