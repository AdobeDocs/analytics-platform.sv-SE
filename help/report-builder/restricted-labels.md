---
title: Vad är begränsade etiketter i Report Builder?
description: Beskriver begränsade etiketter i Report Builder
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: 72e6c568ccad4c5f74612a1f19758a7b41746836
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%

---

# Begränsade etiketter i Report Builder

Vanligtvis ärvs datastyrningsrelaterade inställningar i Customer Journey Analytics från Adobe Experience Platform. Integrationen mellan CJA och Adobe Experience Platform Data Governance möjliggör märkning av känsliga CJA-data och tillämpning av sekretesspolicyer.

Sekretessetiketter och integritetspolicyer som har skapats för datauppsättningar som används av Experience Platform kan visas i arbetsflödet för CJA-datavyer. Dessa etiketter stoppar eller varnar användare som skapar mätvärden och/eller dimensioner från känsliga fält. Mer information om datauppsättningar finns i [Översikt över datauppsättningar](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html)

När data exporteras från CJA (via rapportering, export, API osv.) läggs dessutom varningar eller etiketter till för att meddela användarna att en rapport innehåller känslig information som behöver behandlas på ett visst sätt.

Tack vare den här integreringen kan ni hantera regelefterlevnaden enklare. Datahanteringen i organisationen kan ange regler som begränsar användningen. Detta innebär att era CJA-användare kan använda data med större tillförsikt, i vetskap om att de följer policyer som definieras av dataförvaltare.

Mer information finns i [Customer Journey Analytics och datastyrning](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## Visa begränsade data i Report Builder

Det finns två Adobe-definierade policyer i CJA som påverkar rapportering, hämtning och delning:

* Använd Analytics-policy
* Tillämpa hämtningspolicy

Komponenter som påverkas av dessa principer är nedtonade. När du hovrar över en komponent som har en profil visas en anteckning som anger följande: **Principer har tillämpats på det här fältet som förbjuder användning av dessa data.** Mer information finns i [Etiketter och profiler](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![](assets/rb-restricted-label.png)

## Uppdatera rapporter som innehåller begränsade data

Om en användare har skapat en Report Builder-rapport med dataelement som senare är begränsade visas ett felmeddelande när rapporten uppdateras.

![](assets/error-restricted-data.png)