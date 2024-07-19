---
title: Tidslinjevy
description: Observera sessionshändelser på användarnivå över tid för att hitta upplevelsemönster.
feature: Adobe Product Analytics, Guided Analysis
keywords: produktanalys
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: e9721eaf993175dd46e9d8edf9176d7c00308e8c
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 0%

---

# [!UICONTROL Timeline]-vy

I vyn **[!UICONTROL Timeline]** kan du observera sessionshändelser på användarnivå över tid för att hitta upplevelsemönster och berätta bättre användarberättelser. Med den vänstra listen kan du filtrera flödet efter egenskapsvärden och segment. Med den högra listen kan du välja i en slumpmässig lista över användare som matchar filtervillkoren. I mittområdet visas strömmen för den valda användaren per session, bestående av tidsstämpel, egenskapsvärden och varaktighet. Varaktighet är inte tillgängligt för den senaste händelsen i en given session.

>[!VIDEO](https://video.tv.adobe.com/v/3427810/?learn=on)

>[!NOTE]
>
>I tidslinjevyn måste standardkomponenten **[!UICONTROL Person ID]** vara tillgänglig i [datavyn](/help/data-views/component-reference.md#optional). Inkluderingen av person-ID i en datavy hanteras av din Customer Journey Analytics-administratör, vilket ger din organisation fullständig sekretesskontroll över vem som har åtkomst till dessa data.

Om en datavy inte har komponenten [!UICONTROL Person ID] tillagd visas följande meddelande:

* **Administratörer**: *Egenskapen PersonID krävs för den här analysen. Lägg till person-ID i datavyn.*
* **Icke-administratörer**: *Egenskapen PersonID krävs för den här analysen. Samarbeta med Customer Journey Analytics-administratören för att lägga till person-ID i datavyn.*

## Användningsexempel

Exempel:

* **Friktionssökning**: Om du hittar en brant minskning i vyn [Friktion](friction.md) kan du skapa ett segment för dessa användare och tillämpa segmentet i den här vyn för att undersöka möjliga orsaker.
* **Felbeteende**: Om användarna råkar ut för ett produktfel kan du utforska vad användarna gjorde före eller efter att felet visades.
* **Datainsamlingsvalidering**: Dataadministratörer kan filtrera den här vyn till sitt eget person-ID för att verifiera att organisationens implementering fungerar som förväntat.

## Frågerår

Med frågerefältet kan du konfigurera följande komponenter:

* **[!UICONTROL Property]**: Den egenskap som du vill visa värden för direktuppspelning för. Strömmen i mitten visar värden för den valda egenskapen. Du kan också använda filter för att begränsa strömmen till mer relevanta data. Giltiga operatorer för filtret är [!UICONTROL Equals], [!UICONTROL Does not equal], [!UICONTROL Starts with], [!UICONTROL Ends with], [!UICONTROL Contains], [!UICONTROL Does not contain], [!UICONTROL Exists] och [!UICONTROL Does not exist].
* **[!UICONTROL Segments]**: Det segment som du vill analysera. Det valda segmentet filtrerar data så att de bara fokuserar på de personer som matchar dina segmentkriterier. Om du vill begränsa vyn till ett specifikt person-ID kan du filtrera till detta person-ID här. Ett segment stöds för den här vyn.

## Diagraminställningar

I vyn [!UICONTROL Timeline] finns följande diagraminställningar som kan justeras på menyn ovanför diagrammet:

* **[!UICONTROL Show as]**: Visar önskade egenskapsvärden.
   * [!UICONTROL Show all]: Visa alla egenskapsvärden i en session.
   * [!UICONTROL Highlight]: Egenskapsvärden markeras visuellt i en session som matchar frågefiltren.
   * [!UICONTROL View only]: Visa endast egenskapsvärden i en session som matchar frågefiltren.

## Datumintervall

Det önskade datumintervallet för analysen. Den här inställningen har två komponenter:

* **[!UICONTROL Interval]**: Datumgranulariteten som du vill visa trenddata efter. Den här inställningen påverkar inte vyer som inte är trendade, t.ex. tidslinjen.
* **[!UICONTROL Date]**: Start- och slutdatumet. Förinställningar för rullande datumintervall och tidigare sparade anpassade intervall är tillgängliga för att underlätta, eller så kan du använda kalenderväljaren och välja ett fast datumintervall.
