---
title: Tidslinjevy
description: Utforska mönster i sessionsaktivitet.
feature: Guided Analysis
keywords: produktanalys
role: User
source-git-commit: ecdbe1b68aa0824bd9db4acefd3ef9059d9ac927
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# [!UICONTROL Timeline] visa

The **[!UICONTROL Timeline]** kan du analysera enskilda sessioner för att fastställa mönster i beteendet. Med rätt spår kan du välja det person-ID som du vill analysera. I mittområdet visas tid, markerat egenskapsvärde och varaktighet för varje händelse som personen utför.

Den här analysen kräver att du lägger till **[!UICONTROL Person ID]** standardkomponent till [datavy](/help/data-views/component-reference.md#optional). Om du inte har [!UICONTROL Person ID] som lagts till i datavyn visas följande meddelande:

> Egenskapen PersonID krävs för den här analysen. Lägg till person-ID i datavyn.

## Användningsexempel

Exempel:

* **Friktionsprospektering**: Om du hittar ett brant fall i dialogrutan [Funktion](friction.md) kan du undersöka möjliga orsaker till den släppningen i den här vyn.
* **Felbeteende**: Om en användare råkar ut för ett fel i din produkt kan du utforska vad användaren gör före eller efter det att felet har inträffat.
* **Validering av datainsamling**: Dataadministratörer kan filtrera den här vyn för att isolera sig själva. Den här vyn är ett bra sätt att se till att implementeringen i organisationen fungerar som förväntat.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Property]**: Den egenskap som du vill visa värden för. Sessionsanalysen i mitten visar värden för den egenskap som valts här. Du kan också filtrera data efter den valda egenskapen. Giltiga operatorer för filtret inkluderar [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists]och [!UICONTROL Does not exist].
* **[!UICONTROL Segments]**: Det segment som du vill mäta. Det valda segmentet filtrerar data så att de bara fokuserar på de personer som matchar dina segmentkriterier. Ett segment stöds för den här vyn.

## Diagraminställningar

The [!UICONTROL Timeline] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Show as]**: Visar önskade egenskapsvärden.
   * [!UICONTROL Show all]
   * [!UICONTROL Highlight]
   * [!UICONTROL View only]

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa trenddata efter. Den här inställningen påverkar inte vyer som inte är trendade, t.ex. tidslinjen.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
