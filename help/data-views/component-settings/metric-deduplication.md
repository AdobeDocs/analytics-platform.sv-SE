---
title: Komponentinställningar för måttborttagning av dubbletter
description: Räkna bara den första förekomsten av ett mätvärde i rapporter.
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: af88be97f303095129177b2132c6711c648cea34
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Komponentinställningar för måttborttagning av dubbletter {#metric-deduplication-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_metric_deduplication"
>title="Metrisk deduplicering"
>abstract="Konfigurera ett mätvärde så att det endast räknar värden som förekommer icke-repetitivt."

<!-- markdownlint-enable MD034 -->


Med metrisk borttagning av dubbletter kan du konfigurera ett mätvärde så att det bara räknar värden som inte upprepas.

![Måttborttagning av dubbletter](../assets/metric-deduplication.png)

| Inställning | Beskrivning |
| --- | --- |
| [!UICONTROL Metric deduplication] | En kryssruta där du kan aktivera metrisk deduplicering. Inaktiverad som standard. |
| [!UICONTROL Deduplication scope] | Här kan du bestämma hur långt bakåt den unika kontrollen ska gå.<br/>**[!UICONTROL Global account]**: Endast den första metriska förekomsten i rapportfönstret räknas.<br/>**[!UICONTROL Account]**: Endast den första metriska förekomsten i rapportfönstret räknas.<br/>**[!UICONTROL Opportunity]**: Endast den första metriska förekomsten i rapportfönstret räknas.<br/>**[!UICONTROL Buying group]**: Endast den första metriska förekomsten i rapportfönstret räknas.<br/>**[!UICONTROL Person]**: Endast den första metriska förekomsten i rapportfönstret räknas.<br>**[!UICONTROL Session]**: Endast den första mätarförekomsten av sessionen räknas.<br> |
| [!UICONTROL Deduplication ID] | I stället för att tillämpa borttagning av dubbletter på själva måttet kan du använda metrisk borttagning av dubbletter baserat på en dimension i stället. Värdefull för dimensioner som Inköp-ID för borttagning av dubbletter. |
| [!UICONTROL Value to keep] | <ul><li>**Behåll den första instansen**: Använd den här instansen i situationer där den första instansen av mätvärdet är den giltiga. Den vanligaste är förmodligen en inköpsbekräftelse. Även om någon av misstag läser in sidan igen och vi får en ny instans av en inköpsbekräftelse, är den första händelsen den giltiga.</li><li>**Behåll den sista instansen**: Använd detta i situationer där den sista instansen är mer användbar för att samla in. Exempel: Någon uppdaterar sin onlineprofil. Vi vill bara räkna en av dessa uppdateringar per session. De kan dock uppdatera sin profil flera gånger under sessionen. Om vi behåller den första instansen kan det finnas aktiviteter som inte är kopplade till evenemanget. I det här fallet är det bättre att behålla den sista förekomsten.</li></ul> |

{style="table-layout:auto"}

>[!CAUTION]
>
>Borttagning av dubbletter i ett _person_-omfång utvärderas genom fullständiga månader i UTC-tid. Ett rapportfönster med delar av månaden kanske inte visar alla första eller sista instanser, om vissa inträffade under hela månaden men utanför rapportdatumen.
