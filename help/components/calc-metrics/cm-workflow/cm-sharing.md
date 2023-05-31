---
description: Beroende på dina behörigheter kan du dela mätvärden med hela organisationen, grupper eller enskilda användare.
title: Dela beräknade mätvärden
feature: Calculated Metrics
exl-id: b2a3e4e3-f0aa-4505-b3f5-7d9f14dc1640
source-git-commit: 82ba31eec1455bf3d0c746cf5eebc81ce6162a00
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 2%

---

# Dela beräknade mätvärden

Beroende på dina behörigheter kan du dela mätvärden med hela organisationen, grupper eller enskilda användare.

| Roll | Behörigheter |
|---|---|
| Administratör | Kan dela mätvärden med Alla, med Grupper och med Användare. Grupper konfigureras som behörighetsgrupper i Admin Console. |
| Icke-administratör | Kan endast dela mätvärden med enskilda användare. |

Så här delar du ett beräknat mått:

1. Markera kryssrutan bredvid det mätresultat du vill dela i hanteraren för beräknade värden.

   ![](assets/cm_task_bar.png)

1. Välj **[!UICONTROL Share]** ikon. ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg)

   Dialogrutan Dela beräknade mått visas.

   ![](assets/cm_share.png)

1. Välj **[!UICONTROL Share]**.

1. Välj vem du vill dela med:

   * **[!UICONTROL All]** (Endast administratörer): Delas med alla användare i organisationen.

      Överväg att dela med alla bara om det är användbart för hela företaget och alla känner sig bekväma med att använda det. I det här fallet bör du också överväga att göra det till en [godkänt mätvärde](/help/components/calc-metrics/cm-workflow/cm-approving.md).

   * **[!UICONTROL Groups]** (Endast administratörer): Markera de grupper du vill dela med.

      Överväg att dela med en grupp om mätvärdena ger ett bra affärsvärde för teamet.

   * **[!UICONTROL Individual users]**: Sök efter och välj de användare du vill dela med.

      Det här är det enda delningsalternativet som är tillgängligt för alla användare. Administratörer kan använda det här alternativet för att kontrollera och validera ett mätvärde innan det görs tillgängligt för en grupp eller för alla. Om måttet inte är användbart kan det tas bort. Administratörer bör inte godkänna den här typen av mätvärden officiellt.

1. Välj **[!UICONTROL Share]**.

   Ikonen Delad visas bredvid måttet: ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Share_18_N.svg).

1. Du kan filtrera mätvärden som delas med dig genom att gå till **[!UICONTROL Filters]** > **[!UICONTROL Other Filters]** > **[!UICONTROL Shared with Me]**.

1. (Valfritt) Om du vill filtrera listan med beräknade värden i hanteraren för beräknade mått så att endast mått som delas med dig visas, väljer du **Filter** ikon, expandera **[!UICONTROL Other filters]** väljer **[!UICONTROL Shared with me]**.
