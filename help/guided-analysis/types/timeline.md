---
title: Tidslinjevy
description: Observera sessionshändelser på användarnivå över tid för att hitta upplevelsemönster.
feature: Guided Analysis
keywords: produktanalys
role: User
source-git-commit: 6f3725653453e31244bfed34670782fe9d9c0c2f
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 0%

---

# [!UICONTROL Timeline] visa

The **[!UICONTROL Timeline]** I kan du observera sessionshändelser på användarnivå över tid för att hitta upplevelsemönster och förmedla bättre användarberättelser. Med den vänstra listen kan du filtrera flödet efter egenskapsvärden och segment. Med den högra listen kan du välja i en slumpmässig lista över användare som matchar filtervillkoren. I mittområdet visas strömmen för den valda användaren per session, bestående av tidsstämpel, egenskapsvärden och varaktighet. Varaktighet är inte tillgängligt för den senaste händelsen i en given session.

>[!NOTE]
>
>Tidslinjevyn kräver att **[!UICONTROL Person ID]** standardkomponent är tillgänglig i [datavy](/help/data-views/component-reference.md#optional). Inkluderingen av person-ID i en datavy hanteras av din Customer Journey Analytics-administratör, vilket ger din organisation fullständig sekretesskontroll över vem som har åtkomst till dessa data.

Om en datavy inte har [!UICONTROL Person ID] som lagts till visas följande meddelande:

* **Administratörer**: *Egenskapen PersonID krävs för den här analysen. Lägg till person-ID i datavyn.*
* **Icke-administratörer**: *Egenskapen PersonID krävs för den här analysen. Kontakta Customer Journey Analytics-administratören för att lägga till person-ID i datavyn.*

![Tidslinje, bild](../assets/timeline.png)

## Användningsexempel

Exempel:

* **Friktionsprospektering**: Om du hittar ett brant fall i dialogrutan [Funktion](friction.md) kan du skapa ett segment av dessa användare och använda segmentet i den här vyn för att undersöka möjliga orsaker.
* **Felbeteende**: Om en användare råkar ut för ett produktfel kan du utforska vad användaren gjorde före eller efter det att felet visades.
* **Validering av datainsamling**: Dataadministratörer kan filtrera den här vyn till sitt eget person-ID för att verifiera att organisationens implementering fungerar som förväntat.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Property]**: Den egenskap som du vill visa värden för direktuppspelning för. Strömmen i mitten visar värden för den valda egenskapen. Du kan också använda filter för att begränsa strömmen till mer relevanta data. Giltiga operatorer för filtret inkluderar [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists]och [!UICONTROL Does not exist].
* **[!UICONTROL Segments]**: Det segment som du vill analysera. Det valda segmentet filtrerar data så att de bara fokuserar på de personer som matchar dina segmentkriterier. Om du vill begränsa vyn till ett specifikt person-ID kan du filtrera till detta person-ID här. Ett segment stöds för den här vyn.

## Diagraminställningar

The [!UICONTROL Timeline] I vyn finns följande diagraminställningar som du kan justera på menyn ovanför diagrammet:

* **[!UICONTROL Show as]**: Visar önskade egenskapsvärden.
   * [!UICONTROL Show all]: Visa alla egenskapsvärden i en session.
   * [!UICONTROL Highlight]: Markerar egenskapsvärden visuellt i en session som matchar frågefiltren.
   * [!UICONTROL View only]: Visa endast egenskapsvärden i en session som matchar frågefiltren.

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa trenddata efter. Den här inställningen påverkar inte vyer som inte är trendade, t.ex. tidslinjen.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
