---
title: Inställningar för attribueringskomponent
description: Gör att du kan ange standardattribuering för ett mätresultat.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: b353983b13cbbfb4c846e75aecc1b78da26ddeb2
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 1%

---

# Inställningar för attribueringskomponent

Med Attribution kan du ange en standardattribueringsmodell för ett mätresultat. Du kan åsidosätta en given metrisk attribueringsmodell när du arbetar i Analysis Workspace.

![Attribuering](../assets/attribution-settings.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Set attribution] | Aktiverar en standardattribueringsmodell när det här måttet används. Den här standardinställningen kan åsidosättas i en [!UICONTROL Freeform Table] eller i ett beräknat mått. |
| [!UICONTROL Attribution model] | Här kan du ange vilket standardvärde du vill använda [attribueringsmodell](/help/analysis-workspace/attribution/models.md) att använda. Standardvärdet är [!UICONTROL Last Touch]. Alternativen är: Senaste beröring, första beröring, linjär, deltagande, samma beröring, U-Shaped, J-kurva, omvänd J, tidsfördröjning, anpassad, algoritmisk. Vissa av dessa alternativ skapar ytterligare fält som måste fyllas i, till exempel Anpassad eller Tidsåtgång. Du kan skapa flera mätvärden med samma fält - det betyder att du kan ha ett [!UICONTROL Last touch] intäktsmått och ett [!UICONTROL First Touch] intäktsmått, men baserat på samma intäktsfält i schemat. |
| [!UICONTROL Lookback window] | Gör att du kan ange ett standardfönster för uppslag till ett mätvärde. Alternativen är: [!UICONTROL Person] (Rapporteringsfönster), [!UICONTROL Session], [!UICONTROL Custom]. När [!UICONTROL Custom] har valts, ger vi dig också möjlighet att välja valfritt antal dagar/veckor/månader/osv. (upp till 90 dagar), precis som [!UICONTROL Attribution IQ]. Du kan ha flera mätvärden med samma schemafält, men var och en med ett separat uppslagsfönster. |

{style=&quot;table-layout:auto&quot;}
