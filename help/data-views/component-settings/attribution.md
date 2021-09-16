---
title: Inställningar för attribueringskomponent
description: Gör att du kan ange standardattribuering för ett mätresultat.
source-git-commit: af357167e65f4a577880832818221f6edbfc8b0a
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 1%

---


# Inställningar för attribueringskomponent

Med Attribution kan du ange en standardattribueringsmodell för ett mätresultat. Du kan åsidosätta en given metrisk attribueringsmodell när du arbetar i Analysis Workspace.

![Attribuering](../assets/attribution-settings.png)

| Inställning | Beskrivning/Använd skiftläge |
| --- | --- |
| [!UICONTROL Set attribution] | Aktiverar en standardattribueringsmodell när det här måttet används. Den här standardinställningen kan åsidosättas i ett [!UICONTROL Freeform Table]-värde eller i ett beräknat mått. |
| [!UICONTROL Attribution model] | Här kan du ange vilken [standardattribueringsmodell](/help/analysis-workspace/attribution/models.md) som ska användas. Standardvärdet är [!UICONTROL Last Touch]. Alternativen är: Senaste beröring, första beröring, linjär, deltagande, samma beröring, U-Shaped, J-kurva, omvänd J, tidsfördröjning, anpassad, algoritmisk. Vissa av dessa alternativ skapar ytterligare fält som måste fyllas i, till exempel Anpassad eller Tidsåtgång. Du kan skapa flera mätvärden med samma fält - det innebär att du kan ha ett [!UICONTROL Last touch]-intäktsmått och ett [!UICONTROL First Touch]-intäktsmått, men baserat på samma intäktsfält i schemat. |
| [!UICONTROL Lookback window] | Gör att du kan ange ett standardfönster för uppslag till ett mätvärde. Alternativen är: [!UICONTROL Person] (rapporteringsfönster), [!UICONTROL Session], [!UICONTROL Custom]. När [!UICONTROL Custom] är markerat ger vi dig också möjlighet att välja valfritt antal dagar/veckor/månader/osv. (upp till 90 dagar), precis som [!UICONTROL Attribution IQ]. Du kan ha flera mätvärden med samma schemafält, men var och en med ett separat uppslagsfönster. |
