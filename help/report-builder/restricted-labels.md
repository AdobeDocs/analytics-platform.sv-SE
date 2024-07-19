---
title: Vad är begränsade etiketter i Report Builder?
description: Beskriver begränsade etiketter i Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 48f5e9d6c5d3a33a5bae45e841eb8364b7172876
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Begränsade etiketter i Report Builder

Vanligtvis ärvs datastyrningsrelaterade inställningar i Customer Journey Analytics från Adobe Experience Platform. Integrationen mellan Customer Journey Analytics och Adobe Experience Platform datastyrning möjliggör märkning av känsliga uppgifter från Customer Journey Analytics och tillämpning av integritetspolicyer.

Sekretessetiketter och integritetspolicyer som har skapats för datauppsättningar som används av Experience Platform kan visas i arbetsflödet för datavyer i Customer Journey Analytics. Dessa etiketter stoppar eller varnar användare som skapar mätvärden och/eller dimensioner från känsliga fält. Mer information om datauppsättningar finns i [Datauppsättningsöversikt](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html)

När data exporteras från Customer Journey Analytics (via rapportering, export, API osv.) läggs dessutom varningar eller etiketter till för att meddela användarna att en rapport innehåller känslig information som behöver behandlas på ett visst sätt.

Tack vare den här integreringen kan ni hantera regelefterlevnaden enklare. Datahanteringen i organisationen kan ange regler som begränsar användningen. Det innebär att dina Customer Journey Analytics-användare kan använda data med större tillförsikt, eftersom de vet att de följer de regler som definieras av datahanteringen.

Mer information finns i [Customer Journey Analytics och datastyrning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## Visa begränsade data i Report Builder

Två Adobe-definierade policyer finns i Customer Journey Analytics som påverkar rapportering, nedladdning och delning:

* Använd Analytics-policy
* Tillämpa hämtningspolicy

Komponenter som påverkas av dessa principer är nedtonade. När du hovrar över en komponent som har en tillämpad princip visas en anteckning som anger följande: **Principer har tillämpats på det här fältet som förbjuder användning av dessa data.** Mer information finns i [Etiketter och profiler](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![Principanteckningen anger att data inte får användas.](assets/rb-restricted-label.png)

## Uppdatera rapporter som innehåller begränsade data

Om en användare har skapat en Report Builder-rapport med dataelement som senare är begränsade visas ett felmeddelande när rapporten uppdateras.

![Felmeddelandet som visas efter att dataelement senare har begränsats.](assets/error-restricted-data.png)
